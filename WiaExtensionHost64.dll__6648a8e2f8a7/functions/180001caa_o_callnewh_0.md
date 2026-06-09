# _o__callnewh_0

- ea: `0x180001caa`
- end: `0x180001cb0`
- name: `_o__callnewh_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__callnewh` at `0x180001caa`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall o__callnewh_0(__int64 a1)
{
  return _o__callnewh(a1);
}

```

## disassembly

```asm
0x180001caa  jmp     cs:__imp__o__callnewh
```
