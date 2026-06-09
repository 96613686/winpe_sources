# LsapCrDecryptDataWithAES

- ea: `0x1800708d4`
- end: `0x180070b85`
- name: `LsapCrDecryptDataWithAES`
- size: `689`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, PUCHAR pbSecret, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180071118`

## callees

- `0x1800708d4`
- `0x1800720b0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180070943`
- `msvcrt!memcpy_s` at `0x180070943`
- `KERNELBASE!LocalAlloc` at `0x180070a84`
- `KERNELBASE!LocalAlloc` at `0x180070a84`
- `KERNEL32!LocalFree` at `0x180070b1a`
- `KERNEL32!LocalFree` at `0x180070b1a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180070b46`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180070b46`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180070a14`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180070a14`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180070960`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180070960`
- `bcrypt!BCryptSetProperty` at `0x1800709dc`
- `bcrypt!BCryptSetProperty` at `0x1800709dc`
- `bcrypt!BCryptGetProperty` at `0x18007099c`
- `bcrypt!BCryptGetProperty` at `0x18007099c`
- `bcrypt!BCryptDestroyKey` at `0x180070b2f`
- `bcrypt!BCryptDestroyKey` at `0x180070b2f`
- `bcrypt!BCryptDecrypt` at `0x180070a66`
- `bcrypt!BCryptDecrypt` at `0x180070add`
- `bcrypt!BCryptDecrypt` at `0x180070a66`
- `bcrypt!BCryptDecrypt` at `0x180070add`

## pseudocode

```c

```
