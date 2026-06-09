# EnterCriticalSection

- ea: `0x18000726c`
- end: `0x180007273`
- name: `EnterCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c70`
- `0x180007314`
- `0x180008680`
- `0x180035fd0`
- `0x1800384ec`
- `0x18004c4a4`
- `0x18004ca50`
- `0x18004eefc`
- `0x180056050`
- `0x180056810`
- `0x1800571f0`
- `0x18005dfa4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000726c`

## pseudocode

```c
// attributes: thunk
void __stdcall EnterCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  __imp_EnterCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000726c  jmp     cs:__imp_EnterCriticalSection
```
