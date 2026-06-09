# _log_special_common

- ea: `0x14001c6e0`
- end: `0x14001c779`
- name: `_log_special_common`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001c6c0`

## callees

- `0x14001c490`
- `0x14001c6e0`

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
0x14001c6e0  sub     rsp, 68h
0x14001c6e4  movaps  [rsp+68h+var_18], xmm6
0x14001c6e9  movaps  xmm6, xmm1
0x14001c6ec  mov     edx, r9d
0x14001c6ef  movaps  xmm3, xmm0
0x14001c6f2  sub     r8d, 1
0x14001c6f6  jz      short loc_14001C727
0x14001c6f8  cmp     r8d, 1
0x14001c6fc  jnz     short loc_14001C76C
0x14001c6fe  mov     [rsp+68h+var_28], r8d
0x14001c703  xorps   xmm2, xmm2
0x14001c706  movsd   [rsp+68h+var_30], xmm2
0x14001c70c  mov     r9d, r8d
0x14001c70f  movsd   [rsp+68h+var_38], xmm0
0x14001c715  mov     [rsp+68h+var_40], 21h ; '!'
0x14001c71d  mov     [rsp+68h+var_48], 8
0x14001c725  jmp     short loc_14001C754
0x14001c727  mov     [rsp+68h+var_28], 1
0x14001c72f  xorps   xmm0, xmm0
0x14001c732  movsd   [rsp+68h+var_30], xmm0
0x14001c738  mov     r9d, 2
0x14001c73e  movsd   [rsp+68h+var_38], xmm3
0x14001c744  mov     [rsp+68h+var_40], 22h ; '"'
0x14001c74c  mov     [rsp+68h+var_48], 4
0x14001c754  mov     rcx, [rsp+68h+arg_20]
0x14001c75c  movsd   [rsp+68h+arg_8], xmm6
0x14001c762  mov     r8, [rsp+68h+arg_8]
0x14001c767  call    _handle_error
0x14001c76c  movaps  xmm0, xmm6
0x14001c76f  movaps  xmm6, [rsp+68h+var_18]
0x14001c774  add     rsp, 68h
0x14001c778  retn
```
