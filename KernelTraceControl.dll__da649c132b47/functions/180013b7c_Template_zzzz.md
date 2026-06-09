# Template_zzzz

- ea: `0x180013b7c`
- end: `0x180013cac`
- name: `Template_zzzz`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800140dc`

## callees

- `0x180013b7c`
- `0x180026e30`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180013c89`
- `ADVAPI32!EventWrite` at `0x180013c89`

## pseudocode

```c
ULONG __fastcall Template_zzzz(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  __int64 v6; // rcx
  int v7; // edx
  __int64 v8; // rax
  ULONG v9; // r10d
  const wchar_t *v10; // r11
  const wchar_t *v11; // rax
  __int64 v12; // rax
  int v13; // r8d
  const wchar_t *v14; // rax
  __int64 v15; // rax
  int v16; // r9d
  const wchar_t *v17; // rax
  bool v18; // zf
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-60h] BYREF
  const wchar_t *v21; // [rsp+30h] [rbp-50h]
  int v22; // [rsp+38h] [rbp-48h]
  int v23; // [rsp+3Ch] [rbp-44h]
  const wchar_t *v24; // [rsp+40h] [rbp-40h]
  int v25; // [rsp+48h] [rbp-38h]
  int v26; // [rsp+4Ch] [rbp-34h]
  const wchar_t *v27; // [rsp+50h] [rbp-30h]
  int v28; // [rsp+58h] [rbp-28h]
  int v29; // [rsp+5Ch] [rbp-24h]

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
  UserData.Size = v9;
  v10 = L"NULL";
  UserData.Reserved = 0;
  v11 = L"NULL";
  if ( a3 )
    v11 = a3;
  UserData.Ptr = (ULONGLONG)v11;
  if ( a4 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v13 = 10;
  }
  v22 = v13;
  v14 = L"NULL";
  if ( a4 )
    v14 = a4;
  v23 = 0;
  v21 = v14;
  if ( a5 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a5[v15] );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v16 = 10;
  }
  v25 = v16;
  v17 = L"NULL";
  v26 = 0;
  if ( a5 )
    v17 = a5;
  v24 = v17;
  v18 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v7 = 2 * v6 + 2;
    v18 = a6 == 0;
  }
  if ( !v18 )
    v10 = a6;
  v28 = v7;
  v27 = v10;
  v29 = 0;
  return EventWrite(0, &TraceMerge_NGEN_Configuration, 4u, &UserData);
}

```

## disassembly

```asm
0x180013b7c  mov     [rsp-8+arg_0], rbx
0x180013b81  push    rbp
0x180013b82  mov     rbp, rsp
0x180013b85  sub     rsp, 80h
0x180013b8c  mov     rax, cs:__security_cookie
0x180013b93  xor     rax, rsp
0x180013b96  mov     [rbp+var_10], rax
0x180013b9a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013b9e  xor     ebx, ebx
0x180013ba0  mov     edx, 0Ah
0x180013ba5  test    r8, r8
0x180013ba8  jz      short loc_180013BC1
0x180013baa  mov     rax, rcx
0x180013bad  inc     rax
0x180013bb0  cmp     [r8+rax*2], bx
0x180013bb5  jnz     short loc_180013BAD
0x180013bb7  lea     r10d, ds:2[rax*2]
0x180013bbf  jmp     short loc_180013BC4
0x180013bc1  mov     r10d, edx
0x180013bc4  test    r8, r8
0x180013bc7  mov     [rbp+UserData.Size], r10d
0x180013bcb  lea     r11, aNull; "NULL"
0x180013bd2  mov     dword ptr [rbp+UserData.0Ch], ebx
0x180013bd5  mov     rax, r11
0x180013bd8  cmovnz  rax, r8
0x180013bdc  mov     [rbp+UserData.Ptr], rax
0x180013be0  test    r9, r9
0x180013be3  jz      short loc_180013BFC
0x180013be5  mov     rax, rcx
0x180013be8  inc     rax
0x180013beb  cmp     [r9+rax*2], bx
0x180013bf0  jnz     short loc_180013BE8
0x180013bf2  lea     r8d, ds:2[rax*2]
0x180013bfa  jmp     short loc_180013BFF
0x180013bfc  mov     r8d, edx
0x180013bff  test    r9, r9
0x180013c02  mov     [rbp+var_48], r8d
0x180013c06  mov     r8, [rbp+arg_20]
0x180013c0a  mov     rax, r11
0x180013c0d  cmovnz  rax, r9
0x180013c11  mov     [rbp+var_44], ebx
0x180013c14  mov     [rbp+var_50], rax
0x180013c18  test    r8, r8
0x180013c1b  jz      short loc_180013C34
0x180013c1d  mov     rax, rcx
0x180013c20  inc     rax
0x180013c23  cmp     [r8+rax*2], bx
0x180013c28  jnz     short loc_180013C20
0x180013c2a  lea     r9d, ds:2[rax*2]
0x180013c32  jmp     short loc_180013C37
0x180013c34  mov     r9d, edx
0x180013c37  test    r8, r8
0x180013c3a  mov     [rbp+var_38], r9d
0x180013c3e  mov     rax, r11
0x180013c41  mov     [rbp+var_34], ebx
0x180013c44  cmovnz  rax, r8
0x180013c48  mov     [rbp+var_40], rax
0x180013c4c  mov     rax, [rbp+arg_28]
0x180013c50  test    rax, rax
0x180013c53  jz      short loc_180013C68
0x180013c55  inc     rcx
0x180013c58  cmp     [rax+rcx*2], bx
0x180013c5c  jnz     short loc_180013C55
0x180013c5e  lea     edx, ds:2[rcx*2]
0x180013c65  test    rax, rax
0x180013c68  cmovnz  r11, rax
0x180013c6c  mov     [rbp+var_28], edx
0x180013c6f  lea     rdx, TraceMerge_NGEN_Configuration; EventDescriptor
0x180013c76  mov     [rbp+var_30], r11
0x180013c7a  xor     ecx, ecx; RegHandle
0x180013c7c  mov     [rbp+var_24], ebx
0x180013c7f  lea     r9, [rbp+UserData]; UserData
0x180013c83  mov     r8d, 4; UserDataCount
0x180013c89  call    cs:__imp_EventWrite
0x180013c8f  mov     rcx, [rbp+var_10]
0x180013c93  xor     rcx, rsp; StackCookie
0x180013c96  call    __security_check_cookie
0x180013c9b  mov     rbx, [rsp+80h+arg_0]
0x180013ca3  add     rsp, 80h
0x180013caa  pop     rbp
0x180013cab  retn
```
