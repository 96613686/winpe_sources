# sqlite3MemSize

- ea: `0x140063270`
- end: `0x140063277`
- name: `sqlite3MemSize`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x140063270`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall sqlite3MemSize(__int64 a1)
{
  return _o__msize(a1);
}

```

## disassembly

```asm
0x140063270  jmp     cs:__imp__o__msize
```
