# StoreAppFinder::GetEvidenceFromPackageAndDependencies(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager> const &,std::vector<Application,std::allocator<Application>> &)

- ea: `0x1800d6fec`
- end: `0x1800d7684`
- name: `?GetEvidenceFromPackageAndDependencies@StoreAppFinder@@SAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@45@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@@Z`
- size: `1688`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d5ab4`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18001c5f0`
- `0x18001daec`
- `0x18001df20`
- `0x1800c97f0`
- `0x1800c9810`
- `0x1800d5a0c`
- `0x1800d6e0c`
- `0x1800d6fec`
- `0x1800d7c74`
- `0x1800db734`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d7241`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d7279`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d7241`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d7279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d7228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d728c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d7228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d728c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800d73b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800d73b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7573`

## string_xrefs

- `0x1800d709b`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d70b8`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d70f0`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d710d`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7145`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d71a8`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d74b7`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7509`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d751e`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7533`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7548`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d761e`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7633`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7648`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d765d`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7672`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall StoreAppFinder::GetEvidenceFromPackageAndDependencies(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 *v5; // rdi
  int v8; // eax
  const char *v9; // r9
  int v10; // eax
  const char *v11; // r9
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, _QWORD, _QWORD, HSTRING); // r15
  HSTRING v19; // r14
  const WCHAR *v20; // rdi
  unsigned __int64 v21; // rbx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int *v37; // [rsp+20h] [rbp-E0h]
  _BYTE v38[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h] BYREF
  int v40; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  int v48; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  int v50[2]; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR sourceString; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v52[16]; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v53; // [rsp+A8h] [rbp-58h]
  struct _SYSTEM_INFO v54; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v55[32]; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+100h] [rbp+0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v5 = a3;
  v53 = a3;
  v47 = 0;
  std::set<std::wstring>::set<std::wstring>(v52);
  StoreAppFinder::GetEvidenceFromPackage(a1, a2, a4, v52);
  StoreApplication::GetStoreAppManifestPathFromPackage(v55, a2, 1);
  v44 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  StoreAppFinder::GetManifestReaderFromManifestPath(v55, &v44);
  v42 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 24LL))(v44, &v42);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E2,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v8,
      (int)v37);
  if ( !v42 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3E3,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      v9);
  v39 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 40LL))(v44, &v39);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E7,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v10,
      (int)v37);
  if ( !v44 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3E8,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      v11);
  v41 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 32LL))(v39, &v41);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3EB,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v12,
      (int)v37);
  if ( v41 )
  {
    v48 = 11;
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 32LL))(v42, &v48);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3F3,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
        (const char *)(unsigned int)v14,
        (int)v37);
    while ( 1 )
    {
      v46 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 24LL))(v39, &v46);
      if ( v15 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x3FA,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
          (const char *)(unsigned int)v15,
          (int)v37);
      sourceString = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v46 + 24LL))(v46, &sourceString);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x3FE,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
          (const char *)(unsigned int)v16,
          (int)v37);
      *(_QWORD *)v50 = 0;
      v17 = *v5;
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, HSTRING))(*(_QWORD *)*v5 + 112LL);
      if ( WindowsCreateStringReference(
             L"CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US",
             0x50u,
             &hstringHeader,
             &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v19 = string;
      v20 = sourceString;
      v21 = -1;
      do
        ++v21;
      while ( sourceString[v21] );
      if ( v21 > 0xFFFFFFFF )
      {
        LODWORD(v21) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(v20, v21, (HSTRING_HEADER *)&v54.lpMinimumApplicationAddress, (HSTRING *)&v54);
      v37 = v50;
      v22 = v18(v17, 0, *(_QWORD *)&v54.dwOemId, v19);
      if ( v22 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x40A,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
          (const char *)(unsigned int)v22,
          (int)v50);
      v45 = 0;
      v23 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v50 + 48LL))(*(_QWORD *)v50, &v45);
      if ( v23 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x40E,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
          (const char *)(unsigned int)v23,
          (int)v50);
      v38[0] = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v45 + 56LL))(v45, v38);
      if ( v24 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x412,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
          (const char *)(unsigned int)v24,
          (int)v50);
      if ( !v38[0] )
        break;
      while ( 1 )
      {
        v43 = 0;
        v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL))(v45, &v43);
        if ( v25 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x41C,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
            (const char *)(unsigned int)v25,
            (int)v50);
        v49 = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 48LL))(v43, &v49);
        if ( v26 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x420,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
            (const char *)(unsigned int)v26,
            (int)v50);
        v40 = 0xFFFF;
        v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 64LL))(v49, &v40);
        if ( v27 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x424,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
            (const char *)(unsigned int)v27,
            (int)v50);
        if ( v48 == v40 )
          break;
        if ( v40 == 11 )
          break;
        if ( v48 == 11 )
        {
          memset(&v54, 0, sizeof(v54));
          GetSystemInfo(&v54);
          if ( v40 == v54.wProcessorArchitecture )
            break;
        }
        v28 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v45 + 64LL))(v45, v38);
        if ( v28 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x438,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
            (const char *)(unsigned int)v28,
            (int)v50);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        if ( !v38[0] )
          goto LABEL_40;
      }
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage>::operator=(&v47, &v43);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
LABEL_40:
      if ( v47 )
        StoreAppFinder::GetEvidenceFromPackage(a1, &v47, a4, v52);
      v29 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 40LL))(v39, &v41);
      if ( v29 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x442,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
          (const char *)(unsigned int)v29,
          (int)v50);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v50);
      CoTaskMemFree((LPVOID)sourceString);
      v30 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      if ( !v41 )
      {
        v31 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        goto LABEL_50;
      }
      v5 = v53;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v50);
    CoTaskMemFree((LPVOID)sourceString);
    v33 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
  }
  else
  {
    v13 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
LABEL_50:
    v32 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  std::wstring::_Tidy_deallocate(v55);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v52,
    v52);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
}

```

## disassembly

```asm
0x1800d6fec  push    rbp
0x1800d6fee  push    rbx
0x1800d6fef  push    rsi
0x1800d6ff0  push    rdi
0x1800d6ff1  push    r12
0x1800d6ff3  push    r13
0x1800d6ff5  push    r14
0x1800d6ff7  push    r15
0x1800d6ff9  lea     rbp, [rsp-38h]
0x1800d6ffe  sub     rsp, 138h
0x1800d7005  mov     rax, cs:__security_cookie
0x1800d700c  xor     rax, rsp
0x1800d700f  mov     [rbp+70h+var_50], rax
0x1800d7013  mov     r13, r9
0x1800d7016  mov     rdi, r8
0x1800d7019  mov     [rbp+70h+var_C8], r8
0x1800d701d  mov     rbx, rdx
0x1800d7020  mov     r12, rcx
0x1800d7023  xor     r14d, r14d
0x1800d7026  mov     [rsp+170h+var_100], r14
0x1800d702b  lea     rcx, [rbp+70h+var_D8]
0x1800d702f  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800d7034  nop
0x1800d7035  lea     r9, [rbp+70h+var_D8]
0x1800d7039  mov     r8, r13
0x1800d703c  mov     rdx, rbx
0x1800d703f  mov     rcx, r12
0x1800d7042  call    ?GetEvidenceFromPackage@StoreAppFinder@@SAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@7@@Z; StoreAppFinder::GetEvidenceFromPackage(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,std::vector<Application> &,std::set<std::wstring> &)
0x1800d7047  lea     r8d, [r14+1]
0x1800d704b  mov     rdx, rbx
0x1800d704e  lea     rcx, [rbp+70h+var_90]
0x1800d7052  call    ?GetStoreAppManifestPathFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@W4ManifestType@@@Z; StoreApplication::GetStoreAppManifestPathFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,ManifestType)
0x1800d7057  nop
0x1800d7058  mov     [rsp+170h+var_118], r14
0x1800d705d  lea     rcx, [rsp+170h+var_118]
0x1800d7062  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7067  lea     rdx, [rsp+170h+var_118]
0x1800d706c  lea     rcx, [rbp+70h+var_90]
0x1800d7070  call    ?GetManifestReaderFromManifestPath@StoreAppFinder@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAppxManifestReader@@@Z; StoreAppFinder::GetManifestReaderFromManifestPath(std::wstring const &,IAppxManifestReader * *)
0x1800d7075  mov     [rsp+170h+var_128], r14
0x1800d707a  mov     rcx, [rsp+170h+var_118]
0x1800d707f  mov     rax, [rcx]
0x1800d7082  lea     rdx, [rsp+170h+var_128]
0x1800d7087  mov     rax, [rax+18h]
0x1800d708b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7090  mov     rcx, [rbp+78h]; this
0x1800d7094  test    eax, eax
0x1800d7096  jns     short loc_1800D70AD
0x1800d7098  mov     r9d, eax; char *
0x1800d709b  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d70a2  mov     edx, 3E2h; void *
0x1800d70a7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d70ad  mov     rcx, [rbp+78h]; this
0x1800d70b1  cmp     [rsp+170h+var_128], r14
0x1800d70b6  jnz     short loc_1800D70CA
0x1800d70b8  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d70bf  mov     edx, 3E3h; void *
0x1800d70c4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800d70ca  mov     [rsp+170h+var_138], r14
0x1800d70cf  mov     rcx, [rsp+170h+var_118]
0x1800d70d4  mov     rax, [rcx]
0x1800d70d7  lea     rdx, [rsp+170h+var_138]
0x1800d70dc  mov     rax, [rax+28h]
0x1800d70e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d70e5  mov     rcx, [rbp+78h]; this
0x1800d70e9  test    eax, eax
0x1800d70eb  jns     short loc_1800D7102
0x1800d70ed  mov     r9d, eax; char *
0x1800d70f0  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d70f7  mov     edx, 3E7h; void *
0x1800d70fc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7102  mov     rcx, [rbp+78h]; this
0x1800d7106  cmp     [rsp+170h+var_118], r14
0x1800d710b  jnz     short loc_1800D711F
0x1800d710d  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7114  mov     edx, 3E8h; void *
0x1800d7119  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800d711f  mov     [rsp+170h+var_12C], r14d
0x1800d7124  mov     rcx, [rsp+170h+var_138]
0x1800d7129  mov     rax, [rcx]
0x1800d712c  lea     rdx, [rsp+170h+var_12C]
0x1800d7131  mov     rax, [rax+20h]
0x1800d7135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d713a  mov     rcx, [rbp+78h]; this
0x1800d713e  test    eax, eax
0x1800d7140  jns     short loc_1800D7157
0x1800d7142  mov     r9d, eax; char *
0x1800d7145  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d714c  mov     edx, 3EBh; void *
0x1800d7151  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7157  cmp     [rsp+170h+var_12C], r14d
0x1800d715c  jnz     short loc_1800D717F
0x1800d715e  mov     rcx, [rsp+170h+var_138]
0x1800d7163  test    rcx, rcx
0x1800d7166  jz      short loc_1800D717A
0x1800d7168  mov     [rsp+170h+var_138], r14
0x1800d716d  mov     rax, [rcx]
0x1800d7170  mov     rax, [rax+10h]
0x1800d7174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7179  nop
0x1800d717a  jmp     loc_1800D74E5
0x1800d717f  mov     [rsp+170h+var_F8], 0Bh
0x1800d7187  mov     rcx, [rsp+170h+var_128]
0x1800d718c  mov     rax, [rcx]
0x1800d718f  lea     rdx, [rsp+170h+var_F8]
0x1800d7194  mov     rax, [rax+20h]
0x1800d7198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d719d  mov     rcx, [rbp+78h]; this
0x1800d71a1  test    eax, eax
0x1800d71a3  jns     short loc_1800D71BA
0x1800d71a5  mov     r9d, eax; char *
0x1800d71a8  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d71af  mov     edx, 3F3h; void *
0x1800d71b4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d71ba  mov     [rsp+170h+var_108], r14
0x1800d71bf  mov     rcx, [rsp+170h+var_138]
0x1800d71c4  mov     rax, [rcx]
0x1800d71c7  lea     rdx, [rsp+170h+var_108]
0x1800d71cc  mov     rax, [rax+18h]
0x1800d71d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d71d5  mov     rcx, [rbp+78h]; this
0x1800d71d9  test    eax, eax
0x1800d71db  js      loc_1800D766F
0x1800d71e1  mov     [rbp+70h+sourceString], r14
0x1800d71e5  mov     rcx, [rsp+170h+var_108]
0x1800d71ea  mov     rax, [rcx]
0x1800d71ed  lea     rdx, [rbp+70h+sourceString]
0x1800d71f1  mov     rax, [rax+18h]
0x1800d71f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d71fa  mov     rcx, [rbp+78h]; this
0x1800d71fe  test    eax, eax
0x1800d7200  js      loc_1800D765A
0x1800d7206  mov     qword ptr [rbp+70h+var_E8], r14
0x1800d720a  mov     rsi, [rdi]
0x1800d720d  mov     rax, [rsi]
0x1800d7210  mov     r15, [rax+70h]
0x1800d7214  lea     r9, [rbp+70h+string]; string
0x1800d7218  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x1800d721c  mov     edx, 50h ; 'P'; length
0x1800d7221  lea     rcx, sourceString; "CN=Microsoft Corporation, O=Microsoft C"...
0x1800d7228  call    cs:__imp_WindowsCreateStringReference
0x1800d722e  test    eax, eax
0x1800d7230  jns     short loc_1800D7247
0x1800d7232  xor     r9d, r9d; lpArguments
0x1800d7235  xor     r8d, r8d; nNumberOfArguments
0x1800d7238  lea     edx, [r9+1]; dwExceptionFlags
0x1800d723c  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d7241  call    cs:__imp_RaiseException
0x1800d7247  mov     r14, [rbp+70h+string]
0x1800d724b  mov     rdi, [rbp+70h+sourceString]
0x1800d724f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800d7253  xor     eax, eax
0x1800d7255  inc     rbx
0x1800d7258  cmp     [rdi+rbx*2], ax
0x1800d725c  jnz     short loc_1800D7255
0x1800d725e  mov     eax, 0FFFFFFFFh
0x1800d7263  cmp     rbx, rax
0x1800d7266  jbe     short loc_1800D727F
0x1800d7268  mov     ebx, eax
0x1800d726a  xor     r9d, r9d; lpArguments
0x1800d726d  xor     r8d, r8d; nNumberOfArguments
0x1800d7270  lea     edx, [r9+1]; dwExceptionFlags
0x1800d7274  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d7279  call    cs:__imp_RaiseException
0x1800d727f  lea     r9, [rbp+70h+var_C0]; string
0x1800d7283  lea     r8, [rbp+70h+var_C0.Reserved+8]; hstringHeader
0x1800d7287  mov     edx, ebx; length
0x1800d7289  mov     rcx, rdi; sourceString
0x1800d728c  call    cs:__imp_WindowsCreateStringReference
0x1800d7292  lea     rax, [rbp+70h+var_E8]
0x1800d7296  mov     qword ptr [rsp+170h+var_150], rax; int
0x1800d729b  mov     r9, r14
0x1800d729e  mov     r8, qword ptr [rbp+70h+var_C0.Reserved]
0x1800d72a2  xor     edx, edx
0x1800d72a4  mov     rcx, rsi
0x1800d72a7  mov     rax, r15
0x1800d72aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d72af  mov     rcx, [rbp+78h]; this
0x1800d72b3  xor     r14d, r14d
0x1800d72b6  test    eax, eax
0x1800d72b8  js      loc_1800D7645
0x1800d72be  mov     [rsp+170h+var_110], r14
0x1800d72c3  mov     rcx, qword ptr [rbp+70h+var_E8]
0x1800d72c7  mov     rax, [rcx]
0x1800d72ca  lea     rdx, [rsp+170h+var_110]
0x1800d72cf  mov     rax, [rax+30h]
0x1800d72d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d72d8  mov     rcx, [rbp+78h]; this
0x1800d72dc  test    eax, eax
0x1800d72de  js      loc_1800D7630
0x1800d72e4  mov     [rsp+170h+var_140], r14b
0x1800d72e9  mov     rcx, [rsp+170h+var_110]
0x1800d72ee  mov     rax, [rcx]
0x1800d72f1  lea     rdx, [rsp+170h+var_140]
0x1800d72f6  mov     rax, [rax+38h]
0x1800d72fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d72ff  mov     rcx, [rbp+78h]; this
0x1800d7303  test    eax, eax
0x1800d7305  js      loc_1800D761B
0x1800d730b  cmp     [rsp+170h+var_140], r14b
0x1800d7310  jz      loc_1800D755A
0x1800d7316  mov     [rsp+170h+var_120], r14
0x1800d731b  mov     rcx, [rsp+170h+var_110]
0x1800d7320  mov     rax, [rcx]
0x1800d7323  lea     rdx, [rsp+170h+var_120]
0x1800d7328  mov     rax, [rax+30h]
0x1800d732c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7331  mov     rcx, [rbp+78h]; this
0x1800d7335  test    eax, eax
0x1800d7337  js      loc_1800D7545
0x1800d733d  mov     [rbp+70h+var_F0], r14
0x1800d7341  mov     rcx, [rsp+170h+var_120]
0x1800d7346  mov     rax, [rcx]
0x1800d7349  lea     rdx, [rbp+70h+var_F0]
0x1800d734d  mov     rax, [rax+30h]
0x1800d7351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7356  mov     rcx, [rbp+78h]; this
0x1800d735a  test    eax, eax
0x1800d735c  js      loc_1800D7530
0x1800d7362  mov     [rsp+170h+var_130], 0FFFFh
0x1800d736a  mov     rcx, [rbp+70h+var_F0]
0x1800d736e  mov     rax, [rcx]
0x1800d7371  lea     rdx, [rsp+170h+var_130]
0x1800d7376  mov     rax, [rax+40h]
0x1800d737a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d737f  mov     rcx, [rbp+78h]; this
0x1800d7383  test    eax, eax
0x1800d7385  js      loc_1800D751B
0x1800d738b  mov     eax, [rsp+170h+var_F8]
0x1800d738f  cmp     eax, [rsp+170h+var_130]
0x1800d7393  jz      short loc_1800D7407
0x1800d7395  cmp     [rsp+170h+var_130], 0Bh
0x1800d739a  jz      short loc_1800D7407
0x1800d739c  cmp     eax, 0Bh
0x1800d739f  jnz     short loc_1800D73C4
0x1800d73a1  xorps   xmm0, xmm0
0x1800d73a4  movups  xmmword ptr [rbp+70h+var_C0.Reserved], xmm0
0x1800d73a8  movups  xmmword ptr [rbp+70h+var_C0.Reserved+10h], xmm0
0x1800d73ac  movups  [rbp+70h+var_A0], xmm0
0x1800d73b0  lea     rcx, [rbp+70h+var_C0]; lpSystemInfo
0x1800d73b4  call    cs:__imp_GetSystemInfo
0x1800d73ba  movzx   eax, word ptr [rbp+70h+var_C0.Reserved]
0x1800d73be  cmp     [rsp+170h+var_130], eax
0x1800d73c2  jz      short loc_1800D7407
0x1800d73c4  mov     rcx, [rsp+170h+var_110]
0x1800d73c9  mov     rax, [rcx]
0x1800d73cc  lea     rdx, [rsp+170h+var_140]
0x1800d73d1  mov     rax, [rax+40h]
0x1800d73d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d73da  mov     rcx, [rbp+78h]; this
0x1800d73de  test    eax, eax
0x1800d73e0  js      loc_1800D74B4
0x1800d73e6  lea     rcx, [rbp+70h+var_F0]
0x1800d73ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d73ef  nop
0x1800d73f0  lea     rcx, [rsp+170h+var_120]
0x1800d73f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d73fa  cmp     [rsp+170h+var_140], r14b
0x1800d73ff  jnz     loc_1800D7316
0x1800d7405  jmp     short loc_1800D742B
0x1800d7407  lea     rdx, [rsp+170h+var_120]
0x1800d740c  lea     rcx, [rsp+170h+var_100]
0x1800d7411  call    ??4?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage>::operator=(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)
0x1800d7416  nop
0x1800d7417  lea     rcx, [rbp+70h+var_F0]
0x1800d741b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7420  nop
0x1800d7421  lea     rcx, [rsp+170h+var_120]
0x1800d7426  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d742b  cmp     [rsp+170h+var_100], r14
0x1800d7430  jz      short loc_1800D7446
0x1800d7432  lea     r9, [rbp+70h+var_D8]
0x1800d7436  mov     r8, r13
0x1800d7439  lea     rdx, [rsp+170h+var_100]
0x1800d743e  mov     rcx, r12
0x1800d7441  call    ?GetEvidenceFromPackage@StoreAppFinder@@SAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@7@@Z; StoreAppFinder::GetEvidenceFromPackage(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,std::vector<Application> &,std::set<std::wstring> &)
0x1800d7446  mov     rcx, [rsp+170h+var_138]
0x1800d744b  mov     rax, [rcx]
0x1800d744e  lea     rdx, [rsp+170h+var_12C]
0x1800d7453  mov     rax, [rax+28h]
0x1800d7457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d745c  mov     rcx, [rbp+78h]; this
0x1800d7460  test    eax, eax
0x1800d7462  js      loc_1800D7506
0x1800d7468  lea     rcx, [rsp+170h+var_110]
0x1800d746d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7472  nop
0x1800d7473  lea     rcx, [rbp+70h+var_E8]
0x1800d7477  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d747c  nop
0x1800d747d  mov     rcx, [rbp+70h+sourceString]; pv
0x1800d7481  call    cs:__imp_CoTaskMemFree
0x1800d7487  nop
0x1800d7488  mov     rcx, [rsp+170h+var_108]
0x1800d748d  test    rcx, rcx
0x1800d7490  jz      short loc_1800D74A4
0x1800d7492  mov     [rsp+170h+var_108], r14
0x1800d7497  mov     rax, [rcx]
0x1800d749a  mov     rax, [rax+10h]
0x1800d749e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
