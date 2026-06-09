# McTemplateU0zzzz_EventWriteTransfer

- ea: `0x18002a9e8`
- end: `0x18002ab17`
- name: `McTemplateU0zzzz_EventWriteTransfer`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180028664`

## callees

- `0x180001b90`
- `0x18002a904`
- `0x18002a9e8`

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
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v15,
           (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_Configuration,
           (__int64)a3,
           5u,
           &v18);
}

```

## disassembly

```asm
0x18002a9e8  mov     [rsp-8+arg_0], rbx
0x18002a9ed  push    rbp
0x18002a9ee  lea     rbp, [rsp-47h]
0x18002a9f3  sub     rsp, 90h
0x18002a9fa  mov     rax, cs:__security_cookie
0x18002aa01  xor     rax, rsp
0x18002aa04  mov     [rbp+47h+var_10], rax
0x18002aa08  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002aa0c  xor     r11d, r11d
0x18002aa0f  mov     r10d, 0Ah
0x18002aa15  test    r8, r8
0x18002aa18  jz      short loc_18002AA30
0x18002aa1a  mov     rcx, rax
0x18002aa1d  inc     rcx
0x18002aa20  cmp     [r8+rcx*2], r11w
0x18002aa25  jnz     short loc_18002AA1D
0x18002aa27  lea     ecx, ds:2[rcx*2]
0x18002aa2e  jmp     short loc_18002AA33
0x18002aa30  mov     ecx, r10d
0x18002aa33  test    r8, r8
0x18002aa36  mov     [rbp+47h+var_48], ecx
0x18002aa39  lea     rbx, aNull; "NULL"
0x18002aa40  mov     [rbp+47h+var_44], r11d
0x18002aa44  cmovz   r8, rbx
0x18002aa48  mov     [rbp+47h+var_50], r8
0x18002aa4c  test    r9, r9
0x18002aa4f  jz      short loc_18002AA67
0x18002aa51  mov     rcx, rax
0x18002aa54  inc     rcx
0x18002aa57  cmp     [r9+rcx*2], r11w
0x18002aa5c  jnz     short loc_18002AA54
0x18002aa5e  lea     ecx, ds:2[rcx*2]
0x18002aa65  jmp     short loc_18002AA6A
0x18002aa67  mov     ecx, r10d
0x18002aa6a  test    r9, r9
0x18002aa6d  mov     [rbp+47h+var_38], ecx
0x18002aa70  mov     rcx, [rbp+47h+arg_20]
0x18002aa74  cmovz   r9, rbx
0x18002aa78  mov     [rbp+47h+var_34], r11d
0x18002aa7c  mov     [rbp+47h+var_40], r9
0x18002aa80  test    rcx, rcx
0x18002aa83  jz      short loc_18002AA9B
0x18002aa85  mov     rdx, rax
0x18002aa88  inc     rdx
0x18002aa8b  cmp     [rcx+rdx*2], r11w
0x18002aa90  jnz     short loc_18002AA88
0x18002aa92  lea     edx, ds:2[rdx*2]
0x18002aa99  jmp     short loc_18002AA9E
0x18002aa9b  mov     edx, r10d
0x18002aa9e  test    rcx, rcx
0x18002aaa1  mov     [rbp+47h+var_28], edx
0x18002aaa4  mov     [rbp+47h+var_24], r11d
0x18002aaa8  cmovz   rcx, rbx
0x18002aaac  mov     [rbp+47h+var_30], rcx
0x18002aab0  mov     rcx, [rbp+47h+arg_28]
0x18002aab4  test    rcx, rcx
0x18002aab7  jz      short loc_18002AACE
0x18002aab9  inc     rax
0x18002aabc  cmp     [rcx+rax*2], r11w
0x18002aac1  jnz     short loc_18002AAB9
0x18002aac3  lea     r10d, ds:2[rax*2]
0x18002aacb  test    rcx, rcx
0x18002aace  cmovz   rcx, rbx
0x18002aad2  mov     [rbp+47h+var_18], r10d
0x18002aad6  lea     rax, [rbp+47h+var_60]
0x18002aada  mov     [rbp+47h+var_20], rcx
0x18002aade  mov     r9d, 5
0x18002aae4  mov     [rsp+90h+var_70], rax
0x18002aae9  lea     rdx, TraceMerge_NGEN_Configuration
0x18002aaf0  mov     [rbp+47h+var_14], r11d
0x18002aaf4  call    McGenEventWrite_EventWriteTransfer
0x18002aaf9  mov     rcx, [rbp+47h+var_10]
0x18002aafd  xor     rcx, rsp; StackCookie
0x18002ab00  call    __security_check_cookie
0x18002ab05  mov     rbx, [rsp+90h+arg_0]
0x18002ab0d  add     rsp, 90h
0x18002ab14  pop     rbp
0x18002ab15  retn
```
