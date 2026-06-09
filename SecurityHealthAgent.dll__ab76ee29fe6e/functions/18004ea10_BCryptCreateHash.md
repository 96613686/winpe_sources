# BCryptCreateHash

- ea: `0x18004ea10`
- end: `0x18004ea16`
- name: `BCryptCreateHash`
- size: `6`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_HASH_HANDLE *phHash, PUCHAR pbHashObject, ULONG cbHashObject, PUCHAR pbSecret, ULONG cbSecret, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180039a50`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18004ea10`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall BCryptCreateHash(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_HASH_HANDLE *phHash,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        PUCHAR pbSecret,
        ULONG cbSecret,
        ULONG dwFlags)
{
  return __imp_BCryptCreateHash(hAlgorithm, phHash, pbHashObject, cbHashObject, pbSecret, cbSecret, dwFlags);
}

```

## disassembly

```asm
0x18004ea10  jmp     cs:__imp_BCryptCreateHash
```
