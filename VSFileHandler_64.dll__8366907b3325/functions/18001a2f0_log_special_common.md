# _log_special_common

- ea: `0x18001a2f0`
- end: `0x18001a386`
- name: `_log_special_common`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a2d0`

## callees

- `0x18001a11c`
- `0x18001a2f0`

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
    handle_error(a5, a4, LODWORD(a2), v7, v9, v10, v11, 0, 1);
  }
  return *(__m128 *)&a2;
}

```

## disassembly

```asm
0x18001a2f0  mov     rax, rsp
0x18001a2f3  sub     rsp, 68h
0x18001a2f7  movaps  xmmword ptr [rax-18h], xmm6
0x18001a2fb  movaps  xmm6, xmm1
0x18001a2fe  mov     edx, r9d
0x18001a301  movaps  xmm3, xmm0
0x18001a304  sub     r8d, 1
0x18001a308  jz      short loc_18001A334
0x18001a30a  cmp     r8d, 1
0x18001a30e  jnz     short loc_18001A379
0x18001a310  mov     [rax-28h], r8d
0x18001a314  xorps   xmm2, xmm2
0x18001a317  movsd   qword ptr [rax-30h], xmm2
0x18001a31c  mov     r9d, r8d
0x18001a31f  movsd   qword ptr [rax-38h], xmm0
0x18001a324  mov     dword ptr [rax-40h], 21h ; '!'
0x18001a32b  mov     dword ptr [rax-48h], 8
0x18001a332  jmp     short loc_18001A361
0x18001a334  mov     [rsp+68h+var_28], 1
0x18001a33c  xorps   xmm0, xmm0
0x18001a33f  movsd   [rsp+68h+var_30], xmm0
0x18001a345  mov     r9d, 2
0x18001a34b  movsd   [rsp+68h+var_38], xmm3
0x18001a351  mov     [rsp+68h+var_40], 22h ; '"'
0x18001a359  mov     [rsp+68h+var_48], 4
0x18001a361  mov     rcx, [rsp+68h+arg_20]
0x18001a369  movsd   [rsp+68h+arg_8], xmm6
0x18001a36f  mov     r8, [rsp+68h+arg_8]
0x18001a374  call    _handle_error
0x18001a379  movaps  xmm0, xmm6
0x18001a37c  movaps  xmm6, [rsp+68h+var_18]
0x18001a381  add     rsp, 68h
0x18001a385  retn
```
