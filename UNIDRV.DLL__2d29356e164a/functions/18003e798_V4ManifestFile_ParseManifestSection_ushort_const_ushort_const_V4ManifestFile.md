# V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)

- ea: `0x18003e798`
- end: `0x18003e96f`
- name: `?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z`
- size: `471`
- prototype: `__int64 __fastcall(LPCWSTR lpAppName, LPCWSTR lpFileName, struct V4ManifestFile *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180054090`

## callees

- `0x180024718`
- `0x18003e798`
- `0x18004470c`
- `0x180048d98`
- `0x180049128`
- `0x1800491c4`
- `0x1800491e8`

## import_xrefs

- `KERNEL32!GetPrivateProfileSectionW` at `0x18003e7e7`
- `KERNEL32!GetPrivateProfileSectionW` at `0x18003e7e7`

## pseudocode

```c
__int64 __fastcall V4ManifestFile::ParseManifestSection(
        LPCWSTR lpAppName,
        LPCWSTR lpFileName,
        struct V4ManifestFile *a3)
{
  WCHAR *v6; // rax
  WCHAR *v7; // rbx
  HRESULT v8; // edi
  DWORD PrivateProfileSectionW; // eax
  wchar_t *v11; // rbp
  __int64 v12; // r14
  unsigned __int16 *v13; // rax
  const wchar_t *v14; // r15
  wchar_t *v15; // rax
  unsigned int i; // esi
  __int64 v17; // r12
  __int64 v18; // rax
  size_t v19; // rdi
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // kr00_8
  wchar_t *v22; // rax
  wchar_t *Context; // [rsp+88h] [rbp+20h] BYREF

  v6 = (WCHAR *)operator new(0x2000u, (const struct std::nothrow_t *)byte_18007F401);
  v7 = v6;
  if ( v6 )
  {
    PrivateProfileSectionW = GetPrivateProfileSectionW(lpAppName, v6, 0x1000u, lpFileName);
    if ( !PrivateProfileSectionW )
    {
      operator delete(v7);
      return 0;
    }
    if ( PrivateProfileSectionW == 4094 )
    {
      v8 = -2147024774;
    }
    else
    {
      v11 = v7;
      v8 = 0;
      do
      {
        if ( !*v11 )
          break;
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
        Context = 0;
        v13 = o_wcstok_s_0(v11, L"=", &Context);
        if ( v13 )
        {
          if ( Context )
          {
            v14 = StripWhiteSpaceAndQuotes(v13);
            v15 = StripWhiteSpaceAndQuotes(Context);
            Context = v15;
            if ( *v14 )
            {
              if ( *v15 )
              {
                for ( i = 0; i < 0x14; ++i )
                {
                  v17 = *((_QWORD *)&V4ManifestFile::s_manifestFields + 3 * (int)i + 2);
                  if ( !*(_QWORD *)((char *)a3 + v17)
                    && !wcsicmp(v14, *((const wchar_t **)&V4ManifestFile::s_manifestFields + 3 * (int)i + 1)) )
                  {
                    v18 = -1;
                    do
                      ++v18;
                    while ( Context[v18] );
                    v19 = v18 + 1;
                    v21 = v18 + 1;
                    v20 = 2 * (v18 + 1);
                    if ( !is_mul_ok(v21, 2u) )
                      v20 = -1;
                    v22 = (wchar_t *)operator new(v20, (const struct std::nothrow_t *)byte_18007F401);
                    *(_QWORD *)((char *)a3 + v17) = v22;
                    if ( v22 )
                      v8 = StringCchCopyW(v22, v19, Context);
                    else
                      v8 = -2147024882;
                    break;
                  }
                }
              }
            }
          }
        }
        v11 += v12 + 1;
      }
      while ( v8 >= 0 );
    }
  }
  else
  {
    v8 = -2147024882;
  }
  operator delete(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003e798  push    rbx
0x18003e79a  push    rbp
0x18003e79b  push    rsi
0x18003e79c  push    rdi
0x18003e79d  push    r12
0x18003e79f  push    r13
0x18003e7a1  push    r14
0x18003e7a3  push    r15
0x18003e7a5  sub     rsp, 28h
0x18003e7a9  mov     rdi, rdx
0x18003e7ac  mov     rsi, rcx
0x18003e7af  lea     rdx, byte_18007F401; struct std::nothrow_t *
0x18003e7b6  mov     ecx, 2000h; unsigned __int64
0x18003e7bb  mov     r13, r8
0x18003e7be  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e7c3  xor     r12d, r12d
0x18003e7c6  mov     rbx, rax
0x18003e7c9  test    rax, rax
0x18003e7cc  jnz     short loc_18003E7D8
0x18003e7ce  mov     edi, 8007000Eh
0x18003e7d3  jmp     loc_18003E954
0x18003e7d8  mov     r9, rdi; lpFileName
0x18003e7db  mov     r8d, 1000h; nSize
0x18003e7e1  mov     rdx, rbx; lpReturnedString
0x18003e7e4  mov     rcx, rsi; lpAppName
0x18003e7e7  call    cs:__imp_GetPrivateProfileSectionW
0x18003e7ed  test    eax, eax
0x18003e7ef  jnz     short loc_18003E800
0x18003e7f1  mov     rcx, rbx; Block
0x18003e7f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e7f9  xor     eax, eax
0x18003e7fb  jmp     loc_18003E95E
0x18003e800  cmp     eax, 0FFEh
0x18003e805  jnz     short loc_18003E811
0x18003e807  mov     edi, 8007007Ah
0x18003e80c  jmp     loc_18003E954
0x18003e811  mov     rbp, rbx
0x18003e814  mov     edi, r12d
0x18003e817  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003e81b  cmp     [rbp+0], r12w
0x18003e820  jz      loc_18003E954
0x18003e826  mov     r14, rsi
0x18003e829  inc     r14
0x18003e82c  cmp     [rbp+r14*2+0], r12w
0x18003e832  jnz     short loc_18003E829
0x18003e834  lea     r8, [rsp+68h+Context]; Context
0x18003e83c  mov     [rsp+68h+Context], r12
0x18003e844  lea     rdx, asc_18008003C; "="
0x18003e84b  mov     rcx, rbp; String
0x18003e84e  call    _o_wcstok_s_0
0x18003e853  test    rax, rax
0x18003e856  jz      loc_18003E943
0x18003e85c  cmp     [rsp+68h+Context], r12
0x18003e864  jz      loc_18003E943
0x18003e86a  mov     rcx, rax; unsigned __int16 *
0x18003e86d  call    ?StripWhiteSpaceAndQuotes@@YAPEAGPEAG@Z; StripWhiteSpaceAndQuotes(ushort *)
0x18003e872  mov     rcx, [rsp+68h+Context]; unsigned __int16 *
0x18003e87a  mov     r15, rax
0x18003e87d  call    ?StripWhiteSpaceAndQuotes@@YAPEAGPEAG@Z; StripWhiteSpaceAndQuotes(ushort *)
0x18003e882  mov     [rsp+68h+Context], rax
0x18003e88a  cmp     [r15], r12w
0x18003e88e  jz      loc_18003E943
0x18003e894  cmp     [rax], r12w
0x18003e898  jz      loc_18003E943
0x18003e89e  mov     esi, r12d
0x18003e8a1  cmp     esi, 14h
0x18003e8a4  jnb     loc_18003E93C
0x18003e8aa  movsxd  rax, esi
0x18003e8ad  lea     rdx, [rax+rax*2]
0x18003e8b1  lea     rax, ?s_manifestFields@V4ManifestFile@@0QBUManifestFieldToParse@1@B; V4ManifestFile::ManifestFieldToParse const near * const V4ManifestFile::s_manifestFields
0x18003e8b8  mov     r12, [rax+rdx*8+10h]
0x18003e8bd  cmp     qword ptr [r12+r13], 0
0x18003e8c2  jnz     short loc_18003E8D7
0x18003e8c4  mov     rdx, [rax+rdx*8+8]; String2
0x18003e8c9  mov     rcx, r15; String1
0x18003e8cc  call    _wcsicmp
0x18003e8d1  xor     edx, edx
0x18003e8d3  test    eax, eax
0x18003e8d5  jz      short loc_18003E8DB
0x18003e8d7  inc     esi
0x18003e8d9  jmp     short loc_18003E8A1
0x18003e8db  mov     rcx, [rsp+68h+Context]
0x18003e8e3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003e8e7  mov     rax, rsi
0x18003e8ea  inc     rax
0x18003e8ed  cmp     [rcx+rax*2], dx
0x18003e8f1  jnz     short loc_18003E8EA
0x18003e8f3  lea     rdi, [rax+1]
0x18003e8f7  mov     eax, 2
0x18003e8fc  mul     rdi
0x18003e8ff  lea     rdx, byte_18007F401; struct std::nothrow_t *
0x18003e906  cmovb   rax, rsi
0x18003e90a  mov     rcx, rax; unsigned __int64
0x18003e90d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e912  mov     [r12+r13], rax
0x18003e916  xor     r12d, r12d
0x18003e919  test    rax, rax
0x18003e91c  jnz     short loc_18003E925
0x18003e91e  mov     edi, 8007000Eh
0x18003e923  jmp     short loc_18003E943
0x18003e925  mov     r8, [rsp+68h+Context]; pszSrc
0x18003e92d  mov     rdx, rdi; cchDest
0x18003e930  mov     rcx, rax; pszDest
0x18003e933  call    StringCchCopyW
0x18003e938  mov     edi, eax
0x18003e93a  jmp     short loc_18003E943
0x18003e93c  xor     r12d, r12d
0x18003e93f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003e943  lea     rbp, [rbp+r14*2+0]
0x18003e948  add     rbp, 2
0x18003e94c  test    edi, edi
0x18003e94e  jns     loc_18003E81B
0x18003e954  mov     rcx, rbx; Block
0x18003e957  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e95c  mov     eax, edi
0x18003e95e  add     rsp, 28h
0x18003e962  pop     r15
0x18003e964  pop     r14
0x18003e966  pop     r13
0x18003e968  pop     r12
0x18003e96a  pop     rdi
0x18003e96b  pop     rsi
0x18003e96c  pop     rbp
0x18003e96d  pop     rbx
0x18003e96e  retn
```
