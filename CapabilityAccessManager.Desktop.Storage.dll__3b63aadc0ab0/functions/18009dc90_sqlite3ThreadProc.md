# sqlite3ThreadProc

- ea: `0x18009dc90`
- end: `0x18009dcba`
- name: `sqlite3ThreadProc`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18010d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x18009dcac`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x18009dcac`

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
0x18009dc90  push    rbx
0x18009dc92  sub     rsp, 20h
0x18009dc96  mov     rbx, rcx
0x18009dc99  mov     rcx, [rcx+18h]
0x18009dc9d  mov     rax, [rbx+10h]
0x18009dca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dca6  xor     ecx, ecx
0x18009dca8  mov     [rbx+20h], rax
0x18009dcac  call    cs:__imp__o__endthreadex
0x18009dcb2  xor     eax, eax
0x18009dcb4  add     rsp, 20h
0x18009dcb8  pop     rbx
0x18009dcb9  retn
```
