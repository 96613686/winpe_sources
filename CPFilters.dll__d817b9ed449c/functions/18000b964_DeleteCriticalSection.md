# DeleteCriticalSection

- ea: `0x18000b964`
- end: `0x18000b96b`
- name: `DeleteCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18006cec7`
- `0x18006cf89`
- `0x18006d3c1`
- `0x18006d7f3`
- `0x18006e429`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b964`

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
0x18000b964  jmp     cs:__imp_DeleteCriticalSection
```
