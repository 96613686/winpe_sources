# LeaveCriticalSection

- ea: `0x180007274`
- end: `0x18000727b`
- name: `LeaveCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c70`
- `0x180007398`
- `0x1800086fc`
- `0x180036f04`
- `0x1800384ec`
- `0x18003d4f8`
- `0x18004c4a4`
- `0x18004ca50`
- `0x18004eefc`
- `0x180056050`
- `0x180056810`
- `0x1800571f0`
- `0x18005dfa4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180007274`

## pseudocode

```c
// attributes: thunk
void __stdcall LeaveCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  __imp_LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180007274  jmp     cs:__imp_LeaveCriticalSection
```
