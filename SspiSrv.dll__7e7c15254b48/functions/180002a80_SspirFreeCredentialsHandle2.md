# SspirFreeCredentialsHandle2

- ea: `0x180002a80`
- end: `0x180002ac2`
- name: `SspirFreeCredentialsHandle2`
- size: `66`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int128 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001aa0`
- `0x1800026a0`

## pseudocode

```c
__int64 __fastcall SspirFreeCredentialsHandle2(__int64 a1, __int64 a2, _QWORD *a3, __int128 *a4)
{
  SspiSrvCallBegin(a2);
  return SspirFreeCredentialsHandle(a1, a3, a4);
}

```

## disassembly

```asm
0x180002a80  mov     [rsp+arg_0], rbx
0x180002a85  mov     [rsp+arg_8], rsi
0x180002a8a  push    rdi
0x180002a8b  sub     rsp, 20h
0x180002a8f  mov     rbx, rcx
0x180002a92  mov     rdi, r9
0x180002a95  mov     rcx, rdx
0x180002a98  mov     rsi, r8
0x180002a9b  call    SspiSrvCallBegin
0x180002aa0  mov     r9, [rsp+28h+arg_20]
0x180002aa5  mov     r8, rdi
0x180002aa8  mov     rdx, rsi
0x180002aab  mov     rcx, rbx
0x180002aae  mov     rbx, [rsp+28h+arg_0]
0x180002ab3  mov     rsi, [rsp+28h+arg_8]
0x180002ab8  add     rsp, 20h
0x180002abc  pop     rdi
0x180002abd  jmp     SspirFreeCredentialsHandle
```
