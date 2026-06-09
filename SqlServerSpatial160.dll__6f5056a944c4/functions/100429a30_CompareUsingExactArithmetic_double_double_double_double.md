# CompareUsingExactArithmetic(double,double,double,double)

- ea: `0x100429a30`
- end: `0x100429b6a`
- name: `?CompareUsingExactArithmetic@@YA?AW4COMPARISON@RobustIntersections@@NNNN@Z`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100429b70`
- `0x100429e10`

## callees

- `0x100429a30`
- `0x10042a400`
- `0x10042a4e0`
- `0x10042a7a0`
- `0x100468a30`

## pseudocode

```c
__int64 CompareUsingExactArithmetic()
{
  unsigned int v1; // [rsp+20h] [rbp-B8h] BYREF
  int v2; // [rsp+24h] [rbp-B4h]
  __int64 v3; // [rsp+28h] [rbp-B0h]
  unsigned int v4; // [rsp+48h] [rbp-90h] BYREF
  int v5; // [rsp+4Ch] [rbp-8Ch]
  __int64 v6; // [rsp+50h] [rbp-88h]
  _BYTE v7[40]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v8[40]; // [rsp+98h] [rbp-40h] BYREF

  RobustIntersections::CZ<128>::CZ<128>(&v1);
  RobustIntersections::CZ<128>::CZ<128>(&v4);
  RobustIntersections::CZ<128>::CZ<128>(v8);
  RobustIntersections::CZ<128>::CZ<128>(v7);
  RobustIntersections::CZ<128>::Multiply(&v1, v7);
  RobustIntersections::CZ<128>::Multiply(&v4, v8);
  if ( v2 > v5 )
    return 1;
  if ( v2 < v5 )
    return 0xFFFFFFFFLL;
  if ( v2 > 0 )
    return RobustIntersections::EaCompare(v3, v1, v6, v4);
  if ( v2 >= 0 )
    return 0;
  return RobustIntersections::EaCompare(v6, v4, v3, v1);
}

```

## disassembly

```asm
0x100429a30  sub     rsp, 0D8h
0x100429a37  mov     rax, cs:__security_cookie
0x100429a3e  xor     rax, rsp
0x100429a41  mov     [rsp+0D8h+var_18], rax
0x100429a49  movaps  xmm4, xmm1
0x100429a4c  lea     rcx, [rsp+0D8h+var_B8]
0x100429a51  movaps  xmm1, xmm0
0x100429a54  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100429a59  movaps  xmm1, xmm4
0x100429a5c  lea     rcx, [rsp+0D8h+var_90]
0x100429a61  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100429a66  movaps  xmm1, xmm2
0x100429a69  lea     rcx, [rsp+0D8h+var_40]
0x100429a71  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100429a76  movaps  xmm1, xmm3
0x100429a79  lea     rcx, [rsp+0D8h+var_68]
0x100429a7e  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100429a83  lea     rdx, [rsp+0D8h+var_68]
0x100429a88  lea     rcx, [rsp+0D8h+var_B8]
0x100429a8d  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100429a92  lea     rdx, [rsp+0D8h+var_40]
0x100429a9a  lea     rcx, [rsp+0D8h+var_90]
0x100429a9f  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100429aa4  mov     eax, [rsp+0D8h+var_B4]
0x100429aa8  cmp     eax, [rsp+0D8h+var_8C]
0x100429aac  jle     short loc_100429ACB
0x100429aae  mov     eax, 1
0x100429ab3  mov     rcx, [rsp+0D8h+var_18]
0x100429abb  xor     rcx, rsp; StackCookie
0x100429abe  call    __security_check_cookie
0x100429ac3  add     rsp, 0D8h
0x100429aca  retn
0x100429acb  jge     short loc_100429AEA
0x100429acd  mov     eax, 0FFFFFFFFh
0x100429ad2  mov     rcx, [rsp+0D8h+var_18]
0x100429ada  xor     rcx, rsp; StackCookie
0x100429add  call    __security_check_cookie
0x100429ae2  add     rsp, 0D8h
0x100429ae9  retn
0x100429aea  test    eax, eax
0x100429aec  jle     short loc_100429B1E
0x100429aee  mov     r9d, [rsp+0D8h+var_90]
0x100429af3  mov     r8, [rsp+0D8h+var_88]
0x100429af8  mov     edx, [rsp+0D8h+var_B8]
0x100429afc  mov     rcx, [rsp+0D8h+var_B0]
0x100429b01  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100429b06  mov     rcx, [rsp+0D8h+var_18]
0x100429b0e  xor     rcx, rsp; StackCookie
0x100429b11  call    __security_check_cookie
0x100429b16  add     rsp, 0D8h
0x100429b1d  retn
0x100429b1e  jns     short loc_100429B50
0x100429b20  mov     r9d, [rsp+0D8h+var_B8]
0x100429b25  mov     r8, [rsp+0D8h+var_B0]
0x100429b2a  mov     edx, [rsp+0D8h+var_90]
0x100429b2e  mov     rcx, [rsp+0D8h+var_88]
0x100429b33  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100429b38  mov     rcx, [rsp+0D8h+var_18]
0x100429b40  xor     rcx, rsp; StackCookie
0x100429b43  call    __security_check_cookie
0x100429b48  add     rsp, 0D8h
0x100429b4f  retn
0x100429b50  xor     eax, eax
0x100429b52  mov     rcx, [rsp+0D8h+var_18]
0x100429b5a  xor     rcx, rsp; StackCookie
0x100429b5d  call    __security_check_cookie
0x100429b62  add     rsp, 0D8h
0x100429b69  retn
```
