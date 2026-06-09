# McTemplateU0zzzzz_EventWriteTransfer

- ea: `0x18001ceb4`
- end: `0x18001d00a`
- name: `McTemplateU0zzzzz_EventWriteTransfer`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001be50`

## callees

- `0x180001520`
- `0x180006560`
- `0x18001ceb4`

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
0x18001ceb4  push    rbp
0x18001ceb6  lea     rbp, [rsp-3Fh]
0x18001cebb  sub     rsp, 0A0h
0x18001cec2  mov     rax, cs:__security_cookie
0x18001cec9  xor     rax, rsp
0x18001cecc  mov     [rbp+3Fh+var_10], rax
0x18001ced0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ced4  xor     r10d, r10d
0x18001ced7  mov     edx, 0Ah
0x18001cedc  test    r8, r8
0x18001cedf  jz      short loc_18001CEF7
0x18001cee1  mov     rcx, rax
0x18001cee4  inc     rcx
0x18001cee7  cmp     [r8+rcx*2], r10w
0x18001ceec  jnz     short loc_18001CEE4
0x18001ceee  lea     ecx, ds:2[rcx*2]
0x18001cef5  jmp     short loc_18001CEF9
0x18001cef7  mov     ecx, edx
0x18001cef9  test    r8, r8
0x18001cefc  mov     [rbp+3Fh+var_58], ecx
0x18001ceff  lea     r11, aNull_0; "NULL"
0x18001cf06  mov     [rbp+3Fh+var_54], r10d
0x18001cf0a  cmovz   r8, r11
0x18001cf0e  mov     [rbp+3Fh+var_60], r8
0x18001cf12  test    r9, r9
0x18001cf15  jz      short loc_18001CF2D
0x18001cf17  mov     rcx, rax
0x18001cf1a  inc     rcx
0x18001cf1d  cmp     [r9+rcx*2], r10w
0x18001cf22  jnz     short loc_18001CF1A
0x18001cf24  lea     ecx, ds:2[rcx*2]
0x18001cf2b  jmp     short loc_18001CF2F
0x18001cf2d  mov     ecx, edx
0x18001cf2f  test    r9, r9
0x18001cf32  mov     [rbp+3Fh+var_48], ecx
0x18001cf35  mov     rcx, [rbp+3Fh+arg_20]
0x18001cf39  cmovz   r9, r11
0x18001cf3d  mov     [rbp+3Fh+var_44], r10d
0x18001cf41  mov     [rbp+3Fh+var_50], r9
0x18001cf45  test    rcx, rcx
0x18001cf48  jz      short loc_18001CF61
0x18001cf4a  mov     r8, rax
0x18001cf4d  inc     r8
0x18001cf50  cmp     [rcx+r8*2], r10w
0x18001cf55  jnz     short loc_18001CF4D
0x18001cf57  lea     r8d, ds:2[r8*2]
0x18001cf5f  jmp     short loc_18001CF64
0x18001cf61  mov     r8d, edx
0x18001cf64  test    rcx, rcx
0x18001cf67  mov     [rbp+3Fh+var_38], r8d
0x18001cf6b  mov     [rbp+3Fh+var_34], r10d
0x18001cf6f  cmovz   rcx, r11
0x18001cf73  mov     [rbp+3Fh+var_40], rcx
0x18001cf77  mov     rcx, [rbp+3Fh+arg_28]
0x18001cf7b  test    rcx, rcx
0x18001cf7e  jz      short loc_18001CF97
0x18001cf80  mov     r8, rax
0x18001cf83  inc     r8
0x18001cf86  cmp     [rcx+r8*2], r10w
0x18001cf8b  jnz     short loc_18001CF83
0x18001cf8d  lea     r8d, ds:2[r8*2]
0x18001cf95  jmp     short loc_18001CF9A
0x18001cf97  mov     r8d, edx
0x18001cf9a  test    rcx, rcx
0x18001cf9d  mov     [rbp+3Fh+var_28], r8d
0x18001cfa1  mov     [rbp+3Fh+var_24], r10d
0x18001cfa5  cmovz   rcx, r11
0x18001cfa9  mov     [rbp+3Fh+var_30], rcx
0x18001cfad  mov     rcx, [rbp+3Fh+arg_30]
0x18001cfb1  test    rcx, rcx
0x18001cfb4  jz      short loc_18001CFCA
0x18001cfb6  inc     rax
0x18001cfb9  cmp     [rcx+rax*2], r10w
0x18001cfbe  jnz     short loc_18001CFB6
0x18001cfc0  lea     edx, ds:2[rax*2]
0x18001cfc7  test    rcx, rcx
0x18001cfca  cmovz   rcx, r11
0x18001cfce  mov     [rbp+3Fh+var_18], edx
0x18001cfd1  lea     rax, [rbp+3Fh+var_70]
0x18001cfd5  mov     [rbp+3Fh+var_20], rcx
0x18001cfd9  lea     rdx, MDMCOMMON_TRACE_OUTGOING_HTTP_REQUEST
0x18001cfe0  mov     [rsp+0A0h+var_80], rax
0x18001cfe5  mov     r9d, 6
0x18001cfeb  mov     [rbp+3Fh+var_14], r10d
0x18001cfef  call    McGenEventWrite_EventWriteTransfer
0x18001cff4  mov     rcx, [rbp+3Fh+var_10]
0x18001cff8  xor     rcx, rsp; StackCookie
0x18001cffb  call    __security_check_cookie
0x18001d000  add     rsp, 0A0h
0x18001d007  pop     rbp
0x18001d008  retn
```
