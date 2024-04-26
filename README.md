# PRODIGY_TrackCode_Task1
#prodigy task one alloted and solved with python
def encrypt(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():
            shifted_char = chr((ord(char) - 65 + shift) % 26 + 65) if char.isupper() else chr((ord(char) - 97 + shift) % 26 + 97)
            encrypted_text += shifted_char
        else:
            encrypted_text += char
    return encrypted_text

def decrypt(text, shift):
    decrypted_text = ""
    for char in text:
        if char.isalpha():
            shifted_char = chr((ord(char) - 65 - shift) % 26 + 65) if char.isupper() else chr((ord(char) - 97 - shift) % 26 + 97)
            decrypted_text += shifted_char
        else:
            decrypted_text += char
    return decrypted_text

def main():
    choice = input("Would you like to encrypt or decrypt? (encrypt/decrypt): ").lower()
    if choice == "encrypt":
        message = input("Enter the message to encrypt: ")
        shift = int(input("Enter the shift value (a number between 1 and 25): "))
        encrypted_message = encrypt(message, shift)
        print("Encrypted message:", encrypted_message)
    elif choice == "decrypt":
        message = input("Enter the message to decrypt: ")
        shift = int(input("Enter the shift value (a number between 1 and 25): "))
        decrypted_message = decrypt(message, shift)
        print("Decrypted message:", decrypted_message)
    else:
        print("Invalid choice. Please enter 'encrypt' or 'decrypt'.")

if __name__ == "__main__":
    main()
