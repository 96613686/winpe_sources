# SspirGetUserName2

- ea: `0x180002b90`
- end: `0x180002bdc`
- name: `SspirGetUserName2`
- size: `76`
- prototype: `__int64 __fastcall(__int64, __int64, __int128 *, unsigned int, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001400`
- `0x1800026a0`

## pseudocode

```c
__int64 __fastcall SspirGetUserName2(__int64 a1, __int64 a2, __int128 *a3, unsigned int a4, __int64 a5, _DWORD *a6)
{
  SspiSrvCallBegin(a2);
  return SspirGetUserName(a1, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x180002b90  mov     [rsp+arg_0], rbx
0x180002b95  mov     [rsp+arg_8], rsi
0x180002b9a  push    rdi
0x180002b9b  sub     rsp, 30h
0x180002b9f  mov     rbx, rcx
0x180002ba2  mov     edi, r9d
0x180002ba5  mov     rcx, rdx
0x180002ba8  mov     rsi, r8
0x180002bab  call    SspiSrvCallBegin
0x180002bb0  mov     rax, [rsp+38h+arg_28]
0x180002bb5  mov     r8d, edi
0x180002bb8  mov     r9, [rsp+38h+arg_20]
0x180002bbd  mov     rdx, rsi
0x180002bc0  mov     rcx, rbx
0x180002bc3  mov     [rsp+38h+arg_20], rax
0x180002bc8  mov     rbx, [rsp+38h+arg_0]
0x180002bcd  mov     rsi, [rsp+38h+arg_8]
0x180002bd2  add     rsp, 30h
0x180002bd6  pop     rdi
0x180002bd7  jmp     SspirGetUserName
```
