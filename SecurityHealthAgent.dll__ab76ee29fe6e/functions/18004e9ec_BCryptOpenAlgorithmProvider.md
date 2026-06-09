# BCryptOpenAlgorithmProvider

- ea: `0x18004e9ec`
- end: `0x18004e9f2`
- name: `BCryptOpenAlgorithmProvider`
- size: `6`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, LPCWSTR pszImplementation, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180039a50`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004e9ec`

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
0x18004e9ec  jmp     cs:__imp_BCryptOpenAlgorithmProvider
```
