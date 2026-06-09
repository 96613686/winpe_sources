# DeleteCriticalSection_0

- ea: `0x180032cfd`
- end: `0x180032d03`
- name: `DeleteCriticalSection_0`
- size: `6`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180032cfd`

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
0x180032cfd  jmp     cs:__imp_DeleteCriticalSection
```
