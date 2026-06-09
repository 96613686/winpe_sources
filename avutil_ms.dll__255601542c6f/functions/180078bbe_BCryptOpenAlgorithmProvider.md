# BCryptOpenAlgorithmProvider

- ea: `0x180078bbe`
- end: `0x180078bc4`
- name: `BCryptOpenAlgorithmProvider`
- size: `6`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, LPCWSTR pszImplementation, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18004d360`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180078bbe`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall BCryptOpenAlgorithmProvider(
        BCRYPT_ALG_HANDLE *phAlgorithm,
        LPCWSTR pszAlgId,
        LPCWSTR pszImplementation,
        ULONG dwFlags)
{
  return __imp_BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, pszImplementation, dwFlags);
}

```

## disassembly

```asm
0x180078bbe  jmp     cs:__imp_BCryptOpenAlgorithmProvider
```
