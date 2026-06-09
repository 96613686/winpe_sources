# ComputeFlushPeriod

- ea: `0x140025d50`
- end: `0x140025dd8`
- name: `ComputeFlushPeriod`
- size: `136`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140026158`

## callees

- `0x140009bd8`
- `0x14000af98`

## pseudocode

```c
__int64 __fastcall ComputeFlushPeriod(unsigned __int64 a1, unsigned int a2)
{
  __int64 v2; // rax
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  v2 = *(_QWORD *)(a1 + 344);
  v5 = a1 >> 4;
  v6 = 0;
  v4 = *(_OWORD *)(*(_QWORD *)(v2 + 8) - 16LL);
  RunningHash(&v6, &v4, 16);
  RunningHash(&v6, &v5, 8);
  FinishHash(&v6);
  return v6 % 0x927C0 + 600000;
}

```

## disassembly

```asm
0x140025d50  mov     [rsp+arg_8], edx
0x140025d54  sub     rsp, 38h
0x140025d58  mov     rax, [rcx+158h]
0x140025d5f  mov     r8d, 10h
0x140025d65  shr     rcx, 4
0x140025d69  mov     [rsp+38h+arg_0], rcx
0x140025d6e  lea     rcx, [rsp+38h+arg_8]
0x140025d73  mov     [rsp+38h+arg_8], 0
0x140025d7b  mov     rdx, [rax+8]
0x140025d7f  movups  xmm0, xmmword ptr [rdx-10h]
0x140025d83  lea     rdx, [rsp+38h+var_18]
0x140025d88  movdqu  [rsp+38h+var_18], xmm0
0x140025d8e  call    RunningHash
0x140025d93  lea     rcx, [rsp+38h+arg_8]
0x140025d98  mov     r8d, 8
0x140025d9e  lea     rdx, [rsp+38h+arg_0]
0x140025da3  call    RunningHash
0x140025da8  lea     rcx, [rsp+38h+arg_8]
0x140025dad  call    FinishHash
0x140025db2  mov     r8d, [rsp+38h+arg_8]
0x140025db7  mov     eax, 6FD91D85h
0x140025dbc  mul     r8d
0x140025dbf  shr     edx, 12h
0x140025dc2  imul    ecx, edx, 927C0h
0x140025dc8  sub     r8d, ecx
0x140025dcb  lea     eax, [r8+927C0h]
0x140025dd2  add     rsp, 38h
0x140025dd6  retn
```
