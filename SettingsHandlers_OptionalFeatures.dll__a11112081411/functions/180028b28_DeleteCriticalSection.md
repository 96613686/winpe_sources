# DeleteCriticalSection

- ea: `0x180028b28`
- end: `0x180028b2f`
- name: `DeleteCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180047373`
- `0x180047389`
- `0x180047411`
- `0x180047dfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028b28`

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
0x180028b28  jmp     cs:__imp_DeleteCriticalSection
```
