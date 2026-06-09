# CShtOle::Bind(wchar_t const *,_GUID const &,IUnknown *,bool,int *,void * *,_GUID *)

- ea: `0x1800f05a4`
- end: `0x1800f0aba`
- name: `?Bind@CShtOle@@QEAAJPEB_WAEBU_GUID@@PEAUIUnknown@@_NPEAHPEAPEAXPEAU2@@Z`
- size: `1302`
- prototype: `__int64 __fastcall(CShtOle *this, const wchar_t *, const struct _GUID *, struct IUnknown *, bool, int *, void **, struct _GUID *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f035c`

## callees

- `0x18002f914`
- `0x180038f08`
- `0x1800f05a4`
- `0x1800f0c94`
- `0x1800f1254`
- `0x1800f12d8`
- `0x1800f7aa8`
- `0x18010b360`
- `0x180117984`
- `0x180118518`
- `0x1801199cc`
- `0x18012b9f4`
- `0x1801781b0`
- `0x180188d90`
- `0x180188dc0`
- `0x1801fdddc`
- `0x1801fde7c`
- `0x1801fdfac`
- `0x1801fe784`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f06a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f06a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f0667`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f0667`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f0a37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f0a37`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800f0617`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800f0617`

## string_xrefs

- `0x1800f08d7`: `%ws\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CShtOle::Bind(
        CShtOle *this,
        const wchar_t *a2,
        const struct _GUID *a3,
        struct IUnknown *a4,
        bool a5,
        int *a6,
        void **a7,
        struct _GUID *a8)
{
  CShtOle *v8; // r12
  int *v9; // r13
  LPWSTR ExtensionW; // rax
  __int64 *v11; // r15
  unsigned __int64 v12; // rdi
  signed int IsMssearchExcludedExtension; // esi
  __int64 i; // rdi
  int v15; // r14d
  CShtOle::CClassNode *v16; // rax
  struct CShtOle::CClassNode *v17; // r8
  HKEY v18; // rdx
  int v19; // eax
  HKEY v20; // rdx
  unsigned int v21; // r9d
  unsigned int v22; // r9d
  HKEY v23; // rdx
  unsigned int v24; // r9d
  CShtOle *v25; // rcx
  const struct _GUID *v26; // r9
  __int128 v27; // xmm6
  int v28; // eax
  HKEY v29; // rdx
  unsigned int v30; // r9d
  CShtOle *v31; // rcx
  const struct _GUID *v32; // r9
  __int64 *v33; // r14
  struct IUnknown *v34; // rdx
  const struct _GUID *v35; // r8
  unsigned int v37; // eax
  unsigned int v38; // eax
  int v39; // [rsp+20h] [rbp-398h]
  signed int v40; // [rsp+30h] [rbp-388h]
  wchar_t *v41; // [rsp+40h] [rbp-378h]
  struct _GUID v43; // [rsp+58h] [rbp-360h] BYREF
  __int64 *v44; // [rsp+68h] [rbp-350h]
  void **v45; // [rsp+70h] [rbp-348h]
  struct _GUID *v46; // [rsp+78h] [rbp-340h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-338h]
  struct _GUID v48; // [rsp+88h] [rbp-330h] BYREF
  HKEY phkResult[3]; // [rsp+98h] [rbp-320h] BYREF
  wchar_t v50[152]; // [rsp+B0h] [rbp-308h] BYREF
  wchar_t v51[200]; // [rsp+1E0h] [rbp-1D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  v8 = this;
  v9 = a6;
  v45 = a7;
  v46 = a8;
  if ( a6 )
    *a6 = 0;
  if ( !a2
    || (ExtensionW = PathFindExtensionW(a2), v11 = (__int64 *)ExtensionW, (v41 = ExtensionW) == 0)
    || !*ExtensionW )
  {
    v11 = &qword_1803108E0;
    v41 = (wchar_t *)&qword_1803108E0;
  }
  v12 = -1;
  do
    ++v12;
  while ( *((_WORD *)v11 + v12) );
  IsMssearchExcludedExtension = v12 > 0x40 ? 0x80070057 : 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)v8 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 24));
  if ( v12 > 0x40 )
    goto LABEL_50;
  IsMssearchExcludedExtension = CShtOle::IsMssearchExcludedExtension(v8, (const wchar_t *)v11);
  if ( IsMssearchExcludedExtension < 0 )
    goto LABEL_50;
  v44 = (__int64 *)((char *)v8 + 8);
  for ( i = *((_QWORD *)v8 + 1); i; i = *(_QWORD *)i )
  {
    if ( !(unsigned int)_o__wcsicmp(v11, i + 8) )
      goto LABEL_42;
  }
  if ( *((_WORD *)v11 + 1) && !*(_BYTE *)v8 && a5 )
  {
    v15 = 1;
    *(_BYTE *)v8 = 1;
  }
  else
  {
    v15 = 1;
  }
  v16 = (CShtOle::CClassNode *)operator new(0xF0u);
  i = CShtOle::CClassNode::CClassNode(v16, (const wchar_t *)v11, v17);
  try
  {
    v48 = 0;
    CRegAccess::CRegAccess(phkResult, v18, (const wchar_t *)v11);
    try
    {
      v19 = StringCchPrintfW(v51, 0xC8u, L"%ws\\PersistentHandler", v11);
      IsMssearchExcludedExtension = v19;
      v40 = v19;
      if ( v19 < 0 )
      {
        v37 = wil::verify_hresult<long>((unsigned int)v19);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x111,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\shtole.cxx",
          (const char *)v37,
          v39);
      }
      CRegAccess::CRegAccess((PHKEY)&v43, v20, v51);
      CRegAccess::Get((CRegAccess *)&v43, &psz, v50, v21);
      CShtOle::StringToGuid(v50, &v48);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v43);
    }
    catch ( ... )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58386382>::GetImpl'::`2'::impl) )
        indexer::result::details::result_from_caught_exception<1>(
          retaddr,
          287,
          "onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\shtole.cxx");
      v8 = this;
      if ( (unsigned int)CPolicyDisableList::IsForceEnabled((CShtOle *)((char *)this + 72), v41) )
      {
        IsMssearchExcludedExtension = StringCchPrintfW(v51, 0xC8u, L"%ws\\PersistentHandler", v41);
        if ( IsMssearchExcludedExtension < 0 )
        {
          v15 = 0;
        }
        else
        {
          CRegAccess::CRegAccess((PHKEY)&v43, v23, v51);
          CRegAccess::Get((CRegAccess *)&v43, L"OriginalPersistentHandler", v50, v24);
          CShtOle::StringToGuid(v50, &v48);
          v15 = 1;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v43);
        }
        if ( v15 )
          goto LABEL_29;
      }
      else
      {
        IsMssearchExcludedExtension = v40;
        v15 = 0;
      }
      CRegAccess::Get((CRegAccess *)phkResult, &psz, v50, v22);
LABEL_29:
      v9 = a6;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
    if ( v15 )
    {
      v27 = (__int128)*CShtOle::FindServerFromPHandler(
                         v25,
                         (struct _GUID *)phkResult,
                         &v48,
                         v26,
                         (struct CShtOle::CClassNode *)i);
    }
    else
    {
      v28 = StringCchPrintfW(v51, 0xC8u, L"%ws\\CLSID", v50);
      IsMssearchExcludedExtension = v28;
      if ( v28 < 0 )
      {
        v38 = wil::verify_hresult<long>((unsigned int)v28);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x152,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\shtole.cxx",
          (const char *)v38,
          v39);
      }
      CRegAccess::CRegAccess(phkResult, v29, v51);
      CRegAccess::Get((CRegAccess *)phkResult, &psz, v50, v30);
      CShtOle::StringToGuid(v50, &v48);
      *(struct _GUID *)(i + 140) = v48;
      v27 = (__int128)*CShtOle::FindServer(v31, &v43, &v48, v32, (struct CShtOle::CClassNode *)i);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
    }
    *(_OWORD *)(i + 156) = v27;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      354,
      "onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\shtole.cxx");
  }
  if ( i )
  {
    v33 = v44;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58386382>::GetImpl'::`2'::impl)
      && IsMssearchExcludedExtension < 0 )
    {
      CShtOle::CClassNode::ErrorEncountered((CShtOle::CClassNode *)i, IsMssearchExcludedExtension);
    }
    *(_QWORD *)i = *v33;
    *v33 = i;
  }
  if ( IsMssearchExcludedExtension >= 0 )
  {
    if ( i )
    {
LABEL_42:
      if ( !(unsigned int)CPolicyDisableList::IsDisabled((CShtOle *)((char *)v8 + 72), (const struct _GUID *)(i + 156)) )
      {
        if ( v45 )
        {
          IsMssearchExcludedExtension = CShtOle::CClassNode::CreateInstance((CShtOle::CClassNode *)i, v34, v35, v45);
          if ( IsMssearchExcludedExtension >= 0 )
          {
            if ( v9 )
              *v9 = *(_QWORD *)(i + 192) != 0;
          }
        }
        if ( v46 )
          *v46 = *(struct _GUID *)(i + 156);
        goto LABEL_50;
      }
    }
    IsMssearchExcludedExtension = -2147467259;
  }
LABEL_50:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)IsMssearchExcludedExtension;
}

```

## disassembly

```asm
0x1800f05a4  mov     rax, rsp
0x1800f05a7  mov     [rax+18h], rbx
0x1800f05ab  mov     [rax+20h], rsi
0x1800f05af  push    rdi
0x1800f05b0  push    r12
0x1800f05b2  push    r13
0x1800f05b4  push    r14
0x1800f05b6  push    r15
0x1800f05b8  sub     rsp, 390h
0x1800f05bf  movaps  xmmword ptr [rax-38h], xmm6
0x1800f05c3  mov     rax, cs:__security_cookie
0x1800f05ca  xor     rax, rsp
0x1800f05cd  mov     [rsp+3B8h+var_48], rax
0x1800f05d5  mov     r12, rcx
0x1800f05d8  mov     [rsp+3B8h+var_370], rcx
0x1800f05dd  mov     r13, [rsp+3B8h+arg_28]
0x1800f05e5  mov     [rsp+3B8h+var_368], r13
0x1800f05ea  mov     rax, [rsp+3B8h+arg_30]
0x1800f05f2  mov     [rsp+3B8h+var_348], rax
0x1800f05f7  mov     rax, [rsp+3B8h+arg_38]
0x1800f05ff  mov     [rsp+3B8h+var_340], rax
0x1800f0604  xor     ebx, ebx
0x1800f0606  test    r13, r13
0x1800f0609  jz      short loc_1800F060F
0x1800f060b  mov     [r13+0], ebx
0x1800f060f  test    rdx, rdx
0x1800f0612  jz      short loc_1800F062F
0x1800f0614  mov     rcx, rdx; pszPath
0x1800f0617  call    cs:__imp_PathFindExtensionW
0x1800f061d  mov     r15, rax
0x1800f0620  mov     [rsp+3B8h+var_378], rax
0x1800f0625  test    rax, rax
0x1800f0628  jz      short loc_1800F062F
0x1800f062a  cmp     bx, [rax]
0x1800f062d  jnz     short loc_1800F063B
0x1800f062f  lea     r15, qword_1803108E0
0x1800f0636  mov     [rsp+3B8h+var_378], r15
0x1800f063b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f063f  inc     rdi
0x1800f0642  cmp     [r15+rdi*2], bx
0x1800f0647  jnz     short loc_1800F063F
0x1800f0649  mov     r14d, 40h ; '@'
0x1800f064f  cmp     r14, rdi
0x1800f0652  sbb     esi, esi
0x1800f0654  and     esi, 80070057h
0x1800f065a  lea     rcx, [r12+18h]; lpCriticalSection
0x1800f065f  mov     [rsp+3B8h+lpCriticalSection], rcx
0x1800f0667  call    cs:__imp_EnterCriticalSection
0x1800f066d  nop
0x1800f066e  cmp     rdi, r14
0x1800f0671  ja      loc_1800F0A2F
0x1800f0677  mov     rdx, r15; wchar_t *
0x1800f067a  mov     rcx, r12; this
0x1800f067d  call    ?IsMssearchExcludedExtension@CShtOle@@AEAAJPEB_W@Z; CShtOle::IsMssearchExcludedExtension(wchar_t const *)
0x1800f0682  mov     esi, eax
0x1800f0684  test    eax, eax
0x1800f0686  js      loc_1800F0A2F
0x1800f068c  lea     rcx, [r12+8]
0x1800f0691  mov     [rsp+3B8h+var_350], rcx
0x1800f0696  mov     rdi, [rcx]
0x1800f0699  jmp     short loc_1800F06B3
0x1800f069b  lea     rdx, [rdi+8]
0x1800f069f  mov     rcx, r15
0x1800f06a2  call    cs:__imp__o__wcsicmp
0x1800f06a8  test    eax, eax
0x1800f06aa  jz      loc_1800F09D1
0x1800f06b0  mov     rdi, [rdi]
0x1800f06b3  test    rdi, rdi
0x1800f06b6  jnz     short loc_1800F069B
0x1800f06b8  cmp     [r15+2], bx
0x1800f06bd  jz      short loc_1800F06F4
0x1800f06bf  cmp     [r12], bl
0x1800f06c3  jnz     short loc_1800F06EB
0x1800f06c5  cmp     [rsp+3B8h+arg_20], bl
0x1800f06cc  jz      short loc_1800F06EB
0x1800f06ce  lea     r14d, [rdi+1]
0x1800f06d2  mov     [r12], r14b
0x1800f06d6  jmp     short loc_1800F06FA
0x1800f06d8  xor     ebx, ebx
0x1800f06da  mov     r15, [rsp+3B8h+var_378]
0x1800f06df  mov     r12, [rsp+3B8h+var_370]
0x1800f06e4  mov     r13, [rsp+3B8h+var_368]
0x1800f06e9  jmp     short loc_1800F06F4
0x1800f06eb  test    rdi, rdi
0x1800f06ee  jnz     loc_1800F09D1
0x1800f06f4  mov     r14d, 1
0x1800f06fa  mov     ecx, 0F0h; Size
0x1800f06ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f0704  mov     [rsp+3B8h+var_380], rax
0x1800f0709  mov     rdx, r15; wchar_t *
0x1800f070c  mov     rcx, rax; this
0x1800f070f  call    ??0CClassNode@CShtOle@@QEAA@PEB_WPEAV01@@Z; CShtOle::CClassNode::CClassNode(wchar_t const *,CShtOle::CClassNode *)
0x1800f0714  mov     rdi, rax
0x1800f0717  mov     [rsp+3B8h+var_380], rax
0x1800f071c  xorps   xmm0, xmm0
0x1800f071f  movups  xmmword ptr [rsp+3B8h+var_330.Data1], xmm0
0x1800f0727  mov     r8, r15; wchar_t *
0x1800f072a  lea     rcx, [rsp+3B8h+phkResult]; phkResult
0x1800f0732  call    ??0CRegAccess@@QEAA@PEAUHKEY__@@PEB_W@Z; CRegAccess::CRegAccess(HKEY__ *,wchar_t const *)
0x1800f0737  nop
0x1800f0738  mov     r9, r15
0x1800f073b  lea     r8, aWsPersistentha; "%ws\\PersistentHandler"
0x1800f0742  mov     edx, 0C8h; unsigned __int64
0x1800f0747  lea     rcx, [rsp+3B8h+var_1D8]; wchar_t *
0x1800f074f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800f0754  mov     esi, eax
0x1800f0756  mov     [rsp+3B8h+var_388], eax
0x1800f075a  test    eax, eax
0x1800f075c  js      loc_1800F0A71
0x1800f0762  lea     r8, [rsp+3B8h+var_1D8]; wchar_t *
0x1800f076a  lea     rcx, [rsp+3B8h+var_360]; phkResult
0x1800f076f  call    ??0CRegAccess@@QEAA@PEAUHKEY__@@PEB_W@Z; CRegAccess::CRegAccess(HKEY__ *,wchar_t const *)
0x1800f0774  nop
0x1800f0775  lea     r8, [rsp+3B8h+var_308]; wchar_t *
0x1800f077d  lea     rdx, psz; wchar_t *
0x1800f0784  lea     rcx, [rsp+3B8h+var_360]; this
0x1800f0789  call    ?Get@CRegAccess@@QEAAXPEB_WPEA_WI@Z; CRegAccess::Get(wchar_t const *,wchar_t *,uint)
0x1800f078e  lea     rdx, [rsp+3B8h+var_330]; struct _GUID *
0x1800f0796  lea     rcx, [rsp+3B8h+var_308]; wchar_t *
0x1800f079e  call    ?StringToGuid@CShtOle@@SAXPEB_WAEAU_GUID@@@Z; CShtOle::StringToGuid(wchar_t const *,_GUID &)
0x1800f07a3  nop
0x1800f07a4  lea     rcx, [rsp+3B8h+var_360]
0x1800f07a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f07ae  nop
0x1800f07af  jmp     loc_1800F089B
0x1800f07b4  mov     r12, [rsp+3B8h+var_370]
0x1800f07b9  lea     rcx, [r12+48h]; this
0x1800f07be  mov     rdx, [rsp+3B8h+var_378]; wchar_t *
0x1800f07c3  call    ?IsForceEnabled@CPolicyDisableList@@QEAAHPEB_W@Z; CPolicyDisableList::IsForceEnabled(wchar_t const *)
0x1800f07c8  xor     ebx, ebx
0x1800f07ca  test    eax, eax
0x1800f07cc  jz      loc_1800F086E
0x1800f07d2  mov     r9, [rsp+3B8h+var_378]
0x1800f07d7  lea     r8, aWsPersistentha; "%ws\\PersistentHandler"
0x1800f07de  mov     edx, 0C8h; unsigned __int64
0x1800f07e3  lea     rcx, [rsp+3B8h+var_1D8]; wchar_t *
0x1800f07eb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800f07f0  mov     esi, eax
0x1800f07f2  mov     [rsp+3B8h+var_388], eax
0x1800f07f6  test    eax, eax
0x1800f07f8  js      short loc_1800F0850
0x1800f07fa  lea     r8, [rsp+3B8h+var_1D8]; wchar_t *
0x1800f0802  lea     rcx, [rsp+3B8h+var_360]; phkResult
0x1800f0807  call    ??0CRegAccess@@QEAA@PEAUHKEY__@@PEB_W@Z; CRegAccess::CRegAccess(HKEY__ *,wchar_t const *)
0x1800f080c  nop
0x1800f080d  lea     r8, [rsp+3B8h+var_308]; wchar_t *
0x1800f0815  lea     rdx, aOriginalpersis; "OriginalPersistentHandler"
0x1800f081c  lea     rcx, [rsp+3B8h+var_360]; this
0x1800f0821  call    ?Get@CRegAccess@@QEAAXPEB_WPEA_WI@Z; CRegAccess::Get(wchar_t const *,wchar_t *,uint)
0x1800f0826  lea     rdx, [rsp+3B8h+var_330]; struct _GUID *
0x1800f082e  lea     rcx, [rsp+3B8h+var_308]; wchar_t *
0x1800f0836  call    ?StringToGuid@CShtOle@@SAXPEB_WAEAU_GUID@@@Z; CShtOle::StringToGuid(wchar_t const *,_GUID &)
0x1800f083b  lea     r14d, [rbx+1]
0x1800f083f  mov     [rsp+3B8h+var_384], r14d
0x1800f0844  lea     rcx, [rsp+3B8h+var_360]
0x1800f0849  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f084e  jmp     short loc_1800F0855
0x1800f0850  mov     r14d, [rsp+3B8h+var_384]
0x1800f0855  jmp     short loc_1800F0867
0x1800f0857  xor     ebx, ebx
0x1800f0859  mov     esi, [rsp+3B8h+var_388]
0x1800f085d  mov     r14d, [rsp+3B8h+var_384]
0x1800f0862  mov     r12, [rsp+3B8h+var_370]
0x1800f0867  test    r14d, r14d
0x1800f086a  jz      short loc_1800F0875
0x1800f086c  jmp     short loc_1800F0891
0x1800f086e  mov     esi, [rsp+3B8h+var_388]
0x1800f0872  mov     r14d, ebx
0x1800f0875  lea     r8, [rsp+3B8h+var_308]; wchar_t *
0x1800f087d  lea     rdx, psz; wchar_t *
0x1800f0884  lea     rcx, [rsp+3B8h+phkResult]; this
0x1800f088c  call    ?Get@CRegAccess@@QEAAXPEB_WPEA_WI@Z; CRegAccess::Get(wchar_t const *,wchar_t *,uint)
0x1800f0891  mov     r13, [rsp+3B8h+var_368]
0x1800f0896  mov     rdi, [rsp+3B8h+var_380]
0x1800f089b  lea     rcx, [rsp+3B8h+phkResult]
0x1800f08a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f08a8  test    r14d, r14d
0x1800f08ab  jz      short loc_1800F08CF
0x1800f08ad  mov     qword ptr [rsp+3B8h+var_398], rdi; struct CShtOle::CClassNode *
0x1800f08b2  lea     r8, [rsp+3B8h+var_330]; struct _GUID *
0x1800f08ba  lea     rdx, [rsp+3B8h+phkResult]; retstr
0x1800f08c2  call    ?FindServerFromPHandler@CShtOle@@AEAA?AU_GUID@@AEBU2@0PEAVCClassNode@1@@Z; CShtOle::FindServerFromPHandler(_GUID const &,_GUID const &,CShtOle::CClassNode *)
0x1800f08c7  movups  xmm6, xmmword ptr [rax]
0x1800f08ca  jmp     loc_1800F0978
0x1800f08cf  lea     r9, [rsp+3B8h+var_308]
0x1800f08d7  lea     r8, aWsClsid; "%ws\\CLSID"
0x1800f08de  mov     edx, 0C8h; unsigned __int64
0x1800f08e3  lea     rcx, [rsp+3B8h+var_1D8]; wchar_t *
0x1800f08eb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800f08f0  mov     esi, eax
0x1800f08f2  test    eax, eax
0x1800f08f4  js      loc_1800F0A95
0x1800f08fa  lea     r8, [rsp+3B8h+var_1D8]; wchar_t *
0x1800f0902  lea     rcx, [rsp+3B8h+phkResult]; phkResult
0x1800f090a  call    ??0CRegAccess@@QEAA@PEAUHKEY__@@PEB_W@Z; CRegAccess::CRegAccess(HKEY__ *,wchar_t const *)
0x1800f090f  nop
0x1800f0910  lea     r8, [rsp+3B8h+var_308]; wchar_t *
0x1800f0918  lea     rdx, psz; wchar_t *
0x1800f091f  lea     rcx, [rsp+3B8h+phkResult]; this
0x1800f0927  call    ?Get@CRegAccess@@QEAAXPEB_WPEA_WI@Z; CRegAccess::Get(wchar_t const *,wchar_t *,uint)
0x1800f092c  lea     rdx, [rsp+3B8h+var_330]; struct _GUID *
0x1800f0934  lea     rcx, [rsp+3B8h+var_308]; wchar_t *
0x1800f093c  call    ?StringToGuid@CShtOle@@SAXPEB_WAEAU_GUID@@@Z; CShtOle::StringToGuid(wchar_t const *,_GUID &)
0x1800f0941  movups  xmm0, xmmword ptr [rsp+3B8h+var_330.Data1]
0x1800f0949  movdqu  xmmword ptr [rdi+8Ch], xmm0
0x1800f0951  mov     qword ptr [rsp+3B8h+var_398], rdi; struct CShtOle::CClassNode *
0x1800f0956  lea     r8, [rsp+3B8h+var_330]; struct _GUID *
0x1800f095e  lea     rdx, [rsp+3B8h+var_360]; retstr
0x1800f0963  call    ?FindServer@CShtOle@@AEAA?AU_GUID@@AEBU2@0PEAVCClassNode@1@@Z; CShtOle::FindServer(_GUID const &,_GUID const &,CShtOle::CClassNode *)
0x1800f0968  movups  xmm6, xmmword ptr [rax]
0x1800f096b  lea     rcx, [rsp+3B8h+phkResult]
0x1800f0973  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f0978  movdqu  xmmword ptr [rdi+9Ch], xmm6
0x1800f0980  jmp     short loc_1800F0997
0x1800f0982  xor     ebx, ebx
0x1800f0984  mov     esi, [rsp+3B8h+var_388]
0x1800f0988  mov     rdi, [rsp+3B8h+var_380]
0x1800f098d  mov     r12, [rsp+3B8h+var_370]
0x1800f0992  mov     r13, [rsp+3B8h+var_368]
0x1800f0997  test    rdi, rdi
0x1800f099a  jz      short loc_1800F09C8
0x1800f099c  mov     r14, [rsp+3B8h+var_350]
0x1800f09a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58386382@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58386382@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382> `wil::Feature<__WilFeatureTraits_Feature_58386382>::GetImpl(void)'::`2'::impl
0x1800f09a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58386382@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382>::__private_IsEnabled(void)
0x1800f09ad  test    al, al
0x1800f09af  jz      short loc_1800F09BF
0x1800f09b1  test    esi, esi
0x1800f09b3  jns     short loc_1800F09BF
0x1800f09b5  mov     edx, esi; unsigned int
0x1800f09b7  mov     rcx, rdi; this
0x1800f09ba  call    ?ErrorEncountered@CClassNode@CShtOle@@QEAAXK@Z; CShtOle::CClassNode::ErrorEncountered(ulong)
0x1800f09bf  mov     rax, [r14]
0x1800f09c2  mov     [rdi], rax
0x1800f09c5  mov     [r14], rdi
0x1800f09c8  test    esi, esi
0x1800f09ca  js      short loc_1800F0A2F
0x1800f09cc  test    rdi, rdi
0x1800f09cf  jz      short loc_1800F0A2A
0x1800f09d1  lea     rdx, [rdi+9Ch]; struct _GUID *
0x1800f09d8  lea     rcx, [r12+48h]; this
0x1800f09dd  call    ?IsDisabled@CPolicyDisableList@@QEAAHAEBU_GUID@@@Z; CPolicyDisableList::IsDisabled(_GUID const &)
0x1800f09e2  test    eax, eax
0x1800f09e4  jnz     short loc_1800F0A2A
0x1800f09e6  mov     r9, [rsp+3B8h+var_348]; void **
0x1800f09eb  test    r9, r9
0x1800f09ee  jz      short loc_1800F0A13
0x1800f09f0  mov     rcx, rdi; this
0x1800f09f3  call    ?CreateInstance@CClassNode@CShtOle@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CShtOle::CClassNode::CreateInstance(IUnknown *,_GUID const &,void * *)
0x1800f09f8  mov     esi, eax
0x1800f09fa  test    eax, eax
0x1800f09fc  js      short loc_1800F0A13
0x1800f09fe  test    r13, r13
0x1800f0a01  jz      short loc_1800F0A13
0x1800f0a03  mov     eax, ebx
0x1800f0a05  cmp     [rdi+0C0h], rbx
0x1800f0a0c  setnz   al
0x1800f0a0f  mov     [r13+0], eax
0x1800f0a13  mov     rax, [rsp+3B8h+var_340]
0x1800f0a18  test    rax, rax
0x1800f0a1b  jz      short loc_1800F0A2F
0x1800f0a1d  movups  xmm0, xmmword ptr [rdi+9Ch]
0x1800f0a24  movdqu  xmmword ptr [rax], xmm0
0x1800f0a28  jmp     short loc_1800F0A2F
0x1800f0a2a  mov     esi, 80004005h
0x1800f0a2f  mov     rcx, [rsp+3B8h+lpCriticalSection]; lpCriticalSection
0x1800f0a37  call    cs:__imp_LeaveCriticalSection
0x1800f0a3d  mov     eax, esi
0x1800f0a3f  mov     rcx, [rsp+3B8h+var_48]
0x1800f0a47  xor     rcx, rsp; StackCookie
0x1800f0a4a  call    __security_check_cookie
0x1800f0a4f  lea     r11, [rsp+3B8h+var_28]
0x1800f0a57  mov     rbx, [r11+40h]
0x1800f0a5b  mov     rsi, [r11+48h]
0x1800f0a5f  movaps  xmm6, xmmword ptr [r11-10h]
0x1800f0a64  mov     rsp, r11
0x1800f0a67  pop     r15
0x1800f0a69  pop     r14
0x1800f0a6b  pop     r13
0x1800f0a6d  pop     r12
0x1800f0a6f  pop     rdi
0x1800f0a70  retn
0x1800f0a71  mov     ecx, eax
0x1800f0a73  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800f0a78  mov     r9d, eax; char *
0x1800f0a7b  mov     rcx, [rsp+3B8h]; this
0x1800f0a83  lea     r8, aOnecoreuapBase_229; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f0a8a  mov     edx, 111h; void *
0x1800f0a8f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f0a95  mov     ecx, eax
0x1800f0a97  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800f0a9c  mov     r9d, eax; char *
0x1800f0a9f  mov     rcx, [rsp+3B8h]; this
0x1800f0aa7  lea     r8, aOnecoreuapBase_229; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f0aae  mov     edx, 152h; void *
0x1800f0ab3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
