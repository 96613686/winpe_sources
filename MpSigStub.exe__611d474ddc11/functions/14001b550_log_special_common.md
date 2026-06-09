# _log_special_common

- ea: `0x14001b550`
- end: `0x14001b5e6`
- name: `_log_special_common`
- size: `150`
- prototype: `__m128 __fastcall(double, double, int, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001b530`

## callees

- `0x14001b214`
- `0x14001b550`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__m128 __fastcall log_special_common(double a1, double a2, int a3, int a4, __int64 a5)
{
  int v6; // r8d
  int v7; // r9d
  int v9; // [rsp+20h] [rbp-48h]
  int v10; // [rsp+28h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-38h]

  v6 = a3 - 1;
  if ( !v6 )
  {
    v7 = 2;
    v11 = *(_QWORD *)&a1;
    v10 = 34;
    v9 = 4;
    goto LABEL_5;
  }
  if ( v6 == 1 )
  {
    v7 = 1;
    v11 = *(_QWORD *)&a1;
    v10 = 33;
    v9 = 8;
LABEL_5:
    sub_14001B214(a5, a4, LODWORD(a2), v7, v9, v10, v11, 0, 1);
  }
  return *(__m128 *)&a2;
}

```

## disassembly

```asm
0x14001b550  mov     rax, rsp
0x14001b553  sub     rsp, 68h
0x14001b557  movaps  xmmword ptr [rax-18h], xmm6
0x14001b55b  movaps  xmm6, xmm1
0x14001b55e  mov     edx, r9d
0x14001b561  movaps  xmm3, xmm0
0x14001b564  sub     r8d, 1
0x14001b568  jz      short loc_14001B594
0x14001b56a  cmp     r8d, 1
0x14001b56e  jnz     short loc_14001B5D9
0x14001b570  mov     [rax-28h], r8d
0x14001b574  xorps   xmm2, xmm2
0x14001b577  movsd   qword ptr [rax-30h], xmm2
0x14001b57c  mov     r9d, r8d
0x14001b57f  movsd   qword ptr [rax-38h], xmm0
0x14001b584  mov     dword ptr [rax-40h], 21h ; '!'
0x14001b58b  mov     dword ptr [rax-48h], 8
0x14001b592  jmp     short loc_14001B5C1
0x14001b594  mov     [rsp+68h+var_28], 1
0x14001b59c  xorps   xmm0, xmm0
0x14001b59f  movsd   [rsp+68h+var_30], xmm0
0x14001b5a5  mov     r9d, 2
0x14001b5ab  movsd   [rsp+68h+var_38], xmm3
0x14001b5b1  mov     [rsp+68h+var_40], 22h ; '"'
0x14001b5b9  mov     [rsp+68h+var_48], 4
0x14001b5c1  mov     rcx, [rsp+68h+arg_20]
0x14001b5c9  movsd   [rsp+68h+arg_8], xmm6
0x14001b5cf  mov     r8, [rsp+68h+arg_8]
0x14001b5d4  call    sub_14001B214
0x14001b5d9  movaps  xmm0, xmm6
0x14001b5dc  movaps  xmm6, [rsp+68h+var_18]
0x14001b5e1  add     rsp, 68h
0x14001b5e5  retn
```
