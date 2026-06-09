# SspirDeleteSecurityContext2

- ea: `0x180002a30`
- end: `0x180002a72`
- name: `SspirDeleteSecurityContext2`
- size: `66`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int128 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001470`
- `0x1800026a0`

## pseudocode

```c
__int64 __fastcall SspirDeleteSecurityContext2(__int64 a1, __int64 a2, _QWORD *a3, __int128 *a4)
{
  SspiSrvCallBegin(a2);
  return SspirDeleteSecurityContext(a1, a3, a4);
}

```

## disassembly

```asm
0x180002a30  mov     [rsp+arg_0], rbx
0x180002a35  mov     [rsp+arg_8], rsi
0x180002a3a  push    rdi
0x180002a3b  sub     rsp, 20h
0x180002a3f  mov     rbx, rcx
0x180002a42  mov     rdi, r9
0x180002a45  mov     rcx, rdx
0x180002a48  mov     rsi, r8
0x180002a4b  call    SspiSrvCallBegin
0x180002a50  mov     r9, [rsp+28h+arg_20]
0x180002a55  mov     r8, rdi
0x180002a58  mov     rdx, rsi
0x180002a5b  mov     rcx, rbx
0x180002a5e  mov     rbx, [rsp+28h+arg_0]
0x180002a63  mov     rsi, [rsp+28h+arg_8]
0x180002a68  add     rsp, 20h
0x180002a6c  pop     rdi
0x180002a6d  jmp     SspirDeleteSecurityContext
```
