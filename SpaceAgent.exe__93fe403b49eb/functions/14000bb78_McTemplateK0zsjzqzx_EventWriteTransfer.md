# McTemplateK0zsjzqzx_EventWriteTransfer

- ea: `0x14000bb78`
- end: `0x14000bca6`
- name: `McTemplateK0zsjzqzx_EventWriteTransfer`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a8dc`

## callees

- `0x14000356c`
- `0x14000bb78`
- `0x14001edc0`

## string_xrefs

- `0x14000bbc3`: `SuCreatePool`

## pseudocode

```c
ULONG __fastcall McTemplateK0zsjzqzx_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        const wchar_t *a7,
        char a8,
        const wchar_t *a9,
        char a10)
{
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  const wchar_t *v13; // rax
  __int64 v14; // rdx
  int v15; // edx
  const wchar_t *v16; // rax
  bool v17; // zf
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-69h] BYREF
  WCHAR *v20; // [rsp+40h] [rbp-59h]
  int v21; // [rsp+48h] [rbp-51h]
  int v22; // [rsp+4Ch] [rbp-4Dh]
  const char *v23; // [rsp+50h] [rbp-49h]
  __int64 v24; // [rsp+58h] [rbp-41h]
  __int64 v25; // [rsp+60h] [rbp-39h]
  __int64 v26; // [rsp+68h] [rbp-31h]
  const wchar_t *v27; // [rsp+70h] [rbp-29h]
  int v28; // [rsp+78h] [rbp-21h]
  int v29; // [rsp+7Ch] [rbp-1Dh]
  char *v30; // [rsp+80h] [rbp-19h]
  __int64 v31; // [rsp+88h] [rbp-11h]
  const wchar_t *v32; // [rsp+90h] [rbp-9h]
  int v33; // [rsp+98h] [rbp-1h]
  int v34; // [rsp+9Ch] [rbp+3h]
  char *v35; // [rsp+A0h] [rbp+7h]
  __int64 v36; // [rsp+A8h] [rbp+Fh]

  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *(&ModuleName + v11) );
  v20 = &ModuleName;
  v21 = 2 * v11 + 2;
  v12 = 10;
  v22 = 0;
  v23 = "SuCreatePool";
  v25 = a6;
  v13 = a7;
  v24 = 13;
  v26 = 16;
  if ( a7 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a7[v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v15 = 10;
  }
  v28 = v15;
  v29 = 0;
  if ( !a7 )
    v13 = L"NULL";
  v31 = 4;
  v27 = v13;
  v30 = &a8;
  v16 = a9;
  v17 = a9 == 0;
  if ( a9 )
  {
    do
      ++v10;
    while ( a9[v10] );
    v12 = (unsigned int)(2 * v10 + 2);
    v17 = a9 == 0;
  }
  if ( v17 )
    v16 = L"NULL";
  v33 = v12;
  v32 = v16;
  v34 = 0;
  v35 = &a10;
  v36 = 8;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)SpaceApiProvider_Context,
           (const EVENT_DESCRIPTOR *)CreatePoolSucceeded,
           v12,
           8u,
           &v19);
}

```

## disassembly

```asm
0x14000bb78  push    rbp
0x14000bb7a  lea     rbp, [rsp-27h]
0x14000bb7f  sub     rsp, 0C0h
0x14000bb86  mov     rax, cs:__security_cookie
0x14000bb8d  xor     rax, rsp
0x14000bb90  mov     [rbp+27h+var_10], rax
0x14000bb94  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000bb98  lea     rdx, ?ModuleName@@3PAGA; ushort near * ModuleName
0x14000bb9f  mov     rax, rcx
0x14000bba2  xor     r10d, r10d
0x14000bba5  inc     rax
0x14000bba8  cmp     [rdx+rax*2], r10w
0x14000bbad  jnz     short loc_14000BBA5
0x14000bbaf  lea     eax, ds:2[rax*2]
0x14000bbb6  mov     [rbp+27h+var_80], rdx
0x14000bbba  mov     [rbp+27h+var_78], eax
0x14000bbbd  mov     r8d, 0Ah
0x14000bbc3  lea     rax, aSucreatepool; "SuCreatePool"
0x14000bbca  mov     [rbp+27h+var_74], r10d
0x14000bbce  mov     [rbp+27h+var_70], rax
0x14000bbd2  mov     rax, [rbp+27h+arg_28]
0x14000bbd6  mov     [rbp+27h+var_60], rax
0x14000bbda  mov     rax, [rbp+27h+arg_30]
0x14000bbde  mov     [rbp+27h+var_68], 0Dh
0x14000bbe6  mov     [rbp+27h+var_58], 10h
0x14000bbee  test    rax, rax
0x14000bbf1  jz      short loc_14000BC09
0x14000bbf3  mov     rdx, rcx
0x14000bbf6  inc     rdx
0x14000bbf9  cmp     [rax+rdx*2], r10w
0x14000bbfe  jnz     short loc_14000BBF6
0x14000bc00  lea     edx, ds:2[rdx*2]
0x14000bc07  jmp     short loc_14000BC0C
0x14000bc09  mov     edx, r8d
0x14000bc0c  test    rax, rax
0x14000bc0f  mov     [rbp+27h+var_48], edx
0x14000bc12  lea     r9, aNull_0; "NULL"
0x14000bc19  mov     [rbp+27h+var_44], r10d
0x14000bc1d  cmovz   rax, r9
0x14000bc21  mov     [rbp+27h+var_38], 4
0x14000bc29  mov     [rbp+27h+var_50], rax
0x14000bc2d  lea     rax, [rbp+27h+arg_38]
0x14000bc31  mov     [rbp+27h+var_40], rax
0x14000bc35  mov     rax, [rbp+27h+arg_40]
0x14000bc39  test    rax, rax
0x14000bc3c  jz      short loc_14000BC53
0x14000bc3e  inc     rcx
0x14000bc41  cmp     [rax+rcx*2], r10w
0x14000bc46  jnz     short loc_14000BC3E
0x14000bc48  lea     r8d, ds:2[rcx*2]
0x14000bc50  test    rax, rax
0x14000bc53  cmovz   rax, r9
0x14000bc57  mov     [rbp+27h+var_28], r8d
0x14000bc5b  mov     [rbp+27h+var_30], rax
0x14000bc5f  lea     rdx, CreatePoolSucceeded
0x14000bc66  lea     rax, [rbp+27h+arg_48]
0x14000bc6a  mov     [rbp+27h+var_24], r10d
0x14000bc6e  mov     [rbp+27h+var_20], rax
0x14000bc72  lea     rcx, SpaceApiProvider_Context
0x14000bc79  lea     rax, [rbp+27h+var_90]
0x14000bc7d  mov     r9d, 8
0x14000bc83  mov     [rsp+0C0h+var_A0], rax
0x14000bc88  mov     [rbp+27h+var_18], r9
0x14000bc8c  call    McGenEventWrite_EventWriteTransfer
0x14000bc91  mov     rcx, [rbp+27h+var_10]
0x14000bc95  xor     rcx, rsp; StackCookie
0x14000bc98  call    __security_check_cookie
0x14000bc9d  add     rsp, 0C0h
0x14000bca4  pop     rbp
0x14000bca5  retn
```
