# McTemplateU0zzqqq_EventWriteTransfer

- ea: `0x14001235c`
- end: `0x14001244a`
- name: `McTemplateU0zzqqq_EventWriteTransfer`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f9a4`

## callees

- `0x1400029c0`
- `0x140011ffc`
- `0x14001235c`

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
0x14001235c  push    rbp
0x14001235e  lea     rbp, [rsp-3Fh]
0x140012363  sub     rsp, 0A0h
0x14001236a  mov     rax, cs:__security_cookie
0x140012371  xor     rax, rsp
0x140012374  mov     [rbp+3Fh+var_10], rax
0x140012378  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001237c  xor     r10d, r10d
0x14001237f  mov     edx, 0Ah
0x140012384  test    r8, r8
0x140012387  jz      short loc_14001239F
0x140012389  mov     rcx, rax
0x14001238c  inc     rcx
0x14001238f  cmp     [r8+rcx*2], r10w
0x140012394  jnz     short loc_14001238C
0x140012396  lea     ecx, ds:2[rcx*2]
0x14001239d  jmp     short loc_1400123A1
0x14001239f  mov     ecx, edx
0x1400123a1  test    r8, r8
0x1400123a4  mov     [rbp+3Fh+var_58], ecx
0x1400123a7  lea     r11, aNull_0; "NULL"
0x1400123ae  mov     [rbp+3Fh+var_54], r10d
0x1400123b2  cmovz   r8, r11
0x1400123b6  mov     [rbp+3Fh+var_60], r8
0x1400123ba  test    r9, r9
0x1400123bd  jz      short loc_1400123D3
0x1400123bf  inc     rax
0x1400123c2  cmp     [r9+rax*2], r10w
0x1400123c7  jnz     short loc_1400123BF
0x1400123c9  lea     edx, ds:2[rax*2]
0x1400123d0  test    r9, r9
0x1400123d3  cmovz   r9, r11
0x1400123d7  mov     [rbp+3Fh+var_48], edx
0x1400123da  lea     rax, [rbp+3Fh+arg_20]
0x1400123de  mov     [rbp+3Fh+var_50], r9
0x1400123e2  mov     [rbp+3Fh+var_40], rax
0x1400123e6  lea     rdx, EnterpriseDiagnosticsEnrollRenewScheduleStart
0x1400123ed  lea     rax, [rbp+3Fh+arg_28]
0x1400123f1  mov     [rbp+3Fh+var_44], r10d
0x1400123f5  mov     [rbp+3Fh+var_30], rax
0x1400123f9  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x140012400  lea     rax, [rbp+3Fh+arg_30]
0x140012404  mov     [rbp+3Fh+var_38], 4
0x14001240c  mov     [rbp+3Fh+var_20], rax
0x140012410  mov     r9d, 6
0x140012416  lea     rax, [rbp+3Fh+var_70]
0x14001241a  mov     [rbp+3Fh+var_28], 4
0x140012422  mov     [rsp+0A0h+var_80], rax
0x140012427  mov     [rbp+3Fh+var_18], 4
0x14001242f  call    McGenEventWrite_EventWriteTransfer
0x140012434  mov     rcx, [rbp+3Fh+var_10]
0x140012438  xor     rcx, rsp; StackCookie
0x14001243b  call    __security_check_cookie
0x140012440  add     rsp, 0A0h
0x140012447  pop     rbp
0x140012448  retn
```
