# DeleteCriticalSection

- ea: `0x140005b60`
- end: `0x140005b67`
- name: `DeleteCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000263c`
- `0x140007bf0`
- `0x1400080b0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140005b60`

## pseudocode

```c
// attributes: thunk
void __stdcall DeleteCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  __imp_DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x140005b60  jmp     cs:__imp_DeleteCriticalSection
```
