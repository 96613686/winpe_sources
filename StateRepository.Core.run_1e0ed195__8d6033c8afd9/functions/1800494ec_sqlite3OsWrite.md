# sqlite3OsWrite

- ea: `0x1800494ec`
- end: `0x180049501`
- name: `sqlite3OsWrite`
- size: `21`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180024f90`
- `0x1800490b8`
- `0x180049d1c`
- `0x18004a1f0`
- `0x18004a344`
- `0x180061780`
- `0x18007aa54`
- `0x18007b124`
- `0x18007b3c0`
- `0x18007b4a8`
- `0x18008c010`
- `0x180091fbc`
- `0x180094154`
- `0x18009423c`
- `0x18009889c`
- `0x1800989cc`
- `0x1800995f8`

## callees

- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3OsWrite(__int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
}

```

## disassembly

```asm
0x1800494ec  sub     rsp, 38h
0x1800494f0  mov     rax, [rcx]
0x1800494f3  mov     rax, [rax+18h]
0x1800494f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494fc  add     rsp, 38h
0x180049500  retn
```
