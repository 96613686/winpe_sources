# McTemplateU0zssq_EtwEventWriteTransfer

- ea: `0x180011a98`
- end: `0x180011b93`
- name: `McTemplateU0zssq_EtwEventWriteTransfer`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800114a0`

## callees

- `0x180001960`
- `0x180011a44`
- `0x180011a98`

## pseudocode

```c
__int64 __fastcall McTemplateU0zssq_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const char *a4,
        const char *a5,
        char a6)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // ecx
  __int64 v9; // rcx
  int v10; // ecx
  const char *v11; // rcx
  int v12; // eax
  _BYTE v14[16]; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-9h]
  int v16; // [rsp+48h] [rbp-1h]
  int v17; // [rsp+4Ch] [rbp+3h]
  const char *v18; // [rsp+50h] [rbp+7h]
  int v19; // [rsp+58h] [rbp+Fh]
  int v20; // [rsp+5Ch] [rbp+13h]
  const char *v21; // [rsp+60h] [rbp+17h]
  int v22; // [rsp+68h] [rbp+1Fh]
  int v23; // [rsp+6Ch] [rbp+23h]
  char *v24; // [rsp+70h] [rbp+27h]
  __int64 v25; // [rsp+78h] [rbp+2Fh]

  v6 = -1;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v16 = v8;
  v17 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v15 = a3;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = v9 + 1;
  }
  else
  {
    v10 = 5;
  }
  v19 = v10;
  v11 = a5;
  if ( !a4 )
    a4 = "NULL";
  v20 = 0;
  v18 = a4;
  if ( a5 )
  {
    do
      ++v6;
    while ( a5[v6] );
    v12 = v6 + 1;
  }
  else
  {
    v12 = 5;
  }
  v22 = v12;
  v23 = 0;
  if ( !a5 )
    v11 = "NULL";
  v24 = &a6;
  v21 = v11;
  v25 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(Microsoft_Windows_Store_Context, a2, 5, 5, (__int64)v14);
}

```

## disassembly

```asm
0x180011a98  push    rbp
0x180011a9a  lea     rbp, [rsp-47h]
0x180011a9f  sub     rsp, 90h
0x180011aa6  mov     rax, cs:__security_cookie
0x180011aad  xor     rax, rsp
0x180011ab0  mov     [rbp+47h+var_10], rax
0x180011ab4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011ab8  xor     r11d, r11d
0x180011abb  test    r8, r8
0x180011abe  jz      short loc_180011AD6
0x180011ac0  mov     rcx, rax
0x180011ac3  inc     rcx
0x180011ac6  cmp     [r8+rcx*2], r11w
0x180011acb  jnz     short loc_180011AC3
0x180011acd  lea     ecx, ds:2[rcx*2]
0x180011ad4  jmp     short loc_180011ADB
0x180011ad6  mov     ecx, 0Ah
0x180011adb  test    r8, r8
0x180011ade  mov     [rbp+47h+var_48], ecx
0x180011ae1  lea     r10, aNull_0; "NULL"
0x180011ae8  mov     [rbp+47h+var_44], r11d
0x180011aec  cmovz   r8, r10
0x180011af0  mov     [rbp+47h+var_50], r8
0x180011af4  mov     r8d, 5
0x180011afa  test    r9, r9
0x180011afd  jz      short loc_180011B0F
0x180011aff  mov     rcx, rax
0x180011b02  inc     rcx
0x180011b05  cmp     [r9+rcx], r11b
0x180011b09  jnz     short loc_180011B02
0x180011b0b  inc     ecx
0x180011b0d  jmp     short loc_180011B12
0x180011b0f  mov     ecx, r8d
0x180011b12  test    r9, r9
0x180011b15  mov     [rbp+47h+var_38], ecx
0x180011b18  mov     rcx, [rbp+47h+arg_20]
0x180011b1c  lea     r10, aNull; "NULL"
0x180011b23  cmovz   r9, r10
0x180011b27  mov     [rbp+47h+var_34], r11d
0x180011b2b  mov     [rbp+47h+var_40], r9
0x180011b2f  test    rcx, rcx
0x180011b32  jz      short loc_180011B41
0x180011b34  inc     rax
0x180011b37  cmp     [rcx+rax], r11b
0x180011b3b  jnz     short loc_180011B34
0x180011b3d  inc     eax
0x180011b3f  jmp     short loc_180011B44
0x180011b41  mov     eax, r8d
0x180011b44  test    rcx, rcx
0x180011b47  mov     [rbp+47h+var_28], eax
0x180011b4a  lea     rax, [rbp+47h+arg_28]
0x180011b4e  mov     [rbp+47h+var_24], r11d
0x180011b52  cmovz   rcx, r10
0x180011b56  mov     [rbp+47h+var_20], rax
0x180011b5a  mov     [rbp+47h+var_30], rcx
0x180011b5e  lea     rax, [rbp+47h+var_60]
0x180011b62  lea     rcx, Microsoft_Windows_Store_Context
0x180011b69  mov     [rbp+47h+var_18], 4
0x180011b71  mov     r9d, r8d
0x180011b74  mov     [rsp+90h+var_70], rax
0x180011b79  call    McGenEventWrite_EtwEventWriteTransfer
0x180011b7e  mov     rcx, [rbp+47h+var_10]
0x180011b82  xor     rcx, rsp; StackCookie
0x180011b85  call    __security_check_cookie
0x180011b8a  add     rsp, 90h
0x180011b91  pop     rbp
0x180011b92  retn
```
