# CSyncRootManager::GetStorageProviderContentUriAndIdFromPath(ushort const *,ushort * *,ushort * *)

- ea: `0x180065380`
- end: `0x1800656a0`
- name: `?GetStorageProviderContentUriAndIdFromPath@CSyncRootManager@@UEAAJPEBGPEAPEAG1@Z`
- size: `800`
- prototype: `__int64 __fastcall(CSyncRootManager *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x180007900`
- `0x180009070`
- `0x18000a130`
- `0x18000bc30`
- `0x1800192a0`
- `0x18001d320`
- `0x18001d3e0`
- `0x180031984`
- `0x180037780`
- `0x180065380`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800655af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800655af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065664`

## string_xrefs

- `0x1800653d4`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006546a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006552c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x1800655cc`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006543b`: `Windows.Storage.Provider.StorageProviderGetContentInfoForPathResult`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSyncRootManager::GetStorageProviderContentUriAndIdFromPath(
        CSyncRootManager *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int v8; // eax
  int HandlerFromPathHelper; // ebx
  RTL_SRWLOCK *v10; // rbx
  int ContentInfoForPath; // eax
  __int64 v12; // rdx
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64); // rdi
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rdx
  PCWSTR v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rax
  int v34; // [rsp+20h] [rbp-49h]
  int v35; // [rsp+20h] [rbp-49h]
  HSTRING string; // [rsp+30h] [rbp-39h] BYREF
  __int64 v37; // [rsp+38h] [rbp-31h] BYREF
  HSTRING v38; // [rsp+40h] [rbp-29h] BYREF
  const unsigned __int16 *v39; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int16 *v40; // [rsp+50h] [rbp-19h] BYREF
  int v41; // [rsp+58h] [rbp-11h] BYREF
  int v42[2]; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  __int64 v44; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v39 = a2;
  *a3 = 0;
  *a4 = 0;
  v8 = CSyncRootManager::_EnsureSyncRootManagerCache((CSyncRootManager *)((char *)this - 32));
  HandlerFromPathHelper = v8;
  if ( v8 >= 0 )
  {
    *(_QWORD *)v42 = 0;
    v10 = (RTL_SRWLOCK *)*((_QWORD *)this + 8);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v42);
    *(_QWORD *)v42 = 0;
    HandlerFromPathHelper = CSyncRootManagerCache::GetHandlerFromPathHelper(
                              v10,
                              5,
                              a2,
                              (__int64)&GUID_b29806d1_8be0_4962_8bb6_0d4c2e14d47a,
                              (__int64)v42);
    if ( HandlerFromPathHelper < 0 )
    {
LABEL_26:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v42);
      return (unsigned int)HandlerFromPathHelper;
    }
    v37 = 0;
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Storage.Provider.StorageProviderGetContentInfoForPathResult",
      0x44u,
      0x43u);
    ContentInfoForPath = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Provider::IStorageProviderGetContentInfoForPathResult>>(
                           v44,
                           &v37);
    HandlerFromPathHelper = ContentInfoForPath;
    if ( ContentInfoForPath < 0 )
    {
      v12 = 1904;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)ContentInfoForPath,
        v35);
LABEL_7:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v37);
      goto LABEL_26;
    }
    v13 = *(_QWORD *)v42;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(**(_QWORD **)v42 + 56LL);
    v15 = v37;
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v39);
    ContentInfoForPath = v14(v13, *(_QWORD *)(v16 + 24), v15);
    HandlerFromPathHelper = ContentInfoForPath;
    if ( ContentInfoForPath < 0 )
    {
      v12 = 1905;
      goto LABEL_6;
    }
    v41 = 0;
    ContentInfoForPath = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v37 + 48LL))(v37, &v41);
    HandlerFromPathHelper = ContentInfoForPath;
    if ( ContentInfoForPath < 0 )
    {
      v12 = 1907;
      goto LABEL_6;
    }
    if ( !v41 )
    {
      v38 = 0;
      string = 0;
      v17 = v37;
      v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 64LL);
      WindowsDeleteString(0);
      v38 = 0;
      v19 = v18(v17, &v38);
      HandlerFromPathHelper = v19;
      if ( v19 < 0 )
      {
        v20 = 1912;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)v19,
          v35);
LABEL_16:
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v38);
        v38 = 0;
        goto LABEL_7;
      }
      v21 = v37;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 80LL);
      WindowsDeleteString(string);
      string = 0;
      v19 = v22(v21, &string);
      HandlerFromPathHelper = v19;
      if ( v19 < 0 )
      {
        v20 = 1913;
        goto LABEL_15;
      }
      v39 = 0;
      v40 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v39,
        0);
      StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
      v26 = _AllocString<CTCoAllocPolicy>(v25, v24, StringRawBuffer, &v39);
      HandlerFromPathHelper = v26;
      if ( v26 < 0 )
      {
        v27 = 1916;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)v26,
          v35);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v40);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v39);
        goto LABEL_16;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v40,
        0);
      v28 = WindowsGetStringRawBuffer(string, 0);
      v26 = _AllocString<CTCoAllocPolicy>(v30, v29, v28, &v40);
      HandlerFromPathHelper = v26;
      if ( v26 < 0 )
      {
        v27 = 1917;
        goto LABEL_21;
      }
      v31 = (unsigned __int16 *)v39;
      v39 = 0;
      *a3 = v31;
      v32 = v40;
      v40 = 0;
      *a4 = v32;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v40);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v39);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v38);
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v37);
    HandlerFromPathHelper = 0;
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x76C,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v8,
    v34);
  return (unsigned int)HandlerFromPathHelper;
}

```

## disassembly

```asm
0x180065380  push    rbp
0x180065382  push    rbx
0x180065383  push    rsi
0x180065384  push    rdi
0x180065385  push    r12
0x180065387  push    r14
0x180065389  push    r15
0x18006538b  lea     rbp, [rsp-27h]
0x180065390  sub     rsp, 90h
0x180065397  mov     rax, cs:__security_cookie
0x18006539e  xor     rax, rsp
0x1800653a1  mov     [rbp+57h+var_38], rax
0x1800653a5  mov     r15, r9
0x1800653a8  mov     r14, r8
0x1800653ab  mov     rsi, rdx
0x1800653ae  mov     rdi, rcx
0x1800653b1  mov     [rbp+57h+var_78], rdx
0x1800653b5  xor     r12d, r12d
0x1800653b8  mov     [r8], r12
0x1800653bb  mov     [r9], r12
0x1800653be  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x1800653c2  call    ?_EnsureSyncRootManagerCache@CSyncRootManager@@AEAAJXZ; CSyncRootManager::_EnsureSyncRootManagerCache(void)
0x1800653c7  mov     ebx, eax
0x1800653c9  test    eax, eax
0x1800653cb  jns     short loc_1800653EA
0x1800653cd  mov     rcx, [rbp+5Fh]; this
0x1800653d1  mov     r9d, eax; char *
0x1800653d4  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800653db  mov     edx, 76Ch; void *
0x1800653e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800653e5  jmp     loc_180065680
0x1800653ea  mov     qword ptr [rbp+57h+var_60], r12
0x1800653ee  mov     rbx, [rdi+40h]
0x1800653f2  lea     rcx, [rbp+57h+var_60]
0x1800653f6  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800653fb  mov     qword ptr [rbp+57h+var_60], r12
0x1800653ff  lea     rax, [rbp+57h+var_60]
0x180065403  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180065408  lea     r9, _GUID_b29806d1_8be0_4962_8bb6_0d4c2e14d47a
0x18006540f  mov     r8, rsi
0x180065412  mov     edx, 5
0x180065417  mov     rcx, rbx
0x18006541a  call    ?GetHandlerFromPathHelper@CSyncRootManagerCache@@AEAAJW4HandlerType@1@PEBGAEBU_GUID@@PEAPEAX@Z; CSyncRootManagerCache::GetHandlerFromPathHelper(CSyncRootManagerCache::HandlerType,ushort const *,_GUID const &,void * *)
0x18006541f  mov     ebx, eax
0x180065421  test    eax, eax
0x180065423  js      loc_180065677
0x180065429  mov     [rbp+57h+var_88], r12
0x18006542d  mov     [rbp+57h+var_40], r12
0x180065431  mov     r9d, 43h ; 'C'; unsigned int
0x180065437  lea     r8d, [r9+1]; unsigned int
0x18006543b  lea     rdx, ?RuntimeClass_Windows_Storage_Provider_StorageProviderGetContentInfoForPathResult@@3QBGB; "Windows.Storage.Provider.StorageProvide"...
0x180065442  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180065446  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006544b  lea     rdx, [rbp+57h+var_88]
0x18006544f  mov     rcx, [rbp+57h+var_40]
0x180065453  call    ??$ActivateInstance@V?$ComPtr@UIStorageProviderGetContentInfoForPathResult@Provider@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStorageProviderGetContentInfoForPathResult@Provider@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Provider::IStorageProviderGetContentInfoForPathResult>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Provider::IStorageProviderGetContentInfoForPathResult>>)
0x180065458  mov     ebx, eax
0x18006545a  test    eax, eax
0x18006545c  jns     short loc_180065485
0x18006545e  mov     edx, 770h; void *
0x180065463  mov     rcx, [rbp+5Fh]; this
0x180065467  mov     r9d, eax; char *
0x18006546a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065476  nop
0x180065477  lea     rcx, [rbp+57h+var_88]
0x18006547b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065480  jmp     loc_180065677
0x180065485  mov     rsi, qword ptr [rbp+57h+var_60]
0x180065489  mov     rax, [rsi]
0x18006548c  mov     rdi, [rax+38h]
0x180065490  mov     rbx, [rbp+57h+var_88]
0x180065494  lea     rdx, [rbp+57h+var_78]
0x180065498  lea     rcx, [rbp+57h+hstringHeader]
0x18006549c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800654a1  nop
0x1800654a2  mov     r8, rbx
0x1800654a5  mov     rdx, [rax+18h]
0x1800654a9  mov     rcx, rsi
0x1800654ac  mov     rax, rdi
0x1800654af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654b4  mov     ebx, eax
0x1800654b6  test    eax, eax
0x1800654b8  jns     short loc_1800654C1
0x1800654ba  mov     edx, 771h
0x1800654bf  jmp     short loc_180065463
0x1800654c1  mov     [rbp+57h+var_68], r12d
0x1800654c5  mov     rcx, [rbp+57h+var_88]
0x1800654c9  mov     rax, [rcx]
0x1800654cc  lea     rdx, [rbp+57h+var_68]
0x1800654d0  mov     rax, [rax+30h]
0x1800654d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654d9  mov     ebx, eax
0x1800654db  test    eax, eax
0x1800654dd  jns     short loc_1800654E9
0x1800654df  mov     edx, 773h
0x1800654e4  jmp     loc_180065463
0x1800654e9  cmp     [rbp+57h+var_68], r12d
0x1800654ed  jnz     loc_18006566B
0x1800654f3  mov     [rbp+57h+var_80], r12
0x1800654f7  mov     [rbp+57h+string], r12
0x1800654fb  mov     rdi, [rbp+57h+var_88]
0x1800654ff  mov     rax, [rdi]
0x180065502  mov     rbx, [rax+40h]
0x180065506  xor     ecx, ecx; string
0x180065508  call    cs:__imp_WindowsDeleteString
0x18006550e  mov     [rbp+57h+var_80], r12
0x180065512  lea     rdx, [rbp+57h+var_80]
0x180065516  mov     rcx, rdi
0x180065519  mov     rax, rbx
0x18006551c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065521  mov     ebx, eax
0x180065523  test    eax, eax
0x180065525  jns     short loc_180065561
0x180065527  mov     edx, 778h; void *
0x18006552c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065533  mov     r9d, eax; char *
0x180065536  mov     rcx, [rbp+5Fh]; this
0x18006553a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006553f  nop
0x180065540  mov     rcx, [rbp+57h+string]; string
0x180065544  call    cs:__imp_WindowsDeleteString
0x18006554a  mov     [rbp+57h+string], r12
0x18006554e  mov     rcx, [rbp+57h+var_80]; string
0x180065552  call    cs:__imp_WindowsDeleteString
0x180065558  mov     [rbp+57h+var_80], r12
0x18006555c  jmp     loc_180065477
0x180065561  mov     rdi, [rbp+57h+var_88]
0x180065565  mov     rax, [rdi]
0x180065568  mov     rbx, [rax+50h]
0x18006556c  mov     rcx, [rbp+57h+string]; string
0x180065570  call    cs:__imp_WindowsDeleteString
0x180065576  mov     [rbp+57h+string], r12
0x18006557a  lea     rdx, [rbp+57h+string]
0x18006557e  mov     rcx, rdi
0x180065581  mov     rax, rbx
0x180065584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065589  mov     ebx, eax
0x18006558b  test    eax, eax
0x18006558d  jns     short loc_180065596
0x18006558f  mov     edx, 779h
0x180065594  jmp     short loc_18006552C
0x180065596  mov     [rbp+57h+var_78], r12
0x18006559a  mov     [rbp+57h+var_70], r12
0x18006559e  xor     edx, edx
0x1800655a0  lea     rcx, [rbp+57h+var_78]
0x1800655a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800655a9  xor     edx, edx; length
0x1800655ab  mov     rcx, [rbp+57h+var_80]; string
0x1800655af  call    cs:__imp_WindowsGetStringRawBuffer
0x1800655b5  lea     r9, [rbp+57h+var_78]
0x1800655b9  mov     r8, rax
0x1800655bc  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800655c1  mov     ebx, eax
0x1800655c3  test    eax, eax
0x1800655c5  jns     short loc_1800655F8
0x1800655c7  mov     edx, 77Ch; void *
0x1800655cc  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800655d3  mov     r9d, eax; char *
0x1800655d6  mov     rcx, [rbp+5Fh]; this
0x1800655da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800655df  nop
0x1800655e0  lea     rcx, [rbp+57h+var_70]; void *
0x1800655e4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800655e9  nop
0x1800655ea  lea     rcx, [rbp+57h+var_78]; void *
0x1800655ee  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800655f3  jmp     loc_180065540
0x1800655f8  xor     edx, edx
0x1800655fa  lea     rcx, [rbp+57h+var_70]
0x1800655fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180065603  xor     edx, edx; length
0x180065605  mov     rcx, [rbp+57h+string]; string
0x180065609  call    cs:__imp_WindowsGetStringRawBuffer
0x18006560f  lea     r9, [rbp+57h+var_70]
0x180065613  mov     r8, rax
0x180065616  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18006561b  mov     ebx, eax
0x18006561d  test    eax, eax
0x18006561f  jns     short loc_180065628
0x180065621  mov     edx, 77Dh
0x180065626  jmp     short loc_1800655CC
0x180065628  mov     rax, [rbp+57h+var_78]
0x18006562c  mov     [rbp+57h+var_78], r12
0x180065630  mov     [r14], rax
0x180065633  mov     rax, [rbp+57h+var_70]
0x180065637  mov     [rbp+57h+var_70], r12
0x18006563b  mov     [r15], rax
0x18006563e  lea     rcx, [rbp+57h+var_70]; void *
0x180065642  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180065647  nop
0x180065648  lea     rcx, [rbp+57h+var_78]; void *
0x18006564c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180065651  nop
0x180065652  mov     rcx, [rbp+57h+string]; string
0x180065656  call    cs:__imp_WindowsDeleteString
0x18006565c  mov     [rbp+57h+string], r12
0x180065660  mov     rcx, [rbp+57h+var_80]; string
0x180065664  call    cs:__imp_WindowsDeleteString
0x18006566a  nop
0x18006566b  lea     rcx, [rbp+57h+var_88]
0x18006566f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065674  mov     ebx, r12d
0x180065677  lea     rcx, [rbp+57h+var_60]
0x18006567b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065680  mov     eax, ebx
0x180065682  mov     rcx, [rbp+57h+var_38]
0x180065686  xor     rcx, rsp; StackCookie
0x180065689  call    __security_check_cookie
0x18006568e  add     rsp, 90h
0x180065695  pop     r15
0x180065697  pop     r14
0x180065699  pop     r12
0x18006569b  pop     rdi
0x18006569c  pop     rsi
0x18006569d  pop     rbx
0x18006569e  pop     rbp
0x18006569f  retn
```
