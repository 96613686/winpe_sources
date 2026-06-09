# LsapEncryptDataWithAES

- ea: `0x1800428a4`
- end: `0x180042ace`
- name: `LsapEncryptDataWithAES`
- size: `554`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, __int64, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180042604`

## callees

- `0x1800428a4`
- `0x180065090`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180042a10`
- `KERNELBASE!LocalAlloc` at `0x180042a10`
- `KERNEL32!LocalFree` at `0x180042a7f`
- `KERNEL32!LocalFree` at `0x180042a7f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180042a9f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180042a9f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800429ba`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800429ba`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180042924`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180042924`
- `bcrypt!BCryptSetProperty` at `0x180042988`
- `bcrypt!BCryptSetProperty` at `0x180042988`
- `bcrypt!BCryptGetProperty` at `0x180042954`
- `bcrypt!BCryptGetProperty` at `0x180042954`
- `bcrypt!BCryptDestroyKey` at `0x180042a8e`
- `bcrypt!BCryptDestroyKey` at `0x180042a8e`
- `bcrypt!BCryptEncrypt` at `0x1800429fe`
- `bcrypt!BCryptEncrypt` at `0x180042a59`
- `bcrypt!BCryptEncrypt` at `0x1800429fe`
- `bcrypt!BCryptEncrypt` at `0x180042a59`

## pseudocode

```c

```
