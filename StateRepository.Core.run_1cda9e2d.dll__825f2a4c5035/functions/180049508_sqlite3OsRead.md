# sqlite3OsRead

- ea: `0x180049508`
- end: `0x18004951d`
- name: `sqlite3OsRead`
- size: `21`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180007154`
- `0x1800490b8`
- `0x1800560d4`
- `0x18007abd0`
- `0x18007b124`
- `0x18007cde4`
- `0x18007ce18`
- `0x18007cfd0`
- `0x180091fbc`
- `0x180093b5c`
- `0x180094020`
- `0x180095158`
- `0x180095558`

## callees

- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3OsRead(__int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
}

```

## disassembly

```asm
0x180049508  sub     rsp, 38h
0x18004950c  mov     rax, [rcx]
0x18004950f  mov     rax, [rax+10h]
0x180049513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049518  add     rsp, 38h
0x18004951c  retn
```
