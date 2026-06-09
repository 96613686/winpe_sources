# V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)

- ea: `0x18003f67c`
- end: `0x18003f85a`
- name: `?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z`
- size: `478`
- prototype: `__int64 __fastcall(LPCWSTR lpAppName, LPCWSTR lpFileName, struct V4ManifestFile *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180055b70`

## callees

- `0x180024c98`
- `0x18003f67c`
- `0x1800459fc`
- `0x18004a2b8`
- `0x18004a668`
- `0x18004a704`
- `0x18004a728`

## import_xrefs

- `KERNEL32!GetPrivateProfileSectionW` at `0x18003f6cb`
- `KERNEL32!GetPrivateProfileSectionW` at `0x18003f6cb`

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
  size_t v20; // rax
  unsigned __int64 v21; // kr00_8
  wchar_t *v22; // rax
  wchar_t *Context; // [rsp+88h] [rbp+20h] BYREF

  v6 = (WCHAR *)operator new(0x2000u, (const struct std::nothrow_t *)byte_180081401);
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
                    v22 = (wchar_t *)operator new(v20, (const struct std::nothrow_t *)byte_180081401);
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
0x18003f67c  push    rbx
0x18003f67e  push    rbp
0x18003f67f  push    rsi
0x18003f680  push    rdi
0x18003f681  push    r12
0x18003f683  push    r13
0x18003f685  push    r14
0x18003f687  push    r15
0x18003f689  sub     rsp, 28h
0x18003f68d  mov     rdi, rdx
0x18003f690  mov     rsi, rcx
0x18003f693  lea     rdx, byte_180081401; struct std::nothrow_t *
0x18003f69a  mov     ecx, 2000h; unsigned __int64
0x18003f69f  mov     r13, r8
0x18003f6a2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003f6a7  xor     r12d, r12d
0x18003f6aa  mov     rbx, rax
0x18003f6ad  test    rax, rax
0x18003f6b0  jnz     short loc_18003F6BC
0x18003f6b2  mov     edi, 8007000Eh
0x18003f6b7  jmp     loc_18003F83E
0x18003f6bc  mov     r9, rdi; lpFileName
0x18003f6bf  mov     r8d, 1000h; nSize
0x18003f6c5  mov     rdx, rbx; lpReturnedString
0x18003f6c8  mov     rcx, rsi; lpAppName
0x18003f6cb  call    cs:__imp_GetPrivateProfileSectionW
0x18003f6d2  nop     dword ptr [rax+rax+00h]
0x18003f6d7  test    eax, eax
0x18003f6d9  jnz     short loc_18003F6EA
0x18003f6db  mov     rcx, rbx; Block
0x18003f6de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f6e3  xor     eax, eax
0x18003f6e5  jmp     loc_18003F848
0x18003f6ea  cmp     eax, 0FFEh
0x18003f6ef  jnz     short loc_18003F6FB
0x18003f6f1  mov     edi, 8007007Ah
0x18003f6f6  jmp     loc_18003F83E
0x18003f6fb  mov     rbp, rbx
0x18003f6fe  mov     edi, r12d
0x18003f701  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003f705  cmp     [rbp+0], r12w
0x18003f70a  jz      loc_18003F83E
0x18003f710  mov     r14, rsi
0x18003f713  inc     r14
0x18003f716  cmp     [rbp+r14*2+0], r12w
0x18003f71c  jnz     short loc_18003F713
0x18003f71e  lea     r8, [rsp+68h+Context]; Context
0x18003f726  mov     [rsp+68h+Context], r12
0x18003f72e  lea     rdx, asc_18008203C; "="
0x18003f735  mov     rcx, rbp; String
0x18003f738  call    _o_wcstok_s_0
0x18003f73d  test    rax, rax
0x18003f740  jz      loc_18003F82D
0x18003f746  cmp     [rsp+68h+Context], r12
0x18003f74e  jz      loc_18003F82D
0x18003f754  mov     rcx, rax; unsigned __int16 *
0x18003f757  call    ?StripWhiteSpaceAndQuotes@@YAPEAGPEAG@Z; StripWhiteSpaceAndQuotes(ushort *)
0x18003f75c  mov     rcx, [rsp+68h+Context]; unsigned __int16 *
0x18003f764  mov     r15, rax
0x18003f767  call    ?StripWhiteSpaceAndQuotes@@YAPEAGPEAG@Z; StripWhiteSpaceAndQuotes(ushort *)
0x18003f76c  mov     [rsp+68h+Context], rax
0x18003f774  cmp     [r15], r12w
0x18003f778  jz      loc_18003F82D
0x18003f77e  cmp     [rax], r12w
0x18003f782  jz      loc_18003F82D
0x18003f788  mov     esi, r12d
0x18003f78b  cmp     esi, 14h
0x18003f78e  jnb     loc_18003F826
0x18003f794  movsxd  rax, esi
0x18003f797  lea     rdx, [rax+rax*2]
0x18003f79b  lea     rax, ?s_manifestFields@V4ManifestFile@@0QBUManifestFieldToParse@1@B; V4ManifestFile::ManifestFieldToParse const near * const V4ManifestFile::s_manifestFields
0x18003f7a2  mov     r12, [rax+rdx*8+10h]
0x18003f7a7  cmp     qword ptr [r12+r13], 0
0x18003f7ac  jnz     short loc_18003F7C1
0x18003f7ae  mov     rdx, [rax+rdx*8+8]; String2
0x18003f7b3  mov     rcx, r15; String1
0x18003f7b6  call    _wcsicmp
0x18003f7bb  xor     edx, edx
0x18003f7bd  test    eax, eax
0x18003f7bf  jz      short loc_18003F7C5
0x18003f7c1  inc     esi
0x18003f7c3  jmp     short loc_18003F78B
0x18003f7c5  mov     rcx, [rsp+68h+Context]
0x18003f7cd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003f7d1  mov     rax, rsi
0x18003f7d4  inc     rax
0x18003f7d7  cmp     [rcx+rax*2], dx
0x18003f7db  jnz     short loc_18003F7D4
0x18003f7dd  lea     rdi, [rax+1]
0x18003f7e1  mov     eax, 2
0x18003f7e6  mul     rdi
0x18003f7e9  lea     rdx, byte_180081401; struct std::nothrow_t *
0x18003f7f0  cmovb   rax, rsi
0x18003f7f4  mov     rcx, rax; unsigned __int64
0x18003f7f7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003f7fc  mov     [r12+r13], rax
0x18003f800  xor     r12d, r12d
0x18003f803  test    rax, rax
0x18003f806  jnz     short loc_18003F80F
0x18003f808  mov     edi, 8007000Eh
0x18003f80d  jmp     short loc_18003F82D
0x18003f80f  mov     r8, [rsp+68h+Context]; pszSrc
0x18003f817  mov     rdx, rdi; cchDest
0x18003f81a  mov     rcx, rax; pszDest
0x18003f81d  call    StringCchCopyW
0x18003f822  mov     edi, eax
0x18003f824  jmp     short loc_18003F82D
0x18003f826  xor     r12d, r12d
0x18003f829  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003f82d  lea     rbp, [rbp+r14*2+0]
0x18003f832  add     rbp, 2
0x18003f836  test    edi, edi
0x18003f838  jns     loc_18003F705
0x18003f83e  mov     rcx, rbx; Block
0x18003f841  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f846  mov     eax, edi
0x18003f848  add     rsp, 28h
0x18003f84c  pop     r15
0x18003f84e  pop     r14
0x18003f850  pop     r13
0x18003f852  pop     r12
0x18003f854  pop     rdi
0x18003f855  pop     rsi
0x18003f856  pop     rbp
0x18003f857  pop     rbx
0x18003f858  retn
```
