# CallerIdentity::GetPackageFullNameFromAppId(ushort const *,ushort * *)

- ea: `0x180024c40`
- end: `0x180024eef`
- name: `?GetPackageFullNameFromAppId@CallerIdentity@@YAJPEBGPEAPEAG@Z`
- size: `687`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800243a4`
- `0x180024ad0`

## callees

- `0x180024c40`
- `0x180043c30`
- `0x1800446fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180024ce0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180024ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024d29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024d29`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180024e04`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180024e04`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageFullNameFromAppId(
        wchar_t *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v3; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  wchar_t *v8; // rax
  wchar_t *v9; // rcx
  wchar_t *v10; // rax
  unsigned int v11; // ebx
  _WORD *v13; // rax
  _WORD *v14; // rdx
  WCHAR *v15; // r8
  wchar_t *v16; // rax
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  LONG PackagesByPackageFamily; // eax
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rdi
  WCHAR *v22; // rcx
  unsigned __int64 v23; // r8
  __int64 v24; // r10
  _WORD *v25; // rcx
  __int64 v26; // r9
  __int64 v27; // rdi
  bool v28; // cf
  UINT32 count; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 bufferLength; // [rsp+44h] [rbp-BCh] BYREF
  PWSTR packageFullNames; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Str[136]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR buffer[128]; // [rsp+200h] [rbp+100h] BYREF

  bufferLength = 128;
  v3 = 2147483646;
  *(_QWORD *)a2 = 0;
  packageFullNames = 0;
  count = 1;
  v6 = 130;
  packageFamilyName[0] = 0;
  v7 = 2147483646;
  v8 = Str;
  do
  {
    if ( !v7 )
      break;
    if ( !*this )
      break;
    *v8++ = *this++;
    --v7;
    --v6;
  }
  while ( v6 );
  v9 = v8 - 1;
  if ( v6 )
    v9 = v8;
  *v9 = 0;
  if ( v6 && (v10 = wcsrchr(Str, 0x21u), Str[0] != 33) && v10 && v10[1] )
  {
    *v10 = 0;
    v15 = packageFamilyName;
    v16 = Str;
    v17 = 65;
    do
    {
      if ( !v3 )
        break;
      if ( !*v16 )
        break;
      *v15++ = *v16++;
      --v3;
      --v17;
    }
    while ( v17 );
    v18 = v15 - 1;
    v11 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v18 = v15;
    *v18 = 0;
    if ( v17 )
    {
      PackagesByPackageFamily = FindPackagesByPackageFamily(
                                  packageFamilyName,
                                  0x10u,
                                  &count,
                                  &packageFullNames,
                                  &bufferLength,
                                  buffer,
                                  0);
      v11 = PackagesByPackageFamily;
      if ( PackagesByPackageFamily > 0 )
        v11 = (unsigned __int16)PackagesByPackageFamily | 0x80070000;
      if ( (v11 & 0x80000000) == 0 )
      {
        if ( count != 1 )
          return (unsigned int)-2147221165;
        v20 = -1;
        do
          ++v20;
        while ( buffer[v20] );
        v21 = v20 + 1;
        *(_QWORD *)a2 = 0;
        if ( v20 + 1 < v20 || !is_mul_ok(v21, 2u) )
          return (unsigned int)-2147024362;
        v13 = CoTaskMemAlloc(2 * v21);
        *(_QWORD *)a2 = v13;
        v14 = v13;
        v11 = v13 == 0 ? 0x8007000E : 0;
        if ( !v13 )
          return v11;
        if ( v21 > 0x7FFFFFFF )
        {
LABEL_17:
          *v13 = 0;
          return v11;
        }
        if ( v20 >= 0x7FFFFFFF )
        {
          if ( v20 == -1 )
            return v11;
          goto LABEL_17;
        }
        v22 = buffer;
        v23 = v20 + 1;
        v24 = 0;
        do
        {
          if ( !v20 )
            break;
          if ( !*v22 )
            break;
          *v13++ = *v22++;
          --v20;
          ++v24;
          --v23;
        }
        while ( v23 );
        v25 = v13 - 1;
        v26 = v24 - 1;
        if ( v23 )
        {
          v25 = v13;
          v26 = v24;
        }
        *v25 = 0;
        if ( v23 )
        {
          v28 = v21 == v26;
          v27 = v21 - v26;
          if ( !v28 && v27 != 1 && (unsigned __int64)(2 * v27) > 2 )
            memset_0(&v14[v26 + 1], 0, 2 * v27 - 2);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x180024c40  push    rbp
0x180024c42  push    rbx
0x180024c43  push    rsi
0x180024c44  push    rdi
0x180024c45  push    r14
0x180024c47  push    r15
0x180024c49  lea     rbp, [rsp-218h]
0x180024c51  sub     rsp, 318h
0x180024c58  mov     rax, cs:__security_cookie
0x180024c5f  xor     rax, rsp
0x180024c62  mov     [rbp+240h+var_40], rax
0x180024c69  xor     r15d, r15d
0x180024c6c  mov     [rsp+340h+var_2FC], 80h
0x180024c74  mov     ebx, 7FFFFFFEh
0x180024c79  mov     [rdx], r15
0x180024c7c  mov     r14, rdx
0x180024c7f  mov     [rsp+340h+packageFullNames], r15
0x180024c84  mov     r8, rcx
0x180024c87  mov     [rsp+340h+count], 1
0x180024c8f  mov     edx, 82h
0x180024c94  mov     [rsp+340h+packageFamilyName], r15w
0x180024c9a  mov     ecx, ebx
0x180024c9c  lea     rax, [rbp+240h+Str]
0x180024ca0  test    rcx, rcx
0x180024ca3  jz      short loc_180024CC4
0x180024ca5  movzx   r9d, word ptr [r8]
0x180024ca9  test    r9w, r9w
0x180024cad  jz      short loc_180024CC4
0x180024caf  mov     [rax], r9w
0x180024cb3  add     r8, 2
0x180024cb7  add     rax, 2
0x180024cbb  dec     rcx
0x180024cbe  sub     rdx, 1
0x180024cc2  jnz     short loc_180024CA0
0x180024cc4  test    rdx, rdx
0x180024cc7  lea     rcx, [rax-2]
0x180024ccb  cmovnz  rcx, rax
0x180024ccf  mov     [rcx], r15w
0x180024cd3  jz      short loc_180024CEC
0x180024cd5  mov     edi, 21h ; '!'
0x180024cda  lea     rcx, [rbp+240h+Str]; Str
0x180024cde  mov     edx, edi; Ch
0x180024ce0  call    cs:__imp_wcsrchr
0x180024ce6  cmp     di, [rbp+240h+Str]
0x180024cea  jnz     short loc_180024D68
0x180024cec  mov     ebx, 80070057h
0x180024cf1  jmp     short loc_180024D05
0x180024cf3  mov     eax, 2
0x180024cf8  mul     rdi
0x180024cfb  test    rdx, rdx
0x180024cfe  jz      short loc_180024D26
0x180024d00  mov     ebx, 80070216h
0x180024d05  mov     eax, ebx
0x180024d07  mov     rcx, [rbp+240h+var_40]
0x180024d0e  xor     rcx, rsp; StackCookie
0x180024d11  call    __security_check_cookie
0x180024d16  add     rsp, 318h
0x180024d1d  pop     r15
0x180024d1f  pop     r14
0x180024d21  pop     rdi
0x180024d22  pop     rsi
0x180024d23  pop     rbx
0x180024d24  pop     rbp
0x180024d25  retn
0x180024d26  mov     rcx, rax; cb
0x180024d29  call    cs:__imp_CoTaskMemAlloc
0x180024d2f  mov     rcx, rax
0x180024d32  mov     [r14], rax
0x180024d35  neg     rcx
0x180024d38  mov     rdx, rax
0x180024d3b  sbb     ebx, ebx
0x180024d3d  not     ebx
0x180024d3f  and     ebx, 8007000Eh
0x180024d45  test    rax, rax
0x180024d48  jz      short loc_180024D05
0x180024d4a  mov     eax, 7FFFFFFFh
0x180024d4f  cmp     rdi, rax
0x180024d52  ja      short loc_180024D62
0x180024d54  cmp     rsi, rax
0x180024d57  jb      loc_180024E56
0x180024d5d  test    rdi, rdi
0x180024d60  jz      short loc_180024D05
0x180024d62  mov     [rdx], r15w
0x180024d66  jmp     short loc_180024D05
0x180024d68  test    rax, rax
0x180024d6b  jz      loc_180024CEC
0x180024d71  cmp     r15w, [rax+2]
0x180024d76  jz      loc_180024CEC
0x180024d7c  mov     [rax], r15w
0x180024d80  lea     r8, [rsp+340h+packageFamilyName]
0x180024d85  lea     rax, [rbp+240h+Str]
0x180024d89  mov     edx, 41h ; 'A'
0x180024d8e  test    rbx, rbx
0x180024d91  jz      short loc_180024DB0
0x180024d93  movzx   ecx, word ptr [rax]
0x180024d96  test    cx, cx
0x180024d99  jz      short loc_180024DB0
0x180024d9b  mov     [r8], cx
0x180024d9f  add     rax, 2
0x180024da3  add     r8, 2
0x180024da7  dec     rbx
0x180024daa  sub     rdx, 1
0x180024dae  jnz     short loc_180024D8E
0x180024db0  mov     rax, rdx
0x180024db3  lea     rcx, [r8-2]
0x180024db7  neg     rax
0x180024dba  sbb     ebx, ebx
0x180024dbc  not     ebx
0x180024dbe  and     ebx, 8007007Ah
0x180024dc4  test    rdx, rdx
0x180024dc7  cmovnz  rcx, r8
0x180024dcb  mov     [rcx], r15w
0x180024dcf  jz      loc_180024D05
0x180024dd5  lea     rax, [rbp+240h+var_140]
0x180024ddc  mov     [rsp+340h+packageProperties], r15; packageProperties
0x180024de1  mov     [rsp+340h+buffer], rax; buffer
0x180024de6  lea     r9, [rsp+340h+packageFullNames]; packageFullNames
0x180024deb  lea     rax, [rsp+340h+var_2FC]
0x180024df0  mov     edx, 10h; packageFilters
0x180024df5  lea     r8, [rsp+340h+count]; count
0x180024dfa  mov     [rsp+340h+bufferLength], rax; bufferLength
0x180024dff  lea     rcx, [rsp+340h+packageFamilyName]; packageFamilyName
0x180024e04  call    cs:__imp_FindPackagesByPackageFamily
0x180024e0a  mov     ebx, eax
0x180024e0c  test    eax, eax
0x180024e0e  jle     short loc_180024E19
0x180024e10  movzx   ebx, ax
0x180024e13  or      ebx, 80070000h
0x180024e19  test    ebx, ebx
0x180024e1b  js      loc_180024D05
0x180024e21  cmp     [rsp+340h+count], 1
0x180024e26  jnz     loc_180024EE5
0x180024e2c  lea     rax, [rbp+240h+var_140]
0x180024e33  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180024e37  inc     rsi
0x180024e3a  cmp     [rax+rsi*2], r15w
0x180024e3f  jnz     short loc_180024E37
0x180024e41  lea     rdi, [rsi+1]
0x180024e45  mov     [r14], r15
0x180024e48  cmp     rdi, rsi
0x180024e4b  jb      loc_180024D00
0x180024e51  jmp     loc_180024CF3
0x180024e56  test    rdi, rdi
0x180024e59  jz      loc_180024D05
0x180024e5f  lea     rcx, [rbp+240h+var_140]
0x180024e66  mov     r8, rdi
0x180024e69  mov     rax, rdx
0x180024e6c  mov     r10, r15
0x180024e6f  test    rsi, rsi
0x180024e72  jz      short loc_180024E96
0x180024e74  movzx   r9d, word ptr [rcx]
0x180024e78  test    r9w, r9w
0x180024e7c  jz      short loc_180024E96
0x180024e7e  mov     [rax], r9w
0x180024e82  add     rcx, 2
0x180024e86  add     rax, 2
0x180024e8a  dec     rsi
0x180024e8d  inc     r10
0x180024e90  sub     r8, 1
0x180024e94  jnz     short loc_180024E6F
0x180024e96  test    r8, r8
0x180024e99  lea     rcx, [rax-2]
0x180024e9d  lea     r9, [r10-1]
0x180024ea1  cmovnz  rcx, rax
0x180024ea5  cmovnz  r9, r10
0x180024ea9  mov     [rcx], r15w
0x180024ead  jz      loc_180024D05
0x180024eb3  sub     rdi, r9
0x180024eb6  cmp     rdi, 1
0x180024eba  jbe     loc_180024D05
0x180024ec0  lea     r8, [rdi+rdi]
0x180024ec4  cmp     r8, 2
0x180024ec8  jbe     loc_180024D05
0x180024ece  inc     r9
0x180024ed1  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180024ed5  lea     rcx, [rdx+r9*2]; void *
0x180024ed9  xor     edx, edx; Val
0x180024edb  call    memset_0
0x180024ee0  jmp     loc_180024D05
0x180024ee5  mov     ebx, 80040153h
0x180024eea  jmp     loc_180024D05
```
