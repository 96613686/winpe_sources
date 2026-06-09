# McTemplateU0zzqqq_EventWriteTransfer

- ea: `0x180011f74`
- end: `0x180012062`
- name: `McTemplateU0zzqqq_EventWriteTransfer`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eb90`

## callees

- `0x180001c60`
- `0x180011b54`
- `0x180011f74`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzqqq_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5,
        char a6,
        char a7)
{
  __int64 v7; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  bool v11; // zf
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-31h] BYREF
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
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v15 = v10;
  v16 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v14 = a3;
  v11 = a4 == 0;
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v8 = 2 * v7 + 2;
    v11 = a4 == 0;
  }
  if ( v11 )
    a4 = L"NULL";
  v18 = v8;
  v17 = a4;
  v20 = &a5;
  v19 = 0;
  v22 = &a6;
  v21 = 4;
  v24 = &a7;
  v23 = 4;
  v25 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)MDM_ENTERPRISE_DIAGNOSTICS_Context,
           (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsEnrollRenewScheduleStart,
           (__int64)a3,
           6u,
           &v13);
}

```

## disassembly

```asm
0x180011f74  push    rbp
0x180011f76  lea     rbp, [rsp-3Fh]
0x180011f7b  sub     rsp, 0A0h
0x180011f82  mov     rax, cs:__security_cookie
0x180011f89  xor     rax, rsp
0x180011f8c  mov     [rbp+3Fh+var_10], rax
0x180011f90  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011f94  xor     r10d, r10d
0x180011f97  mov     edx, 0Ah
0x180011f9c  test    r8, r8
0x180011f9f  jz      short loc_180011FB7
0x180011fa1  mov     rcx, rax
0x180011fa4  inc     rcx
0x180011fa7  cmp     [r8+rcx*2], r10w
0x180011fac  jnz     short loc_180011FA4
0x180011fae  lea     ecx, ds:2[rcx*2]
0x180011fb5  jmp     short loc_180011FB9
0x180011fb7  mov     ecx, edx
0x180011fb9  test    r8, r8
0x180011fbc  mov     [rbp+3Fh+var_58], ecx
0x180011fbf  lea     r11, aNull_0; "NULL"
0x180011fc6  mov     [rbp+3Fh+var_54], r10d
0x180011fca  cmovz   r8, r11
0x180011fce  mov     [rbp+3Fh+var_60], r8
0x180011fd2  test    r9, r9
0x180011fd5  jz      short loc_180011FEB
0x180011fd7  inc     rax
0x180011fda  cmp     [r9+rax*2], r10w
0x180011fdf  jnz     short loc_180011FD7
0x180011fe1  lea     edx, ds:2[rax*2]
0x180011fe8  test    r9, r9
0x180011feb  cmovz   r9, r11
0x180011fef  mov     [rbp+3Fh+var_48], edx
0x180011ff2  lea     rax, [rbp+3Fh+arg_20]
0x180011ff6  mov     [rbp+3Fh+var_50], r9
0x180011ffa  mov     [rbp+3Fh+var_40], rax
0x180011ffe  lea     rdx, EnterpriseDiagnosticsEnrollRenewScheduleStart
0x180012005  lea     rax, [rbp+3Fh+arg_28]
0x180012009  mov     [rbp+3Fh+var_44], r10d
0x18001200d  mov     [rbp+3Fh+var_30], rax
0x180012011  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180012018  lea     rax, [rbp+3Fh+arg_30]
0x18001201c  mov     [rbp+3Fh+var_38], 4
0x180012024  mov     [rbp+3Fh+var_20], rax
0x180012028  mov     r9d, 6
0x18001202e  lea     rax, [rbp+3Fh+var_70]
0x180012032  mov     [rbp+3Fh+var_28], 4
0x18001203a  mov     [rsp+0A0h+var_80], rax
0x18001203f  mov     [rbp+3Fh+var_18], 4
0x180012047  call    McGenEventWrite_EventWriteTransfer
0x18001204c  mov     rcx, [rbp+3Fh+var_10]
0x180012050  xor     rcx, rsp; StackCookie
0x180012053  call    __security_check_cookie
0x180012058  add     rsp, 0A0h
0x18001205f  pop     rbp
0x180012060  retn
```
