# LsapCrEncryptDataWithAES

- ea: `0x180070b8c`
- end: `0x180070e11`
- name: `LsapCrEncryptDataWithAES`
- size: `645`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, __int64, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800714f0`

## callees

- `0x180070b8c`
- `0x1800720b0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180070c01`
- `msvcrt!memcpy_s` at `0x180070c01`
- `KERNELBASE!LocalAlloc` at `0x180070d2c`
- `KERNELBASE!LocalAlloc` at `0x180070d2c`
- `KERNEL32!LocalFree` at `0x180070daf`
- `KERNEL32!LocalFree` at `0x180070daf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180070ddb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180070ddb`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180070cc6`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180070cc6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180070c1e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180070c1e`
- `bcrypt!BCryptSetProperty` at `0x180070c8e`
- `bcrypt!BCryptSetProperty` at `0x180070c8e`
- `bcrypt!BCryptGetProperty` at `0x180070c54`
- `bcrypt!BCryptGetProperty` at `0x180070c54`
- `bcrypt!BCryptDestroyKey` at `0x180070dc4`
- `bcrypt!BCryptDestroyKey` at `0x180070dc4`
- `bcrypt!BCryptEncrypt` at `0x180070d10`
- `bcrypt!BCryptEncrypt` at `0x180070d82`
- `bcrypt!BCryptEncrypt` at `0x180070d10`
- `bcrypt!BCryptEncrypt` at `0x180070d82`

## pseudocode

```c

```
