# CMapi2SearchItem::AddSearchFolder(TLMString<192,64,32767> const &,int,POLICY_RESULT_ID)

- ea: `0x180028bf8`
- end: `0x180028e5a`
- name: `?AddSearchFolder@CMapi2SearchItem@@AEAAJAEBV?$TLMString@$0MA@$0EA@$0HPPP@@@HW4POLICY_RESULT_ID@@@Z`
- size: `610`
- prototype: `__int64 __fastcall(__int64, __int64, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028e60`

## callees

- `0x180002300`
- `0x180002780`
- `0x18000e6e0`
- `0x18000ed28`
- `0x18000edec`
- `0x180011884`
- `0x18001ed24`
- `0x180020984`
- `0x1800285f0`
- `0x180028bf8`
- `0x180028f20`
- `0x18002904c`
- `0x18002b784`
- `0x18003a060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028d22`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028d22`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180028dad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180028dad`

## pseudocode

```c
__int64 __fastcall CMapi2SearchItem::AddSearchFolder(__int64 a1, __int64 a2, int a3, int a4)
{
  CDesktopSearchFolder *v7; // rax
  CDesktopSearchFolder *v8; // rdi
  int DisplayFolderOrUrlHelper; // esi
  CDesktopSearchFolder *v10; // r15
  unsigned int v11; // edx
  unsigned int v12; // r12d
  unsigned int v13; // esi
  struct CResourceLibrary *ResourceLibrary; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // rax
  __int64 v17; // rcx
  struct CSingleLink *Link; // rax
  CLnkList *v19; // rcx
  struct CSingleLink *v20; // rdx
  PCNZWCH **i; // rax
  __int64 v22; // rcx
  wchar_t *v25; // [rsp+38h] [rbp-2070h] BYREF
  CDesktopSearchFolder *v26; // [rsp+40h] [rbp-2068h]
  _QWORD v27[2]; // [rsp+48h] [rbp-2060h] BYREF
  struct CSingleLink *v28; // [rsp+58h] [rbp-2050h]
  __int64 v29; // [rsp+60h] [rbp-2048h]
  wchar_t Str[4096]; // [rsp+70h] [rbp-2038h] BYREF
  void *retaddr; // [rsp+20A8h] [rbp+0h]

  v29 = a2;
  v7 = (CDesktopSearchFolder *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  v26 = v7;
  if ( v7 )
  {
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
    *((_QWORD *)v7 + 2) = 0;
    *((_DWORD *)v7 + 6) = 0;
    v26 = v7;
    DisplayFolderOrUrlHelper = GetDisplayFolderOrUrlHelper(*(const wchar_t **)(a2 + 8), 0, 1, Str, 0x1000u);
    v10 = v8;
  }
  else
  {
    v10 = 0;
    v8 = 0;
    v26 = 0;
    DisplayFolderOrUrlHelper = -2147024882;
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v25);
  if ( DisplayFolderOrUrlHelper < 0 )
  {
LABEL_25:
    if ( v8 )
      CDesktopSearchFolder::`scalar deleting destructor'(v8, v11);
    goto LABEL_27;
  }
  v12 = 0;
  if ( !a3 )
  {
    v12 = 0x8000;
    if ( a4 == 1 )
    {
      v13 = 112;
    }
    else if ( a4 == 2 )
    {
      v13 = 113;
    }
    else
    {
      v13 = 111;
      if ( a4 == 3 )
        v13 = 114;
    }
    ResourceLibrary = GetResourceLibrary();
    if ( !(unsigned int)LoadCString(ResourceLibrary, &v25, v13) )
    {
      DisplayFolderOrUrlHelper = -2147467259;
      goto LABEL_25;
    }
  }
  v15 = wcsrchr(Str, 0x2Fu);
  if ( v15 )
    v16 = v15 + 1;
  else
    v16 = Str;
  DisplayFolderOrUrlHelper = CDesktopSearchFolder::Init(v10, v16, *(const wchar_t **)(v29 + 8), v25, v12);
  if ( DisplayFolderOrUrlHelper < 0 )
    goto LABEL_25;
  try
  {
    v27[0] = a1 + 120;
    v27[1] = a1 + 128;
    v28 = 0;
    for ( i = (PCNZWCH **)CTPtrSListIterator<CDesktopSearchFolder>::operator++(v27);
          *i;
          i = (PCNZWCH **)CTPtrSListIterator<CDesktopSearchFolder>::operator++(v27) )
    {
      if ( CompareStringW(0x7Fu, 1u, **i, -1, *(PCNZWCH *)v8, -1) == 1 )
      {
        Link = (struct CSingleLink *)CTPtrSList<CDesktopSearchFolder>::CreateLink(v17, v8);
        v19 = (CLnkList *)(v27[0] + 8LL);
        v20 = v28;
        goto LABEL_24;
      }
    }
    Link = (struct CSingleLink *)CTPtrSList<CDesktopSearchFolder>::CreateLink(v22, v8);
    v20 = *(struct CSingleLink **)(a1 + 144);
    v19 = (CLnkList *)(a1 + 128);
LABEL_24:
    CLnkList::InsertAfter(v19, v20, Link);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      254,
      "onecoreuap\\base\\appmodel\\search\\mssph\\mapi2\\mapi2searchitem.cxx");
  }
LABEL_27:
  ATL::CStringData::Release((ATL::CStringData *)(v25 - 12));
  return (unsigned int)DisplayFolderOrUrlHelper;
}

```

## disassembly

```asm
0x180028bf8  mov     [rsp+arg_10], rbx
0x180028bfd  mov     [rsp+arg_18], rsi
0x180028c02  push    rdi
0x180028c03  push    r12
0x180028c05  push    r13
0x180028c07  push    r14
0x180028c09  push    r15
0x180028c0b  mov     eax, 2080h
0x180028c10  call    _alloca_probe
0x180028c15  sub     rsp, rax
0x180028c18  mov     rax, cs:__security_cookie
0x180028c1f  xor     rax, rsp
0x180028c22  mov     [rsp+20A8h+var_38], rax
0x180028c2a  mov     r14d, r9d
0x180028c2d  mov     r13d, r8d
0x180028c30  mov     rsi, rdx
0x180028c33  mov     [rsp+20A8h+var_2048], rdx
0x180028c38  mov     [rsp+20A8h+var_2078], rcx
0x180028c3d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028c44  mov     ecx, 20h ; ' '; unsigned __int64
0x180028c49  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028c4e  mov     rdi, rax
0x180028c51  mov     [rsp+20A8h+var_2068], rax
0x180028c56  xor     ebx, ebx
0x180028c58  test    rax, rax
0x180028c5b  jz      short loc_180028C9D
0x180028c5d  mov     [rax], rbx
0x180028c60  mov     [rax+8], rbx
0x180028c64  mov     [rax+10h], rbx
0x180028c68  mov     [rax+18h], ebx
0x180028c6b  mov     [rsp+20A8h+var_2068], rax
0x180028c70  test    rax, rax
0x180028c73  jnz     short loc_180028C7A
0x180028c75  mov     r15, rax
0x180028c78  jmp     short loc_180028CA8
0x180028c7a  mov     dword ptr [rsp+20A8h+lpString2], 1000h; unsigned int
0x180028c82  lea     r9, [rsp+20A8h+Str]; wchar_t *
0x180028c87  xor     edx, edx; wchar_t *
0x180028c89  lea     r8d, [rdx+1]; int
0x180028c8d  mov     rcx, [rsi+8]; wchar_t *
0x180028c91  call    ?GetDisplayFolderOrUrlHelper@@YAJPEB_W0HPEA_WK@Z; GetDisplayFolderOrUrlHelper(wchar_t const *,wchar_t const *,int,wchar_t *,ulong)
0x180028c96  mov     esi, eax
0x180028c98  mov     r15, rdi
0x180028c9b  jmp     short loc_180028CAD
0x180028c9d  mov     r15, rbx
0x180028ca0  mov     rdi, rbx
0x180028ca3  mov     [rsp+20A8h+var_2068], rbx
0x180028ca8  mov     esi, 8007000Eh
0x180028cad  lea     rcx, [rsp+20A8h+var_2070]
0x180028cb2  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180028cb7  nop
0x180028cb8  test    esi, esi
0x180028cba  js      loc_180028E0F
0x180028cc0  mov     r12d, ebx
0x180028cc3  test    r13d, r13d
0x180028cc6  jnz     short loc_180028D18
0x180028cc8  mov     r12d, 8000h
0x180028cce  cmp     r14d, 1
0x180028cd2  jnz     short loc_180028CDA
0x180028cd4  lea     esi, [r13+70h]
0x180028cd8  jmp     short loc_180028CF5
0x180028cda  cmp     r14d, 2
0x180028cde  jnz     short loc_180028CE6
0x180028ce0  lea     esi, [r14+6Fh]
0x180028ce4  jmp     short loc_180028CF5
0x180028ce6  mov     esi, 6Fh ; 'o'
0x180028ceb  lea     eax, [rsi+3]
0x180028cee  cmp     r14d, 3
0x180028cf2  cmovz   esi, eax
0x180028cf5  call    ?GetResourceLibrary@@YAAEAVCResourceLibrary@@XZ; GetResourceLibrary(void)
0x180028cfa  mov     rcx, rax
0x180028cfd  mov     r8d, esi
0x180028d00  lea     rdx, [rsp+20A8h+var_2070]
0x180028d05  call    ?LoadCString@@YAHAEAVCResourceLibrary@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@I@Z; LoadCString(CResourceLibrary &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,uint)
0x180028d0a  test    eax, eax
0x180028d0c  jnz     short loc_180028D18
0x180028d0e  mov     esi, 80004005h
0x180028d13  jmp     loc_180028E0F
0x180028d18  mov     edx, 2Fh ; '/'; Ch
0x180028d1d  lea     rcx, [rsp+20A8h+Str]; Str
0x180028d22  call    cs:__imp_wcsrchr
0x180028d28  test    rax, rax
0x180028d2b  jz      short loc_180028D33
0x180028d2d  add     rax, 2
0x180028d31  jmp     short loc_180028D38
0x180028d33  lea     rax, [rsp+20A8h+Str]
0x180028d38  mov     dword ptr [rsp+20A8h+lpString2], r12d; unsigned int
0x180028d3d  mov     r9, [rsp+20A8h+var_2070]; wchar_t *
0x180028d42  mov     r8, [rsp+20A8h+var_2048]
0x180028d47  mov     r8, [r8+8]; wchar_t *
0x180028d4b  mov     rdx, rax; psz
0x180028d4e  mov     rcx, r15; this
0x180028d51  call    ?Init@CDesktopSearchFolder@@QEAAJPEB_W00K@Z; CDesktopSearchFolder::Init(wchar_t const *,wchar_t const *,wchar_t const *,ulong)
0x180028d56  mov     esi, eax
0x180028d58  test    eax, eax
0x180028d5a  js      loc_180028E0F
0x180028d60  mov     rax, [rsp+20A8h+var_2078]
0x180028d65  add     rax, 78h ; 'x'
0x180028d69  mov     [rsp+20A8h+var_2060], rax
0x180028d6e  add     rax, 8
0x180028d72  mov     [rsp+20A8h+var_2058], rax
0x180028d77  mov     [rsp+20A8h+var_2050], rbx
0x180028d7c  lea     rcx, [rsp+20A8h+var_2060]
0x180028d81  call    ??E?$CTPtrSListIterator@VCDesktopSearchFolder@@@@QEAAAEAPEAVCDesktopSearchFolder@@XZ; CTPtrSListIterator<CDesktopSearchFolder>::operator++(void)
0x180028d86  or      r14d, 0FFFFFFFFh
0x180028d8a  mov     r8, [rax]
0x180028d8d  test    r8, r8
0x180028d90  jz      short loc_180028DDC
0x180028d92  mov     [rsp+20A8h+cchCount2], r14d; cchCount2
0x180028d97  mov     rax, [rdi]
0x180028d9a  mov     [rsp+20A8h+lpString2], rax; lpString2
0x180028d9f  mov     r9d, r14d; cchCount1
0x180028da2  mov     r8, [r8]; lpString1
0x180028da5  mov     edx, 1; dwCmpFlags
0x180028daa  lea     ecx, [rdx+7Eh]; Locale
0x180028dad  call    cs:__imp_CompareStringW
0x180028db3  cmp     eax, 1
0x180028db6  jnz     short loc_180028DD0
0x180028db8  mov     rdx, rdi
0x180028dbb  call    ?CreateLink@?$CTPtrSList@VCDesktopSearchFolder@@@@IEAAPEAV?$CTPtrSingleLink@VCDesktopSearchFolder@@@@PEAVCDesktopSearchFolder@@@Z; CTPtrSList<CDesktopSearchFolder>::CreateLink(CDesktopSearchFolder *)
0x180028dc0  mov     rcx, [rsp+20A8h+var_2060]
0x180028dc5  add     rcx, 8
0x180028dc9  mov     rdx, [rsp+20A8h+var_2050]
0x180028dce  jmp     short loc_180028DF7
0x180028dd0  lea     rcx, [rsp+20A8h+var_2060]
0x180028dd5  call    ??E?$CTPtrSListIterator@VCDesktopSearchFolder@@@@QEAAAEAPEAVCDesktopSearchFolder@@XZ; CTPtrSListIterator<CDesktopSearchFolder>::operator++(void)
0x180028dda  jmp     short loc_180028D8A
0x180028ddc  mov     rbx, [rsp+20A8h+var_2078]
0x180028de1  mov     rdx, rdi
0x180028de4  call    ?CreateLink@?$CTPtrSList@VCDesktopSearchFolder@@@@IEAAPEAV?$CTPtrSingleLink@VCDesktopSearchFolder@@@@PEAVCDesktopSearchFolder@@@Z; CTPtrSList<CDesktopSearchFolder>::CreateLink(CDesktopSearchFolder *)
0x180028de9  mov     rdx, [rbx+90h]; struct CSingleLink *
0x180028df0  lea     rcx, [rbx+80h]; this
0x180028df7  mov     r8, rax; struct CSingleLink *
0x180028dfa  call    ?InsertAfter@CLnkList@@IEAAXPEAVCSingleLink@@0@Z; CLnkList::InsertAfter(CSingleLink *,CSingleLink *)
0x180028dff  nop
0x180028e00  jmp     short loc_180028E1D
0x180028e02  mov     esi, dword ptr [rsp+20A8h+var_2078]
0x180028e06  test    esi, esi
0x180028e08  jns     short loc_180028E1D
0x180028e0a  mov     rdi, [rsp+20A8h+var_2068]
0x180028e0f  test    rdi, rdi
0x180028e12  jz      short loc_180028E1D
0x180028e14  mov     rcx, rdi; this
0x180028e17  call    ??_GCDesktopSearchFolder@@QEAAPEAXI@Z; CDesktopSearchFolder::`scalar deleting destructor'(uint)
0x180028e1c  nop
0x180028e1d  mov     rcx, [rsp+20A8h+var_2070]
0x180028e22  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180028e26  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028e2b  mov     eax, esi
0x180028e2d  mov     rcx, [rsp+20A8h+var_38]
0x180028e35  xor     rcx, rsp; StackCookie
0x180028e38  call    __security_check_cookie
0x180028e3d  lea     r11, [rsp+20A8h+var_28]
0x180028e45  mov     rbx, [r11+40h]
0x180028e49  mov     rsi, [r11+48h]
0x180028e4d  mov     rsp, r11
0x180028e50  pop     r15
0x180028e52  pop     r14
0x180028e54  pop     r13
0x180028e56  pop     r12
0x180028e58  pop     rdi
0x180028e59  retn
```
