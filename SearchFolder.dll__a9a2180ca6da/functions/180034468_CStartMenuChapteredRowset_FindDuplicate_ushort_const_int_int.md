# CStartMenuChapteredRowset::_FindDuplicate(ushort const *,int,int)

- ea: `0x180034468`
- end: `0x1800347b5`
- name: `?_FindDuplicate@CStartMenuChapteredRowset@@AEAAJPEBGHH@Z`
- size: `845`
- prototype: `__int64 __fastcall(CStartMenuChapteredRowset *this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180029368`
- `0x180034468`

## callees

- `0x180005460`
- `0x180006900`
- `0x180006924`
- `0x180006dc4`
- `0x180028b44`
- `0x180029750`
- `0x1800297b8`
- `0x1800314b0`
- `0x180034468`
- `0x180034f2c`
- `0x180035e74`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800344f3`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800345fd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800344f3`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800345fd`
- `SHLWAPI!PathFindExtensionW` at `0x180034556`
- `SHLWAPI!PathFindExtensionW` at `0x180034556`
- `SHLWAPI!StrCmpNIW` at `0x18003471e`
- `SHLWAPI!StrCmpNIW` at `0x18003471e`
- `SHLWAPI!PathFindFileNameW` at `0x180034541`
- `SHLWAPI!PathFindFileNameW` at `0x180034541`
- `SHLWAPI!PathRemoveExtensionW` at `0x180034590`
- `SHLWAPI!PathRemoveExtensionW` at `0x180034590`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18003457f`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18003457f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003464d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034735`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003464d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034735`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180034508`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180034508`

## pseudocode

```c
__int64 __fastcall CStartMenuChapteredRowset::_FindDuplicate(
        CStartMenuChapteredRowset *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4)
{
  CByteHashTable *v7; // r13
  int Value; // ebx
  const WCHAR *FileNameW; // rax
  WCHAR *v10; // r14
  LPWSTR ExtensionW; // rax
  unsigned __int8 **v12; // r9
  __int64 v13; // r15
  __int64 v14; // r8
  PROPVARIANT *v15; // rax
  PROPVARIANT *v16; // rdi
  LPWSTR v17; // rcx
  PROPVARIANT *v18; // rdi
  const unsigned __int16 *v19; // r12
  CStartMenuChapteredRowset *v20; // rcx
  int *Src; // [rsp+20h] [rbp-E0h]
  unsigned int (*v23)(const unsigned __int8 *, unsigned int, unsigned int); // [rsp+28h] [rbp-D8h]
  unsigned int v24; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *v25; // [rsp+30h] [rbp-D0h]
  size_t v26; // [rsp+38h] [rbp-C8h]
  LPWSTR v27; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR ppwsz; // [rsp+48h] [rbp-B8h] BYREF
  CStartMenuChapteredRowset *v29; // [rsp+50h] [rbp-B0h] BYREF
  PROPVARIANT *pvar; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR psz2[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR psz[264]; // [rsp+270h] [rbp+170h] BYREF

  LODWORD(v27) = a4;
  v29 = this;
  v7 = (CStartMenuChapteredRowset *)((char *)this + 120);
  if ( *((_QWORD *)this + 17)
    || (Value = CByteHashTable::Create(
                  (CStartMenuChapteredRowset *)((char *)this + 120),
                  (unsigned int)a2,
                  a3,
                  a4,
                  (unsigned int)Src,
                  v23),
        Value >= 0) )
  {
    Value = -2147467259;
    if ( a2 )
    {
      if ( *a2 )
      {
        ppwsz = 0;
        Value = SHStrDupW(a2, &ppwsz);
        if ( Value >= 0 )
        {
          CharLowerW(ppwsz);
          Value = CHashTable<tagPROPVARIANT,unsigned short>::ContainsKey(v7, ppwsz);
          if ( Value < 0 )
          {
            if ( a4 )
              CHashTable<tagPROPVARIANT,unsigned short>::AddPtr(v7, ppwsz, 0);
            Value = -2147467259;
            FileNameW = PathFindFileNameW(ppwsz);
            v10 = (WCHAR *)FileNameW;
            if ( FileNameW )
            {
              ExtensionW = PathFindExtensionW(FileNameW);
              if ( ExtensionW )
              {
                if ( *ExtensionW && !StrCmpNICW(ExtensionW, L".lnk", 4) )
                {
                  PathRemoveExtensionW(v10);
                  pvar = 0;
                  v13 = -1;
                  v14 = -1;
                  do
                    ++v14;
                  while ( v10[v14] );
                  Value = CByteHashTable::_GetValue(
                            v7,
                            (const unsigned __int8 *)v10,
                            2 * (int)v14 + 2,
                            v12,
                            Src,
                            (unsigned __int8 *)&pvar,
                            8);
                  if ( Value >= 0 || a3 )
                  {
                    v18 = pvar;
                    if ( pvar && *(_WORD *)pvar == 31 )
                      v19 = (const unsigned __int16 *)pvar[1];
                    else
                      v19 = 0;
                    Value = CStartMenuChapteredRowset::_GetLinkTarget(0, a2, psz);
                    if ( Value >= 0 )
                    {
                      Value = CStartMenuChapteredRowset::_FindDuplicate(v29, psz, 0, (int)v27);
                      if ( Value < 0 )
                      {
                        if ( v19 )
                        {
                          Value = CStartMenuChapteredRowset::_GetLinkTarget(v20, v19, psz2);
                          if ( Value >= 0 )
                          {
                            Value = CStartMenuChapteredRowset::_FindDuplicate(v29, psz2, 0, (int)v27);
                            if ( Value >= 0 && StrCmpNIW(psz, psz2, 260) )
                              Value = -2147467259;
                            if ( (_DWORD)v27 )
                            {
                              PropVariantClear(v18);
                              operator delete(v18, (const struct std::nothrow_t *)0x18);
                              v29 = 0;
                              do
                                ++v13;
                              while ( v10[v13] );
                              LODWORD(v26) = 8;
                              CByteHashTable::_AddUpdateItem(
                                v7,
                                0,
                                (const unsigned __int8 *)v10,
                                2 * v13 + 2,
                                (const unsigned __int8 *)&v29,
                                v24,
                                v25,
                                v26);
                            }
                          }
                        }
                      }
                    }
                  }
                  else if ( a4 )
                  {
                    v27 = 0;
                    if ( SHStrDupW(a2, &v27) >= 0 )
                    {
                      v15 = (PROPVARIANT *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
                      v16 = v15;
                      if ( v15 )
                      {
                        *(_WORD *)v15 = 31;
                        v17 = v27;
                        v27 = 0;
                        v15[1] = v17;
                        if ( (int)CHashTable<tagPROPVARIANT,unsigned short>::AddPtr(v7, v10, v15) < 0 )
                        {
                          PropVariantClear(v16);
                          operator delete(v16, (const struct std::nothrow_t *)0x18);
                        }
                      }
                      else
                      {
                        Value = -2147024882;
                      }
                    }
                    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v27);
                  }
                }
              }
            }
          }
        }
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&ppwsz);
      }
    }
  }
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180034468  mov     [rsp-8+arg_10], rbx
0x18003446d  push    rbp
0x18003446e  push    rsi
0x18003446f  push    rdi
0x180034470  push    r12
0x180034472  push    r13
0x180034474  push    r14
0x180034476  push    r15
0x180034478  lea     rbp, [rsp-390h]
0x180034480  sub     rsp, 490h
0x180034487  mov     rax, cs:__security_cookie
0x18003448e  xor     rax, rsp
0x180034491  mov     [rbp+3C0h+var_40], rax
0x180034498  mov     edi, r9d
0x18003449b  mov     dword ptr [rsp+4C0h+var_480], r9d
0x1800344a0  mov     r12d, r8d
0x1800344a3  mov     rsi, rdx
0x1800344a6  mov     [rsp+4C0h+var_470], rcx
0x1800344ab  lea     r13, [rcx+78h]
0x1800344af  xor     r15d, r15d
0x1800344b2  cmp     [r13+10h], r15
0x1800344b6  jnz     short loc_1800344CA
0x1800344b8  mov     rcx, r13; this
0x1800344bb  call    ?Create@CByteHashTable@@QEAAJIIIIP6AIPEBEII@Z@Z; CByteHashTable::Create(uint,uint,uint,uint,uint (*)(uchar const *,uint,uint))
0x1800344c0  mov     ebx, eax
0x1800344c2  test    eax, eax
0x1800344c4  js      loc_180034789
0x1800344ca  mov     r14d, 80004005h
0x1800344d0  mov     ebx, r14d
0x1800344d3  test    rsi, rsi
0x1800344d6  jz      loc_180034789
0x1800344dc  cmp     [rsi], r15w
0x1800344e0  jz      loc_180034789
0x1800344e6  mov     [rsp+4C0h+ppwsz], r15
0x1800344eb  lea     rdx, [rsp+4C0h+ppwsz]; ppwsz
0x1800344f0  mov     rcx, rsi; psz
0x1800344f3  call    cs:__imp_SHStrDupW
0x1800344f9  mov     ebx, eax
0x1800344fb  test    eax, eax
0x1800344fd  js      loc_18003477F
0x180034503  mov     rcx, [rsp+4C0h+ppwsz]; lpsz
0x180034508  call    cs:__imp_CharLowerW
0x18003450e  mov     rdx, [rsp+4C0h+ppwsz]
0x180034513  mov     rcx, r13
0x180034516  call    ?ContainsKey@?$CHashTable@UtagPROPVARIANT@@G@@QEBAJPEBG@Z; CHashTable<tagPROPVARIANT,ushort>::ContainsKey(ushort const *)
0x18003451b  mov     ebx, eax
0x18003451d  test    eax, eax
0x18003451f  jns     loc_18003477F
0x180034525  test    edi, edi
0x180034527  jz      short loc_180034539
0x180034529  xor     r8d, r8d
0x18003452c  mov     rdx, [rsp+4C0h+ppwsz]
0x180034531  mov     rcx, r13
0x180034534  call    ?AddPtr@?$CHashTable@UtagPROPVARIANT@@G@@QEAAJPEBGPEAUtagPROPVARIANT@@@Z; CHashTable<tagPROPVARIANT,ushort>::AddPtr(ushort const *,tagPROPVARIANT *)
0x180034539  mov     ebx, r14d
0x18003453c  mov     rcx, [rsp+4C0h+ppwsz]; pszPath
0x180034541  call    cs:__imp_PathFindFileNameW
0x180034547  mov     r14, rax
0x18003454a  test    rax, rax
0x18003454d  jz      loc_18003477F
0x180034553  mov     rcx, rax; pszPath
0x180034556  call    cs:__imp_PathFindExtensionW
0x18003455c  test    rax, rax
0x18003455f  jz      loc_18003477F
0x180034565  cmp     [rax], r15w
0x180034569  jz      loc_18003477F
0x18003456f  mov     r8d, 4; nChar
0x180034575  lea     rdx, aLnk; ".lnk"
0x18003457c  mov     rcx, rax; pszStr1
0x18003457f  call    cs:__imp_StrCmpNICW
0x180034585  test    eax, eax
0x180034587  jnz     loc_18003477F
0x18003458d  mov     rcx, r14; pszPath
0x180034590  call    cs:__imp_PathRemoveExtensionW
0x180034596  mov     [rsp+4C0h+pvar], r15
0x18003459b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003459f  mov     r8, r15
0x1800345a2  xor     eax, eax
0x1800345a4  inc     r8
0x1800345a7  cmp     [r14+r8*2], ax
0x1800345ac  jnz     short loc_1800345A4
0x1800345ae  lea     r8d, ds:2[r8*2]; unsigned int
0x1800345b6  mov     dword ptr [rsp+4C0h+var_490], 8; unsigned __int8 *
0x1800345be  lea     rax, [rsp+4C0h+pvar]
0x1800345c3  mov     [rsp+4C0h+var_498], rax; unsigned int
0x1800345c8  mov     rdx, r14; unsigned __int8 *
0x1800345cb  mov     rcx, r13; this
0x1800345ce  call    ?_GetValue@CByteHashTable@@AEBAJPEBEIPEAPEAEPEAHPEAEH@Z; CByteHashTable::_GetValue(uchar const *,uint,uchar * *,int *,uchar *,int)
0x1800345d3  mov     ebx, eax
0x1800345d5  xor     ecx, ecx; this
0x1800345d7  test    eax, eax
0x1800345d9  jns     loc_180034673
0x1800345df  test    r12d, r12d
0x1800345e2  jnz     loc_180034673
0x1800345e8  test    edi, edi
0x1800345ea  jz      loc_18003477F
0x1800345f0  mov     [rsp+4C0h+var_480], rcx
0x1800345f5  lea     rdx, [rsp+4C0h+var_480]; ppwsz
0x1800345fa  mov     rcx, rsi; psz
0x1800345fd  call    cs:__imp_SHStrDupW
0x180034603  xor     r15d, r15d
0x180034606  test    eax, eax
0x180034608  js      short loc_180034664
0x18003460a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034611  lea     esi, [r12+18h]
0x180034616  mov     ecx, esi; unsigned __int64
0x180034618  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003461d  mov     rdi, rax
0x180034620  test    rax, rax
0x180034623  jz      short loc_18003465F
0x180034625  mov     word ptr [rax], 1Fh
0x18003462a  mov     rcx, [rsp+4C0h+var_480]
0x18003462f  mov     [rsp+4C0h+var_480], r15
0x180034634  mov     [rax+8], rcx
0x180034638  mov     r8, rax
0x18003463b  mov     rdx, r14
0x18003463e  mov     rcx, r13
0x180034641  call    ?AddPtr@?$CHashTable@UtagPROPVARIANT@@G@@QEAAJPEBGPEAUtagPROPVARIANT@@@Z; CHashTable<tagPROPVARIANT,ushort>::AddPtr(ushort const *,tagPROPVARIANT *)
0x180034646  test    eax, eax
0x180034648  jns     short loc_180034664
0x18003464a  mov     rcx, rdi; pvar
0x18003464d  call    cs:__imp_PropVariantClear
0x180034653  mov     edx, esi; struct std::nothrow_t *
0x180034655  mov     rcx, rdi; void *
0x180034658  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003465d  jmp     short loc_180034664
0x18003465f  mov     ebx, 8007000Eh
0x180034664  lea     rcx, [rsp+4C0h+var_480]; void *
0x180034669  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18003466e  jmp     loc_18003477F
0x180034673  mov     rdi, [rsp+4C0h+pvar]
0x180034678  test    rdi, rdi
0x18003467b  jz      short loc_18003468D
0x18003467d  mov     eax, 1Fh
0x180034682  cmp     [rdi], ax
0x180034685  jnz     short loc_18003468D
0x180034687  mov     r12, [rdi+8]
0x18003468b  jmp     short loc_180034690
0x18003468d  mov     r12, rcx
0x180034690  lea     r8, [rbp+3C0h+psz]; unsigned __int16 *
0x180034697  mov     rdx, rsi; unsigned __int16 *
0x18003469a  call    ?_GetLinkTarget@CStartMenuChapteredRowset@@AEAAJPEBGPEAGI@Z; CStartMenuChapteredRowset::_GetLinkTarget(ushort const *,ushort *,uint)
0x18003469f  mov     ebx, eax
0x1800346a1  test    eax, eax
0x1800346a3  js      loc_18003477F
0x1800346a9  mov     esi, dword ptr [rsp+4C0h+var_480]
0x1800346ad  mov     r9d, esi; int
0x1800346b0  xor     r8d, r8d; int
0x1800346b3  lea     rdx, [rbp+3C0h+psz]; unsigned __int16 *
0x1800346ba  mov     rcx, [rsp+4C0h+var_470]; this
0x1800346bf  call    ?_FindDuplicate@CStartMenuChapteredRowset@@AEAAJPEBGHH@Z; CStartMenuChapteredRowset::_FindDuplicate(ushort const *,int,int)
0x1800346c4  mov     ebx, eax
0x1800346c6  test    eax, eax
0x1800346c8  jns     loc_18003477F
0x1800346ce  test    r12, r12
0x1800346d1  jz      loc_18003477F
0x1800346d7  lea     r8, [rsp+4C0h+psz2]; unsigned __int16 *
0x1800346dc  mov     rdx, r12; unsigned __int16 *
0x1800346df  call    ?_GetLinkTarget@CStartMenuChapteredRowset@@AEAAJPEBGPEAGI@Z; CStartMenuChapteredRowset::_GetLinkTarget(ushort const *,ushort *,uint)
0x1800346e4  mov     ebx, eax
0x1800346e6  xor     r12d, r12d
0x1800346e9  test    eax, eax
0x1800346eb  js      loc_18003477F
0x1800346f1  mov     r9d, esi; int
0x1800346f4  xor     r8d, r8d; int
0x1800346f7  lea     rdx, [rsp+4C0h+psz2]; unsigned __int16 *
0x1800346fc  mov     rcx, [rsp+4C0h+var_470]; this
0x180034701  call    ?_FindDuplicate@CStartMenuChapteredRowset@@AEAAJPEBGHH@Z; CStartMenuChapteredRowset::_FindDuplicate(ushort const *,int,int)
0x180034706  mov     ebx, eax
0x180034708  test    eax, eax
0x18003470a  js      short loc_18003472E
0x18003470c  mov     r8d, 104h; nChar
0x180034712  lea     rdx, [rsp+4C0h+psz2]; psz2
0x180034717  lea     rcx, [rbp+3C0h+psz]; psz1
0x18003471e  call    cs:__imp_StrCmpNIW
0x180034724  test    eax, eax
0x180034726  mov     eax, 80004005h
0x18003472b  cmovnz  ebx, eax
0x18003472e  test    esi, esi
0x180034730  jz      short loc_18003477F
0x180034732  mov     rcx, rdi; pvar
0x180034735  call    cs:__imp_PropVariantClear
0x18003473b  mov     edx, 18h; struct std::nothrow_t *
0x180034740  mov     rcx, rdi; void *
0x180034743  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034748  mov     [rsp+4C0h+var_470], r12
0x18003474d  inc     r15
0x180034750  cmp     [r14+r15*2], r12w
0x180034755  jnz     short loc_18003474D
0x180034757  lea     r9d, ds:2[r15*2]; unsigned int
0x18003475f  mov     dword ptr [rsp+4C0h+var_488], 8; unsigned int
0x180034767  lea     rax, [rsp+4C0h+var_470]
0x18003476c  mov     [rsp+4C0h+Src], rax; Src
0x180034771  mov     r8, r14; unsigned __int8 *
0x180034774  xor     edx, edx; int
0x180034776  mov     rcx, r13; this
0x180034779  call    ?_AddUpdateItem@CByteHashTable@@AEAAJHPEBEI0IPEAEI@Z; CByteHashTable::_AddUpdateItem(int,uchar const *,uint,uchar const *,uint,uchar *,uint)
0x18003477e  nop
0x18003477f  lea     rcx, [rsp+4C0h+ppwsz]; void *
0x180034784  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180034789  mov     eax, ebx
0x18003478b  mov     rcx, [rbp+3C0h+var_40]
0x180034792  xor     rcx, rsp; StackCookie
0x180034795  call    __security_check_cookie
0x18003479a  mov     rbx, [rsp+4C0h+arg_10]
0x1800347a2  add     rsp, 490h
0x1800347a9  pop     r15
0x1800347ab  pop     r14
0x1800347ad  pop     r13
0x1800347af  pop     r12
0x1800347b1  pop     rdi
0x1800347b2  pop     rsi
0x1800347b3  pop     rbp
0x1800347b4  retn
```
