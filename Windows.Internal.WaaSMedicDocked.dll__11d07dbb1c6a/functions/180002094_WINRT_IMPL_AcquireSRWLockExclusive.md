# WINRT_IMPL_AcquireSRWLockExclusive

- ea: `0x180002094`
- end: `0x18000209a`
- name: `WINRT_IMPL_AcquireSRWLockExclusive`
- size: `6`
- prototype: `void __stdcall(PSRWLOCK SRWLock)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800067f0`
- `0x180006e30`
- `0x180007014`
- `0x1800071d0`
- `0x18000917c`
- `0x1800093a0`
- `0x1800097e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002094`

## pseudocode

```c
// attributes: thunk
void __stdcall WINRT_IMPL_AcquireSRWLockExclusive(PSRWLOCK SRWLock)
{
  AcquireSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x180002094  jmp     cs:__imp_AcquireSRWLockExclusive
```
