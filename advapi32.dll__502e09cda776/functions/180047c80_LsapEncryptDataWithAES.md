# LsapEncryptDataWithAES

- ea: `0x180047c80`
- end: `0x180047ee7`
- name: `LsapEncryptDataWithAES`
- size: `615`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, __int64, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800479c0`

## callees

- `0x180047c80`
- `0x1800720b0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180047e0a`
- `KERNELBASE!LocalAlloc` at `0x180047e0a`
- `KERNEL32!LocalFree` at `0x180047e85`
- `KERNEL32!LocalFree` at `0x180047e85`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180047eb1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180047eb1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180047da8`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180047da8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180047d00`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180047d00`
- `bcrypt!BCryptSetProperty` at `0x180047d70`
- `bcrypt!BCryptSetProperty` at `0x180047d70`
- `bcrypt!BCryptGetProperty` at `0x180047d36`
- `bcrypt!BCryptGetProperty` at `0x180047d36`
- `bcrypt!BCryptDestroyKey` at `0x180047e9a`
- `bcrypt!BCryptDestroyKey` at `0x180047e9a`
- `bcrypt!BCryptEncrypt` at `0x180047df2`
- `bcrypt!BCryptEncrypt` at `0x180047e59`
- `bcrypt!BCryptEncrypt` at `0x180047df2`
- `bcrypt!BCryptEncrypt` at `0x180047e59`

## pseudocode

```c

```
