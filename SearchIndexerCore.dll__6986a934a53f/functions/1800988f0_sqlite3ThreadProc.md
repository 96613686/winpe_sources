# sqlite3ThreadProc

- ea: `0x1800988f0`
- end: `0x18009891a`
- name: `sqlite3ThreadProc`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800b0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x18009890c`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x18009890c`

## pseudocode

```c
__int64 __fastcall sqlite3ThreadProc(__int64 a1)
{
  *(_QWORD *)(a1 + 32) = (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 24));
  _o__endthreadex(0);
  return 0;
}

```

## disassembly

```asm
0x1800988f0  push    rbx
0x1800988f2  sub     rsp, 20h
0x1800988f6  mov     rbx, rcx
0x1800988f9  mov     rcx, [rcx+18h]
0x1800988fd  mov     rax, [rbx+10h]
0x180098901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098906  xor     ecx, ecx
0x180098908  mov     [rbx+20h], rax
0x18009890c  call    cs:__imp__o__endthreadex
0x180098912  xor     eax, eax
0x180098914  add     rsp, 20h
0x180098918  pop     rbx
0x180098919  retn
```
