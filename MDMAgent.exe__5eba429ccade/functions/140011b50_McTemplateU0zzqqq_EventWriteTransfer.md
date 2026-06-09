# McTemplateU0zzqqq_EventWriteTransfer

- ea: `0x140011b50`
- end: `0x140011c3d`
- name: `McTemplateU0zzqqq_EventWriteTransfer`
- size: `237`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, const wchar_t *, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f1f8`

## callees

- `0x140002930`
- `0x1400117fc`
- `0x140011b50`

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
0x140011b50  push    rbp
0x140011b52  lea     rbp, [rsp-3Fh]
0x140011b57  sub     rsp, 0A0h
0x140011b5e  mov     rax, cs:__security_cookie
0x140011b65  xor     rax, rsp
0x140011b68  mov     [rbp+3Fh+var_10], rax
0x140011b6c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011b70  xor     r10d, r10d
0x140011b73  mov     edx, 0Ah
0x140011b78  test    r8, r8
0x140011b7b  jz      short loc_140011B93
0x140011b7d  mov     rcx, rax
0x140011b80  inc     rcx
0x140011b83  cmp     [r8+rcx*2], r10w
0x140011b88  jnz     short loc_140011B80
0x140011b8a  lea     ecx, ds:2[rcx*2]
0x140011b91  jmp     short loc_140011B95
0x140011b93  mov     ecx, edx
0x140011b95  test    r8, r8
0x140011b98  mov     [rbp+3Fh+var_58], ecx
0x140011b9b  lea     r11, aNull_0; "NULL"
0x140011ba2  mov     [rbp+3Fh+var_54], r10d
0x140011ba6  cmovz   r8, r11
0x140011baa  mov     [rbp+3Fh+var_60], r8
0x140011bae  test    r9, r9
0x140011bb1  jz      short loc_140011BC7
0x140011bb3  inc     rax
0x140011bb6  cmp     [r9+rax*2], r10w
0x140011bbb  jnz     short loc_140011BB3
0x140011bbd  lea     edx, ds:2[rax*2]
0x140011bc4  test    r9, r9
0x140011bc7  cmovz   r9, r11
0x140011bcb  mov     [rbp+3Fh+var_48], edx
0x140011bce  lea     rax, [rbp+3Fh+arg_20]
0x140011bd2  mov     [rbp+3Fh+var_50], r9
0x140011bd6  mov     [rbp+3Fh+var_40], rax
0x140011bda  lea     rdx, EnterpriseDiagnosticsEnrollRenewScheduleStart
0x140011be1  lea     rax, [rbp+3Fh+arg_28]
0x140011be5  mov     [rbp+3Fh+var_44], r10d
0x140011be9  mov     [rbp+3Fh+var_30], rax
0x140011bed  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x140011bf4  lea     rax, [rbp+3Fh+arg_30]
0x140011bf8  mov     [rbp+3Fh+var_38], 4
0x140011c00  mov     [rbp+3Fh+var_20], rax
0x140011c04  mov     r9d, 6
0x140011c0a  lea     rax, [rbp+3Fh+var_70]
0x140011c0e  mov     [rbp+3Fh+var_28], 4
0x140011c16  mov     [rsp+0A0h+var_80], rax
0x140011c1b  mov     [rbp+3Fh+var_18], 4
0x140011c23  call    McGenEventWrite_EventWriteTransfer
0x140011c28  mov     rcx, [rbp+3Fh+var_10]
0x140011c2c  xor     rcx, rsp; StackCookie
0x140011c2f  call    __security_check_cookie
0x140011c34  add     rsp, 0A0h
0x140011c3b  pop     rbp
0x140011c3c  retn
```
