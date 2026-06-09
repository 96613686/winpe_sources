# DeleteCriticalSection

- ea: `0x180087048`
- end: `0x18008704f`
- name: `DeleteCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1801d7690`
- `0x1801d784c`
- `0x1801d785c`
- `0x1801d78f0`
- `0x1801d7b57`
- `0x1801d7b78`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180087048`

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
0x180087048  jmp     cs:__imp_DeleteCriticalSection
```
