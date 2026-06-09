# sqlite3ThreadProc

- ea: `0x18008f440`
- end: `0x18008f46a`
- name: `sqlite3ThreadProc`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x18008f45c`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x18008f45c`

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
0x18008f440  push    rbx
0x18008f442  sub     rsp, 20h
0x18008f446  mov     rbx, rcx
0x18008f449  mov     rcx, [rcx+18h]
0x18008f44d  mov     rax, [rbx+10h]
0x18008f451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f456  xor     ecx, ecx
0x18008f458  mov     [rbx+20h], rax
0x18008f45c  call    cs:__imp__o__endthreadex
0x18008f462  xor     eax, eax
0x18008f464  add     rsp, 20h
0x18008f468  pop     rbx
0x18008f469  retn
```
