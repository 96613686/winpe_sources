# McTemplateU0zzqdq_USE_EtwEventWrite

- ea: `0x18000dca4`
- end: `0x18000dd85`
- name: `McTemplateU0zzqdq_USE_EtwEventWrite`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dc6c`

## callees

- `0x18000dca4`
- `0x180012a1c`
- `0x18001b7e0`

## pseudocode

```c
__int64 __fastcall McTemplateU0zzqdq_USE_EtwEventWrite(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5,
        char a6,
        char a7)
{
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  bool v10; // zf
  __int64 v12; // rcx
  _BYTE v13[16]; // [rsp+30h] [rbp-31h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-21h]
  int v15; // [rsp+48h] [rbp-19h]
  int v16; // [rsp+4Ch] [rbp-15h]
  const wchar_t *v17; // [rsp+50h] [rbp-11h]
  int v18; // [rsp+58h] [rbp-9h]
  int v19; // [rsp+5Ch] [rbp-5h]
  char *v20; // [rsp+60h] [rbp-1h]
  __int64 v21; // [rsp+68h] [rbp+7h]
  char *v22; // [rsp+70h] [rbp+Fh]
  __int64 v23; // [rsp+78h] [rbp+17h]
  char *v24; // [rsp+80h] [rbp+1Fh]
  __int64 v25; // [rsp+88h] [rbp+27h]

  v7 = -1;
  v8 = 10;
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    v9 = (unsigned int)(2 * v12 + 2);
  }
  else
  {
    v9 = 10;
  }
  v15 = v9;
  v16 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v14 = a3;
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v8 = (unsigned int)(2 * v7 + 2);
    v10 = a4 == 0;
  }
  v18 = v8;
  v20 = &a5;
  if ( v10 )
    a4 = L"NULL";
  v17 = a4;
  v22 = &a6;
  v24 = &a7;
  v19 = 0;
  v21 = 4;
  v23 = 4;
  v25 = 4;
  return McGenEventWrite_USE_EtwEventWrite(v9, v8, (__int64)a3, (__int64)a4, (__int64)v13);
}

```

## disassembly

```asm
0x18000dca4  push    rbp
0x18000dca6  lea     rbp, [rsp-3Fh]
0x18000dcab  sub     rsp, 0A0h
0x18000dcb2  mov     rax, cs:__security_cookie
0x18000dcb9  xor     rax, rsp
0x18000dcbc  mov     [rbp+3Fh+var_10], rax
0x18000dcc0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dcc4  xor     r10d, r10d
0x18000dcc7  mov     edx, 0Ah
0x18000dccc  test    r8, r8
0x18000dccf  jnz     loc_18000DD6C
0x18000dcd5  mov     ecx, edx
0x18000dcd7  test    r8, r8
0x18000dcda  mov     [rbp+3Fh+var_58], ecx
0x18000dcdd  lea     r11, aNull_0; "NULL"
0x18000dce4  mov     [rbp+3Fh+var_54], r10d
0x18000dce8  cmovz   r8, r11
0x18000dcec  mov     [rbp+3Fh+var_60], r8
0x18000dcf0  test    r9, r9
0x18000dcf3  jz      short loc_18000DD09
0x18000dcf5  inc     rax
0x18000dcf8  cmp     [r9+rax*2], r10w
0x18000dcfd  jnz     short loc_18000DCF5
0x18000dcff  lea     edx, ds:2[rax*2]
0x18000dd06  test    r9, r9
0x18000dd09  lea     rax, [rbp+3Fh+arg_20]
0x18000dd0d  mov     [rbp+3Fh+var_48], edx
0x18000dd10  mov     [rbp+3Fh+var_40], rax
0x18000dd14  cmovz   r9, r11
0x18000dd18  lea     rax, [rbp+3Fh+arg_28]
0x18000dd1c  mov     [rbp+3Fh+var_50], r9
0x18000dd20  mov     [rbp+3Fh+var_30], rax
0x18000dd24  lea     rax, [rbp+3Fh+arg_30]
0x18000dd28  mov     [rbp+3Fh+var_20], rax
0x18000dd2c  lea     rax, [rbp+3Fh+var_70]
0x18000dd30  mov     [rsp+0A0h+var_80], rax
0x18000dd35  mov     [rbp+3Fh+var_44], r10d
0x18000dd39  mov     [rbp+3Fh+var_38], 4
0x18000dd41  mov     [rbp+3Fh+var_28], 4
0x18000dd49  mov     [rbp+3Fh+var_18], 4
0x18000dd51  call    McGenEventWrite_USE_EtwEventWrite
0x18000dd56  mov     rcx, [rbp+3Fh+var_10]
0x18000dd5a  xor     rcx, rsp; StackCookie
0x18000dd5d  call    __security_check_cookie
0x18000dd62  add     rsp, 0A0h
0x18000dd69  pop     rbp
0x18000dd6a  retn
0x18000dd6c  mov     rcx, rax
0x18000dd6f  inc     rcx
0x18000dd72  cmp     [r8+rcx*2], r10w
0x18000dd77  jnz     short loc_18000DD6F
0x18000dd79  lea     ecx, ds:2[rcx*2]
0x18000dd80  jmp     loc_18000DCD7
```
