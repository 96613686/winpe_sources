# DeleteCriticalSection

- ea: `0x180007028`
- end: `0x18000702f`
- name: `DeleteCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c20`
- `0x1800072ec`
- `0x180007650`
- `0x1800086c0`
- `0x18006c150`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007028`

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
0x180007028  jmp     cs:__imp_DeleteCriticalSection
```
