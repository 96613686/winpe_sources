# LsapCrEncryptDataWithAES

- ea: `0x180063cf4`
- end: `0x180063f32`
- name: `LsapCrEncryptDataWithAES`
- size: `574`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, __int64, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180064594`

## callees

- `0x180063cf4`
- `0x180065090`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180063d69`
- `msvcrt!memcpy_s` at `0x180063d69`
- `KERNELBASE!LocalAlloc` at `0x180063e6c`
- `KERNELBASE!LocalAlloc` at `0x180063e6c`
- `KERNEL32!LocalFree` at `0x180063ee3`
- `KERNEL32!LocalFree` at `0x180063ee3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180063f03`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180063f03`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180063e16`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180063e16`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063d80`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063d80`
- `bcrypt!BCryptSetProperty` at `0x180063de4`
- `bcrypt!BCryptSetProperty` at `0x180063de4`
- `bcrypt!BCryptGetProperty` at `0x180063db0`
- `bcrypt!BCryptGetProperty` at `0x180063db0`
- `bcrypt!BCryptDestroyKey` at `0x180063ef2`
- `bcrypt!BCryptDestroyKey` at `0x180063ef2`
- `bcrypt!BCryptEncrypt` at `0x180063e5a`
- `bcrypt!BCryptEncrypt` at `0x180063ebc`
- `bcrypt!BCryptEncrypt` at `0x180063e5a`
- `bcrypt!BCryptEncrypt` at `0x180063ebc`

## pseudocode

```c

```
