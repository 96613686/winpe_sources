# ComputeFlushPeriod

- ea: `0x14000ec00`
- end: `0x14000ec88`
- name: `ComputeFlushPeriod`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ef90`

## callees

- `0x140002398`
- `0x1400024d4`

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
0x14000ec00  mov     [rsp+arg_8], edx
0x14000ec04  sub     rsp, 38h
0x14000ec08  mov     rax, [rcx+158h]
0x14000ec0f  mov     r8d, 10h
0x14000ec15  shr     rcx, 4
0x14000ec19  mov     [rsp+38h+arg_0], rcx
0x14000ec1e  lea     rcx, [rsp+38h+arg_8]
0x14000ec23  mov     [rsp+38h+arg_8], 0
0x14000ec2b  mov     rdx, [rax+8]
0x14000ec2f  movups  xmm0, xmmword ptr [rdx-10h]
0x14000ec33  lea     rdx, [rsp+38h+var_18]
0x14000ec38  movdqu  [rsp+38h+var_18], xmm0
0x14000ec3e  call    RunningHash
0x14000ec43  lea     rcx, [rsp+38h+arg_8]
0x14000ec48  mov     r8d, 8
0x14000ec4e  lea     rdx, [rsp+38h+arg_0]
0x14000ec53  call    RunningHash
0x14000ec58  lea     rcx, [rsp+38h+arg_8]
0x14000ec5d  call    FinishHash
0x14000ec62  mov     r8d, [rsp+38h+arg_8]
0x14000ec67  mov     eax, 6FD91D85h
0x14000ec6c  mul     r8d
0x14000ec6f  shr     edx, 12h
0x14000ec72  imul    ecx, edx, 927C0h
0x14000ec78  sub     r8d, ecx
0x14000ec7b  lea     eax, [r8+927C0h]
0x14000ec82  add     rsp, 38h
0x14000ec86  retn
```
