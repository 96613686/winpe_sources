# McTemplateU0zzzz_EventWriteTransfer

- ea: `0x180018968`
- end: `0x180018a96`
- name: `McTemplateU0zzzz_EventWriteTransfer`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800166b4`

## callees

- `0x180001870`
- `0x180018910`
- `0x180018968`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v7; // r10d
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // ecx
  const wchar_t *v12; // rcx
  __int64 v13; // rdx
  int v14; // edx
  const wchar_t *v15; // rcx
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v19; // [rsp+40h] [rbp-9h]
  int v20; // [rsp+48h] [rbp-1h]
  int v21; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v22; // [rsp+50h] [rbp+7h]
  int v23; // [rsp+58h] [rbp+Fh]
  int v24; // [rsp+5Ch] [rbp+13h]
  const wchar_t *v25; // [rsp+60h] [rbp+17h]
  int v26; // [rsp+68h] [rbp+1Fh]
  int v27; // [rsp+6Ch] [rbp+23h]
  const wchar_t *v28; // [rsp+70h] [rbp+27h]
  int v29; // [rsp+78h] [rbp+2Fh]
  int v30; // [rsp+7Ch] [rbp+33h]

  v6 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v20 = v9;
  v21 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v19 = a3;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v23 = v11;
  v12 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v24 = 0;
  v22 = a4;
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  v26 = v14;
  v27 = 0;
  if ( !a5 )
    v12 = L"NULL";
  v25 = v12;
  v15 = a6;
  v16 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v7 = 2 * v6 + 2;
    v16 = a6 == 0;
  }
  if ( v16 )
    v15 = L"NULL";
  v29 = v7;
  v28 = v15;
  v30 = 0;
  return McGenEventWrite_EventWriteTransfer((__int64)v15, &TraceMerge_NGEN_Configuration, (__int64)a3, 5u, &v18);
}

```

## disassembly

```asm
0x180018968  mov     [rsp-8+arg_0], rbx
0x18001896d  push    rbp
0x18001896e  lea     rbp, [rsp-47h]
0x180018973  sub     rsp, 90h
0x18001897a  mov     rax, cs:__security_cookie
0x180018981  xor     rax, rsp
0x180018984  mov     [rbp+47h+var_10], rax
0x180018988  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001898c  xor     r11d, r11d
0x18001898f  mov     r10d, 0Ah
0x180018995  test    r8, r8
0x180018998  jz      short loc_1800189B0
0x18001899a  mov     rcx, rax
0x18001899d  inc     rcx
0x1800189a0  cmp     [r8+rcx*2], r11w
0x1800189a5  jnz     short loc_18001899D
0x1800189a7  lea     ecx, ds:2[rcx*2]
0x1800189ae  jmp     short loc_1800189B3
0x1800189b0  mov     ecx, r10d
0x1800189b3  test    r8, r8
0x1800189b6  mov     [rbp+47h+var_48], ecx
0x1800189b9  lea     rbx, aNull; "NULL"
0x1800189c0  mov     [rbp+47h+var_44], r11d
0x1800189c4  cmovz   r8, rbx
0x1800189c8  mov     [rbp+47h+var_50], r8
0x1800189cc  test    r9, r9
0x1800189cf  jz      short loc_1800189E7
0x1800189d1  mov     rcx, rax
0x1800189d4  inc     rcx
0x1800189d7  cmp     [r9+rcx*2], r11w
0x1800189dc  jnz     short loc_1800189D4
0x1800189de  lea     ecx, ds:2[rcx*2]
0x1800189e5  jmp     short loc_1800189EA
0x1800189e7  mov     ecx, r10d
0x1800189ea  test    r9, r9
0x1800189ed  mov     [rbp+47h+var_38], ecx
0x1800189f0  mov     rcx, [rbp+47h+arg_20]
0x1800189f4  cmovz   r9, rbx
0x1800189f8  mov     [rbp+47h+var_34], r11d
0x1800189fc  mov     [rbp+47h+var_40], r9
0x180018a00  test    rcx, rcx
0x180018a03  jz      short loc_180018A1B
0x180018a05  mov     rdx, rax
0x180018a08  inc     rdx
0x180018a0b  cmp     [rcx+rdx*2], r11w
0x180018a10  jnz     short loc_180018A08
0x180018a12  lea     edx, ds:2[rdx*2]
0x180018a19  jmp     short loc_180018A1E
0x180018a1b  mov     edx, r10d
0x180018a1e  test    rcx, rcx
0x180018a21  mov     [rbp+47h+var_28], edx
0x180018a24  mov     [rbp+47h+var_24], r11d
0x180018a28  cmovz   rcx, rbx
0x180018a2c  mov     [rbp+47h+var_30], rcx
0x180018a30  mov     rcx, [rbp+47h+arg_28]
0x180018a34  test    rcx, rcx
0x180018a37  jz      short loc_180018A4E
0x180018a39  inc     rax
0x180018a3c  cmp     [rcx+rax*2], r11w
0x180018a41  jnz     short loc_180018A39
0x180018a43  lea     r10d, ds:2[rax*2]
0x180018a4b  test    rcx, rcx
0x180018a4e  cmovz   rcx, rbx
0x180018a52  mov     [rbp+47h+var_18], r10d
0x180018a56  lea     rax, [rbp+47h+var_60]
0x180018a5a  mov     [rbp+47h+var_20], rcx
0x180018a5e  mov     r9d, 5
0x180018a64  mov     [rsp+90h+var_70], rax
0x180018a69  lea     rdx, TraceMerge_NGEN_Configuration
0x180018a70  mov     [rbp+47h+var_14], r11d
0x180018a74  call    McGenEventWrite_EventWriteTransfer
0x180018a79  mov     rcx, [rbp+47h+var_10]
0x180018a7d  xor     rcx, rsp; StackCookie
0x180018a80  call    __security_check_cookie
0x180018a85  mov     rbx, [rsp+90h+arg_0]
0x180018a8d  add     rsp, 90h
0x180018a94  pop     rbp
0x180018a95  retn
```
