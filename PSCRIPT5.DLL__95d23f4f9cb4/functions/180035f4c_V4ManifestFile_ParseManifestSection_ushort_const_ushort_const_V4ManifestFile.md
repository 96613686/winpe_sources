# V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)

- ea: `0x180035f4c`
- end: `0x180036110`
- name: `?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z`
- size: `452`
- prototype: `__int64 __fastcall(LPCWSTR lpAppName, LPCWSTR lpFileName, struct V4ManifestFile *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180035e3c`

## callees

- `0x180002498`
- `0x18000283c`
- `0x1800028c0`
- `0x18000298c`
- `0x180005568`
- `0x180035f4c`
- `0x180036814`

## import_xrefs

- `KERNEL32!GetPrivateProfileSectionW` at `0x180035f9b`
- `KERNEL32!GetPrivateProfileSectionW` at `0x180035f9b`

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
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // kr00_8
  wchar_t *v22; // rax
  wchar_t *Context; // [rsp+88h] [rbp+20h] BYREF

  v6 = (WCHAR *)operator new(0x2000u, (const struct std::nothrow_t *)byte_18006C430);
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
                v22 = (wchar_t *)operator new(v20, (const struct std::nothrow_t *)byte_18006C430);
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
0x180035f4c  push    rbx
0x180035f4e  push    rbp
0x180035f4f  push    rsi
0x180035f50  push    rdi
0x180035f51  push    r12
0x180035f53  push    r13
0x180035f55  push    r14
0x180035f57  push    r15
0x180035f59  sub     rsp, 28h
0x180035f5d  mov     rdi, rdx
0x180035f60  mov     rsi, rcx
0x180035f63  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x180035f6a  mov     ecx, 2000h; unsigned __int64
0x180035f6f  mov     r13, r8
0x180035f72  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035f77  xor     r12d, r12d
0x180035f7a  mov     rbx, rax
0x180035f7d  test    rax, rax
0x180035f80  jnz     short loc_180035F8C
0x180035f82  mov     edi, 8007000Eh
0x180035f87  jmp     loc_180036091
0x180035f8c  mov     r9, rdi; lpFileName
0x180035f8f  mov     r8d, 1000h; nSize
0x180035f95  mov     rdx, rbx; lpReturnedString
0x180035f98  mov     rcx, rsi; lpAppName
0x180035f9b  call    cs:__imp_GetPrivateProfileSectionW
0x180035fa1  test    eax, eax
0x180035fa3  jnz     short loc_180035FB4
0x180035fa5  mov     rcx, rbx; Block
0x180035fa8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035fad  xor     eax, eax
0x180035faf  jmp     loc_18003609B
0x180035fb4  cmp     eax, 0FFEh
0x180035fb9  jnz     short loc_180035FC5
0x180035fbb  mov     edi, 8007007Ah
0x180035fc0  jmp     loc_180036091
0x180035fc5  mov     rbp, rbx
0x180035fc8  mov     edi, r12d
0x180035fcb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180035fcf  cmp     [rbp+0], r12w
0x180035fd4  jz      loc_180036091
0x180035fda  mov     r14, rsi
0x180035fdd  inc     r14
0x180035fe0  cmp     [rbp+r14*2+0], r12w
0x180035fe6  jnz     short loc_180035FDD
0x180035fe8  lea     r8, [rsp+68h+Context]; Context
0x180035ff0  mov     [rsp+68h+Context], r12
0x180035ff8  lea     rdx, Delimiter; "="
0x180035fff  mov     rcx, rbp; String
0x180036002  call    _o_wcstok_s_0
0x180036007  test    rax, rax
0x18003600a  jz      short loc_180036080
0x18003600c  cmp     [rsp+68h+Context], r12
0x180036014  jz      short loc_180036080
0x180036016  mov     rcx, rax; unsigned __int16 *
0x180036019  call    ?StripWhiteSpaceAndQuotes@@YAPEAGPEAG@Z; StripWhiteSpaceAndQuotes(ushort *)
0x18003601e  mov     rcx, [rsp+68h+Context]; unsigned __int16 *
0x180036026  mov     r15, rax
0x180036029  call    ?StripWhiteSpaceAndQuotes@@YAPEAGPEAG@Z; StripWhiteSpaceAndQuotes(ushort *)
0x18003602e  mov     [rsp+68h+Context], rax
0x180036036  cmp     [r15], r12w
0x18003603a  jz      short loc_180036080
0x18003603c  cmp     [rax], r12w
0x180036040  jz      short loc_180036080
0x180036042  mov     esi, r12d
0x180036045  movsxd  rax, esi
0x180036048  lea     rdx, [rax+rax*2]
0x18003604c  lea     rax, ?s_manifestFields@V4ManifestFile@@0QBUManifestFieldToParse@1@B; V4ManifestFile::ManifestFieldToParse const near * const V4ManifestFile::s_manifestFields
0x180036053  mov     r12, [rax+rdx*8+10h]
0x180036058  cmp     qword ptr [r12+r13], 0
0x18003605d  jnz     short loc_180036072
0x18003605f  mov     rdx, [rax+rdx*8+8]; String2
0x180036064  mov     rcx, r15; String1
0x180036067  call    _wcsicmp
0x18003606c  xor     edx, edx
0x18003606e  test    eax, eax
0x180036070  jz      short loc_1800360AC
0x180036072  inc     esi
0x180036074  cmp     esi, 14h
0x180036077  jb      short loc_180036045
0x180036079  xor     r12d, r12d
0x18003607c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180036080  lea     rbp, [rbp+r14*2+0]
0x180036085  add     rbp, 2
0x180036089  test    edi, edi
0x18003608b  jns     loc_180035FCF
0x180036091  mov     rcx, rbx; Block
0x180036094  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036099  mov     eax, edi
0x18003609b  add     rsp, 28h
0x18003609f  pop     r15
0x1800360a1  pop     r14
0x1800360a3  pop     r13
0x1800360a5  pop     r12
0x1800360a7  pop     rdi
0x1800360a8  pop     rsi
0x1800360a9  pop     rbp
0x1800360aa  pop     rbx
0x1800360ab  retn
0x1800360ac  mov     rcx, [rsp+68h+Context]
0x1800360b4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800360b8  mov     rax, rsi
0x1800360bb  inc     rax
0x1800360be  cmp     [rcx+rax*2], dx
0x1800360c2  jnz     short loc_1800360BB
0x1800360c4  lea     rdi, [rax+1]
0x1800360c8  mov     eax, 2
0x1800360cd  mul     rdi
0x1800360d0  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x1800360d7  cmovb   rax, rsi
0x1800360db  mov     rcx, rax; unsigned __int64
0x1800360de  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800360e3  mov     [r12+r13], rax
0x1800360e7  xor     r12d, r12d
0x1800360ea  test    rax, rax
0x1800360ed  jnz     short loc_1800360F6
0x1800360ef  mov     edi, 8007000Eh
0x1800360f4  jmp     short loc_180036080
0x1800360f6  mov     r8, [rsp+68h+Context]; pszSrc
0x1800360fe  mov     rdx, rdi; cchDest
0x180036101  mov     rcx, rax; pszDest
0x180036104  call    StringCchCopyW
0x180036109  mov     edi, eax
0x18003610b  jmp     loc_180036080
```
