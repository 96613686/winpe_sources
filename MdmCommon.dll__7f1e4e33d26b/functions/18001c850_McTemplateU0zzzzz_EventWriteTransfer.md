# McTemplateU0zzzzz_EventWriteTransfer

- ea: `0x18001c850`
- end: `0x18001c9a5`
- name: `McTemplateU0zzzzz_EventWriteTransfer`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x180001520`
- `0x1800064f0`
- `0x18001c850`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        const wchar_t *a7)
{
  __int64 v7; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  __int64 v11; // rcx
  int v12; // ecx
  const wchar_t *v13; // rcx
  __int64 v14; // r8
  int v15; // r8d
  const wchar_t *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r8
  const wchar_t *v19; // rcx
  bool v20; // zf
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+30h] [rbp-31h] BYREF
  const wchar_t *v23; // [rsp+40h] [rbp-21h]
  int v24; // [rsp+48h] [rbp-19h]
  int v25; // [rsp+4Ch] [rbp-15h]
  const wchar_t *v26; // [rsp+50h] [rbp-11h]
  int v27; // [rsp+58h] [rbp-9h]
  int v28; // [rsp+5Ch] [rbp-5h]
  const wchar_t *v29; // [rsp+60h] [rbp-1h]
  int v30; // [rsp+68h] [rbp+7h]
  int v31; // [rsp+6Ch] [rbp+Bh]
  const wchar_t *v32; // [rsp+70h] [rbp+Fh]
  int v33; // [rsp+78h] [rbp+17h]
  int v34; // [rsp+7Ch] [rbp+1Bh]
  const wchar_t *v35; // [rsp+80h] [rbp+1Fh]
  int v36; // [rsp+88h] [rbp+27h]
  int v37; // [rsp+8Ch] [rbp+2Bh]

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
  v24 = v10;
  v25 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v23 = a3;
  if ( a4 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v12 = 10;
  }
  v27 = v12;
  v13 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v28 = 0;
  v26 = a4;
  if ( a5 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a5[v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v15 = 10;
  }
  v30 = v15;
  v31 = 0;
  if ( !a5 )
    v13 = L"NULL";
  v29 = v13;
  v16 = a6;
  if ( a6 )
  {
    v17 = -1;
    do
      ++v17;
    while ( a6[v17] );
    v18 = (unsigned int)(2 * v17 + 2);
  }
  else
  {
    v18 = 10;
  }
  v33 = v18;
  v34 = 0;
  if ( !a6 )
    v16 = L"NULL";
  v32 = v16;
  v19 = a7;
  v20 = a7 == 0;
  if ( a7 )
  {
    do
      ++v7;
    while ( a7[v7] );
    v8 = 2 * v7 + 2;
    v20 = a7 == 0;
  }
  if ( v20 )
    v19 = L"NULL";
  v36 = v8;
  v35 = v19;
  v37 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v19,
           (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_OUTGOING_HTTP_REQUEST,
           v18,
           6u,
           &v22);
}

```

## disassembly

```asm
0x18001c850  push    rbp
0x18001c852  lea     rbp, [rsp-3Fh]
0x18001c857  sub     rsp, 0A0h
0x18001c85e  mov     rax, cs:__security_cookie
0x18001c865  xor     rax, rsp
0x18001c868  mov     [rbp+3Fh+var_10], rax
0x18001c86c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c870  xor     r10d, r10d
0x18001c873  mov     edx, 0Ah
0x18001c878  test    r8, r8
0x18001c87b  jz      short loc_18001C893
0x18001c87d  mov     rcx, rax
0x18001c880  inc     rcx
0x18001c883  cmp     [r8+rcx*2], r10w
0x18001c888  jnz     short loc_18001C880
0x18001c88a  lea     ecx, ds:2[rcx*2]
0x18001c891  jmp     short loc_18001C895
0x18001c893  mov     ecx, edx
0x18001c895  test    r8, r8
0x18001c898  mov     [rbp+3Fh+var_58], ecx
0x18001c89b  lea     r11, aNull_0; "NULL"
0x18001c8a2  mov     [rbp+3Fh+var_54], r10d
0x18001c8a6  cmovz   r8, r11
0x18001c8aa  mov     [rbp+3Fh+var_60], r8
0x18001c8ae  test    r9, r9
0x18001c8b1  jz      short loc_18001C8C9
0x18001c8b3  mov     rcx, rax
0x18001c8b6  inc     rcx
0x18001c8b9  cmp     [r9+rcx*2], r10w
0x18001c8be  jnz     short loc_18001C8B6
0x18001c8c0  lea     ecx, ds:2[rcx*2]
0x18001c8c7  jmp     short loc_18001C8CB
0x18001c8c9  mov     ecx, edx
0x18001c8cb  test    r9, r9
0x18001c8ce  mov     [rbp+3Fh+var_48], ecx
0x18001c8d1  mov     rcx, [rbp+3Fh+arg_20]
0x18001c8d5  cmovz   r9, r11
0x18001c8d9  mov     [rbp+3Fh+var_44], r10d
0x18001c8dd  mov     [rbp+3Fh+var_50], r9
0x18001c8e1  test    rcx, rcx
0x18001c8e4  jz      short loc_18001C8FD
0x18001c8e6  mov     r8, rax
0x18001c8e9  inc     r8
0x18001c8ec  cmp     [rcx+r8*2], r10w
0x18001c8f1  jnz     short loc_18001C8E9
0x18001c8f3  lea     r8d, ds:2[r8*2]
0x18001c8fb  jmp     short loc_18001C900
0x18001c8fd  mov     r8d, edx
0x18001c900  test    rcx, rcx
0x18001c903  mov     [rbp+3Fh+var_38], r8d
0x18001c907  mov     [rbp+3Fh+var_34], r10d
0x18001c90b  cmovz   rcx, r11
0x18001c90f  mov     [rbp+3Fh+var_40], rcx
0x18001c913  mov     rcx, [rbp+3Fh+arg_28]
0x18001c917  test    rcx, rcx
0x18001c91a  jz      short loc_18001C933
0x18001c91c  mov     r8, rax
0x18001c91f  inc     r8
0x18001c922  cmp     [rcx+r8*2], r10w
0x18001c927  jnz     short loc_18001C91F
0x18001c929  lea     r8d, ds:2[r8*2]
0x18001c931  jmp     short loc_18001C936
0x18001c933  mov     r8d, edx
0x18001c936  test    rcx, rcx
0x18001c939  mov     [rbp+3Fh+var_28], r8d
0x18001c93d  mov     [rbp+3Fh+var_24], r10d
0x18001c941  cmovz   rcx, r11
0x18001c945  mov     [rbp+3Fh+var_30], rcx
0x18001c949  mov     rcx, [rbp+3Fh+arg_30]
0x18001c94d  test    rcx, rcx
0x18001c950  jz      short loc_18001C966
0x18001c952  inc     rax
0x18001c955  cmp     [rcx+rax*2], r10w
0x18001c95a  jnz     short loc_18001C952
0x18001c95c  lea     edx, ds:2[rax*2]
0x18001c963  test    rcx, rcx
0x18001c966  cmovz   rcx, r11
0x18001c96a  mov     [rbp+3Fh+var_18], edx
0x18001c96d  lea     rax, [rbp+3Fh+var_70]
0x18001c971  mov     [rbp+3Fh+var_20], rcx
0x18001c975  lea     rdx, MDMCOMMON_TRACE_OUTGOING_HTTP_REQUEST
0x18001c97c  mov     [rsp+0A0h+var_80], rax
0x18001c981  mov     r9d, 6
0x18001c987  mov     [rbp+3Fh+var_14], r10d
0x18001c98b  call    McGenEventWrite_EventWriteTransfer
0x18001c990  mov     rcx, [rbp+3Fh+var_10]
0x18001c994  xor     rcx, rsp; StackCookie
0x18001c997  call    __security_check_cookie
0x18001c99c  add     rsp, 0A0h
0x18001c9a3  pop     rbp
0x18001c9a4  retn
```
