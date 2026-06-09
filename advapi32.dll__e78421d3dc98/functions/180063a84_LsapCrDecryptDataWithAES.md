# LsapCrDecryptDataWithAES

- ea: `0x180063a84`
- end: `0x180063ceb`
- name: `LsapCrDecryptDataWithAES`
- size: `615`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, PUCHAR pbSecret, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800641ec`

## callees

- `0x180063a84`
- `0x180065090`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180063af3`
- `msvcrt!memcpy_s` at `0x180063af3`
- `KERNELBASE!LocalAlloc` at `0x180063c10`
- `KERNELBASE!LocalAlloc` at `0x180063c10`
- `KERNEL32!LocalFree` at `0x180063c93`
- `KERNEL32!LocalFree` at `0x180063c93`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180063cb3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180063cb3`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180063bac`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180063bac`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063b0a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063b0a`
- `bcrypt!BCryptSetProperty` at `0x180063b7a`
- `bcrypt!BCryptSetProperty` at `0x180063b7a`
- `bcrypt!BCryptGetProperty` at `0x180063b40`
- `bcrypt!BCryptGetProperty` at `0x180063b40`
- `bcrypt!BCryptDestroyKey` at `0x180063ca2`
- `bcrypt!BCryptDestroyKey` at `0x180063ca2`
- `bcrypt!BCryptDecrypt` at `0x180063bf8`
- `bcrypt!BCryptDecrypt` at `0x180063c60`
- `bcrypt!BCryptDecrypt` at `0x180063bf8`
- `bcrypt!BCryptDecrypt` at `0x180063c60`

## pseudocode

```c

```
