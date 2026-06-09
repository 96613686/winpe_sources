# StoreAppFinder::GetEvidenceFromPackageAndDependencies(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager> const &,std::vector<Application,std::allocator<Application>> &)

- ea: `0x18003e66c`
- end: `0x18003ed0c`
- name: `?GetEvidenceFromPackageAndDependencies@StoreAppFinder@@SAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@45@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@@Z`
- size: `1696`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008e58`

## callees

- `0x18000a39c`
- `0x180018a60`
- `0x18002a970`
- `0x18003d72c`
- `0x18003dacc`
- `0x18003dd14`
- `0x18003e66c`
- `0x180040254`
- `0x180043598`
- `0x180059920`
- `0x1800679f8`
- `0x1800f8c48`
- `0x1801003f4`
- `0x180130010`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18003ea3c`
- `KERNEL32!GetSystemInfo` at `0x18003ea3c`
- `KERNEL32!RaiseException` at `0x18003e8c8`
- `KERNEL32!RaiseException` at `0x18003e901`
- `KERNEL32!RaiseException` at `0x18003e8c8`
- `KERNEL32!RaiseException` at `0x18003e901`
- `ole32!CoTaskMemFree` at `0x18003eb09`
- `ole32!CoTaskMemFree` at `0x18003ebfb`
- `ole32!CoTaskMemFree` at `0x18003eb09`
- `ole32!CoTaskMemFree` at `0x18003ebfb`

## string_xrefs

- `0x18003e723`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003e740`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003e778`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003e795`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003e7cd`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003e830`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003eb3f`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003eb91`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003eba6`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003ebbb`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003ebd0`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003eca6`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003ecbb`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003ecd0`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003ece5`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003ecfa`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
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
  __int64 v54; // [rsp+B0h] [rbp-50h]
  struct _SYSTEM_INFO v55; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v56[32]; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING string; // [rsp+108h] [rbp+8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v54 = -2;
  v5 = a3;
  v53 = a3;
  v47 = 0;
  std::set<std::wstring>::set<std::wstring>(v52);
  StoreAppFinder::GetEvidenceFromPackage(a1, a2, a4, v52);
  StoreApplication::GetStoreAppManifestPathFromPackage(v56, a2, 1);
  v44 = 0;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v44);
  StoreAppFinder::GetManifestReaderFromManifestPath(v56, &v44);
  v42 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 24LL))(v44, &v42);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E2,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v8,
      (int)v37);
  if ( !v42 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3E3,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      v9);
  v39 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 40LL))(v44, &v39);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E7,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v10,
      (int)v37);
  if ( !v44 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3E8,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      v11);
  v41 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 32LL))(v39, &v41);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3EB,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
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
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
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
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
          (const char *)(unsigned int)v15,
          (int)v37);
      sourceString = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v46 + 24LL))(v46, &sourceString);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x3FE,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
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
      WindowsCreateStringReference(v20, v21, (HSTRING_HEADER *)&v55.lpMinimumApplicationAddress, (HSTRING *)&v55);
      v37 = v50;
      v22 = v18(v17, 0, *(_QWORD *)&v55.dwOemId, v19);
      if ( v22 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x40A,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
          (const char *)(unsigned int)v22,
          (int)v50);
      v45 = 0;
      v23 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v50 + 48LL))(*(_QWORD *)v50, &v45);
      if ( v23 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x40E,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
          (const char *)(unsigned int)v23,
          (int)v50);
      v38[0] = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v45 + 56LL))(v45, v38);
      if ( v24 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x412,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
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
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
            (const char *)(unsigned int)v25,
            (int)v50);
        v49 = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 48LL))(v43, &v49);
        if ( v26 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x420,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
            (const char *)(unsigned int)v26,
            (int)v50);
        v40 = 0xFFFF;
        v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 64LL))(v49, &v40);
        if ( v27 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x424,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
            (const char *)(unsigned int)v27,
            (int)v50);
        if ( v48 == v40 )
          break;
        if ( v40 == 11 )
          break;
        if ( v48 == 11 )
        {
          memset(&v55, 0, sizeof(v55));
          GetSystemInfo(&v55);
          if ( v40 == v55.wProcessorArchitecture )
            break;
        }
        v28 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v45 + 64LL))(v45, v38);
        if ( v28 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x438,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
            (const char *)(unsigned int)v28,
            (int)v50);
        Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v49);
        Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v43);
        if ( !v38[0] )
          goto LABEL_40;
      }
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage>::operator=(&v47, &v43);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v43);
LABEL_40:
      if ( v47 )
        StoreAppFinder::GetEvidenceFromPackage(a1, &v47, a4, v52);
      v29 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 40LL))(v39, &v41);
      if ( v29 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x442,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
          (const char *)(unsigned int)v29,
          (int)v50);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(v50);
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
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(v50);
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
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v44);
  std::wstring::~wstring(v56);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v52,
    v52);
  return Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v47);
}

```

## disassembly

```asm
0x18003e66c  push    rbp
0x18003e66e  push    rbx
0x18003e66f  push    rsi
0x18003e670  push    rdi
0x18003e671  push    r12
0x18003e673  push    r13
0x18003e675  push    r14
0x18003e677  push    r15
0x18003e679  lea     rbp, [rsp-38h]
0x18003e67e  sub     rsp, 138h
0x18003e685  mov     [rbp+70h+var_C0], 0FFFFFFFFFFFFFFFEh
0x18003e68d  mov     rax, cs:__security_cookie
0x18003e694  xor     rax, rsp
0x18003e697  mov     [rbp+70h+var_48], rax
0x18003e69b  mov     r13, r9
0x18003e69e  mov     rdi, r8
0x18003e6a1  mov     [rbp+70h+var_C8], r8
0x18003e6a5  mov     rbx, rdx
0x18003e6a8  mov     r12, rcx
0x18003e6ab  xor     r14d, r14d
0x18003e6ae  mov     [rsp+170h+var_100], r14
0x18003e6b3  lea     rcx, [rbp+70h+var_D8]
0x18003e6b7  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18003e6bc  nop
0x18003e6bd  lea     r9, [rbp+70h+var_D8]
0x18003e6c1  mov     r8, r13
0x18003e6c4  mov     rdx, rbx
0x18003e6c7  mov     rcx, r12
0x18003e6ca  call    ?GetEvidenceFromPackage@StoreAppFinder@@SAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@7@@Z; StoreAppFinder::GetEvidenceFromPackage(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,std::vector<Application> &,std::set<std::wstring> &)
0x18003e6cf  lea     r8d, [r14+1]
0x18003e6d3  mov     rdx, rbx
0x18003e6d6  lea     rcx, [rbp+70h+var_88]
0x18003e6da  call    ?GetStoreAppManifestPathFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@W4ManifestType@@@Z; StoreApplication::GetStoreAppManifestPathFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,ManifestType)
0x18003e6df  nop
0x18003e6e0  mov     [rsp+170h+var_118], r14
0x18003e6e5  lea     rcx, [rsp+170h+var_118]
0x18003e6ea  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18003e6ef  lea     rdx, [rsp+170h+var_118]
0x18003e6f4  lea     rcx, [rbp+70h+var_88]
0x18003e6f8  call    ?GetManifestReaderFromManifestPath@StoreAppFinder@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAppxManifestReader@@@Z; StoreAppFinder::GetManifestReaderFromManifestPath(std::wstring const &,IAppxManifestReader * *)
0x18003e6fd  mov     [rsp+170h+var_128], r14
0x18003e702  mov     rcx, [rsp+170h+var_118]
0x18003e707  mov     rax, [rcx]
0x18003e70a  lea     rdx, [rsp+170h+var_128]
0x18003e70f  mov     rax, [rax+18h]
0x18003e713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e718  mov     rcx, [rbp+78h]; this
0x18003e71c  test    eax, eax
0x18003e71e  jns     short loc_18003E735
0x18003e720  mov     r9d, eax; char *
0x18003e723  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003e72a  mov     edx, 3E2h; void *
0x18003e72f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003e735  mov     rcx, [rbp+78h]; this
0x18003e739  cmp     [rsp+170h+var_128], r14
0x18003e73e  jnz     short loc_18003E752
0x18003e740  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003e747  mov     edx, 3E3h; void *
0x18003e74c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18003e752  mov     [rsp+170h+var_138], r14
0x18003e757  mov     rcx, [rsp+170h+var_118]
0x18003e75c  mov     rax, [rcx]
0x18003e75f  lea     rdx, [rsp+170h+var_138]
0x18003e764  mov     rax, [rax+28h]
0x18003e768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e76d  mov     rcx, [rbp+78h]; this
0x18003e771  test    eax, eax
0x18003e773  jns     short loc_18003E78A
0x18003e775  mov     r9d, eax; char *
0x18003e778  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003e77f  mov     edx, 3E7h; void *
0x18003e784  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003e78a  mov     rcx, [rbp+78h]; this
0x18003e78e  cmp     [rsp+170h+var_118], r14
0x18003e793  jnz     short loc_18003E7A7
0x18003e795  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003e79c  mov     edx, 3E8h; void *
0x18003e7a1  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18003e7a7  mov     [rsp+170h+var_12C], r14d
0x18003e7ac  mov     rcx, [rsp+170h+var_138]
0x18003e7b1  mov     rax, [rcx]
0x18003e7b4  lea     rdx, [rsp+170h+var_12C]
0x18003e7b9  mov     rax, [rax+20h]
0x18003e7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7c2  mov     rcx, [rbp+78h]; this
0x18003e7c6  test    eax, eax
0x18003e7c8  jns     short loc_18003E7DF
0x18003e7ca  mov     r9d, eax; char *
0x18003e7cd  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003e7d4  mov     edx, 3EBh; void *
0x18003e7d9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003e7df  cmp     [rsp+170h+var_12C], r14d
0x18003e7e4  jnz     short loc_18003E807
0x18003e7e6  mov     rcx, [rsp+170h+var_138]
0x18003e7eb  test    rcx, rcx
0x18003e7ee  jz      short loc_18003E802
0x18003e7f0  mov     [rsp+170h+var_138], r14
0x18003e7f5  mov     rax, [rcx]
0x18003e7f8  mov     rax, [rax+10h]
0x18003e7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e801  nop
0x18003e802  jmp     loc_18003EB6D
0x18003e807  mov     [rsp+170h+var_F8], 0Bh
0x18003e80f  mov     rcx, [rsp+170h+var_128]
0x18003e814  mov     rax, [rcx]
0x18003e817  lea     rdx, [rsp+170h+var_F8]
0x18003e81c  mov     rax, [rax+20h]
0x18003e820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e825  mov     rcx, [rbp+78h]; this
0x18003e829  test    eax, eax
0x18003e82b  jns     short loc_18003E842
0x18003e82d  mov     r9d, eax; char *
0x18003e830  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003e837  mov     edx, 3F3h; void *
0x18003e83c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003e842  mov     [rsp+170h+var_108], r14
0x18003e847  mov     rcx, [rsp+170h+var_138]
0x18003e84c  mov     rax, [rcx]
0x18003e84f  lea     rdx, [rsp+170h+var_108]
0x18003e854  mov     rax, [rax+18h]
0x18003e858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e85d  mov     rcx, [rbp+78h]; this
0x18003e861  test    eax, eax
0x18003e863  js      loc_18003ECF7
0x18003e869  mov     [rbp+70h+sourceString], r14
0x18003e86d  mov     rcx, [rsp+170h+var_108]
0x18003e872  mov     rax, [rcx]
0x18003e875  lea     rdx, [rbp+70h+sourceString]
0x18003e879  mov     rax, [rax+18h]
0x18003e87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e882  mov     rcx, [rbp+78h]; this
0x18003e886  test    eax, eax
0x18003e888  js      loc_18003ECE2
0x18003e88e  mov     qword ptr [rbp+70h+var_E8], r14
0x18003e892  mov     rsi, [rdi]
0x18003e895  mov     rax, [rsi]
0x18003e898  mov     r15, [rax+70h]
0x18003e89c  lea     r9, [rbp+70h+string]; string
0x18003e8a0  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x18003e8a4  mov     edx, 50h ; 'P'; length
0x18003e8a9  lea     rcx, sourceString; "CN=Microsoft Corporation, O=Microsoft C"...
0x18003e8b0  call    WindowsCreateStringReference
0x18003e8b5  test    eax, eax
0x18003e8b7  jns     short loc_18003E8CF
0x18003e8b9  xor     r9d, r9d; lpArguments
0x18003e8bc  xor     r8d, r8d; nNumberOfArguments
0x18003e8bf  lea     edx, [r9+1]; dwExceptionFlags
0x18003e8c3  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e8c8  call    cs:__imp_RaiseException
0x18003e8ce  nop
0x18003e8cf  mov     r14, [rbp+70h+string]
0x18003e8d3  mov     rdi, [rbp+70h+sourceString]
0x18003e8d7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003e8db  xor     eax, eax
0x18003e8dd  inc     rbx
0x18003e8e0  cmp     [rdi+rbx*2], ax
0x18003e8e4  jnz     short loc_18003E8DD
0x18003e8e6  mov     eax, 0FFFFFFFFh
0x18003e8eb  cmp     rbx, rax
0x18003e8ee  jbe     short loc_18003E907
0x18003e8f0  mov     ebx, eax
0x18003e8f2  xor     r9d, r9d; lpArguments
0x18003e8f5  xor     r8d, r8d; nNumberOfArguments
0x18003e8f8  lea     edx, [r9+1]; dwExceptionFlags
0x18003e8fc  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e901  call    cs:__imp_RaiseException
0x18003e907  lea     r9, [rbp+70h+var_B8]; string
0x18003e90b  lea     r8, [rbp+70h+var_B8.Reserved+8]; hstringHeader
0x18003e90f  mov     edx, ebx; length
0x18003e911  mov     rcx, rdi; sourceString
0x18003e914  call    WindowsCreateStringReference
0x18003e919  nop
0x18003e91a  lea     rax, [rbp+70h+var_E8]
0x18003e91e  mov     qword ptr [rsp+170h+var_150], rax; int
0x18003e923  mov     r9, r14
0x18003e926  mov     r8, qword ptr [rbp+70h+var_B8.Reserved]
0x18003e92a  xor     edx, edx
0x18003e92c  mov     rcx, rsi
0x18003e92f  mov     rax, r15
0x18003e932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e937  mov     rcx, [rbp+78h]; this
0x18003e93b  xor     r14d, r14d
0x18003e93e  test    eax, eax
0x18003e940  js      loc_18003ECCD
0x18003e946  mov     [rsp+170h+var_110], r14
0x18003e94b  mov     rcx, qword ptr [rbp+70h+var_E8]
0x18003e94f  mov     rax, [rcx]
0x18003e952  lea     rdx, [rsp+170h+var_110]
0x18003e957  mov     rax, [rax+30h]
0x18003e95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e960  mov     rcx, [rbp+78h]; this
0x18003e964  test    eax, eax
0x18003e966  js      loc_18003ECB8
0x18003e96c  mov     [rsp+170h+var_140], r14b
0x18003e971  mov     rcx, [rsp+170h+var_110]
0x18003e976  mov     rax, [rcx]
0x18003e979  lea     rdx, [rsp+170h+var_140]
0x18003e97e  mov     rax, [rax+38h]
0x18003e982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e987  mov     rcx, [rbp+78h]; this
0x18003e98b  test    eax, eax
0x18003e98d  js      loc_18003ECA3
0x18003e993  cmp     [rsp+170h+var_140], r14b
0x18003e998  jz      loc_18003EBE2
0x18003e99e  mov     [rsp+170h+var_120], r14
0x18003e9a3  mov     rcx, [rsp+170h+var_110]
0x18003e9a8  mov     rax, [rcx]
0x18003e9ab  lea     rdx, [rsp+170h+var_120]
0x18003e9b0  mov     rax, [rax+30h]
0x18003e9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9b9  mov     rcx, [rbp+78h]; this
0x18003e9bd  test    eax, eax
0x18003e9bf  js      loc_18003EBCD
0x18003e9c5  mov     [rbp+70h+var_F0], r14
0x18003e9c9  mov     rcx, [rsp+170h+var_120]
0x18003e9ce  mov     rax, [rcx]
0x18003e9d1  lea     rdx, [rbp+70h+var_F0]
0x18003e9d5  mov     rax, [rax+30h]
0x18003e9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9de  mov     rcx, [rbp+78h]; this
0x18003e9e2  test    eax, eax
0x18003e9e4  js      loc_18003EBB8
0x18003e9ea  mov     [rsp+170h+var_130], 0FFFFh
0x18003e9f2  mov     rcx, [rbp+70h+var_F0]
0x18003e9f6  mov     rax, [rcx]
0x18003e9f9  lea     rdx, [rsp+170h+var_130]
0x18003e9fe  mov     rax, [rax+40h]
0x18003ea02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea07  mov     rcx, [rbp+78h]; this
0x18003ea0b  test    eax, eax
0x18003ea0d  js      loc_18003EBA3
0x18003ea13  mov     eax, [rsp+170h+var_F8]
0x18003ea17  cmp     eax, [rsp+170h+var_130]
0x18003ea1b  jz      short loc_18003EA8F
0x18003ea1d  cmp     [rsp+170h+var_130], 0Bh
0x18003ea22  jz      short loc_18003EA8F
0x18003ea24  cmp     eax, 0Bh
0x18003ea27  jnz     short loc_18003EA4C
0x18003ea29  xorps   xmm0, xmm0
0x18003ea2c  movups  xmmword ptr [rbp+70h+var_B8.Reserved], xmm0
0x18003ea30  movups  xmmword ptr [rbp+70h+var_B8.Reserved+10h], xmm0
0x18003ea34  movups  [rbp+70h+var_98], xmm0
0x18003ea38  lea     rcx, [rbp+70h+var_B8]; lpSystemInfo
0x18003ea3c  call    cs:__imp_GetSystemInfo
0x18003ea42  movzx   eax, word ptr [rbp+70h+var_B8.Reserved]
0x18003ea46  cmp     [rsp+170h+var_130], eax
0x18003ea4a  jz      short loc_18003EA8F
0x18003ea4c  mov     rcx, [rsp+170h+var_110]
0x18003ea51  mov     rax, [rcx]
0x18003ea54  lea     rdx, [rsp+170h+var_140]
0x18003ea59  mov     rax, [rax+40h]
0x18003ea5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea62  mov     rcx, [rbp+78h]; this
0x18003ea66  test    eax, eax
0x18003ea68  js      loc_18003EB3C
0x18003ea6e  lea     rcx, [rbp+70h+var_F0]
0x18003ea72  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18003ea77  nop
0x18003ea78  lea     rcx, [rsp+170h+var_120]
0x18003ea7d  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18003ea82  cmp     [rsp+170h+var_140], r14b
0x18003ea87  jnz     loc_18003E99E
0x18003ea8d  jmp     short loc_18003EAB3
0x18003ea8f  lea     rdx, [rsp+170h+var_120]
0x18003ea94  lea     rcx, [rsp+170h+var_100]
0x18003ea99  call    ??4?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage>::operator=(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)
0x18003ea9e  nop
0x18003ea9f  lea     rcx, [rbp+70h+var_F0]
0x18003eaa3  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18003eaa8  nop
0x18003eaa9  lea     rcx, [rsp+170h+var_120]
0x18003eaae  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18003eab3  cmp     [rsp+170h+var_100], r14
0x18003eab8  jz      short loc_18003EACE
0x18003eaba  lea     r9, [rbp+70h+var_D8]
0x18003eabe  mov     r8, r13
0x18003eac1  lea     rdx, [rsp+170h+var_100]
0x18003eac6  mov     rcx, r12
0x18003eac9  call    ?GetEvidenceFromPackage@StoreAppFinder@@SAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@7@@Z; StoreAppFinder::GetEvidenceFromPackage(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,std::vector<Application> &,std::set<std::wstring> &)
0x18003eace  mov     rcx, [rsp+170h+var_138]
0x18003ead3  mov     rax, [rcx]
0x18003ead6  lea     rdx, [rsp+170h+var_12C]
0x18003eadb  mov     rax, [rax+28h]
0x18003eadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eae4  mov     rcx, [rbp+78h]; this
0x18003eae8  test    eax, eax
0x18003eaea  js      loc_18003EB8E
0x18003eaf0  lea     rcx, [rsp+170h+var_110]
0x18003eaf5  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18003eafa  nop
0x18003eafb  lea     rcx, [rbp+70h+var_E8]
0x18003eaff  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18003eb04  nop
0x18003eb05  mov     rcx, [rbp+70h+sourceString]; pv
0x18003eb09  call    cs:__imp_CoTaskMemFree
0x18003eb0f  nop
0x18003eb10  mov     rcx, [rsp+170h+var_108]
0x18003eb15  test    rcx, rcx
0x18003eb18  jz      short loc_18003EB2C
0x18003eb1a  mov     [rsp+170h+var_108], r14
  ... truncated ...
```
