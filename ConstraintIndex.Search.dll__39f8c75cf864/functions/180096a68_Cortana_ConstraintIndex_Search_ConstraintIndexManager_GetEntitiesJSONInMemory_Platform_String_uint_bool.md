# Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetEntitiesJSONInMemory(Platform::String *,uint,bool)

- ea: `0x180096a68`
- end: `0x180097108`
- name: `?GetEntitiesJSONInMemory@ConstraintIndexManager@Search@ConstraintIndex@Cortana@@QEAAPE$AAVString@Platform@@PE$AAV56@I_N@Z`
- size: `1696`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x18009df80`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18000616e`
- `0x18000617a`
- `0x18003a900`
- `0x18003b2f4`
- `0x18003b7a0`
- `0x18003c0e0`
- `0x18003fd04`
- `0x18003ff00`
- `0x18003ff8c`
- `0x180083118`
- `0x180092d24`
- `0x180095114`
- `0x180095680`
- `0x180095780`
- `0x1800968f4`
- `0x180096a24`
- `0x180096a68`
- `0x1800989ec`
- `0x180098ae8`
- `0x180099d54`
- `0x18009af90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180096aee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180096b0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180097068`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180096aee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180096b0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180097068`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096bd0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096e7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096bd0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096e7a`

## string_xrefs

- `0x180096ab6`: `ConstraintIndexManager_GetEntitiesJSONInMemory`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetEntitiesJSONInMemory(
        __int64 a1,
        __int64 a2,
        int a3,
        char a4)
{
  char v5; // bl
  HSTRING ConstraintIndexCurrentFolderName; // rbx
  HSTRING v7; // rdi
  HSTRING v8; // r15
  bool v9; // bl
  HSTRING v10; // rbx
  HSTRING v11; // r13
  HSTRING v12; // r15
  HSTRING v13; // rbx
  HSTRING v14; // rdi
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HSTRING v18; // rdi
  HRESULT v19; // eax
  __int64 v20; // rdx
  HSTRING *v21; // rcx
  char v22; // bl
  HSTRING v23; // rbx
  HSTRING v24; // rdi
  HSTRING v25; // rbx
  HSTRING v26; // r15
  HRESULT v27; // eax
  HSTRING v28; // r13
  HRESULT v29; // eax
  HRESULT v30; // eax
  HSTRING v31; // rdi
  HSTRING v32; // rbx
  HSTRING EntitiesJson__Q__ICSGSuggesterPublicNonVirtuals_CSGSuggestion_ConstraintIndex_Cortana__CSGSuggester_234_UE_AAAPE_AAVString_Platform__PE_AAV67_0H_N_Z; // rbx
  __int64 v34; // rbx
  HSTRING v37; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v38; // [rsp+40h] [rbp-C0h]
  HSTRING ConstraintIndexLatestFolderName; // [rsp+48h] [rbp-B8h]
  HSTRING v40; // [rsp+50h] [rbp-B0h]
  int v41; // [rsp+58h] [rbp-A8h]
  HSTRING v42; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v45; // [rsp+78h] [rbp-88h]
  HSTRING v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h]
  HSTRING v48; // [rsp+90h] [rbp-70h]
  HSTRING_HEADER v49; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER v51; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v52; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v54[42]; // [rsp+F0h] [rbp-10h] BYREF

  v41 = a3;
  v47 = a2;
  memset_0(v54, 0, sizeof(v54));
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
  v54[0] = &ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory::`vftable';
  ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory::StartActivity(
    (__int64)v54,
    *(HSTRING *)(a1 + 24));
  v42 = 0;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 112));
  v52 = (HSTRING)(a1 + 112);
  v5 = Cortana::ConstraintIndex::Search::IConstraintIndexOptions::IsDataBuildingEnabled::get(*(_QWORD *)(a1 + 96));
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v52);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 112));
  if ( v5 )
  {
    v52 = (HSTRING)(a1 + 112);
    ConstraintIndexCurrentFolderName = (HSTRING)Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexCurrentFolderName(a1);
    v7 = (HSTRING)__abi_winrt_ptrto_string_ctor(ConstraintIndexCurrentFolderName);
    WindowsDeleteString_0(ConstraintIndexCurrentFolderName);
    ConstraintIndexLatestFolderName = (HSTRING)Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexLatestFolderName(a1);
    v8 = (HSTRING)__abi_winrt_ptrto_string_ctor(ConstraintIndexLatestFolderName);
    v37 = v8;
    WindowsDeleteString_0(ConstraintIndexLatestFolderName);
    v9 = !*(_BYTE *)(a1 + 16)
      || (unsigned __int8)Platform::String::operator!=(v7, 0)
      && (unsigned __int8)Platform::String::operator!=(v8, 0)
      && (unsigned __int8)Platform::String::operator!=(v7, v8);
    WindowsDeleteString_0(v8);
    WindowsDeleteString_0(v7);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v52);
    if ( v9 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 112));
      v37 = (HSTRING)(a1 + 112);
      v10 = (HSTRING)Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexCurrentFolderName(a1);
      v11 = (HSTRING)__abi_winrt_ptrto_string_ctor(v10);
      v48 = v11;
      WindowsDeleteString_0(v10);
      ConstraintIndexLatestFolderName = (HSTRING)Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexLatestFolderName(a1);
      v12 = (HSTRING)__abi_winrt_ptrto_string_ctor(ConstraintIndexLatestFolderName);
      v40 = v12;
      WindowsDeleteString_0(ConstraintIndexLatestFolderName);
      if ( !*(_BYTE *)(a1 + 16)
        || (unsigned __int8)Platform::String::operator!=(v11, 0)
        && (unsigned __int8)Platform::String::operator!=(v12, 0)
        && (unsigned __int8)Platform::String::operator!=(v11, v12) )
      {
        v13 = (HSTRING)Cortana::ConstraintIndex::Search::IConstraintIndexOptions::CurrentConstraintIndexCabPath::get(*(_QWORD *)(a1 + 96));
        v14 = (HSTRING)__abi_winrt_ptrto_string_ctor(v13);
        ConstraintIndexLatestFolderName = v14;
        WindowsDeleteString_0(v13);
        v44 = *(_QWORD *)(a1 + 104);
        v52 = *(HSTRING *)(a1 + 64);
        string = 0;
        v15 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, &string);
        if ( v15 < 0 )
          __abi_WinRTraiseException(v15);
        v46 = (HSTRING)Platform::String::Concat(v12, string);
        v52 = (HSTRING)Platform::String::Concat(v46, v52);
        v38 = *(HSTRING *)(a1 + 48);
        string = 0;
        v16 = WindowsCreateStringReference_0(L"\\", 1u, &v51, &string);
        if ( v16 < 0 )
          __abi_WinRTraiseException(v16);
        v45 = (HSTRING)Platform::String::Concat(v12, string);
        v38 = (HSTRING)Platform::String::Concat(v45, v38);
        v43 = *(HSTRING *)(a1 + 40);
        string = 0;
        v17 = WindowsCreateStringReference_0(L"\\", 1u, &v49, &string);
        if ( v17 < 0 )
          __abi_WinRTraiseException(v17);
        v18 = (HSTRING)Platform::String::Concat(v14, string);
        string = v18;
        v43 = (HSTRING)Platform::String::Concat(v18, v43);
        _LoadIndexIntoMemory__Q__ICSGSuggesterPublicNonVirtuals_CSGSuggestion_ConstraintIndex_Cortana__CSGSuggester_234_UE_AAAXPE_AAVString_Platform__00_Z(
          v44,
          v43,
          v38,
          v52);
        WindowsDeleteString_0(v43);
        WindowsDeleteString_0(v18);
        WindowsDeleteString_0(v38);
        WindowsDeleteString_0(v45);
        WindowsDeleteString_0(v52);
        WindowsDeleteString_0(v46);
        v52 = 0;
        v19 = WindowsCreateStringReference_0(L"CurrentConstraintIndexFolder", 0x1Cu, &v49, &v52);
        if ( v19 < 0 )
          __abi_WinRTraiseException(v19);
        Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::WriteStringValue(
          (_QWORD *)(a1 + 88),
          v20,
          v52,
          v12);
        *(_BYTE *)(a1 + 16) = 1;
        WindowsDeleteString_0(ConstraintIndexLatestFolderName);
      }
      WindowsDeleteString_0(v12);
      WindowsDeleteString_0(v11);
      v21 = &v37;
LABEL_33:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v21);
    }
  }
  else
  {
    v37 = (HSTRING)(a1 + 112);
    v22 = *(_BYTE *)(a1 + 16);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v37);
    if ( !v22 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 112));
      v44 = a1 + 112;
      if ( !*(_BYTE *)(a1 + 16) )
      {
        v23 = (HSTRING)Cortana::ConstraintIndex::Search::IConstraintIndexOptions::CurrentConstraintIndexCabPath::get(*(_QWORD *)(a1 + 96));
        v40 = v23;
        v24 = (HSTRING)__abi_winrt_ptrto_string_ctor(v23);
        v45 = v24;
        WindowsDeleteString_0(v23);
        v25 = (HSTRING)Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexLatestFolderName(a1);
        v40 = v25;
        v26 = (HSTRING)__abi_winrt_ptrto_string_ctor(v25);
        v40 = v26;
        WindowsDeleteString_0(v25);
        ConstraintIndexLatestFolderName = *(HSTRING *)(a1 + 104);
        v37 = *(HSTRING *)(a1 + 64);
        v52 = 0;
        v27 = WindowsCreateStringReference_0(L"\\", 1u, &v49, &v52);
        if ( v27 < 0 )
          __abi_WinRTraiseException(v27);
        v28 = (HSTRING)Platform::String::Concat(v26, v52);
        v48 = v28;
        string = (HSTRING)Platform::String::Concat(v28, v37);
        v37 = *(HSTRING *)(a1 + 48);
        v52 = 0;
        v29 = WindowsCreateStringReference_0(L"\\", 1u, &v51, &v52);
        if ( v29 < 0 )
          __abi_WinRTraiseException(v29);
        v46 = (HSTRING)Platform::String::Concat(v26, v52);
        v38 = (HSTRING)Platform::String::Concat(v46, v37);
        v37 = *(HSTRING *)(a1 + 40);
        v52 = 0;
        v30 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, &v52);
        if ( v30 < 0 )
          __abi_WinRTraiseException(v30);
        v31 = (HSTRING)Platform::String::Concat(v24, v52);
        v43 = v31;
        v32 = (HSTRING)Platform::String::Concat(v31, v37);
        v37 = v32;
        _LoadIndexIntoMemory__Q__ICSGSuggesterPublicNonVirtuals_CSGSuggestion_ConstraintIndex_Cortana__CSGSuggester_234_UE_AAAXPE_AAVString_Platform__00_Z(
          ConstraintIndexLatestFolderName,
          v32,
          v38,
          string);
        WindowsDeleteString_0(v32);
        WindowsDeleteString_0(v31);
        WindowsDeleteString_0(v38);
        WindowsDeleteString_0(v46);
        WindowsDeleteString_0(string);
        WindowsDeleteString_0(v28);
        *(_BYTE *)(a1 + 16) = 1;
        WindowsDeleteString_0(v26);
        WindowsDeleteString_0(v45);
      }
      v21 = (HSTRING *)&v44;
      goto LABEL_33;
    }
  }
  AcquireSRWLockShared((PSRWLOCK)(a1 + 112));
  v37 = (HSTRING)(a1 + 112);
  EntitiesJson__Q__ICSGSuggesterPublicNonVirtuals_CSGSuggestion_ConstraintIndex_Cortana__CSGSuggester_234_UE_AAAPE_AAVString_Platform__PE_AAV67_0H_N_Z = (HSTRING)_GetEntitiesJson__Q__ICSGSuggesterPublicNonVirtuals_CSGSuggestion_ConstraintIndex_Cortana__CSGSuggester_234_UE_AAAPE_AAVString_Platform__PE_AAV67_0H_N_Z(*(_QWORD *)(a1 + 104), v47, *(_QWORD *)(a1 + 24), v41, a4);
  v40 = EntitiesJson__Q__ICSGSuggesterPublicNonVirtuals_CSGSuggestion_ConstraintIndex_Cortana__CSGSuggester_234_UE_AAAPE_AAVString_Platform__PE_AAV67_0H_N_Z;
  __abi_winrt_ptrto_string_assign(
    &v42,
    EntitiesJson__Q__ICSGSuggesterPublicNonVirtuals_CSGSuggestion_ConstraintIndex_Cortana__CSGSuggester_234_UE_AAAPE_AAVString_Platform__PE_AAV67_0H_N_Z);
  WindowsDeleteString_0(EntitiesJson__Q__ICSGSuggesterPublicNonVirtuals_CSGSuggestion_ConstraintIndex_Cortana__CSGSuggester_234_UE_AAAPE_AAVString_Platform__PE_AAV67_0H_N_Z);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v37);
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54);
  v34 = __abi_winrt_ptrto_string_ctor(v42);
  WindowsDeleteString_0(v42);
  ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory::~ConstraintIndexManager_GetEntitiesJSONInMemory((ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory *)v54);
  return v34;
}

```

## disassembly

```asm
0x180096a68  push    rbp
0x180096a6a  push    rbx
0x180096a6b  push    rsi
0x180096a6c  push    rdi
0x180096a6d  push    r13
0x180096a6f  push    r14
0x180096a71  push    r15
0x180096a73  lea     rbp, [rsp-150h]
0x180096a7b  sub     rsp, 250h
0x180096a82  mov     rax, cs:__security_cookie
0x180096a89  xor     rax, rsp
0x180096a8c  mov     [rbp+180h+var_40], rax
0x180096a93  mov     [rsp+280h+var_250], r9b
0x180096a98  mov     [rsp+280h+var_228], r8d
0x180096a9d  mov     [rbp+180h+var_1F8], rdx
0x180096aa1  mov     rsi, rcx
0x180096aa4  xor     edx, edx; Val
0x180096aa6  mov     r8d, 150h; Size
0x180096aac  lea     rcx, [rbp+180h+var_190]; void *
0x180096ab0  call    memset_0
0x180096ab5  nop
0x180096ab6  lea     rdx, aConstraintinde_5; "ConstraintIndexManager_GetEntitiesJSONI"...
0x180096abd  lea     rcx, [rbp+180h+var_190]; struct wil::details::IFailureCallback *
0x180096ac1  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180096ac6  lea     rax, ??_7ConstraintIndexManager_GetEntitiesJSONInMemory@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory::`vftable'
0x180096acd  mov     [rbp+180h+var_190], rax
0x180096ad1  mov     rdx, [rsi+18h]
0x180096ad5  lea     rcx, [rbp+180h+var_190]
0x180096ad9  call    ?StartActivity@ConstraintIndexManager_GetEntitiesJSONInMemory@ConstraintIndexTelemetry@@QEAAXPE$AAVString@Platform@@@Z; ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory::StartActivity(Platform::String *)
0x180096ade  nop
0x180096adf  xor     r13d, r13d
0x180096ae2  mov     [rsp+280h+var_220], r13
0x180096ae7  lea     r14, [rsi+70h]
0x180096aeb  mov     rcx, r14; SRWLock
0x180096aee  call    cs:__imp_AcquireSRWLockShared
0x180096af4  mov     [rbp+180h+var_1A0], r14
0x180096af8  mov     rcx, [rsi+60h]
0x180096afc  call    ?get@IsDataBuildingEnabled@IConstraintIndexOptions@Search@ConstraintIndex@Cortana@@UE$AAA_NXZ; Cortana::ConstraintIndex::Search::IConstraintIndexOptions::IsDataBuildingEnabled::get(void)
0x180096b01  mov     bl, al
0x180096b03  lea     rcx, [rbp+180h+var_1A0]
0x180096b07  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180096b0c  mov     rcx, r14; SRWLock
0x180096b0f  call    cs:__imp_AcquireSRWLockShared
0x180096b15  test    bl, bl
0x180096b17  jz      loc_180096E5D
0x180096b1d  mov     [rbp+180h+var_1A0], r14
0x180096b21  mov     rcx, rsi
0x180096b24  call    ?GetConstraintIndexCurrentFolderName@ConstraintIndexManager@Search@ConstraintIndex@Cortana@@AEAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexCurrentFolderName(void)
0x180096b29  mov     rbx, rax
0x180096b2c  mov     [rsp+280h+var_248], rax
0x180096b31  mov     rcx, rax
0x180096b34  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x180096b39  mov     rdi, rax
0x180096b3c  mov     [rsp+280h+var_248], rax
0x180096b41  mov     rcx, rbx; string
0x180096b44  call    WindowsDeleteString_0
0x180096b49  nop
0x180096b4a  mov     rcx, rsi
0x180096b4d  call    ?GetConstraintIndexLatestFolderName@ConstraintIndexManager@Search@ConstraintIndex@Cortana@@AEAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexLatestFolderName(void)
0x180096b52  mov     rbx, rax
0x180096b55  mov     [rsp+280h+var_238], rax
0x180096b5a  mov     rcx, rax
0x180096b5d  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x180096b62  mov     r15, rax
0x180096b65  mov     [rsp+280h+var_248], rax
0x180096b6a  mov     rcx, rbx; string
0x180096b6d  call    WindowsDeleteString_0
0x180096b72  cmp     [rsi+10h], r13b
0x180096b76  jz      short loc_180096BA8
0x180096b78  xor     edx, edx
0x180096b7a  mov     rcx, rdi
0x180096b7d  call    ??9String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator!=(Platform::String *,Platform::String *)
0x180096b82  test    al, al
0x180096b84  jz      short loc_180096BA3
0x180096b86  xor     edx, edx
0x180096b88  mov     rcx, r15
0x180096b8b  call    ??9String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator!=(Platform::String *,Platform::String *)
0x180096b90  test    al, al
0x180096b92  jz      short loc_180096BA3
0x180096b94  mov     rdx, r15
0x180096b97  mov     rcx, rdi
0x180096b9a  call    ??9String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator!=(Platform::String *,Platform::String *)
0x180096b9f  test    al, al
0x180096ba1  jnz     short loc_180096BA8
0x180096ba3  mov     bl, r13b
0x180096ba6  jmp     short loc_180096BAA
0x180096ba8  mov     bl, 1
0x180096baa  mov     rcx, r15; string
0x180096bad  call    WindowsDeleteString_0
0x180096bb2  nop
0x180096bb3  mov     rcx, rdi; string
0x180096bb6  call    WindowsDeleteString_0
0x180096bbb  nop
0x180096bbc  lea     rcx, [rbp+180h+var_1A0]
0x180096bc0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180096bc5  test    bl, bl
0x180096bc7  jz      loc_180097065
0x180096bcd  mov     rcx, r14; SRWLock
0x180096bd0  call    cs:__imp_AcquireSRWLockExclusive
0x180096bd6  mov     [rsp+280h+var_248], r14
0x180096bdb  mov     rcx, rsi
0x180096bde  call    ?GetConstraintIndexCurrentFolderName@ConstraintIndexManager@Search@ConstraintIndex@Cortana@@AEAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexCurrentFolderName(void)
0x180096be3  mov     rbx, rax
0x180096be6  mov     [rsp+280h+var_238], rax
0x180096beb  mov     rcx, rax
0x180096bee  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x180096bf3  mov     r13, rax
0x180096bf6  mov     [rbp+180h+var_1F0], rax
0x180096bfa  mov     rcx, rbx; string
0x180096bfd  call    WindowsDeleteString_0
0x180096c02  nop
0x180096c03  mov     rcx, rsi
0x180096c06  call    ?GetConstraintIndexLatestFolderName@ConstraintIndexManager@Search@ConstraintIndex@Cortana@@AEAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexLatestFolderName(void)
0x180096c0b  mov     rbx, rax
0x180096c0e  mov     [rsp+280h+var_238], rax
0x180096c13  mov     rcx, rax
0x180096c16  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x180096c1b  mov     r15, rax
0x180096c1e  mov     [rsp+280h+var_230], rax
0x180096c23  mov     rcx, rbx; string
0x180096c26  call    WindowsDeleteString_0
0x180096c2b  nop
0x180096c2c  cmp     byte ptr [rsi+10h], 0
0x180096c30  jz      short loc_180096C69
0x180096c32  xor     edx, edx
0x180096c34  mov     rcx, r13
0x180096c37  call    ??9String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator!=(Platform::String *,Platform::String *)
0x180096c3c  test    al, al
0x180096c3e  jz      loc_180096E41
0x180096c44  xor     edx, edx
0x180096c46  mov     rcx, r15
0x180096c49  call    ??9String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator!=(Platform::String *,Platform::String *)
0x180096c4e  test    al, al
0x180096c50  jz      loc_180096E41
0x180096c56  mov     rdx, r15
0x180096c59  mov     rcx, r13
0x180096c5c  call    ??9String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator!=(Platform::String *,Platform::String *)
0x180096c61  test    al, al
0x180096c63  jz      loc_180096E41
0x180096c69  mov     rcx, [rsi+60h]
0x180096c6d  call    ?get@CurrentConstraintIndexCabPath@IConstraintIndexOptions@Search@ConstraintIndex@Cortana@@UE$AAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::IConstraintIndexOptions::CurrentConstraintIndexCabPath::get(void)
0x180096c72  mov     rbx, rax
0x180096c75  mov     [rsp+280h+var_238], rax
0x180096c7a  mov     rcx, rax
0x180096c7d  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x180096c82  mov     rdi, rax
0x180096c85  mov     [rsp+280h+var_238], rax
0x180096c8a  mov     rcx, rbx; string
0x180096c8d  call    WindowsDeleteString_0
0x180096c92  nop
0x180096c93  mov     rax, [rsi+68h]
0x180096c97  mov     [rsp+280h+var_210], rax
0x180096c9c  mov     rax, [rsi+40h]
0x180096ca0  mov     [rbp+180h+var_1A0], rax
0x180096ca4  mov     [rbp+180h+string], 0
0x180096cac  lea     r9, [rbp+180h+string]; string
0x180096cb0  lea     r8, [rbp+180h+hstringHeader]; hstringHeader
0x180096cb4  mov     edx, 1; length
0x180096cb9  lea     rbx, asc_180104F88; "\\"
0x180096cc0  mov     rcx, rbx; sourceString
0x180096cc3  call    WindowsCreateStringReference_0
0x180096cc8  test    eax, eax
0x180096cca  jns     short loc_180096CD4
0x180096ccc  mov     ecx, eax; int
0x180096cce  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180096cd4  mov     rdx, [rbp+180h+string]
0x180096cd8  mov     rcx, r15
0x180096cdb  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x180096ce0  mov     [rbp+180h+var_200], rax
0x180096ce4  mov     rdx, [rbp+180h+var_1A0]
0x180096ce8  mov     rcx, rax
0x180096ceb  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x180096cf0  mov     [rbp+180h+var_1A0], rax
0x180096cf4  mov     rax, [rsi+30h]
0x180096cf8  mov     [rsp+280h+var_240], rax
0x180096cfd  mov     [rbp+180h+string], 0
0x180096d05  lea     r9, [rbp+180h+string]; string
0x180096d09  lea     r8, [rbp+180h+var_1B8]; hstringHeader
0x180096d0d  mov     edx, 1; length
0x180096d12  mov     rcx, rbx; sourceString
0x180096d15  call    WindowsCreateStringReference_0
0x180096d1a  test    eax, eax
0x180096d1c  jns     short loc_180096D26
0x180096d1e  mov     ecx, eax; int
0x180096d20  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180096d26  mov     rdx, [rbp+180h+string]
0x180096d2a  mov     rcx, r15
0x180096d2d  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x180096d32  mov     [rsp+280h+var_208], rax
0x180096d37  mov     rdx, [rsp+280h+var_240]
0x180096d3c  mov     rcx, rax
0x180096d3f  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x180096d44  mov     [rsp+280h+var_240], rax
0x180096d49  mov     rax, [rsi+28h]
0x180096d4d  mov     [rsp+280h+var_218], rax
0x180096d52  mov     [rbp+180h+string], 0
0x180096d5a  lea     r9, [rbp+180h+string]; string
0x180096d5e  lea     r8, [rbp+180h+var_1E8]; hstringHeader
0x180096d62  mov     edx, 1; length
0x180096d67  mov     rcx, rbx; sourceString
0x180096d6a  call    WindowsCreateStringReference_0
0x180096d6f  test    eax, eax
0x180096d71  jns     short loc_180096D7B
0x180096d73  mov     ecx, eax; int
0x180096d75  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180096d7b  mov     rdx, [rbp+180h+string]
0x180096d7f  mov     rcx, rdi
0x180096d82  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x180096d87  mov     rdi, rax
0x180096d8a  mov     [rbp+180h+string], rax
0x180096d8e  mov     rdx, [rsp+280h+var_218]
0x180096d93  mov     rcx, rax
0x180096d96  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x180096d9b  mov     rbx, rax
0x180096d9e  mov     [rsp+280h+var_218], rax
0x180096da3  mov     r9, [rbp+180h+var_1A0]
0x180096da7  mov     r8, [rsp+280h+var_240]
0x180096dac  mov     rdx, rax
0x180096daf  mov     rcx, [rsp+280h+var_210]
0x180096db4  call    ?LoadIndexIntoMemory@?Q__ICSGSuggesterPublicNonVirtuals@CSGSuggestion@ConstraintIndex@Cortana@@CSGSuggester@234@UE$AAAXPE$AAVString@Platform@@00@Z
0x180096db9  nop
0x180096dba  mov     rcx, rbx; string
0x180096dbd  call    WindowsDeleteString_0
0x180096dc2  nop
0x180096dc3  mov     rcx, rdi; string
0x180096dc6  call    WindowsDeleteString_0
0x180096dcb  nop
0x180096dcc  mov     rcx, [rsp+280h+var_240]; string
0x180096dd1  call    WindowsDeleteString_0
0x180096dd6  nop
0x180096dd7  mov     rcx, [rsp+280h+var_208]; string
0x180096ddc  call    WindowsDeleteString_0
0x180096de1  nop
0x180096de2  mov     rcx, [rbp+180h+var_1A0]; string
0x180096de6  call    WindowsDeleteString_0
0x180096deb  nop
0x180096dec  mov     rcx, [rbp+180h+var_200]; string
0x180096df0  call    WindowsDeleteString_0
0x180096df5  mov     [rbp+180h+var_1A0], 0
0x180096dfd  lea     r9, [rbp+180h+var_1A0]; string
0x180096e01  lea     r8, [rbp+180h+var_1E8]; hstringHeader
0x180096e05  mov     edx, 1Ch; length
0x180096e0a  lea     rcx, aCurrentconstra_0; "CurrentConstraintIndexFolder"
0x180096e11  call    WindowsCreateStringReference_0
0x180096e16  test    eax, eax
0x180096e18  jns     short loc_180096E22
0x180096e1a  mov     ecx, eax; int
0x180096e1c  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180096e22  lea     rcx, [rsi+58h]
0x180096e26  mov     r9, r15
0x180096e29  mov     r8, [rbp+180h+var_1A0]
0x180096e2d  call    ?WriteStringValue@ConstraintIndexRegistryContainer@Search@ConstraintIndex@Cortana@@QEBAXPE$AAVString@Platform@@00@Z; Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::WriteStringValue(Platform::String *,Platform::String *,Platform::String *)
0x180096e32  mov     byte ptr [rsi+10h], 1
0x180096e36  mov     rcx, [rsp+280h+var_238]; string
0x180096e3b  call    WindowsDeleteString_0
0x180096e40  nop
0x180096e41  mov     rcx, r15; string
0x180096e44  call    WindowsDeleteString_0
0x180096e49  nop
0x180096e4a  mov     rcx, r13; string
0x180096e4d  call    WindowsDeleteString_0
0x180096e52  nop
0x180096e53  lea     rcx, [rsp+280h+var_248]
0x180096e58  jmp     loc_180097060
0x180096e5d  mov     [rsp+280h+var_248], r14
0x180096e62  mov     bl, [rsi+10h]
0x180096e65  lea     rcx, [rsp+280h+var_248]
0x180096e6a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180096e6f  test    bl, bl
0x180096e71  jnz     loc_180097065
0x180096e77  mov     rcx, r14; SRWLock
0x180096e7a  call    cs:__imp_AcquireSRWLockExclusive
0x180096e80  mov     [rsp+280h+var_210], r14
0x180096e85  cmp     [rsi+10h], r13b
0x180096e89  jnz     loc_18009705B
0x180096e8f  mov     rcx, [rsi+60h]
0x180096e93  call    ?get@CurrentConstraintIndexCabPath@IConstraintIndexOptions@Search@ConstraintIndex@Cortana@@UE$AAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::IConstraintIndexOptions::CurrentConstraintIndexCabPath::get(void)
0x180096e98  mov     rbx, rax
0x180096e9b  mov     [rsp+280h+var_230], rax
0x180096ea0  mov     rcx, rax
0x180096ea3  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x180096ea8  mov     rdi, rax
0x180096eab  mov     [rsp+280h+var_208], rax
0x180096eb0  mov     rcx, rbx; string
0x180096eb3  call    WindowsDeleteString_0
0x180096eb8  nop
0x180096eb9  mov     rcx, rsi
0x180096ebc  call    ?GetConstraintIndexLatestFolderName@ConstraintIndexManager@Search@ConstraintIndex@Cortana@@AEAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::ConstraintIndexManager::GetConstraintIndexLatestFolderName(void)
0x180096ec1  mov     rbx, rax
0x180096ec4  mov     [rsp+280h+var_230], rax
0x180096ec9  mov     rcx, rax
0x180096ecc  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x180096ed1  mov     r15, rax
0x180096ed4  mov     [rsp+280h+var_230], rax
0x180096ed9  mov     rcx, rbx; string
0x180096edc  call    WindowsDeleteString_0
0x180096ee1  nop
0x180096ee2  mov     rax, [rsi+68h]
0x180096ee6  mov     [rsp+280h+var_238], rax
0x180096eeb  mov     rax, [rsi+40h]
  ... truncated ...
```
