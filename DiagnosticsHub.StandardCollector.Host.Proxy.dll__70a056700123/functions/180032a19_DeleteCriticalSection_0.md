# DeleteCriticalSection_0

- ea: `0x180032a19`
- end: `0x180032a1f`
- name: `DeleteCriticalSection_0`
- size: `6`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180032a19`

## pseudocode

```c
// attributes: thunk
void __stdcall DeleteCriticalSection_0(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180032a19  jmp     cs:__imp_DeleteCriticalSection
```
