# V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY__ *,V4ConnectionFiles * *)

- ea: `0x180035c30`
- end: `0x180035fab`
- name: `?CreateV4ConnectionFileStruct@V4ConnectionFiles@@SAJPEAUHKEY__@@PEAPEAU1@@Z`
- size: `891`
- prototype: `__int64 __fastcall(HKEY hkey, struct V4ConnectionFiles **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180035ae0`

## callees

- `0x180001f20`
- `0x1800024d8`
- `0x180002938`
- `0x1800029ec`
- `0x180020acc`
- `0x180029488`
- `0x180035c30`
- `0x180036430`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180035e6d`
- `ADVAPI32!RegEnumValueW` at `0x180035e6d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180035da6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180035da6`

## pseudocode

```c
__int64 __fastcall V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY hkey, struct V4ConnectionFiles **a2)
{
  WCHAR *v2; // r14
  struct V4ConnectionFiles *v6; // rdx
  unsigned int i; // ecx
  __int64 v8; // rax
  __int64 v9; // r13
  signed int ConnectionSpecificDirectory; // ebx
  __int64 v11; // rdx
  wchar_t *v12; // rax
  BYTE *v13; // r15
  LSTATUS v14; // eax
  size_t v15; // rax
  unsigned __int64 v16; // rcx
  size_t v17; // rax
  DWORD v18; // esi
  LSTATUS v19; // eax
  unsigned int v20; // edx
  WCHAR *v21; // rcx
  int v22; // eax
  int v23; // r8d
  __int64 v24; // rbx
  __int64 v25; // rdi
  unsigned __int64 v26; // r13
  size_t v27; // rax
  wchar_t *v28; // rax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  HKEY hKey; // [rsp+80h] [rbp-80h]
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF

  v2 = 0;
  hKey = hkey;
  if ( !a2 )
    return 2147942487LL;
  v6 = (struct V4ConnectionFiles *)operator new(0x68u, (const struct std::nothrow_t *)byte_18006E400);
  if ( v6 )
  {
    for ( i = 0; i < 0xD; ++i )
    {
      v8 = (int)i;
      *(_QWORD *)((char *)v6 + *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v8 + 1)) = 0;
    }
    *a2 = v6;
    memset_0(pszDest, 0, 0x208u);
    v34 = 0;
    LODWORD(v9) = 0;
    ConnectionSpecificDirectory = GetConnectionSpecificDirectory(hkey, (BYTE *)pszDest, 0x104u);
    if ( ConnectionSpecificDirectory >= 0 )
    {
      ConnectionSpecificDirectory = StringCchCatW(pszDest, 0x104u, L"\\");
      if ( ConnectionSpecificDirectory >= 0 )
      {
        v11 = 260;
        v12 = pszDest;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        ConnectionSpecificDirectory = v11 == 0 ? 0x80070057 : 0;
        v9 = (260 - v11) & -(__int64)(v11 != 0);
        v34 = v9;
      }
    }
    cValues = 0;
    v13 = 0;
    cbMaxValueNameLen = 0;
    cbMaxValueLen = 0;
    if ( ConnectionSpecificDirectory >= 0 )
    {
      v14 = RegQueryInfoKeyW(hkey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
      if ( v14 )
      {
        if ( v14 > 0 )
          ConnectionSpecificDirectory = (unsigned __int16)v14 | 0x80070000;
        else
          ConnectionSpecificDirectory = v14;
      }
      else
      {
        v15 = 2LL * (cbMaxValueNameLen + 1);
        if ( !is_mul_ok(cbMaxValueNameLen + 1, 2u) )
          v15 = -1;
        v2 = (WCHAR *)operator new(v15, (const struct std::nothrow_t *)byte_18006E400);
        v16 = (unsigned __int64)cbMaxValueLen >> 1;
        v17 = 2 * v16;
        if ( !is_mul_ok(v16, 2u) )
          v17 = -1;
        v13 = (BYTE *)operator new(v17, (const struct std::nothrow_t *)byte_18006E400);
        if ( !v13 || !v2 )
          ConnectionSpecificDirectory = -2147024882;
      }
    }
    v18 = 0;
    if ( ConnectionSpecificDirectory >= 0 )
    {
LABEL_25:
      while ( v18 < cValues )
      {
        cchValueName = cbMaxValueNameLen + 1;
        cbData = cbMaxValueLen;
        v19 = RegEnumValueW(hKey, v18, v2, &cchValueName, 0, 0, v13, &cbData);
        if ( v19 )
        {
          if ( v19 > 0 )
            ConnectionSpecificDirectory = (unsigned __int16)v19 | 0x80070000;
          else
            ConnectionSpecificDirectory = v19;
        }
        else
        {
          *(_WORD *)&v13[2 * ((unsigned __int64)cbMaxValueLen >> 1) - 2] = 0;
          v2[cbMaxValueNameLen] = 0;
        }
        if ( ConnectionSpecificDirectory >= 0 )
        {
          v20 = 0;
          while ( 1 )
          {
            v21 = v2;
            do
            {
              v22 = *(WCHAR *)((char *)v21 + *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v20) - (_QWORD)v2);
              v23 = *v21 - v22;
              if ( v23 )
                break;
              ++v21;
            }
            while ( v22 );
            if ( !v23 )
              break;
            if ( ++v20 >= 0xD )
            {
              ++v18;
              goto LABEL_25;
            }
          }
          v24 = (__int64)*a2;
          v25 = *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v20 + 1);
          v26 = (cbData >> 1) + (unsigned int)v9;
          v27 = 2 * v26;
          if ( !is_mul_ok(v26, 2u) )
            v27 = -1;
          v28 = (wchar_t *)operator new(v27, (const struct std::nothrow_t *)byte_18006E400);
          *(_QWORD *)(v25 + v24) = v28;
          if ( !v28 )
          {
            ConnectionSpecificDirectory = -2147024882;
            break;
          }
          ConnectionSpecificDirectory = StringCchPrintfW(v28, (unsigned int)v26, L"%ws%ws", pszDest, v13);
        }
        ++v18;
        if ( ConnectionSpecificDirectory < 0 )
          break;
        LODWORD(v9) = v34;
      }
    }
    operator delete(v13);
    operator delete(v2);
    return (unsigned int)ConnectionSpecificDirectory;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180035c30  mov     [rsp-8+arg_10], rbx
0x180035c35  push    rbp
0x180035c36  push    rsi
0x180035c37  push    rdi
0x180035c38  push    r12
0x180035c3a  push    r13
0x180035c3c  push    r14
0x180035c3e  push    r15
0x180035c40  lea     rbp, [rsp-1B0h]
0x180035c48  sub     rsp, 2B0h
0x180035c4f  mov     rax, cs:__security_cookie
0x180035c56  xor     rax, rsp
0x180035c59  mov     [rbp+1E0h+var_40], rax
0x180035c60  xor     r14d, r14d
0x180035c63  mov     [rbp+1E0h+hKey], rcx
0x180035c67  mov     r12, rdx
0x180035c6a  mov     rsi, rcx
0x180035c6d  test    rdx, rdx
0x180035c70  jnz     short loc_180035C7C
0x180035c72  mov     eax, 80070057h
0x180035c77  jmp     loc_180035F80
0x180035c7c  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x180035c83  mov     ecx, 68h ; 'h'; unsigned __int64
0x180035c88  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035c8d  mov     rdx, rax
0x180035c90  test    rax, rax
0x180035c93  jz      loc_180035F77
0x180035c99  mov     ecx, r14d
0x180035c9c  lea     r8, ?s_connectionFiles@V4ConnectionFiles@@0QBUConnectionFileToRetrieve@1@B; V4ConnectionFiles::ConnectionFileToRetrieve const near * const V4ConnectionFiles::s_connectionFiles
0x180035ca3  movsxd  rax, ecx
0x180035ca6  inc     ecx
0x180035ca8  add     rax, rax
0x180035cab  mov     rax, [r8+rax*8+8]
0x180035cb0  mov     [rdx+rax], r14
0x180035cb4  cmp     ecx, 0Dh
0x180035cb7  jb      short loc_180035CA3
0x180035cb9  mov     [r12], rdx
0x180035cbd  lea     rcx, [rbp+1E0h+pszDest]; void *
0x180035cc1  xor     edx, edx; Val
0x180035cc3  mov     r8d, 208h; Size
0x180035cc9  call    memset_0
0x180035cce  mov     edi, 104h
0x180035cd3  mov     [rsp+2E0h+var_268], r14
0x180035cd8  mov     r8d, edi; cchDest
0x180035cdb  lea     rdx, [rbp+1E0h+pszDest]; pszDest
0x180035cdf  mov     rcx, rsi; hkey
0x180035ce2  mov     r13, r14
0x180035ce5  call    ?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z; GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)
0x180035cea  mov     ebx, eax
0x180035cec  test    eax, eax
0x180035cee  js      short loc_180035D4B
0x180035cf0  lea     r8, SubBlock; "\\"
0x180035cf7  mov     edx, edi; cchDest
0x180035cf9  lea     rcx, [rbp+1E0h+pszDest]; pszDest
0x180035cfd  call    StringCchCatW
0x180035d02  mov     ebx, eax
0x180035d04  test    eax, eax
0x180035d06  js      short loc_180035D4B
0x180035d08  mov     edx, edi
0x180035d0a  lea     rax, [rbp+1E0h+pszDest]
0x180035d0e  cmp     [rax], r14w
0x180035d12  jz      short loc_180035D1E
0x180035d14  add     rax, 2
0x180035d18  sub     rdx, 1
0x180035d1c  jnz     short loc_180035D0E
0x180035d1e  mov     rax, rdx
0x180035d21  neg     rax
0x180035d24  mov     rax, rdx
0x180035d27  sbb     ebx, ebx
0x180035d29  sub     rdi, rdx
0x180035d2c  not     ebx
0x180035d2e  and     ebx, 80070057h
0x180035d34  neg     rax
0x180035d37  sbb     rcx, rcx
0x180035d3a  and     rcx, rdi
0x180035d3d  neg     rdx
0x180035d40  sbb     r13, r13
0x180035d43  and     r13, rcx
0x180035d46  mov     [rsp+2E0h+var_268], r13
0x180035d4b  xor     edi, edi
0x180035d4d  mov     [rsp+2E0h+cValues], edi
0x180035d51  mov     r15d, edi
0x180035d54  mov     [rsp+2E0h+cbMaxValueNameLen], edi
0x180035d58  mov     [rsp+2E0h+cbMaxValueLen], edi
0x180035d5c  test    ebx, ebx
0x180035d5e  js      loc_180035E20
0x180035d64  mov     [rsp+2E0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180035d69  lea     rax, [rsp+2E0h+cbMaxValueLen]
0x180035d6e  mov     [rsp+2E0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180035d73  xor     r9d, r9d; lpReserved
0x180035d76  mov     [rsp+2E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180035d7b  xor     r8d, r8d; lpcchClass
0x180035d7e  lea     rax, [rsp+2E0h+cbMaxValueNameLen]
0x180035d83  xor     edx, edx; lpClass
0x180035d85  mov     [rsp+2E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180035d8a  mov     rcx, rsi; hKey
0x180035d8d  lea     rax, [rsp+2E0h+cValues]
0x180035d92  mov     [rsp+2E0h+lpcValues], rax; lpcValues
0x180035d97  mov     [rsp+2E0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180035d9c  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180035da1  mov     [rsp+2E0h+lpcSubKeys], rdi; lpcSubKeys
0x180035da6  call    cs:__imp_RegQueryInfoKeyW
0x180035dad  nop     dword ptr [rax+rax+00h]
0x180035db2  test    eax, eax
0x180035db4  jnz     short loc_180035E11
0x180035db6  mov     ecx, [rsp+2E0h+cbMaxValueNameLen]
0x180035dba  lea     esi, [rdi+2]
0x180035dbd  inc     ecx
0x180035dbf  lea     r15, [rdi-1]
0x180035dc3  mov     eax, esi
0x180035dc5  mul     rcx
0x180035dc8  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x180035dcf  cmovb   rax, r15
0x180035dd3  mov     rcx, rax; unsigned __int64
0x180035dd6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035ddb  mov     ecx, [rsp+2E0h+cbMaxValueLen]
0x180035ddf  mov     r14, rax
0x180035de2  shr     rcx, 1
0x180035de5  mov     eax, esi
0x180035de7  mul     rcx
0x180035dea  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x180035df1  cmovb   rax, r15
0x180035df5  mov     rcx, rax; unsigned __int64
0x180035df8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035dfd  mov     r15, rax
0x180035e00  test    rax, rax
0x180035e03  jz      short loc_180035E0A
0x180035e05  test    r14, r14
0x180035e08  jnz     short loc_180035E20
0x180035e0a  mov     ebx, 8007000Eh
0x180035e0f  jmp     short loc_180035E20
0x180035e11  jg      short loc_180035E17
0x180035e13  mov     ebx, eax
0x180035e15  jmp     short loc_180035E20
0x180035e17  movzx   ebx, ax
0x180035e1a  or      ebx, 80070000h
0x180035e20  mov     esi, edi
0x180035e22  test    ebx, ebx
0x180035e24  js      loc_180035F63
0x180035e2a  cmp     esi, [rsp+2E0h+cValues]
0x180035e2e  jnb     loc_180035F63
0x180035e34  mov     eax, [rsp+2E0h+cbMaxValueNameLen]
0x180035e38  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x180035e3d  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180035e41  inc     eax
0x180035e43  mov     [rsp+2E0h+cchValueName], eax
0x180035e47  mov     r8, r14; lpValueName
0x180035e4a  mov     eax, [rsp+2E0h+cbMaxValueLen]
0x180035e4e  mov     edx, esi; dwIndex
0x180035e50  mov     [rsp+2E0h+cbData], eax
0x180035e54  lea     rax, [rsp+2E0h+cbData]
0x180035e59  mov     [rsp+2E0h+lpcValues], rax; lpcbData
0x180035e5e  mov     [rsp+2E0h+lpcbMaxClassLen], r15; lpData
0x180035e63  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rdi; lpType
0x180035e68  mov     [rsp+2E0h+lpcSubKeys], rdi; lpReserved
0x180035e6d  call    cs:__imp_RegEnumValueW
0x180035e74  nop     dword ptr [rax+rax+00h]
0x180035e79  test    eax, eax
0x180035e7b  jz      short loc_180035E8E
0x180035e7d  jg      short loc_180035E83
0x180035e7f  mov     ebx, eax
0x180035e81  jmp     short loc_180035EA4
0x180035e83  movzx   ebx, ax
0x180035e86  or      ebx, 80070000h
0x180035e8c  jmp     short loc_180035EA4
0x180035e8e  mov     ecx, [rsp+2E0h+cbMaxValueLen]
0x180035e92  shr     rcx, 1
0x180035e95  mov     [r15+rcx*2-2], di
0x180035e9b  mov     ecx, [rsp+2E0h+cbMaxValueNameLen]
0x180035e9f  mov     [r14+rcx*2], di
0x180035ea4  test    ebx, ebx
0x180035ea6  js      loc_180035F4E
0x180035eac  mov     edx, edi
0x180035eae  lea     r10, ?s_connectionFiles@V4ConnectionFiles@@0QBUConnectionFileToRetrieve@1@B; V4ConnectionFiles::ConnectionFileToRetrieve const near * const V4ConnectionFiles::s_connectionFiles
0x180035eb5  mov     eax, edx
0x180035eb7  mov     rcx, r14
0x180035eba  add     rax, rax
0x180035ebd  mov     r9, [r10+rax*8]
0x180035ec1  sub     r9, r14
0x180035ec4  movzx   r8d, word ptr [rcx]
0x180035ec8  movzx   eax, word ptr [rcx+r9]
0x180035ecd  sub     r8d, eax
0x180035ed0  jnz     short loc_180035EDA
0x180035ed2  add     rcx, 2
0x180035ed6  test    eax, eax
0x180035ed8  jnz     short loc_180035EC4
0x180035eda  test    r8d, r8d
0x180035edd  jz      short loc_180035EED
0x180035edf  inc     edx
0x180035ee1  cmp     edx, 0Dh
0x180035ee4  jb      short loc_180035EB5
0x180035ee6  inc     esi
0x180035ee8  jmp     loc_180035E2A
0x180035eed  mov     rbx, [r12]
0x180035ef1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180035ef8  mov     eax, edx
0x180035efa  add     rax, rax
0x180035efd  mov     rdi, [r10+rax*8+8]
0x180035f02  mov     eax, [rsp+2E0h+cbData]
0x180035f06  shr     eax, 1
0x180035f08  add     r13d, eax
0x180035f0b  mov     eax, 2
0x180035f10  mul     r13
0x180035f13  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x180035f1a  cmovb   rax, rcx
0x180035f1e  mov     rcx, rax; unsigned __int64
0x180035f21  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035f26  mov     [rdi+rbx], rax
0x180035f2a  xor     edi, edi
0x180035f2c  test    rax, rax
0x180035f2f  jz      short loc_180035F5E
0x180035f31  lea     r9, [rbp+1E0h+pszDest]
0x180035f35  mov     [rsp+2E0h+lpcSubKeys], r15
0x180035f3a  lea     r8, aWsWs; "%ws%ws"
0x180035f41  mov     edx, r13d; cchDest
0x180035f44  mov     rcx, rax; pszDest
0x180035f47  call    StringCchPrintfW
0x180035f4c  mov     ebx, eax
0x180035f4e  inc     esi
0x180035f50  test    ebx, ebx
0x180035f52  js      short loc_180035F63
0x180035f54  mov     r13, [rsp+2E0h+var_268]
0x180035f59  jmp     loc_180035E2A
0x180035f5e  mov     ebx, 8007000Eh
0x180035f63  mov     rcx, r15; Block
0x180035f66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035f6b  mov     rcx, r14; Block
0x180035f6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035f73  mov     eax, ebx
0x180035f75  jmp     short loc_180035F80
0x180035f77  mov     [r12], r14
0x180035f7b  mov     eax, 8007000Eh
0x180035f80  mov     rcx, [rbp+1E0h+var_40]
0x180035f87  xor     rcx, rsp; StackCookie
0x180035f8a  call    __security_check_cookie
0x180035f8f  mov     rbx, [rsp+2E0h+arg_10]
0x180035f97  add     rsp, 2B0h
0x180035f9e  pop     r15
0x180035fa0  pop     r14
0x180035fa2  pop     r13
0x180035fa4  pop     r12
0x180035fa6  pop     rdi
0x180035fa7  pop     rsi
0x180035fa8  pop     rbp
0x180035fa9  retn
```
