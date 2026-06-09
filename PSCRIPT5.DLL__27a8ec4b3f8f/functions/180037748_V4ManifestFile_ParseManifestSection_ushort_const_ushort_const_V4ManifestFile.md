# V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)

- ea: `0x180037748`
- end: `0x180037913`
- name: `?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z`
- size: `459`
- prototype: `__int64 __fastcall(LPCWSTR lpAppName, LPCWSTR lpFileName, struct V4ManifestFile *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180037634`

## callees

- `0x1800024d8`
- `0x18000289c`
- `0x180002920`
- `0x1800029ec`
- `0x1800055fc`
- `0x180037748`
- `0x180038070`

## import_xrefs

- `KERNEL32!GetPrivateProfileSectionW` at `0x180037797`
- `KERNEL32!GetPrivateProfileSectionW` at `0x180037797`

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
  int v16; // esi
  __int64 v17; // r12
  __int64 v18; // rax
  size_t v19; // rdi
  size_t v20; // rax
  unsigned __int64 v21; // kr00_8
  wchar_t *v22; // rax
  wchar_t *Context; // [rsp+88h] [rbp+20h] BYREF

  v6 = (WCHAR *)operator new(0x2000u, (const struct std::nothrow_t *)byte_18006E400);
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
                v16 = 0;
                while ( 1 )
                {
                  v17 = *((_QWORD *)&V4ManifestFile::s_manifestFields + 3 * v16 + 2);
                  if ( !*(_QWORD *)((char *)a3 + v17)
                    && !wcsicmp(v14, *((const wchar_t **)&V4ManifestFile::s_manifestFields + 3 * v16 + 1)) )
                  {
                    break;
                  }
                  if ( (unsigned int)++v16 >= 0x14 )
                    goto LABEL_19;
                }
                v18 = -1;
                do
                  ++v18;
                while ( Context[v18] );
                v19 = v18 + 1;
                v21 = v18 + 1;
                v20 = 2 * (v18 + 1);
                if ( !is_mul_ok(v21, 2u) )
                  v20 = -1;
                v22 = (wchar_t *)operator new(v20, (const struct std::nothrow_t *)byte_18006E400);
                *(_QWORD *)((char *)a3 + v17) = v22;
                if ( v22 )
                  v8 = StringCchCopyW(v22, v19, Context);
                else
                  v8 = -2147024882;
              }
            }
          }
        }
LABEL_19:
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
0x180037748  push    rbx
0x18003774a  push    rbp
0x18003774b  push    rsi
0x18003774c  push    rdi
0x18003774d  push    r12
0x18003774f  push    r13
0x180037751  push    r14
0x180037753  push    r15
0x180037755  sub     rsp, 28h
0x180037759  mov     rdi, rdx
0x18003775c  mov     rsi, rcx
0x18003775f  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x180037766  mov     ecx, 2000h; unsigned __int64
0x18003776b  mov     r13, r8
0x18003776e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037773  xor     r12d, r12d
0x180037776  mov     rbx, rax
0x180037779  test    rax, rax
0x18003777c  jnz     short loc_180037788
0x18003777e  mov     edi, 8007000Eh
0x180037783  jmp     loc_180037893
0x180037788  mov     r9, rdi; lpFileName
0x18003778b  mov     r8d, 1000h; nSize
0x180037791  mov     rdx, rbx; lpReturnedString
0x180037794  mov     rcx, rsi; lpAppName
0x180037797  call    cs:__imp_GetPrivateProfileSectionW
0x18003779e  nop     dword ptr [rax+rax+00h]
0x1800377a3  test    eax, eax
0x1800377a5  jnz     short loc_1800377B6
0x1800377a7  mov     rcx, rbx; Block
0x1800377aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800377af  xor     eax, eax
0x1800377b1  jmp     loc_18003789D
0x1800377b6  cmp     eax, 0FFEh
0x1800377bb  jnz     short loc_1800377C7
0x1800377bd  mov     edi, 8007007Ah
0x1800377c2  jmp     loc_180037893
0x1800377c7  mov     rbp, rbx
0x1800377ca  mov     edi, r12d
0x1800377cd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800377d1  cmp     [rbp+0], r12w
0x1800377d6  jz      loc_180037893
0x1800377dc  mov     r14, rsi
0x1800377df  inc     r14
0x1800377e2  cmp     [rbp+r14*2+0], r12w
0x1800377e8  jnz     short loc_1800377DF
0x1800377ea  lea     r8, [rsp+68h+Context]; Context
0x1800377f2  mov     [rsp+68h+Context], r12
0x1800377fa  lea     rdx, Delimiter; "="
0x180037801  mov     rcx, rbp; String
0x180037804  call    _o_wcstok_s_0
0x180037809  test    rax, rax
0x18003780c  jz      short loc_180037882
0x18003780e  cmp     [rsp+68h+Context], r12
0x180037816  jz      short loc_180037882
0x180037818  mov     rcx, rax; unsigned __int16 *
0x18003781b  call    ?StripWhiteSpaceAndQuotes@@YAPEAGPEAG@Z; StripWhiteSpaceAndQuotes(ushort *)
0x180037820  mov     rcx, [rsp+68h+Context]; unsigned __int16 *
0x180037828  mov     r15, rax
0x18003782b  call    ?StripWhiteSpaceAndQuotes@@YAPEAGPEAG@Z; StripWhiteSpaceAndQuotes(ushort *)
0x180037830  mov     [rsp+68h+Context], rax
0x180037838  cmp     [r15], r12w
0x18003783c  jz      short loc_180037882
0x18003783e  cmp     [rax], r12w
0x180037842  jz      short loc_180037882
0x180037844  mov     esi, r12d
0x180037847  movsxd  rax, esi
0x18003784a  lea     rdx, [rax+rax*2]
0x18003784e  lea     rax, ?s_manifestFields@V4ManifestFile@@0QBUManifestFieldToParse@1@B; V4ManifestFile::ManifestFieldToParse const near * const V4ManifestFile::s_manifestFields
0x180037855  mov     r12, [rax+rdx*8+10h]
0x18003785a  cmp     qword ptr [r12+r13], 0
0x18003785f  jnz     short loc_180037874
0x180037861  mov     rdx, [rax+rdx*8+8]; String2
0x180037866  mov     rcx, r15; String1
0x180037869  call    _wcsicmp
0x18003786e  xor     edx, edx
0x180037870  test    eax, eax
0x180037872  jz      short loc_1800378AF
0x180037874  inc     esi
0x180037876  cmp     esi, 14h
0x180037879  jb      short loc_180037847
0x18003787b  xor     r12d, r12d
0x18003787e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180037882  lea     rbp, [rbp+r14*2+0]
0x180037887  add     rbp, 2
0x18003788b  test    edi, edi
0x18003788d  jns     loc_1800377D1
0x180037893  mov     rcx, rbx; Block
0x180037896  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003789b  mov     eax, edi
0x18003789d  add     rsp, 28h
0x1800378a1  pop     r15
0x1800378a3  pop     r14
0x1800378a5  pop     r13
0x1800378a7  pop     r12
0x1800378a9  pop     rdi
0x1800378aa  pop     rsi
0x1800378ab  pop     rbp
0x1800378ac  pop     rbx
0x1800378ad  retn
0x1800378af  mov     rcx, [rsp+68h+Context]
0x1800378b7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800378bb  mov     rax, rsi
0x1800378be  inc     rax
0x1800378c1  cmp     [rcx+rax*2], dx
0x1800378c5  jnz     short loc_1800378BE
0x1800378c7  lea     rdi, [rax+1]
0x1800378cb  mov     eax, 2
0x1800378d0  mul     rdi
0x1800378d3  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x1800378da  cmovb   rax, rsi
0x1800378de  mov     rcx, rax; unsigned __int64
0x1800378e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800378e6  mov     [r12+r13], rax
0x1800378ea  xor     r12d, r12d
0x1800378ed  test    rax, rax
0x1800378f0  jnz     short loc_1800378F9
0x1800378f2  mov     edi, 8007000Eh
0x1800378f7  jmp     short loc_180037882
0x1800378f9  mov     r8, [rsp+68h+Context]; pszSrc
0x180037901  mov     rdx, rdi; cchDest
0x180037904  mov     rcx, rax; pszDest
0x180037907  call    StringCchCopyW
0x18003790c  mov     edi, eax
0x18003790e  jmp     loc_180037882
```
