# CGatherApplication::InitNew(CRegistry *,wchar_t const *,wchar_t const *,wchar_t const *,CGatherApplication *)

- ea: `0x1800e2540`
- end: `0x1800e2ed0`
- name: `?InitNew@CGatherApplication@@QEAAJPEAVCRegistry@@PEB_W11PEAV1@@Z`
- size: `2448`
- prototype: `__int64 __usercall@<rax>(CGatherApplication *__hidden this@<rcx>, struct CRegistry *@<rdx>, const wchar_t *@<r8>, const wchar_t *@<r9>, const wchar_t *, struct CGatherApplication *)`
- caller_count: `2`
- callee_count: `49`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e61a8`
- `0x180199260`

## callees

- `0x18000a23c`
- `0x1800269b0`
- `0x18002751c`
- `0x18002dc6c`
- `0x1800495c0`
- `0x180054cb8`
- `0x180054e14`
- `0x1800555f0`
- `0x180056610`
- `0x1800569e0`
- `0x18005edc4`
- `0x18006a040`
- `0x18006a618`
- `0x1800781e8`
- `0x180078ac0`
- `0x18007a620`
- `0x1800800f4`
- `0x1800995c8`
- `0x1800b0760`
- `0x1800b2d2c`
- `0x1800bdfcc`
- `0x1800bfb94`
- `0x1800e2374`
- `0x1800e2540`
- `0x1800e4520`
- `0x1800e95f0`
- `0x1800f5a4c`
- `0x1800f89d0`
- `0x1800fab54`
- `0x1801010c4`
- `0x180108190`
- `0x180109ebc`
- `0x180116cd4`
- `0x1801244c0`
- `0x1801710cc`
- `0x180193d18`
- `0x180198238`
- `0x180198288`
- `0x1801982d8`
- `0x180198384`
- `0x180198430`
- `0x1801984dc`
- `0x180198570`
- `0x18019861c`
- `0x180198e60`
- `0x1801adfa4`
- `0x180207dd4`
- `0x180207ea8`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e261b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e281b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e261b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e281b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e2d69`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e2d69`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800e2a2c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800e2a2c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e2a5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e2a5d`

## string_xrefs

- `0x1800e2b3b`: `PluginManagers`
- `0x1800e2808`: `ApplicationPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
signed int __fastcall CGatherApplication::InitNew(
        CGatherApplication *this,
        struct CRegistry *a2,
        wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        struct CGatherApplication *a6)
{
  signed int result; // eax
  char *v11; // r12
  int v12; // eax
  __int64 v13; // rax
  int v14; // ebx
  const wchar_t *v15; // rdx
  int DirectoryDeepNoThrow; // eax
  signed int LastError; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 RootRegistryKeyName; // rax
  __int64 v21; // rax
  int v22; // ebx
  __int64 v23; // rax
  int v24; // ebx
  HRESULT v25; // ebx
  __int64 v26; // rax
  _QWORD *v27; // r15
  __int64 (__fastcall ***v28)(_QWORD, GUID *, struct CAccessControl **); // rdi
  __int64 (__fastcall *v29)(_QWORD, GUID *, struct CAccessControl **); // rbx
  int v30; // eax
  const char *v31; // r9
  const char *v32; // r9
  signed int Blob; // edi
  const wchar_t *v34; // r8
  const wchar_t *v35; // rdx
  CGatheringService *v36; // rcx
  struct CGthrPrj *v37; // rbx
  int v38; // eax
  int v39; // eax
  wchar_t *v40; // rbx
  const char *v41; // r9
  int v42; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-438h]
  int ppva; // [rsp+20h] [rbp-438h]
  struct CAccessControl *v45; // [rsp+50h] [rbp-408h] BYREF
  struct CGthrPrj *v46; // [rsp+58h] [rbp-400h] BYREF
  wchar_t *v47; // [rsp+60h] [rbp-3F8h] BYREF
  _DWORD v48[2]; // [rsp+68h] [rbp-3F0h] BYREF
  _BYTE *v49; // [rsp+70h] [rbp-3E8h]
  __int64 v50; // [rsp+78h] [rbp-3E0h]
  int v51; // [rsp+80h] [rbp-3D8h]
  CGatherApplication *v52; // [rsp+88h] [rbp-3D0h]
  wchar_t *v53; // [rsp+90h] [rbp-3C8h]
  CRegistry *v54; // [rsp+98h] [rbp-3C0h]
  _BYTE v55[160]; // [rsp+A0h] [rbp-3B8h] BYREF
  GUID clsid; // [rsp+140h] [rbp-318h] BYREF
  const int *v57; // [rsp+150h] [rbp-308h] BYREF
  wchar_t *v58; // [rsp+158h] [rbp-300h]
  __int64 v59; // [rsp+160h] [rbp-2F8h]
  __int16 v60; // [rsp+168h] [rbp-2F0h] BYREF
  _BYTE v61[20]; // [rsp+1F0h] [rbp-268h] BYREF
  int v62; // [rsp+204h] [rbp-254h]
  _BYTE v63[192]; // [rsp+290h] [rbp-1C8h] BYREF
  _BYTE v64[192]; // [rsp+350h] [rbp-108h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+0h]

  v52 = this;
  v54 = a2;
  v53 = a3;
  v46 = a6;
  SearchIndexerTrace::Critical(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\gthrapp.cxx\"",
    (const wchar_t *)0x1AA,
    (unsigned int)L"[SrchGatherSvc] Initialize New Application: %ls called ",
    a3);
  if ( !a2 || !a3 || !*a3 || !a4 || !a5 || !*a5 )
    return -2147024809;
  CLMString::operator=((char *)this + 272, a3);
  if ( !(*(unsigned int (__fastcall **)(struct CRegistry *, wchar_t *))(*(_QWORD *)a2 + 24LL))(a2, a3) )
  {
    result = GetLastError();
    if ( result != 183 )
      goto LABEL_11;
    (*(void (__fastcall **)(struct CRegistry *, wchar_t *))(*(_QWORD *)a2 + 32LL))(a2, a3);
    if ( !(*(unsigned int (__fastcall **)(struct CRegistry *, wchar_t *))(*(_QWORD *)a2 + 24LL))(a2, a3) )
    {
      result = GetLastError();
LABEL_11:
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
  }
  v58 = (wchar_t *)&v60;
  v59 = 65;
  v60 = 0;
  v57 = &CCICommonPathString::`vftable';
  *((_BYTE *)this + 368) = a6 != 0;
  v11 = (char *)this + 32;
  v12 = CRegistry::Init(
          (CGatherApplication *)((char *)this + 32),
          *((HKEY *)a2 + 22),
          a3,
          0xF003Fu,
          *((const wchar_t **)a2 + 2));
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
      (const char *)(unsigned int)v12,
      (int)ppv);
  CSearchRootRegistry::CSearchRootRegistry(
    (CSearchRootRegistry *)v64,
    (const wchar_t *)((unsigned __int64)a3 & -(__int64)(*((_BYTE *)this + 368) != 0)),
    0x20019u);
  CRegistry::CRegistry((CRegistry *)v63, (struct CRegistry *)v64, L"Applications", 0xF003Fu);
  CRegistry::CreateSubKey((CRegistry *)v63, a3);
  v13 = TLMString<32,32,1024>::TLMString<32,32,1024>(v61, a5);
  v14 = CGatherApplication::SetGathererPlugin(this, v13);
  TLMString<32,32,1024>::~TLMString<32,32,1024>(v61);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
      (const char *)(unsigned int)v14,
      (int)ppv);
  CLMString::operator=(&v57, a4);
  DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(v58, v15);
  if ( DirectoryDeepNoThrow < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
      (const char *)(unsigned int)DirectoryDeepNoThrow,
      (int)ppv);
  CGatherApplication::CreateDirectoryWithSecurity(this, v58, a3);
  AppendBackSlashIf((struct CLMString *)&v57);
  TLMString<192,64,32767>::operator=((char *)this + 2048, &v57);
  if ( CRegistry::SetValue(
         (CGatherApplication *)((char *)this + 32),
         L"ApplicationPath",
         (CGatherApplication *)((char *)this + 2048)) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError == -2147024890 )
      LastError = -2147218172;
  }
  if ( LastError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E8,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
      (const char *)(unsigned int)LastError,
      (int)ppv);
  CLMString::Append((CLMString *)&v57, L"Projects", 0xFFFFFFFF);
  CGatherApplication::CreateDirectoryWithSecurity(this, v58, a3);
  v18 = TLMString<64,64,32767>::TLMString<64,64,32767>(v61, &v57);
  v19 = CGatherApplication::SetDefaultProjectPath(this, v18);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
      (const char *)(unsigned int)v19,
      (int)ppv);
  RootRegistryKeyName = GetRootRegistryKeyName(v61);
  v21 = TLMString<64,64,32767>::TLMString<64,64,32767>(v55, RootRegistryKeyName);
  v22 = CGatherApplication::SetDefaultCatalogConfigUrl(this, v21);
  TLMString<32,32,1024>::~TLMString<32,32,1024>(v61);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
      (const char *)(unsigned int)v22,
      (int)ppv);
  TLMString<192,64,32767>::operator=(&v57, (char *)this + 2048);
  CLMString::Append((CLMString *)&v57, L"GatherLogs", 0xFFFFFFFF);
  CGatherApplication::CreateDirectoryWithSecurity(this, v58, a3);
  v23 = TLMString<64,64,32767>::TLMString<64,64,32767>(v55, &v57);
  v24 = CGatherApplication::SetGatherLogsPath(this, v23);
  if ( v24 >= 0 )
  {
    TLMString<32,32,1024>::TLMString<32,32,1024>(v61, a5);
    v25 = CGatherApplication::SetGathererPlugin(this, v61);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(v61);
    clsid = 0;
    if ( v25 >= 0 )
    {
      v26 = TLMString<32,32,1024>::TLMString<32,32,1024>(v61, (char *)this + 272);
      v25 = CGatherApplication::SetDisplayName(this, v26);
      if ( v25 >= 0 )
      {
        v25 = CLSIDFromProgID(*((LPCOLESTR *)this + 159), &clsid);
        if ( v25 >= 0 )
        {
          v27 = (_QWORD *)((char *)this + 1360);
          v25 = CoCreateInstance(&clsid, 0, 0x17u, &GUID_c7310558_ac80_11d1_8df3_00c04fb6ef4f, (LPVOID *)this + 170);
          if ( v25 >= 0 )
          {
            if ( *((_BYTE *)this + 368) )
            {
              v45 = 0;
              v28 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct CAccessControl **))*v27;
              v29 = **(__int64 (__fastcall ***)(_QWORD, GUID *, struct CAccessControl **))*v27;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
              v30 = v29(v28, &GUID_c5a782aa_b7fe_45ab_bcb6_84d2f514acd4, &v45);
              if ( v30 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x219,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
                  (const char *)(unsigned int)v30,
                  (int)ppv);
              (*(void (__fastcall **)(struct CAccessControl *))(*(_QWORD *)v45 + 24LL))(v45);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
            }
            v25 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD))(*(_QWORD *)*v27 + 24LL))(
                    *v27,
                    a3,
                    *((_QWORD *)this + 217));
            (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v27 + 96LL))(*v27, *((_QWORD *)this + 313));
          }
        }
      }
    }
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x222,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
        (const char *)(unsigned int)v25,
        (int)ppv);
    if ( !(*(unsigned int (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v11 + 24LL))(
            (char *)this + 32,
            L"PluginManagers") )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x226,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
        v31);
    if ( !(*(unsigned int (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v11 + 24LL))(
            (char *)this + 32,
            L"Projects") )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x22B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
        v32);
    CGatherApplication::SetDataTimeout(this, 0);
    CGatherApplication::SetConnectTimeout(this, 0);
    CGatherApplication::SetRetryLimit(this, 0);
    Blob = CGatherApplication::SetFilterSecurity(this, 1);
    if ( Blob >= 0 )
    {
      Blob = CPluginMgrCollection::Init((CGatherApplication *)((char *)this + 864), this, v34);
      if ( Blob >= 0 )
      {
        Blob = CGatherPrjCollection::Init((CGatherApplication *)((char *)this + 376), v35, this, 0, 0);
        if ( Blob >= 0 )
        {
          Blob = CAccessControlImpl::Init(
                   (CGatherApplication *)((char *)this + 1368),
                   (CGatherApplication *)((char *)this + 32),
                   0,
                   0);
          if ( Blob >= 0 )
          {
            v45 = 0;
            CGatheringService::GetAccessControl(v36, &v45);
            Blob = v45 == 0 ? 0x80040D23 : 0;
            v50 = 0;
            LODWORD(v49) = 0;
            v48[0] = 0;
            v51 = 0;
            if ( v45 )
            {
              Blob = CAccessControlImpl::GetBlob(v45, (struct CBlob *)v48);
              if ( Blob >= 0 )
                Blob = CAccessControlImpl::AssignFromBlob(
                         (CGatherApplication *)((char *)this + 1368),
                         (struct CBlob *)v48);
            }
            CBlob::Free((CBlob *)v48);
            TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v45);
            if ( Blob >= 0 )
              *((_DWORD *)this + 93) = 1;
          }
        }
      }
    }
    if ( *((_BYTE *)this + 368) )
    {
      v37 = v46;
      v38 = TCollection_IApplicationPlugins___GUID_b05651c1_9b10_425e_b616_1fcd828db3b1__LIBID_MSSITLB_CPluginManager_CNamedISList_CPluginManager_IApplicationPlugin__CNamedListIter_CPluginManager_IApplicationPlugin__IApplicationPlugin___GUID_b05651c2_9b10_425e_b616_1fcd828db3b1__ObjectToVariant_CPluginManager___::ForEachItem__lambda_fe5bfd11bc666f9732241be37e7d47e2___(
              (char *)v46 + 864,
              this);
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x26D,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
          (const char *)(unsigned int)v38,
          (int)ppv);
      TLMString<32,32,1024>::TLMString<32,32,1024>(v61, L"SystemIndex");
      v48[0] = 0;
      v48[1] = v62;
      v49 = v61;
      v46 = 0;
      v39 = CGatherPrjCollection::LookupProject(
              (struct CGthrPrj *)((char *)v37 + 376),
              (struct CLMSubStr *)v48,
              &v46,
              0,
              0);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x272,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
          (const char *)(unsigned int)v39,
          ppva);
      v40 = SysAllocString(L"SystemIndex");
      v47 = v40;
      if ( !v40 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x275,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
          v41);
      v45 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      v42 = CGatherPrjCollection::AddInternal(
              (CGatherApplication *)((char *)this + 376),
              v40,
              0,
              -1,
              0,
              0,
              0,
              v46,
              &v45);
      if ( v42 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x280,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gthrapp.cxx",
          (const char *)(unsigned int)v42,
          (int)ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v47);
      TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v46);
      TLMString<32,32,1024>::~TLMString<32,32,1024>(v61);
    }
    CRegistry::~CRegistry((CRegistry *)v63);
    CRegistry::~CRegistry((CRegistry *)v64);
    LODWORD(ppv) = Blob;
    SearchIndexerTrace::Critical(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\gthrapp.cxx\"",
      (const wchar_t *)0x299,
      (unsigned int)L"[SrchGatherSvc] Leaving Initialize New Application: %ls ; hr=0x%08x ",
      a3,
      ppv);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v57);
    return Blob;
  }
  else
  {
    CRegistry::~CRegistry((CRegistry *)v63);
    CRegistry::~CRegistry((CRegistry *)v64);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v57);
    return v24;
  }
}

```

## disassembly

```asm
0x1800e2540  push    rbx
0x1800e2542  push    rsi
0x1800e2543  push    rdi
0x1800e2544  push    r12
0x1800e2546  push    r13
0x1800e2548  push    r14
0x1800e254a  push    r15
0x1800e254c  sub     rsp, 420h
0x1800e2553  mov     rax, cs:__security_cookie
0x1800e255a  xor     rax, rsp
0x1800e255d  mov     [rsp+458h+var_48], rax
0x1800e2565  mov     rdi, r9
0x1800e2568  mov     r14, r8
0x1800e256b  mov     rbx, rdx
0x1800e256e  mov     rsi, rcx
0x1800e2571  mov     [rsp+458h+var_3D0], rcx
0x1800e2579  mov     [rsp+458h+var_3C0], rdx
0x1800e2581  mov     [rsp+458h+var_3C8], r8
0x1800e2589  mov     r15, [rsp+458h+arg_20]
0x1800e2591  mov     r12, [rsp+458h+arg_28]
0x1800e2599  mov     [rsp+458h+var_400], r12
0x1800e259e  mov     r9, r8; wchar_t *
0x1800e25a1  lea     r8, aSrchgathersvcI_5; "[SrchGatherSvc] Initialize New Applicat"...
0x1800e25a8  mov     edx, 1AAh; wchar_t *
0x1800e25ad  lea     rcx, aOnecoreuapBase_51; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800e25b4  call    ?Critical@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Critical(wchar_t const *,uint,wchar_t const *,...)
0x1800e25b9  xor     eax, eax
0x1800e25bb  test    rbx, rbx
0x1800e25be  jz      loc_1800E2EA8
0x1800e25c4  test    r14, r14
0x1800e25c7  jz      loc_1800E2EA8
0x1800e25cd  cmp     [r14], ax
0x1800e25d1  jz      loc_1800E2EA8
0x1800e25d7  test    rdi, rdi
0x1800e25da  jz      loc_1800E2EA8
0x1800e25e0  test    r15, r15
0x1800e25e3  jz      loc_1800E2EA8
0x1800e25e9  cmp     [r15], ax
0x1800e25ed  jz      loc_1800E2EA8
0x1800e25f3  lea     r13, [rsi+110h]
0x1800e25fa  mov     rdx, r14
0x1800e25fd  mov     rcx, r13
0x1800e2600  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800e2605  mov     rax, [rbx]
0x1800e2608  mov     rdx, r14
0x1800e260b  mov     rcx, rbx
0x1800e260e  mov     rax, [rax+18h]
0x1800e2612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2617  test    eax, eax
0x1800e2619  jnz     short loc_1800E266B
0x1800e261b  call    cs:__imp_GetLastError
0x1800e2621  cmp     eax, 0B7h
0x1800e2626  jnz     short loc_1800E2656
0x1800e2628  mov     rax, [rbx]
0x1800e262b  mov     rdx, r14
0x1800e262e  mov     rcx, rbx
0x1800e2631  mov     rax, [rax+20h]
0x1800e2635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e263a  mov     rax, [rbx]
0x1800e263d  mov     rdx, r14
0x1800e2640  mov     rcx, rbx
0x1800e2643  mov     rax, [rax+18h]
0x1800e2647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e264c  test    eax, eax
0x1800e264e  jnz     short loc_1800E266B
0x1800e2650  call    cs:__imp_GetLastError
0x1800e2656  test    eax, eax
0x1800e2658  jle     loc_1800E2EAD
0x1800e265e  movzx   eax, ax
0x1800e2661  or      eax, 80070000h
0x1800e2666  jmp     loc_1800E2EAD
0x1800e266b  lea     rax, [rsp+458h+var_2F0]
0x1800e2673  mov     [rsp+458h+var_300], rax
0x1800e267b  mov     [rsp+458h+var_2F8], 41h ; 'A'
0x1800e2687  xor     eax, eax
0x1800e2689  mov     [rsp+458h+var_2F0], ax
0x1800e2691  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1800e2698  mov     [rsp+458h+var_308], rax
0x1800e26a0  test    r12, r12
0x1800e26a3  setnz   al
0x1800e26a6  mov     [rsi+170h], al
0x1800e26ac  lea     r12, [rsi+20h]
0x1800e26b0  mov     rax, [rbx+10h]
0x1800e26b4  mov     [rsp+458h+ppv], rax; int
0x1800e26b9  mov     r9d, 0F003Fh; unsigned int
0x1800e26bf  mov     r8, r14; wchar_t *
0x1800e26c2  mov     rdx, [rbx+0B0h]; HKEY
0x1800e26c9  mov     rcx, r12; this
0x1800e26cc  call    ?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z; CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x1800e26d1  mov     rcx, [rsp+458h]; this
0x1800e26d9  test    eax, eax
0x1800e26db  jns     short loc_1800E26F1
0x1800e26dd  mov     r9d, eax; char *
0x1800e26e0  lea     r8, aOnecoreuapBase_222; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e26e7  mov     edx, 1D7h; void *
0x1800e26ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e26f1  mov     al, [rsi+170h]
0x1800e26f7  neg     al
0x1800e26f9  sbb     rdx, rdx
0x1800e26fc  and     rdx, r14; wchar_t *
0x1800e26ff  mov     r8d, 20019h; unsigned int
0x1800e2705  lea     rcx, [rsp+458h+var_108]; this
0x1800e270d  call    ??0CSearchRootRegistry@@QEAA@PEB_WK@Z; CSearchRootRegistry::CSearchRootRegistry(wchar_t const *,ulong)
0x1800e2712  nop
0x1800e2713  mov     r9d, 0F003Fh; unsigned int
0x1800e2719  lea     r8, aApplications_0; "Applications"
0x1800e2720  lea     rdx, [rsp+458h+var_108]; struct CRegistry *
0x1800e2728  lea     rcx, [rsp+458h+var_1C8]; this
0x1800e2730  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x1800e2735  nop
0x1800e2736  mov     rdx, r14; wchar_t *
0x1800e2739  lea     rcx, [rsp+458h+var_1C8]; this
0x1800e2741  call    ?CreateSubKey@CRegistry@@UEAAHPEB_W@Z; CRegistry::CreateSubKey(wchar_t const *)
0x1800e2746  mov     rdx, r15
0x1800e2749  lea     rcx, [rsp+458h+var_268]
0x1800e2751  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800e2756  nop
0x1800e2757  mov     rdx, rax
0x1800e275a  mov     rcx, rsi
0x1800e275d  call    ?SetGathererPlugin@CGatherApplication@@QEAAJAEBV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; CGatherApplication::SetGathererPlugin(TLMString<32,32,1024> const &)
0x1800e2762  mov     ebx, eax
0x1800e2764  lea     rcx, [rsp+458h+var_268]
0x1800e276c  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800e2771  mov     rcx, [rsp+458h]; this
0x1800e2779  test    ebx, ebx
0x1800e277b  jns     short loc_1800E2791
0x1800e277d  mov     r9d, ebx; char *
0x1800e2780  lea     r8, aOnecoreuapBase_222; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e2787  mov     edx, 1DEh; void *
0x1800e278c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e2791  mov     rdx, rdi
0x1800e2794  lea     rcx, [rsp+458h+var_308]
0x1800e279c  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800e27a1  mov     rcx, [rsp+458h+var_300]; this
0x1800e27a9  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEB_W@Z; wil::CreateDirectoryDeepNoThrow(wchar_t const *)
0x1800e27ae  mov     rcx, [rsp+458h]; this
0x1800e27b6  test    eax, eax
0x1800e27b8  jns     short loc_1800E27CE
0x1800e27ba  mov     r9d, eax; char *
0x1800e27bd  lea     r8, aOnecoreuapBase_222; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e27c4  mov     edx, 1E2h; void *
0x1800e27c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e27ce  mov     r8, r14; wchar_t *
0x1800e27d1  mov     rdx, [rsp+458h+var_300]; wchar_t *
0x1800e27d9  mov     rcx, rsi; this
0x1800e27dc  call    ?CreateDirectoryWithSecurity@CGatherApplication@@IEAAXPEB_W0@Z; CGatherApplication::CreateDirectoryWithSecurity(wchar_t const *,wchar_t const *)
0x1800e27e1  lea     rcx, [rsp+458h+var_308]; struct CLMString *
0x1800e27e9  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x1800e27ee  lea     rdi, [rsi+800h]
0x1800e27f5  lea     rdx, [rsp+458h+var_308]
0x1800e27fd  mov     rcx, rdi
0x1800e2800  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1800e2805  mov     r8, rdi; struct CLMString *
0x1800e2808  lea     rdx, aApplicationpat; "ApplicationPath"
0x1800e280f  mov     rcx, r12; this
0x1800e2812  call    ?SetValue@CRegistry@@QEAAHPEB_WAEBVCLMString@@@Z; CRegistry::SetValue(wchar_t const *,CLMString const &)
0x1800e2817  test    eax, eax
0x1800e2819  jnz     short loc_1800E283C
0x1800e281b  call    cs:__imp_GetLastError
0x1800e2821  test    eax, eax
0x1800e2823  jle     short loc_1800E282D
0x1800e2825  movzx   eax, ax
0x1800e2828  or      eax, 80070000h
0x1800e282d  mov     ecx, 80040D04h
0x1800e2832  cmp     eax, 80070006h
0x1800e2837  cmovz   eax, ecx
0x1800e283a  jmp     short loc_1800E283E
0x1800e283c  xor     eax, eax
0x1800e283e  mov     rcx, [rsp+458h]; this
0x1800e2846  test    eax, eax
0x1800e2848  jns     short loc_1800E285E
0x1800e284a  mov     r9d, eax; char *
0x1800e284d  lea     r8, aOnecoreuapBase_222; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e2854  mov     edx, 1E8h; void *
0x1800e2859  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e285e  or      r8d, 0FFFFFFFFh; unsigned int
0x1800e2862  lea     rdx, aProjects; "Projects"
0x1800e2869  lea     rcx, [rsp+458h+var_308]; this
0x1800e2871  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800e2876  mov     r8, r14; wchar_t *
0x1800e2879  mov     rdx, [rsp+458h+var_300]; wchar_t *
0x1800e2881  mov     rcx, rsi; this
0x1800e2884  call    ?CreateDirectoryWithSecurity@CGatherApplication@@IEAAXPEB_W0@Z; CGatherApplication::CreateDirectoryWithSecurity(wchar_t const *,wchar_t const *)
0x1800e2889  lea     rdx, [rsp+458h+var_308]
0x1800e2891  lea     rcx, [rsp+458h+var_268]
0x1800e2899  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@AEBV0@@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(TLMString<64,64,32767> const &)
0x1800e289e  mov     rdx, rax
0x1800e28a1  mov     rcx, rsi
0x1800e28a4  call    ?SetDefaultProjectPath@CGatherApplication@@QEAAJV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; CGatherApplication::SetDefaultProjectPath(TLMString<64,64,32767>)
0x1800e28a9  mov     rcx, [rsp+458h]; this
0x1800e28b1  test    eax, eax
0x1800e28b3  jns     short loc_1800E28C9
0x1800e28b5  mov     r9d, eax; char *
0x1800e28b8  lea     r8, aOnecoreuapBase_222; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e28bf  mov     edx, 1EDh; void *
0x1800e28c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e28c9  lea     rcx, [rsp+458h+var_268]
0x1800e28d1  call    ?GetRootRegistryKeyName@@YA?AV?$TLMString@$0CA@$0CA@$0EAA@@@XZ; GetRootRegistryKeyName(void)
0x1800e28d6  nop
0x1800e28d7  mov     rdx, rax
0x1800e28da  lea     rcx, [rsp+458h+var_3B8]
0x1800e28e2  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@AEBV0@@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(TLMString<64,64,32767> const &)
0x1800e28e7  mov     rdx, rax
0x1800e28ea  mov     rcx, rsi
0x1800e28ed  call    ?SetDefaultCatalogConfigUrl@CGatherApplication@@QEAAJV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; CGatherApplication::SetDefaultCatalogConfigUrl(TLMString<64,64,32767>)
0x1800e28f2  mov     ebx, eax
0x1800e28f4  lea     rcx, [rsp+458h+var_268]
0x1800e28fc  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800e2901  mov     rcx, [rsp+458h]; this
0x1800e2909  test    ebx, ebx
0x1800e290b  jns     short loc_1800E2921
0x1800e290d  mov     r9d, ebx; char *
0x1800e2910  lea     r8, aOnecoreuapBase_222; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e2917  mov     edx, 1F0h; void *
0x1800e291c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e2921  mov     rdx, rdi
0x1800e2924  lea     rcx, [rsp+458h+var_308]
0x1800e292c  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1800e2931  or      r8d, 0FFFFFFFFh; unsigned int
0x1800e2935  lea     rdx, aGatherlogs; "GatherLogs"
0x1800e293c  lea     rcx, [rsp+458h+var_308]; this
0x1800e2944  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800e2949  mov     r8, r14; wchar_t *
0x1800e294c  mov     rdx, [rsp+458h+var_300]; wchar_t *
0x1800e2954  mov     rcx, rsi; this
0x1800e2957  call    ?CreateDirectoryWithSecurity@CGatherApplication@@IEAAXPEB_W0@Z; CGatherApplication::CreateDirectoryWithSecurity(wchar_t const *,wchar_t const *)
0x1800e295c  lea     rdx, [rsp+458h+var_308]
0x1800e2964  lea     rcx, [rsp+458h+var_3B8]
0x1800e296c  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@AEBV0@@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(TLMString<64,64,32767> const &)
0x1800e2971  mov     rdx, rax
0x1800e2974  mov     rcx, rsi
0x1800e2977  call    ?SetGatherLogsPath@CGatherApplication@@QEAAJV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; CGatherApplication::SetGatherLogsPath(TLMString<64,64,32767>)
0x1800e297c  mov     ebx, eax
0x1800e297e  test    eax, eax
0x1800e2980  jns     short loc_1800E29B2
0x1800e2982  lea     rcx, [rsp+458h+var_1C8]; this
0x1800e298a  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800e298f  nop
0x1800e2990  lea     rcx, [rsp+458h+var_108]; this
0x1800e2998  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800e299d  nop
0x1800e299e  lea     rcx, [rsp+458h+var_308]
0x1800e29a6  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800e29ab  mov     eax, ebx
0x1800e29ad  jmp     loc_1800E2EAD
0x1800e29b2  mov     rdx, r15
0x1800e29b5  lea     rcx, [rsp+458h+var_268]
0x1800e29bd  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800e29c2  nop
0x1800e29c3  lea     rdx, [rsp+458h+var_268]
0x1800e29cb  mov     rcx, rsi
0x1800e29ce  call    ?SetGathererPlugin@CGatherApplication@@QEAAJAEBV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; CGatherApplication::SetGathererPlugin(TLMString<32,32,1024> const &)
0x1800e29d3  mov     ebx, eax
0x1800e29d5  lea     rcx, [rsp+458h+var_268]
0x1800e29dd  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800e29e2  xorps   xmm0, xmm0
0x1800e29e5  movups  xmmword ptr [rsp+458h+clsid.Data1], xmm0
0x1800e29ed  test    ebx, ebx
0x1800e29ef  js      loc_1800E2B14
0x1800e29f5  mov     rdx, r13
0x1800e29f8  lea     rcx, [rsp+458h+var_268]
0x1800e2a00  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@AEBV0@@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(TLMString<32,32,1024> const &)
0x1800e2a05  mov     rdx, rax
0x1800e2a08  mov     rcx, rsi
0x1800e2a0b  call    ?SetDisplayName@CGatherApplication@@QEAAJV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; CGatherApplication::SetDisplayName(TLMString<32,32,1024>)
0x1800e2a10  mov     ebx, eax
0x1800e2a12  xor     r13d, r13d
0x1800e2a15  test    eax, eax
0x1800e2a17  js      loc_1800E2B17
0x1800e2a1d  lea     rdx, [rsp+458h+clsid]; lpclsid
0x1800e2a25  mov     rcx, [rsi+4F8h]; lpszProgID
0x1800e2a2c  call    cs:__imp_CLSIDFromProgID
0x1800e2a32  mov     ebx, eax
0x1800e2a34  test    eax, eax
0x1800e2a36  js      loc_1800E2B17
0x1800e2a3c  lea     r15, [rsi+550h]
0x1800e2a43  mov     [rsp+458h+ppv], r15; int
0x1800e2a48  lea     r9, _GUID_c7310558_ac80_11d1_8df3_00c04fb6ef4f; riid
0x1800e2a4f  xor     edx, edx; pUnkOuter
0x1800e2a51  lea     r8d, [r13+17h]; dwClsContext
0x1800e2a55  lea     rcx, [rsp+458h+clsid]; rclsid
0x1800e2a5d  call    cs:__imp_CoCreateInstance
0x1800e2a63  mov     ebx, eax
0x1800e2a65  test    eax, eax
0x1800e2a67  js      loc_1800E2B17
0x1800e2a6d  cmp     [rsi+170h], r13b
0x1800e2a74  jz      short loc_1800E2AE1
0x1800e2a76  mov     [rsp+458h+var_408], r13
0x1800e2a7b  mov     rdi, [r15]
0x1800e2a7e  mov     rax, [rdi]
0x1800e2a81  mov     rbx, [rax]
0x1800e2a84  lea     rcx, [rsp+458h+var_408]
0x1800e2a89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e2a8e  lea     r8, [rsp+458h+var_408]
0x1800e2a93  lea     rdx, _GUID_c5a782aa_b7fe_45ab_bcb6_84d2f514acd4
0x1800e2a9a  mov     rcx, rdi
0x1800e2a9d  mov     rax, rbx
0x1800e2aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2aa5  mov     rcx, [rsp+458h]; this
0x1800e2aad  test    eax, eax
  ... truncated ...
```
