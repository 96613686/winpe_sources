# ReleaseSRWLockExclusive_0

- ea: `0x180002088`
- end: `0x18000208e`
- name: `ReleaseSRWLockExclusive_0`
- size: `6`
- prototype: `void __stdcall(PSRWLOCK SRWLock)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180006a50`
- `0x180006e30`
- `0x180007014`
- `0x1800071d0`
- `0x18000917c`
- `0x1800093a0`
- `0x1800097e0`
- `0x18000a034`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002088`

## pseudocode

```c
// attributes: thunk
void __stdcall ReleaseSRWLockExclusive_0(PSRWLOCK SRWLock)
{
  ReleaseSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x180002088  jmp     cs:__imp_ReleaseSRWLockExclusive
```
