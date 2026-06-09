# V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY__ *,V4ConnectionFiles * *)

- ea: `0x180048c38`
- end: `0x180048f84`
- name: `?CreateV4ConnectionFileStruct@V4ConnectionFiles@@SAJPEAUHKEY__@@PEAPEAU1@@Z`
- size: `844`
- prototype: `__int64 __fastcall(HKEY hkey, struct V4ConnectionFiles **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18004866c`

## callees

- `0x180033e78`
- `0x180046888`
- `0x180048bcc`
- `0x180048c38`
- `0x180049d00`
- `0x18004a2b8`
- `0x18004a71c`
- `0x18004a728`
- `0x180053c88`
- `0x180058614`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180048e42`
- `ADVAPI32!RegEnumValueW` at `0x180048e42`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180048d6f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180048d6f`

## pseudocode

```c
__int64 __fastcall V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY hkey, struct V4ConnectionFiles **a2)
{
  DWORD v2; // esi
  HKEY v4; // rdi
  V4ConnectionFiles *v6; // rax
  struct V4ConnectionFiles *v7; // rbx
  int v8; // r13d
  signed int ConnectionSpecificDirectory; // ebx
  HRESULT v10; // eax
  WCHAR *v11; // r14
  BYTE *v12; // r15
  LSTATUS v13; // eax
  size_t v14; // rax
  size_t v15; // rax
  LSTATUS v16; // eax
  unsigned int v17; // edx
  WCHAR *v18; // rcx
  int v19; // eax
  int v20; // r8d
  __int64 v21; // rbx
  __int64 v22; // rdi
  unsigned __int64 v23; // r13
  size_t v24; // rax
  wchar_t *v25; // rax
  HRESULT v26; // eax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-90h] BYREF
  size_t pcchLength; // [rsp+78h] [rbp-88h] BYREF
  HKEY v33; // [rsp+80h] [rbp-80h]
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF

  v2 = 0;
  v33 = hkey;
  v4 = hkey;
  if ( !a2 )
    return 2147942487LL;
  v6 = (V4ConnectionFiles *)operator new(0x68u, (const struct std::nothrow_t *)byte_180081401);
  v7 = v6;
  if ( v6 )
  {
    V4ConnectionFiles::ResetV4ConnectionFileStruct(v6, 0);
    *a2 = v7;
    memset_0(pszDest, 0, 0x208u);
    pcchLength = 0;
    v8 = 0;
    ConnectionSpecificDirectory = GetConnectionSpecificDirectory(v4, (BYTE *)pszDest, 0x104u);
    if ( ConnectionSpecificDirectory >= 0 )
    {
      ConnectionSpecificDirectory = StringCchCatW(pszDest, 0x104u, L"\\");
      if ( ConnectionSpecificDirectory >= 0 )
      {
        v10 = StringCchLengthW(pszDest, 0x104u, &pcchLength);
        v8 = pcchLength;
        ConnectionSpecificDirectory = v10;
      }
    }
    cValues = 0;
    v11 = 0;
    cbMaxValueNameLen = 0;
    v12 = 0;
    cbMaxValueLen = 0;
    if ( ConnectionSpecificDirectory >= 0 )
    {
      v13 = RegQueryInfoKeyW(v4, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
      if ( v13 )
      {
        ConnectionSpecificDirectory = v13 > 0 ? (unsigned __int16)v13 | 0x80070000 : v13;
      }
      else
      {
        v14 = 2LL * (cbMaxValueNameLen + 1);
        if ( !is_mul_ok(cbMaxValueNameLen + 1, 2u) )
          v14 = -1;
        v11 = (WCHAR *)operator new(v14, (const struct std::nothrow_t *)byte_180081401);
        v15 = 2 * ((unsigned __int64)cbMaxValueLen >> 1);
        if ( !is_mul_ok((unsigned __int64)cbMaxValueLen >> 1, 2u) )
          v15 = -1;
        v12 = (BYTE *)operator new(v15, (const struct std::nothrow_t *)byte_180081401);
        if ( !v12 || !v11 )
          ConnectionSpecificDirectory = -2147024882;
      }
      if ( ConnectionSpecificDirectory >= 0 )
      {
LABEL_20:
        while ( v2 < cValues )
        {
          cchValueName = cbMaxValueNameLen + 1;
          cbData = cbMaxValueLen;
          v16 = RegEnumValueW(v4, v2, v11, &cchValueName, 0, 0, v12, &cbData);
          if ( v16 )
          {
            if ( v16 > 0 )
              ConnectionSpecificDirectory = (unsigned __int16)v16 | 0x80070000;
            else
              ConnectionSpecificDirectory = v16;
          }
          else
          {
            *(_WORD *)&v12[2 * ((unsigned __int64)cbMaxValueLen >> 1) - 2] = 0;
            v11[cbMaxValueNameLen] = 0;
          }
          if ( ConnectionSpecificDirectory >= 0 )
          {
            v17 = 0;
            while ( 1 )
            {
              v18 = v11;
              do
              {
                v19 = *(WCHAR *)((char *)v18 + *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v17)
                                             - (_QWORD)v11);
                v20 = *v18 - v19;
                if ( v20 )
                  break;
                ++v18;
              }
              while ( v19 );
              if ( !v20 )
                break;
              if ( ++v17 >= 0xD )
              {
                ++v2;
                goto LABEL_20;
              }
            }
            v21 = (__int64)*a2;
            v22 = *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v17 + 1);
            v23 = (cbData >> 1) + v8;
            v24 = 2 * v23;
            if ( !is_mul_ok(v23, 2u) )
              v24 = -1;
            v25 = (wchar_t *)operator new(v24, (const struct std::nothrow_t *)byte_180081401);
            *(_QWORD *)(v22 + v21) = v25;
            if ( !v25 )
            {
              ConnectionSpecificDirectory = -2147024882;
              break;
            }
            v26 = StringCchPrintfW(v25, (unsigned int)v23, L"%ws%ws", pszDest, v12);
            v4 = v33;
            ConnectionSpecificDirectory = v26;
          }
          ++v2;
          if ( ConnectionSpecificDirectory < 0 )
            break;
          v8 = pcchLength;
        }
      }
    }
    operator delete(v12);
    operator delete(v11);
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
0x180048c38  mov     [rsp-8+arg_10], rbx
0x180048c3d  push    rbp
0x180048c3e  push    rsi
0x180048c3f  push    rdi
0x180048c40  push    r12
0x180048c42  push    r13
0x180048c44  push    r14
0x180048c46  push    r15
0x180048c48  lea     rbp, [rsp-1B0h]
0x180048c50  sub     rsp, 2B0h
0x180048c57  mov     rax, cs:__security_cookie
0x180048c5e  xor     rax, rsp
0x180048c61  mov     [rbp+1E0h+var_40], rax
0x180048c68  xor     esi, esi
0x180048c6a  mov     [rbp+1E0h+var_260], rcx
0x180048c6e  mov     r12, rdx
0x180048c71  mov     rdi, rcx
0x180048c74  test    rdx, rdx
0x180048c77  jnz     short loc_180048C83
0x180048c79  mov     eax, 80070057h
0x180048c7e  jmp     loc_180048F59
0x180048c83  lea     rdx, byte_180081401; struct std::nothrow_t *
0x180048c8a  mov     ecx, 68h ; 'h'; unsigned __int64
0x180048c8f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048c94  mov     rbx, rax
0x180048c97  test    rax, rax
0x180048c9a  jz      loc_180048F50
0x180048ca0  xor     edx, edx; bool
0x180048ca2  mov     rcx, rax; this
0x180048ca5  call    ?ResetV4ConnectionFileStruct@V4ConnectionFiles@@AEAAX_N@Z; V4ConnectionFiles::ResetV4ConnectionFileStruct(bool)
0x180048caa  xor     edx, edx; Val
0x180048cac  mov     [r12], rbx
0x180048cb0  mov     r8d, 208h; Size
0x180048cb6  lea     rcx, [rbp+1E0h+pszDest]; void *
0x180048cba  call    memset_0
0x180048cbf  mov     r14d, 104h
0x180048cc5  mov     [rsp+2E0h+pcchLength], rsi
0x180048cca  mov     r8d, r14d; cchDest
0x180048ccd  lea     rdx, [rbp+1E0h+pszDest]; pszDest
0x180048cd1  mov     rcx, rdi; hkey
0x180048cd4  mov     r13, rsi
0x180048cd7  call    ?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z; GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)
0x180048cdc  mov     ebx, eax
0x180048cde  test    eax, eax
0x180048ce0  js      short loc_180048D13
0x180048ce2  lea     r8, asc_180082C18; "\\"
0x180048ce9  mov     edx, r14d; cchDest
0x180048cec  lea     rcx, [rbp+1E0h+pszDest]; pszDest
0x180048cf0  call    StringCchCatW
0x180048cf5  mov     ebx, eax
0x180048cf7  test    eax, eax
0x180048cf9  js      short loc_180048D13
0x180048cfb  lea     r8, [rsp+2E0h+pcchLength]; pcchLength
0x180048d00  mov     edx, r14d; cchMax
0x180048d03  lea     rcx, [rbp+1E0h+pszDest]; psz
0x180048d07  call    StringCchLengthW
0x180048d0c  mov     r13, [rsp+2E0h+pcchLength]
0x180048d11  mov     ebx, eax
0x180048d13  mov     [rsp+2E0h+cValues], esi
0x180048d17  mov     r14, rsi
0x180048d1a  mov     [rsp+2E0h+cbMaxValueNameLen], esi
0x180048d1e  mov     r15, rsi
0x180048d21  mov     [rsp+2E0h+cbMaxValueLen], esi
0x180048d25  test    ebx, ebx
0x180048d27  js      loc_180048F3C
0x180048d2d  mov     [rsp+2E0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180048d32  lea     rax, [rsp+2E0h+cbMaxValueLen]
0x180048d37  mov     [rsp+2E0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180048d3c  xor     r9d, r9d; lpReserved
0x180048d3f  mov     [rsp+2E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180048d44  xor     r8d, r8d; lpcchClass
0x180048d47  lea     rax, [rsp+2E0h+cbMaxValueNameLen]
0x180048d4c  xor     edx, edx; lpClass
0x180048d4e  mov     [rsp+2E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180048d53  mov     rcx, rdi; hKey
0x180048d56  lea     rax, [rsp+2E0h+cValues]
0x180048d5b  mov     [rsp+2E0h+lpcValues], rax; lpcValues
0x180048d60  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180048d65  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180048d6a  mov     [rsp+2E0h+lpcSubKeys], rsi; lpcSubKeys
0x180048d6f  call    cs:__imp_RegQueryInfoKeyW
0x180048d76  nop     dword ptr [rax+rax+00h]
0x180048d7b  test    eax, eax
0x180048d7d  jnz     short loc_180048DE1
0x180048d7f  mov     ecx, [rsp+2E0h+cbMaxValueNameLen]
0x180048d83  lea     r15d, [rax+2]
0x180048d87  inc     ecx
0x180048d89  mov     eax, r15d
0x180048d8c  mul     rcx
0x180048d8f  lea     rcx, [r15-3]
0x180048d93  lea     rdx, byte_180081401; struct std::nothrow_t *
0x180048d9a  cmovb   rax, rcx
0x180048d9e  mov     rcx, rax; unsigned __int64
0x180048da1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048da6  mov     ecx, [rsp+2E0h+cbMaxValueLen]
0x180048daa  mov     r14, rax
0x180048dad  shr     rcx, 1
0x180048db0  mov     eax, r15d
0x180048db3  mul     rcx
0x180048db6  lea     rcx, [r15-3]
0x180048dba  lea     rdx, byte_180081401; struct std::nothrow_t *
0x180048dc1  cmovb   rax, rcx
0x180048dc5  mov     rcx, rax; unsigned __int64
0x180048dc8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048dcd  mov     r15, rax
0x180048dd0  test    rax, rax
0x180048dd3  jz      short loc_180048DDA
0x180048dd5  test    r14, r14
0x180048dd8  jnz     short loc_180048DF0
0x180048dda  mov     ebx, 8007000Eh
0x180048ddf  jmp     short loc_180048DF0
0x180048de1  jg      short loc_180048DE7
0x180048de3  mov     ebx, eax
0x180048de5  jmp     short loc_180048DF0
0x180048de7  movzx   ebx, ax
0x180048dea  or      ebx, 80070000h
0x180048df0  test    ebx, ebx
0x180048df2  js      loc_180048F3C
0x180048df8  cmp     esi, [rsp+2E0h+cValues]
0x180048dfc  jnb     loc_180048F3C
0x180048e02  mov     eax, [rsp+2E0h+cbMaxValueNameLen]
0x180048e06  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x180048e0b  inc     eax
0x180048e0d  mov     r8, r14; lpValueName
0x180048e10  mov     [rsp+2E0h+cchValueName], eax
0x180048e14  mov     edx, esi; dwIndex
0x180048e16  mov     eax, [rsp+2E0h+cbMaxValueLen]
0x180048e1a  mov     rcx, rdi; hKey
0x180048e1d  mov     [rsp+2E0h+cbData], eax
0x180048e21  lea     rax, [rsp+2E0h+cbData]
0x180048e26  mov     [rsp+2E0h+lpcValues], rax; lpcbData
0x180048e2b  mov     [rsp+2E0h+lpcbMaxClassLen], r15; lpData
0x180048e30  mov     [rsp+2E0h+lpcbMaxSubKeyLen], 0; lpType
0x180048e39  mov     [rsp+2E0h+lpcSubKeys], 0; lpReserved
0x180048e42  call    cs:__imp_RegEnumValueW
0x180048e49  nop     dword ptr [rax+rax+00h]
0x180048e4e  test    eax, eax
0x180048e50  jz      short loc_180048E63
0x180048e52  jg      short loc_180048E58
0x180048e54  mov     ebx, eax
0x180048e56  jmp     short loc_180048E7B
0x180048e58  movzx   ebx, ax
0x180048e5b  or      ebx, 80070000h
0x180048e61  jmp     short loc_180048E7B
0x180048e63  mov     ecx, [rsp+2E0h+cbMaxValueLen]
0x180048e67  shr     rcx, 1
0x180048e6a  xor     eax, eax
0x180048e6c  mov     [r15+rcx*2-2], ax
0x180048e72  mov     ecx, [rsp+2E0h+cbMaxValueNameLen]
0x180048e76  mov     [r14+rcx*2], ax
0x180048e7b  test    ebx, ebx
0x180048e7d  js      loc_180048F27
0x180048e83  xor     edx, edx
0x180048e85  lea     r10, ?s_connectionFiles@V4ConnectionFiles@@0QBUConnectionFileToRetrieve@1@B; V4ConnectionFiles::ConnectionFileToRetrieve const near * const V4ConnectionFiles::s_connectionFiles
0x180048e8c  mov     eax, edx
0x180048e8e  mov     rcx, r14
0x180048e91  add     rax, rax
0x180048e94  mov     r9, [r10+rax*8]
0x180048e98  sub     r9, r14
0x180048e9b  movzx   r8d, word ptr [rcx]
0x180048e9f  movzx   eax, word ptr [rcx+r9]
0x180048ea4  sub     r8d, eax
0x180048ea7  jnz     short loc_180048EB1
0x180048ea9  add     rcx, 2
0x180048ead  test    eax, eax
0x180048eaf  jnz     short loc_180048E9B
0x180048eb1  test    r8d, r8d
0x180048eb4  jz      short loc_180048EC4
0x180048eb6  inc     edx
0x180048eb8  cmp     edx, 0Dh
0x180048ebb  jb      short loc_180048E8C
0x180048ebd  inc     esi
0x180048ebf  jmp     loc_180048DF8
0x180048ec4  mov     rbx, [r12]
0x180048ec8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180048ecf  mov     eax, edx
0x180048ed1  add     rax, rax
0x180048ed4  mov     rdi, [r10+rax*8+8]
0x180048ed9  mov     eax, [rsp+2E0h+cbData]
0x180048edd  shr     eax, 1
0x180048edf  add     r13d, eax
0x180048ee2  mov     eax, 2
0x180048ee7  mul     r13
0x180048eea  lea     rdx, byte_180081401; struct std::nothrow_t *
0x180048ef1  cmovb   rax, rcx
0x180048ef5  mov     rcx, rax; unsigned __int64
0x180048ef8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048efd  mov     [rdi+rbx], rax
0x180048f01  test    rax, rax
0x180048f04  jz      short loc_180048F37
0x180048f06  lea     r9, [rbp+1E0h+pszDest]
0x180048f0a  mov     [rsp+2E0h+lpcSubKeys], r15
0x180048f0f  lea     r8, aWsWs; "%ws%ws"
0x180048f16  mov     edx, r13d; cchDest
0x180048f19  mov     rcx, rax; pszDest
0x180048f1c  call    StringCchPrintfW
0x180048f21  mov     rdi, [rbp+1E0h+var_260]
0x180048f25  mov     ebx, eax
0x180048f27  inc     esi
0x180048f29  test    ebx, ebx
0x180048f2b  js      short loc_180048F3C
0x180048f2d  mov     r13, [rsp+2E0h+pcchLength]
0x180048f32  jmp     loc_180048DF8
0x180048f37  mov     ebx, 8007000Eh
0x180048f3c  mov     rcx, r15; Block
0x180048f3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180048f44  mov     rcx, r14; Block
0x180048f47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180048f4c  mov     eax, ebx
0x180048f4e  jmp     short loc_180048F59
0x180048f50  mov     [r12], rsi
0x180048f54  mov     eax, 8007000Eh
0x180048f59  mov     rcx, [rbp+1E0h+var_40]
0x180048f60  xor     rcx, rsp; StackCookie
0x180048f63  call    __security_check_cookie
0x180048f68  mov     rbx, [rsp+2E0h+arg_10]
0x180048f70  add     rsp, 2B0h
0x180048f77  pop     r15
0x180048f79  pop     r14
0x180048f7b  pop     r13
0x180048f7d  pop     r12
0x180048f7f  pop     rdi
0x180048f80  pop     rsi
0x180048f81  pop     rbp
0x180048f82  retn
```
