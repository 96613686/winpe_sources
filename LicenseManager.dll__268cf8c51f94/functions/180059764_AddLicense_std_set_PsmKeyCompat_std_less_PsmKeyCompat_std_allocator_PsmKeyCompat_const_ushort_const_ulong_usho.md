# AddLicense(std::set<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>> const &,ushort const *,ulong,ushort const *,ushort const *,Microsoft::WRL::ComPtr<ILicenseInstance> &)

- ea: `0x180059764`
- end: `0x180059d60`
- name: `?AddLicense@@YAXAEBV?$set@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@@std@@PEBGK11AEAV?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@@Z`
- size: `1532`
- prototype: ``
- caller_count: `1`
- callee_count: `39`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029664`

## callees

- `0x180004738`
- `0x1800061e0`
- `0x18000a110`
- `0x18000b3f4`
- `0x18000c70c`
- `0x180012dc0`
- `0x18001dad0`
- `0x18002c228`
- `0x1800333f0`
- `0x180033c04`
- `0x18003ba34`
- `0x180042bbc`
- `0x180056a6c`
- `0x180056d74`
- `0x1800593bc`
- `0x180059764`
- `0x18005b4cc`
- `0x18005b504`
- `0x18005b52c`
- `0x18005b560`
- `0x180065908`
- `0x1800682d8`
- `0x18006e4b4`
- `0x180072c54`
- `0x180075e60`
- `0x1800767e0`
- `0x18008a400`
- `0x18008c9d8`
- `0x18008cc78`
- `0x18008cca4`
- `0x18008cf30`
- `0x18008d00c`
- `0x18008d8c4`
- `0x18008d904`
- `0x18008dba8`
- `0x18008dc28`
- `0x18008dd0c`
- `0x1800905e4`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059d26`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059d26`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180059b08`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180059b08`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180059cea`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180059cea`

## string_xrefs

- `0x1800597d7`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180059964`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800599ab`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180059a2e`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180059a85`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180059ac4`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180059c6d`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180059cfb`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall AddLicense(_BYTE *a1, const WCHAR *a2, int a3, PackageLicense *a4, const WCHAR *a5, _QWORD *a6)
{
  const WCHAR *v7; // r14
  _BYTE *v8; // r15
  const WCHAR *v9; // r12
  __int64 v10; // rcx
  __int64 v11; // rdi
  _QWORD *v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // r15
  __int64 v22; // rsi
  int v23; // eax
  _QWORD *v24; // rsi
  int v25; // eax
  int v26; // eax
  __int64 v27; // r8
  __int64 Nexus; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rcx
  PackageLicense *v35; // rax
  const char *v36; // r9
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  LPCWCH lpString2; // [rsp+48h] [rbp-B8h] BYREF
  const WCHAR *v42; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v43[2]; // [rsp+58h] [rbp-A8h] BYREF
  PackageLicense *v44; // [rsp+68h] [rbp-98h] BYREF
  LPCWCH lpString1; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v46[16]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v47[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v48; // [rsp+98h] [rbp-68h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v50; // [rsp+B0h] [rbp-50h] BYREF
  int v51[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v52[32]; // [rsp+D0h] [rbp-30h] BYREF
  char v53[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE Src[32]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v7 = a2;
  v8 = a1;
  v43[0] = a1;
  lpString1 = a2;
  LODWORD(v42) = a3;
  v44 = a4;
  v9 = a5;
  lpString2 = a5;
  v48 = a6;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x65F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)0x80004003LL,
      bIgnoreCase);
  std::wstring::wstring(&v50, a2);
  GetKey(Src, &v50, a4);
  ContentIdString::~ContentIdString((ContentIdString *)&v50);
  v50 = 0;
  *(_QWORD *)v51 = 0;
  Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(&v50, a6);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &ActiveLicensesLock);
  std::_Tree<std::_Tmap_traits<std::wstring,ActiveLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ActiveLicense>>,0>>::find(
    v10,
    &v40,
    Src);
  v11 = v40;
  if ( v40 == ActiveLicenses )
  {
    Nexus = GetNexus(&v48);
    v29 = CaptureCurrentIdentity(v43, Nexus);
    Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::operator=(v51, v29);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v43);
    v30 = MakeCom<LicenseInstanceChangeListener,unsigned short const * &,unsigned long &,Microsoft::WRL::ComPtr<ILicenseInstance> &,Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &,unsigned short const * &,unsigned short const * &>(
            (unsigned int)&v40,
            (unsigned int)&lpString1,
            (unsigned int)&v42,
            (unsigned int)&v50,
            (__int64)v51,
            (__int64)&lpString2,
            (__int64)&v44);
    Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=((char *)&v50 + 8, v30);
    v31 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    std::set<PsmKeyCompat>::set<PsmKeyCompat>(v46);
    v47[0] = 0;
    v47[1] = 0;
    v47[0] = std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>>>();
    if ( v46 != v8 )
    {
      std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::clear(v46);
      std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::_Copy<0>(
        v46,
        v8);
    }
    v32 = std::pair<std::wstring,PackageLicense>::pair<std::wstring,PackageLicense>(v52, &lpString2, &v50);
    std::map<std::wstring,PackageLicense>::insert<std::pair<std::wstring,PackageLicense>,0>(v47, v43, v32);
    std::pair<std::wstring,PackageLicense>::~pair<std::wstring,PackageLicense>((ContentIdString *)v52);
    v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v50 + 112LL))(v50, *((_QWORD *)&v50 + 1));
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x679,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v33,
        bIgnoreCaseb);
    std::wstring::wstring(v52, Src);
    ActiveLicense::ActiveLicense((ActiveLicense *)v53, (const struct ActiveLicense *)v46);
    std::_Tree<std::_Tmap_traits<std::wstring,ActiveLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ActiveLicense>>,0>>::_Emplace<std::pair<std::wstring,ActiveLicense>>(
      v34,
      v43,
      v52);
    std::pair<std::wstring,ActiveLicense>::~pair<std::wstring,ActiveLicense>((ContentIdString *)v52);
    ActiveLicense::~ActiveLicense((ActiveLicense *)v46);
  }
  else
  {
    v12 = (_QWORD *)(v40 + 80);
    std::wstring::wstring(v52, a5);
    v13 = std::_Tree<std::_Tmap_traits<std::wstring,PackageLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageLicense>>,0>>::_Find<std::wstring>(
            v11 + 80,
            v52);
    ContentIdString::~ContentIdString((ContentIdString *)v52);
    if ( v13 == *v12 )
    {
      v14 = GetNexus(v43);
      v15 = CaptureCurrentIdentity(&v40, v14);
      Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::operator=(v51, v15);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      v16 = MakeCom<LicenseInstanceChangeListener,unsigned short const * &,unsigned long &,Microsoft::WRL::ComPtr<ILicenseInstance> &,Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &,unsigned short const * &,unsigned short const * &>(
              (unsigned int)&v40,
              (unsigned int)&lpString1,
              (unsigned int)&v42,
              (unsigned int)&v50,
              (__int64)v51,
              (__int64)&lpString2,
              (__int64)&v44);
      Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=((char *)&v50 + 8, v16);
      v17 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      v18 = std::pair<std::wstring,PackageLicense>::pair<std::wstring,PackageLicense>(v52, &lpString2, &v50);
      std::map<std::wstring,PackageLicense>::insert<std::pair<std::wstring,PackageLicense>,0>(v11 + 80, v43, v18);
      std::pair<std::wstring,PackageLicense>::~pair<std::wstring,PackageLicense>((ContentIdString *)v52);
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v50 + 112LL))(v50, *((_QWORD *)&v50 + 1));
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x691,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          (const char *)(unsigned int)v19,
          bIgnoreCasea);
      v7 = lpString1;
      v9 = lpString2;
    }
    else
    {
      v42 = 0;
      lpString2 = 0;
      v20 = Microsoft::WRL::ComPtr<ILicenseInstance>::As<IUnknown>(&v50, &lpString2);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x699,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          (const char *)(unsigned int)v20,
          bIgnoreCase);
      Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(&v50, v13 + 64);
      v21 = *((_QWORD *)&v50 + 1);
      v22 = *(_QWORD *)(v13 + 72);
      if ( *((_QWORD *)&v50 + 1) != v22 )
      {
        if ( v22 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 8LL))(*(_QWORD *)(v13 + 72));
        *((_QWORD *)&v50 + 1) = v22;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(v51, v13 + 80);
      v23 = Microsoft::WRL::ComPtr<ILicenseInstance>::As<IUnknown>(&v50, &v42);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x69B,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          (const char *)(unsigned int)v23,
          bIgnoreCase);
      if ( v42 != lpString2 )
      {
        v24 = v48;
        Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(v13 + 64, v48);
        v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v50 + 120LL))(v50, *(_QWORD *)(v13 + 72));
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6A1,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v25,
            bIgnoreCase);
        LicenseInstanceChangeListener::SetLicense(*((_QWORD *)&v50 + 1), v24);
        v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v24 + 112LL))(*v24, *((_QWORD *)&v50 + 1));
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6A3,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v26,
            bIgnoreCase);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&lpString2);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
      v12 = (_QWORD *)(v11 + 80);
      v8 = (_BYTE *)v43[0];
    }
    if ( CompareStringOrdinal(v7, -1, v9, -1, 0) == 2 )
      LeaseAllOptionalPackages(v7, v12);
    v27 = **(_QWORD **)v8;
    v40 = v27;
    while ( !*(_BYTE *)(v27 + 25) )
    {
      std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::_Emplace<PsmKeyCompat const &>(
        v11 + 64,
        v43,
        v27 + 32);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<PsmKeyCompat>>,std::_Iterator_base0>::operator++(&v40);
      v27 = v40;
    }
  }
  v35 = (PackageLicense *)operator new(0x18u);
  v44 = PackageLicense::PackageLicense(v35, (const struct PackageLicense *)&v50);
  if ( !QueueUserWorkItem(AddListenerForLeaseThreadProc, v44, 0x110u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6B6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      v36);
  v44 = 0;
  std::unique_ptr<PackageLicense>::~unique_ptr<PackageLicense>(&v44);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  PackageLicense::~PackageLicense((PackageLicense *)&v50);
  ContentIdString::~ContentIdString((ContentIdString *)Src);
}

```

## disassembly

```asm
0x180059764  push    rbp
0x180059766  push    rbx
0x180059767  push    rsi
0x180059768  push    rdi
0x180059769  push    r12
0x18005976b  push    r13
0x18005976d  push    r14
0x18005976f  push    r15
0x180059771  lea     rbp, [rsp-48h]
0x180059776  sub     rsp, 148h
0x18005977d  mov     rax, cs:__security_cookie
0x180059784  xor     rax, rsp
0x180059787  mov     [rbp+80h+var_50], rax
0x18005978b  mov     rdi, r9
0x18005978e  mov     esi, r8d
0x180059791  mov     r14, rdx
0x180059794  mov     r15, rcx
0x180059797  mov     [rsp+180h+var_128], rcx
0x18005979c  mov     [rsp+180h+lpString1], rdx
0x1800597a1  mov     dword ptr [rsp+180h+var_130], r8d
0x1800597a6  mov     [rsp+180h+var_118], r9
0x1800597ab  mov     r12, [rbp+80h+arg_20]
0x1800597b2  mov     [rsp+180h+lpString2], r12
0x1800597b7  mov     rbx, [rbp+80h+arg_28]
0x1800597be  mov     [rbp+80h+var_E8], rbx
0x1800597c2  mov     rcx, [rbp+88h]; this
0x1800597c9  xor     r13d, r13d
0x1800597cc  test    rdx, rdx
0x1800597cf  jnz     short loc_1800597E9
0x1800597d1  mov     r9d, 80004003h; char *
0x1800597d7  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800597de  mov     edx, 65Fh; void *
0x1800597e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800597e9  lea     rcx, [rbp+80h+var_D0]
0x1800597ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800597f2  nop
0x1800597f3  mov     r9d, esi
0x1800597f6  mov     r8, rdi; void *
0x1800597f9  lea     rdx, [rbp+80h+var_D0]; void *
0x1800597fd  lea     rcx, [rbp+80h+Src]; Src
0x180059801  call    ?GetKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@PEBGK@Z; GetKey(std::wstring const &,ushort const *,ulong)
0x180059806  nop
0x180059807  lea     rcx, [rbp+80h+var_D0]; this
0x18005980b  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180059810  xorps   xmm0, xmm0
0x180059813  movdqu  [rbp+80h+var_D0], xmm0
0x180059818  mov     qword ptr [rbp+80h+var_C0], r13
0x18005981c  mov     rdx, rbx
0x18005981f  lea     rcx, [rbp+80h+var_D0]
0x180059823  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x180059828  lea     rdx, ?ActiveLicensesLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock ActiveLicensesLock
0x18005982f  lea     rcx, [rbp+80h+SRWLock]
0x180059833  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180059838  nop
0x180059839  lea     r8, [rbp+80h+Src]
0x18005983d  lea     rdx, [rsp+180h+var_140]
0x180059842  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ActiveLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ActiveLicense>>,0>>::find(std::wstring const &)
0x180059847  mov     rdi, [rsp+180h+var_140]
0x18005984c  cmp     rdi, cs:?ActiveLicenses@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@@std@@A; std::map<std::wstring,ActiveLicense> ActiveLicenses
0x180059853  jz      loc_180059B56
0x180059859  lea     rsi, [rdi+50h]
0x18005985d  mov     rdx, r12
0x180059860  lea     rcx, [rbp+80h+var_B0]
0x180059864  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180059869  lea     rdx, [rbp+80h+var_B0]
0x18005986d  mov     rcx, rsi
0x180059870  call    ??$_Find@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PackageLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageLicense>>,0>>::_Find<std::wstring>(std::wstring const &)
0x180059875  mov     rbx, rax
0x180059878  lea     rcx, [rbp+80h+var_B0]; this
0x18005987c  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180059881  cmp     rbx, [rsi]
0x180059884  jnz     loc_180059985
0x18005988a  lea     rcx, [rsp+180h+var_128]
0x18005988f  call    ?GetNexus@@YA?AV?$shared_ptr@VNexus@@@std@@XZ; GetNexus(void)
0x180059894  mov     rdx, rax
0x180059897  lea     rcx, [rsp+180h+var_140]
0x18005989c  call    ?CaptureCurrentIdentity@@YA?AV?$ComPtr@UILicenseIdentityInternal@@@WRL@Microsoft@@V?$shared_ptr@VNexus@@@std@@@Z; CaptureCurrentIdentity(std::shared_ptr<Nexus>)
0x1800598a1  mov     rdx, rax
0x1800598a4  lea     rcx, [rbp+80h+var_C0]
0x1800598a8  call    ??4?$ComPtr@UILicenseIdentityInternal@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::operator=(Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &&)
0x1800598ad  lea     rcx, [rsp+180h+var_140]
0x1800598b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800598b7  lea     rax, [rsp+180h+var_118]
0x1800598bc  mov     [rsp+180h+var_150], rax
0x1800598c1  lea     rax, [rsp+180h+lpString2]
0x1800598c6  mov     [rsp+180h+var_158], rax
0x1800598cb  lea     rax, [rbp+80h+var_C0]
0x1800598cf  mov     qword ptr [rsp+180h+bIgnoreCase], rax; int
0x1800598d4  lea     r9, [rbp+80h+var_D0]
0x1800598d8  lea     r8, [rsp+180h+var_130]
0x1800598dd  lea     rdx, [rsp+180h+lpString1]
0x1800598e2  lea     rcx, [rsp+180h+var_140]
0x1800598e7  call    ??$MakeCom@VLicenseInstanceChangeListener@@AEAPEBGAEAKAEAV?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@AEAV?$ComPtr@UILicenseIdentityInternal@@@34@AEAPEBGAEAPEBG@@YA?AV?$ComPtr@VLicenseInstanceChangeListener@@@WRL@Microsoft@@AEAPEBGAEAKAEAV?$ComPtr@UILicenseInstance@@@12@AEAV?$ComPtr@UILicenseIdentityInternal@@@12@00@Z; MakeCom<LicenseInstanceChangeListener,ushort const * &,ulong &,Microsoft::WRL::ComPtr<ILicenseInstance> &,Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &,ushort const * &,ushort const * &>(ushort const * &,ulong &,Microsoft::WRL::ComPtr<ILicenseInstance> &,Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &,ushort const * &,ushort const * &)
0x1800598ec  mov     rdx, rax
0x1800598ef  lea     rcx, [rbp+80h+var_D0+8]
0x1800598f3  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x1800598f8  nop
0x1800598f9  mov     rcx, [rsp+180h+var_140]
0x1800598fe  test    rcx, rcx
0x180059901  jz      short loc_180059915
0x180059903  mov     [rsp+180h+var_140], r13
0x180059908  mov     rax, [rcx]
0x18005990b  mov     rax, [rax+10h]
0x18005990f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059914  nop
0x180059915  lea     r8, [rbp+80h+var_D0]
0x180059919  lea     rdx, [rsp+180h+lpString2]
0x18005991e  lea     rcx, [rbp+80h+var_B0]
0x180059922  call    ??$?0AEAPEBGAEAUPackageLicense@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@QEAA@AEAPEBGAEAUPackageLicense@@@Z; std::pair<std::wstring,PackageLicense>::pair<std::wstring,PackageLicense>(ushort const * &,PackageLicense &)
0x180059927  nop
0x180059928  mov     r8, rax
0x18005992b  lea     rdx, [rsp+180h+var_128]
0x180059930  mov     rcx, rsi
0x180059933  call    ??$insert@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@$0A@@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@1@@Z; std::map<std::wstring,PackageLicense>::insert<std::pair<std::wstring,PackageLicense>,0>(std::pair<std::wstring,PackageLicense> &&)
0x180059938  nop
0x180059939  lea     rcx, [rbp+80h+var_B0]; this
0x18005993d  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@QEAA@XZ; std::pair<std::wstring,PackageLicense>::~pair<std::wstring,PackageLicense>(void)
0x180059942  mov     rcx, qword ptr [rbp+80h+var_D0]
0x180059946  mov     rax, [rcx]
0x180059949  mov     rdx, qword ptr [rbp+80h+var_D0+8]
0x18005994d  mov     rax, [rax+70h]
0x180059951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059956  mov     rcx, [rbp+88h]; this
0x18005995d  test    eax, eax
0x18005995f  jns     short loc_180059976
0x180059961  mov     r9d, eax; char *
0x180059964  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005996b  mov     edx, 691h; void *
0x180059970  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180059976  mov     r14, [rsp+180h+lpString1]
0x18005997b  mov     r12, [rsp+180h+lpString2]
0x180059980  jmp     loc_180059AF7
0x180059985  mov     [rsp+180h+var_130], r13
0x18005998a  mov     [rsp+180h+lpString2], r13
0x18005998f  lea     rdx, [rsp+180h+lpString2]
0x180059994  lea     rcx, [rbp+80h+var_D0]
0x180059998  call    ??$As@UIUnknown@@@?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::As<IUnknown>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>)
0x18005999d  mov     rcx, [rbp+88h]; this
0x1800599a4  test    eax, eax
0x1800599a6  jns     short loc_1800599BD
0x1800599a8  mov     r9d, eax; char *
0x1800599ab  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800599b2  mov     edx, 699h; void *
0x1800599b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800599bd  lea     rdx, [rbx+40h]
0x1800599c1  lea     rcx, [rbp+80h+var_D0]
0x1800599c5  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x1800599ca  mov     r15, qword ptr [rbp+80h+var_D0+8]
0x1800599ce  mov     rsi, [rbx+48h]
0x1800599d2  cmp     r15, rsi
0x1800599d5  jz      short loc_180059A05
0x1800599d7  test    rsi, rsi
0x1800599da  jz      short loc_1800599EC
0x1800599dc  mov     rax, [rsi]
0x1800599df  mov     rcx, rsi
0x1800599e2  mov     rax, [rax+8]
0x1800599e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599eb  nop
0x1800599ec  mov     qword ptr [rbp+80h+var_D0+8], rsi
0x1800599f0  test    r15, r15
0x1800599f3  jz      short loc_180059A05
0x1800599f5  mov     rax, [r15]
0x1800599f8  mov     rcx, r15
0x1800599fb  mov     rax, [rax+10h]
0x1800599ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a04  nop
0x180059a05  lea     rdx, [rbx+50h]
0x180059a09  lea     rcx, [rbp+80h+var_C0]
0x180059a0d  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x180059a12  lea     rdx, [rsp+180h+var_130]
0x180059a17  lea     rcx, [rbp+80h+var_D0]
0x180059a1b  call    ??$As@UIUnknown@@@?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::As<IUnknown>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>)
0x180059a20  mov     rcx, [rbp+88h]; this
0x180059a27  test    eax, eax
0x180059a29  jns     short loc_180059A40
0x180059a2b  mov     r9d, eax; char *
0x180059a2e  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180059a35  mov     edx, 69Bh; void *
0x180059a3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180059a40  mov     rax, [rsp+180h+lpString2]
0x180059a45  cmp     [rsp+180h+var_130], rax
0x180059a4a  jz      loc_180059AD6
0x180059a50  mov     rsi, [rbp+80h+var_E8]
0x180059a54  mov     rdx, rsi
0x180059a57  lea     rcx, [rbx+40h]
0x180059a5b  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x180059a60  mov     rcx, qword ptr [rbp+80h+var_D0]
0x180059a64  mov     rax, [rcx]
0x180059a67  mov     rdx, [rbx+48h]
0x180059a6b  mov     rax, [rax+78h]
0x180059a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a74  mov     rcx, [rbp+88h]; this
0x180059a7b  xor     r13d, r13d
0x180059a7e  test    eax, eax
0x180059a80  jns     short loc_180059A97
0x180059a82  mov     r9d, eax; char *
0x180059a85  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180059a8c  mov     edx, 6A1h; void *
0x180059a91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180059a97  mov     rdx, rsi
0x180059a9a  mov     rcx, qword ptr [rbp+80h+var_D0+8]
0x180059a9e  call    ?SetLicense@LicenseInstanceChangeListener@@QEAAXAEBV?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@@Z; LicenseInstanceChangeListener::SetLicense(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x180059aa3  mov     rcx, [rsi]
0x180059aa6  mov     rax, [rcx]
0x180059aa9  mov     rdx, qword ptr [rbp+80h+var_D0+8]
0x180059aad  mov     rax, [rax+70h]
0x180059ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ab6  mov     rcx, [rbp+88h]; this
0x180059abd  test    eax, eax
0x180059abf  jns     short loc_180059AD9
0x180059ac1  mov     r9d, eax; char *
0x180059ac4  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180059acb  mov     edx, 6A3h; void *
0x180059ad0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180059ad6  xor     r13d, r13d
0x180059ad9  lea     rcx, [rsp+180h+lpString2]
0x180059ade  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180059ae3  nop
0x180059ae4  lea     rcx, [rsp+180h+var_130]
0x180059ae9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180059aee  lea     rsi, [rdi+50h]
0x180059af2  mov     r15, [rsp+180h+var_128]
0x180059af7  mov     [rsp+180h+bIgnoreCase], r13d; bIgnoreCase
0x180059afc  or      edx, 0FFFFFFFFh; cchCount1
0x180059aff  mov     r9d, edx; cchCount2
0x180059b02  mov     r8, r12; lpString2
0x180059b05  mov     rcx, r14; lpString1
0x180059b08  call    cs:__imp_CompareStringOrdinal
0x180059b0e  cmp     eax, 2
0x180059b11  jnz     short loc_180059B1E
0x180059b13  mov     rdx, rsi
0x180059b16  mov     rcx, r14
0x180059b19  call    ?LeaseAllOptionalPackages@@YAXPEBGAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@@2@@std@@@Z; LeaseAllOptionalPackages(ushort const *,std::map<std::wstring,PackageLicense> &)
0x180059b1e  mov     r8, [r15]
0x180059b21  mov     r8, [r8]
0x180059b24  mov     [rsp+180h+var_140], r8
0x180059b29  cmp     [r8+19h], r13b
0x180059b2d  jnz     loc_180059CBF
0x180059b33  add     r8, 20h ; ' '
0x180059b37  lea     rcx, [rdi+40h]
0x180059b3b  lea     rdx, [rsp+180h+var_128]
0x180059b40  call    ??$_Emplace@AEBUPsmKeyCompat@@@?$_Tree@V?$_Tset_traits@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@UPsmKeyCompat@@PEAX@std@@_N@1@AEBUPsmKeyCompat@@@Z; std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::_Emplace<PsmKeyCompat const &>(PsmKeyCompat const &)
0x180059b45  lea     rcx, [rsp+180h+var_140]
0x180059b4a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UPsmKeyCompat@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<PsmKeyCompat>>,std::_Iterator_base0>::operator++(void)
0x180059b4f  mov     r8, [rsp+180h+var_140]
0x180059b54  jmp     short loc_180059B29
0x180059b56  lea     rcx, [rbp+80h+var_E8]
0x180059b5a  call    ?GetNexus@@YA?AV?$shared_ptr@VNexus@@@std@@XZ; GetNexus(void)
0x180059b5f  mov     rdx, rax
0x180059b62  lea     rcx, [rsp+180h+var_128]
0x180059b67  call    ?CaptureCurrentIdentity@@YA?AV?$ComPtr@UILicenseIdentityInternal@@@WRL@Microsoft@@V?$shared_ptr@VNexus@@@std@@@Z; CaptureCurrentIdentity(std::shared_ptr<Nexus>)
0x180059b6c  mov     rdx, rax
0x180059b6f  lea     rcx, [rbp+80h+var_C0]
0x180059b73  call    ??4?$ComPtr@UILicenseIdentityInternal@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::operator=(Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &&)
0x180059b78  lea     rcx, [rsp+180h+var_128]
0x180059b7d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180059b82  lea     rax, [rsp+180h+var_118]
0x180059b87  mov     [rsp+180h+var_150], rax
0x180059b8c  lea     rax, [rsp+180h+lpString2]
0x180059b91  mov     [rsp+180h+var_158], rax
0x180059b96  lea     rax, [rbp+80h+var_C0]
0x180059b9a  mov     qword ptr [rsp+180h+bIgnoreCase], rax; int
0x180059b9f  lea     r9, [rbp+80h+var_D0]
0x180059ba3  lea     r8, [rsp+180h+var_130]
0x180059ba8  lea     rdx, [rsp+180h+lpString1]
0x180059bad  lea     rcx, [rsp+180h+var_140]
0x180059bb2  call    ??$MakeCom@VLicenseInstanceChangeListener@@AEAPEBGAEAKAEAV?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@AEAV?$ComPtr@UILicenseIdentityInternal@@@34@AEAPEBGAEAPEBG@@YA?AV?$ComPtr@VLicenseInstanceChangeListener@@@WRL@Microsoft@@AEAPEBGAEAKAEAV?$ComPtr@UILicenseInstance@@@12@AEAV?$ComPtr@UILicenseIdentityInternal@@@12@00@Z; MakeCom<LicenseInstanceChangeListener,ushort const * &,ulong &,Microsoft::WRL::ComPtr<ILicenseInstance> &,Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &,ushort const * &,ushort const * &>(ushort const * &,ulong &,Microsoft::WRL::ComPtr<ILicenseInstance> &,Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &,ushort const * &,ushort const * &)
0x180059bb7  mov     rdx, rax
0x180059bba  lea     rcx, [rbp+80h+var_D0+8]
0x180059bbe  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x180059bc3  nop
0x180059bc4  mov     rcx, [rsp+180h+var_140]
0x180059bc9  test    rcx, rcx
0x180059bcc  jz      short loc_180059BE0
0x180059bce  mov     [rsp+180h+var_140], r13
0x180059bd3  mov     rax, [rcx]
0x180059bd6  mov     rax, [rax+10h]
0x180059bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059bdf  nop
0x180059be0  lea     rcx, [rsp+180h+var_108]
0x180059be5  call    ??0?$set@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@@std@@QEAA@XZ; std::set<PsmKeyCompat>::set<PsmKeyCompat>(void)
0x180059bea  nop
0x180059beb  mov     [rbp+80h+var_F8], r13
0x180059bef  mov     [rbp+80h+var_F0], r13
0x180059bf3  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>> &)
0x180059bf8  mov     [rbp+80h+var_F8], rax
0x180059bfc  lea     rax, [rsp+180h+var_108]
0x180059c01  cmp     rax, r15
0x180059c04  jz      short loc_180059C1D
0x180059c06  lea     rcx, [rsp+180h+var_108]
0x180059c0b  call    ?clear@?$_Tree@V?$_Tset_traits@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::clear(void)
0x180059c10  mov     rdx, r15
0x180059c13  lea     rcx, [rsp+180h+var_108]
0x180059c18  call    ??$_Copy@$0A@@?$_Tree@V?$_Tset_traits@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::_Copy<0>(std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>> const &)
0x180059c1d  lea     r8, [rbp+80h+var_D0]
0x180059c21  lea     rdx, [rsp+180h+lpString2]
0x180059c26  lea     rcx, [rbp+80h+var_B0]
0x180059c2a  call    ??$?0AEAPEBGAEAUPackageLicense@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@QEAA@AEAPEBGAEAUPackageLicense@@@Z; std::pair<std::wstring,PackageLicense>::pair<std::wstring,PackageLicense>(ushort const * &,PackageLicense &)
0x180059c2f  nop
0x180059c30  mov     r8, rax
  ... truncated ...
```
