# HSTRING_UserFree64_0

- ea: `0x180001770`
- end: `0x180001776`
- name: `HSTRING_UserFree64_0`
- size: `6`
- prototype: `void __stdcall(unsigned int *, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!HSTRING_UserFree64` at `0x180001770`

## pseudocode

```c
// attributes: thunk
void __stdcall HSTRING_UserFree64_0(unsigned int *a1, HSTRING *a2)
{
  HSTRING_UserFree64(a1, a2);
}

```

## disassembly

```asm
0x180001770  jmp     cs:__imp_HSTRING_UserFree64
```
