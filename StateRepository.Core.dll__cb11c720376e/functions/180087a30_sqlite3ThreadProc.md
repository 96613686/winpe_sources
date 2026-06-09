# sqlite3ThreadProc

- ea: `0x180087a30`
- end: `0x180087a5a`
- name: `sqlite3ThreadProc`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18009a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x180087a4c`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x180087a4c`

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
0x180087a30  push    rbx
0x180087a32  sub     rsp, 20h
0x180087a36  mov     rbx, rcx
0x180087a39  mov     rcx, [rcx+18h]
0x180087a3d  mov     rax, [rbx+10h]
0x180087a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087a46  xor     ecx, ecx
0x180087a48  mov     [rbx+20h], rax
0x180087a4c  call    cs:__imp__o__endthreadex
0x180087a52  xor     eax, eax
0x180087a54  add     rsp, 20h
0x180087a58  pop     rbx
0x180087a59  retn
```
