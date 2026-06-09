# Windows::Internal::Security::Authentication::TokenBroker::ActivateSilentlyAndGetBuffer(Windows::Foundation::Collections::IPropertySet *,void *,HSTRING__ *,Windows::Security::Authentication::Web::Provider::WebAccountProviderOperationKind,Windows::Internal::Security::Authentication::Web::CallerContext *,bool *,_GUID *,ulong *,ulong *,Windows::Storage::Streams::IBuffer * *)

- ea: `0x180066608`
- end: `0x180067723`
- name: `?ActivateSilentlyAndGetBuffer@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIPropertySet@Collections@Foundation@5@PEAXPEAUHSTRING__@@W4WebAccountProviderOperationKind@Provider@Web@235@PEAVCallerContext@Web@2345@PEA_NPEAU_GUID@@PEAK7PEAPEAUIBuffer@Streams@Storage@5@@Z`
- size: `4379`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005aa84`
- `0x1800bfa0c`
- `0x1800c08fc`
- `0x1800c0b9c`
- `0x1800d1cc0`

## callees

- `0x180001a48`
- `0x180001ac8`
- `0x180007350`
- `0x18000bd40`
- `0x18001a510`
- `0x1800200b4`
- `0x18002dd64`
- `0x18002fa00`
- `0x180030380`
- `0x180043a1c`
- `0x180044210`
- `0x1800467f0`
- `0x18004e850`
- `0x18004fdbc`
- `0x180052088`
- `0x180052120`
- `0x180055a64`
- `0x180056d10`
- `0x18005fb0c`
- `0x180063fc4`
- `0x180066608`
- `0x18006772c`
- `0x18006d538`
- `0x18006d630`
- `0x18006e378`
- `0x1800700e0`
- `0x18008e690`
- `0x18008f928`
- `0x1800d8aa0`
- `0x1800db0a8`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180067072`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180067072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006688b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006688b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006684a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800668d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006691a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800669a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800669b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066a33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066aad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066d08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066db4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066dc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066ed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066fe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066ff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006730d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006731c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067396`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006746e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006747d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006754e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006755d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067616`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800676ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800676bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006684a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800668d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006691a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800669a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800669b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066a33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066aad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066d08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066db4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066dc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066ed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066fe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066ff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006730d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006731c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067396`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006746e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006747d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006754e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006755d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067616`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800676ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800676bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066c12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066cd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066d8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066e9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800670ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800671fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800672e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067361`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067528`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800675f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066c12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066cd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066d8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066e9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800670ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800671fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800672e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067361`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067528`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800675f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067688`

## string_xrefs

- `0x1800666e1`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800667b4`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18006682f`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800668ff`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180066984`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180066a07`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180066a91`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180066b29`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180066bf7`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180066cad`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180066d69`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180066e7a`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180066f9d`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800670ca`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18006733c`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18006740f`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800674ef`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800675b7`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::ActivateSilentlyAndGetBuffer(
        unsigned __int8 *a1,
        void *a2,
        struct Windows::Internal::Security::Authentication::Web::CallerContext *a3,
        int a4,
        struct Windows::Internal::Security::Authentication::Web::CallerContext *a5,
        _BYTE *a6,
        _OWORD *a7,
        unsigned int *a8,
        int *a9,
        struct Windows::Storage::Streams::IRandomAccessStreamReference *a10)
{
  int IsXboxSku; // eax
  unsigned int v12; // ebx
  unsigned __int64 v13; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v14; // rcx
  unsigned __int64 v15; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v16; // rcx
  int IsRegisteredForUser; // eax
  unsigned __int64 v18; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v19; // rcx
  int PluginPackageFullName; // eax
  unsigned __int64 v21; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v22; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  signed int SinglePackageFullNameFromPackageFamilyName; // eax
  int v25; // r9d
  int v26; // eax
  unsigned __int64 v27; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v28; // rcx
  int PluginEntryPoint; // eax
  unsigned __int64 v30; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v31; // rcx
  int Lpcwstr; // eax
  unsigned __int64 v33; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v34; // rcx
  int IsPluginMultiUserAware; // eax
  unsigned __int64 v36; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v37; // rcx
  struct Windows::ApplicationModel::Contracts::Internal::IContractBroker **v38; // r9
  int ContractBroker; // eax
  unsigned __int64 v40; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v41; // rcx
  int BackgroundActivationArgs; // eax
  unsigned __int64 v43; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v44; // rcx
  int ByteArrayFromBuffer; // eax
  unsigned __int64 v46; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v47; // rcx
  int v48; // eax
  int v49; // r8d
  int v50; // r9d
  unsigned __int64 v51; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v52; // rcx
  unsigned __int64 v53; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v54; // rcx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v55; // rdi
  HSTRING v56; // rbx
  const unsigned __int16 *v57; // rax
  int v58; // eax
  signed int v59; // edi
  unsigned __int64 v60; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v61; // rcx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v62; // rax
  DWORD v63; // eax
  __int64 v64; // r8
  signed int LastError; // eax
  int v66; // r9d
  unsigned __int64 v67; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v68; // rcx
  int v69; // r8d
  int v70; // r9d
  unsigned __int64 v71; // rdx
  unsigned int v72; // r14d
  int v73; // edi
  int v74; // ecx
  int v75; // r8d
  int v76; // r9d
  unsigned __int64 v77; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v78; // rcx
  __int64 v79; // rsi
  __int64 (__fastcall *v80)(__int64, __int64 *); // rdi
  int v81; // eax
  unsigned __int64 v82; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v83; // rcx
  __int64 v84; // rsi
  __int64 (__fastcall *v85)(__int64, _QWORD, Windows::Internal::Security::Authentication::TokenBroker **); // rdi
  int v86; // eax
  struct Windows::Storage::Streams::IBuffer **v87; // r8
  unsigned __int64 v88; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v89; // rcx
  int BufferFromStreamReference; // eax
  unsigned __int64 v91; // rdx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v92; // rcx
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v93; // rcx
  int bAlertable; // [rsp+20h] [rbp-E0h]
  int bAlertablea; // [rsp+20h] [rbp-E0h]
  int bAlertableb; // [rsp+20h] [rbp-E0h]
  int bAlertablec; // [rsp+20h] [rbp-E0h]
  char v99; // [rsp+50h] [rbp-B0h] BYREF
  Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *v100; // [rsp+58h] [rbp-A8h] BYREF
  bool v101[8]; // [rsp+60h] [rbp-A0h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v102; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v103; // [rsp+70h] [rbp-90h] BYREF
  HSTRING__ v104[2]; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v106; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-70h]
  __int64 v108; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v109; // [rsp+A0h] [rbp-60h] BYREF
  int v110[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v111; // [rsp+B0h] [rbp-50h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v112; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v113; // [rsp+C0h] [rbp-40h] BYREF
  void *v114; // [rsp+C8h] [rbp-38h]
  _BYTE *v115; // [rsp+D0h] [rbp-30h]
  HANDLE Handles[5]; // [rsp+D8h] [rbp-28h] BYREF
  char v117; // [rsp+100h] [rbp+0h]
  struct Windows::Storage::Streams::IRandomAccessStreamReference *v118[2]; // [rsp+108h] [rbp+8h] BYREF
  struct _GUID v119; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v110[0] = a4;
  v114 = a2;
  v106 = a1;
  v115 = a6;
  v118[0] = a10;
  v100 = 0;
  v99 = 0;
  *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = -1;
  if ( a9 )
    *a9 = -1;
  v102 = 0;
  Handles[2] = &v102;
  Handles[3] = &v100;
  Handles[4] = &v99;
  v117 = 1;
  v101[0] = 0;
  IsXboxSku = Windows::Internal::Security::Authentication::TokenBroker::IsXboxSku(
                (Windows::Internal::Security::Authentication::TokenBroker *)v101,
                (bool *)a2);
  v12 = IsXboxSku;
  if ( IsXboxSku < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BD,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)IsXboxSku,
      bAlertable);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v13);
    v14 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v14 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v14);
    }
    goto LABEL_305;
  }
  if ( !v101[0] && !Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::IsBIReadyForUser(a5) )
  {
    if ( (unsigned int)dword_180175000 > 3 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180175000,
        &byte_18014A27F,
        0,
        0);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v15);
    v16 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v16 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v16);
    }
    v12 = -805306268;
    goto LABEL_305;
  }
  IsRegisteredForUser = TbEnsurePfnIsRegisteredForUser(*((_QWORD *)a5 + 1), (HSTRING)a3);
  v12 = IsRegisteredForUser;
  if ( IsRegisteredForUser < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C9,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)IsRegisteredForUser,
      bAlertable);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v18);
    v19 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v19 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v19);
    }
    goto LABEL_305;
  }
  string = 0;
  if ( (unsigned __int8)IsEnsurePackageRegisteredForMultiUserSessionPresent() )
  {
    PluginPackageFullName = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPackageFullName(
                              a5,
                              (HSTRING)a3,
                              &string);
    v12 = PluginPackageFullName;
    if ( PluginPackageFullName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D0,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)PluginPackageFullName,
        bAlertable);
      if ( string )
        WindowsDeleteString(string);
      if ( v102 )
        Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v21);
      v22 = v100;
      if ( v100 )
      {
        if ( v99 )
        {
          Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
          v22 = v100;
        }
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v22);
      }
      goto LABEL_305;
    }
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a3, 0);
    SinglePackageFullNameFromPackageFamilyName = Windows::Internal::Security::Authentication::Web::CallerContext::GetSinglePackageFullNameFromPackageFamilyName(
                                                   a5,
                                                   StringRawBuffer,
                                                   (struct Windows::Internal::String *)&string);
    if ( SinglePackageFullNameFromPackageFamilyName < 0 )
    {
      if ( (unsigned int)dword_180175000 > 3 )
      {
        v109 = SinglePackageFullNameFromPackageFamilyName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180175000,
          (unsigned int)byte_18014A223,
          0,
          v25,
          (__int64)&v109);
      }
      WindowsDeleteString(string);
      string = 0;
      v26 = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPackageFullName(
              a5,
              (HSTRING)a3,
              &string);
      v12 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2DF,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v26,
          bAlertable);
        if ( string )
          WindowsDeleteString(string);
        if ( v102 )
          Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v27);
        v28 = v100;
        if ( v100 )
        {
          if ( v99 )
          {
            Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
            v28 = v100;
          }
          Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v28);
        }
        goto LABEL_305;
      }
    }
  }
  v103 = 0;
  v113 = 0;
  PluginEntryPoint = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginEntryPoint(
                       a5,
                       (HSTRING)a3,
                       &v103);
  v12 = PluginEntryPoint;
  if ( PluginEntryPoint < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E6,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)PluginEntryPoint,
      bAlertable);
    if ( v103 )
      WindowsDeleteString(v103);
    if ( string )
      WindowsDeleteString(string);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v30);
    v31 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v31 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v31);
    }
    goto LABEL_305;
  }
  Lpcwstr = Windows::Internal::String::GetLpcwstr((Windows::Internal::String *)&v103, (const unsigned __int16 **)&v113);
  v12 = Lpcwstr;
  if ( Lpcwstr < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)Lpcwstr,
      bAlertable);
    if ( v103 )
      WindowsDeleteString(v103);
    if ( string )
      WindowsDeleteString(string);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v33);
    v34 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v34 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v34);
    }
    goto LABEL_305;
  }
  v101[0] = 0;
  IsPluginMultiUserAware = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(
                             a5,
                             (HSTRING)a3,
                             v101);
  v12 = IsPluginMultiUserAware;
  if ( IsPluginMultiUserAware < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)IsPluginMultiUserAware,
      bAlertable);
    if ( v103 )
      WindowsDeleteString(v103);
    if ( string )
      WindowsDeleteString(string);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v36);
    v37 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v37 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v37);
    }
    goto LABEL_305;
  }
  *(_QWORD *)&v104[0].unused = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
  ContractBroker = Windows::Internal::Security::Authentication::TokenBroker::CreateContractBroker(a5, a3, v104, v38);
  v12 = ContractBroker;
  if ( ContractBroker < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)ContractBroker,
      bAlertable);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
    if ( v103 )
      WindowsDeleteString(v103);
    if ( string )
      WindowsDeleteString(string);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v40);
    v41 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v41 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v41);
    }
    goto LABEL_305;
  }
  v108 = 0;
  hObject = 0;
  bAlertablea = (int)v106;
  BackgroundActivationArgs = CreateBackgroundActivationArgs(a5, (unsigned int)v110[0], *(_QWORD *)&v104[0].unused, a3);
  v12 = BackgroundActivationArgs;
  if ( BackgroundActivationArgs < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)BackgroundActivationArgs,
      bAlertablea);
    if ( hObject )
      CloseHandle(hObject);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
    if ( v103 )
      WindowsDeleteString(v103);
    if ( string )
      WindowsDeleteString(string);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v43);
    v44 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v44 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v44);
    }
    goto LABEL_305;
  }
  v109 = 0;
  v106 = 0;
  ByteArrayFromBuffer = Windows::Internal::Security::Authentication::TokenBroker::GetByteArrayFromBuffer(
                          v108,
                          &v109,
                          &v106);
  v12 = ByteArrayFromBuffer;
  if ( ByteArrayFromBuffer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F9,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)ByteArrayFromBuffer,
      bAlertablea);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
    if ( hObject )
      CloseHandle(hObject);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
    if ( v103 )
      WindowsDeleteString(v103);
    if ( string )
      WindowsDeleteString(string);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v46);
    v47 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v47 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v47);
    }
    goto LABEL_305;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient>::InternalRelease(&v100);
  v48 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient,Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient,>(&v100);
  v12 = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v48,
      bAlertablea);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
    if ( hObject )
      CloseHandle(hObject);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
    if ( v103 )
      WindowsDeleteString(v103);
    if ( string )
      WindowsDeleteString(string);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v51);
    v52 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v52 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v52);
    }
    goto LABEL_305;
  }
  v119 = GUID_13847af0_912c_470b_87b7_7fc3483bd5f9;
  if ( *((_QWORD *)a5 + 38) )
  {
    v114 = (void *)*((_QWORD *)a5 + 38);
  }
  else
  {
    if ( (unsigned int)dword_180175000 > 5 )
    {
      *(_QWORD *)v110 = v114;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (_DWORD)v114,
        (unsigned int)&unk_18014A190,
        v49,
        v50,
        (__int64)v110);
    }
    if ( !v114 )
    {
      if ( (unsigned int)dword_180175000 > 2 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_180175000,
          &dword_18014A1D4,
          0,
          0);
      v12 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x313,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)0x80070057LL,
        bAlertablea);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
      if ( hObject )
        CloseHandle(hObject);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
      if ( v103 )
        WindowsDeleteString(v103);
      if ( string )
        WindowsDeleteString(string);
      if ( v102 )
        Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v53);
      v54 = v100;
      if ( v100 )
      {
        if ( v99 )
        {
          Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
          v54 = v100;
        }
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v54);
      }
      goto LABEL_305;
    }
  }
  if ( (unsigned int)dword_180175000 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &unk_18014A150,
      0,
      0);
  v55 = v100;
  v56 = string;
  v57 = WindowsGetStringRawBuffer(string, 0);
  v58 = Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::LaunchBackgroundTask(
          v55,
          a5,
          v57,
          v113,
          &v119,
          v106,
          v109,
          v114,
          v101[0]);
  v59 = v58;
  if ( v58 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x323,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v58,
      bAlertableb);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
    if ( hObject )
      CloseHandle(hObject);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
    if ( v103 )
      WindowsDeleteString(v103);
    if ( v56 )
      WindowsDeleteString(v56);
    if ( v102 )
      Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v60);
    v61 = v100;
    if ( v100 )
    {
      if ( v99 )
      {
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
        v61 = v100;
      }
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v61);
    }
LABEL_183:
    v12 = v59;
    goto LABEL_305;
  }
  v62 = v100;
  if ( a7 )
    *a7 = *(_OWORD *)((char *)v100 + 88);
  Handles[0] = hObject;
  Handles[1] = *((HANDLE *)v62 + 18);
  v63 = WaitForMultipleObjectsEx(2u, Handles, 0, 0x493E0u, 0);
  switch ( v63 )
  {
    case 0xFFFFFFFF:
      LastError = GetLastError();
      v59 = LastError;
      if ( LastError > 0 )
        v59 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_180175000 > 2 )
      {
        v110[0] = v59;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180175000,
          (unsigned int)&word_18014A0D6,
          0,
          v66,
          (__int64)v110);
      }
      if ( v59 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x338,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v59,
          bAlertablec);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
      if ( hObject )
        CloseHandle(hObject);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
      if ( v103 )
        WindowsDeleteString(v103);
      if ( v56 )
        WindowsDeleteString(v56);
      if ( v102 )
        Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v67);
      v68 = v100;
      if ( v100 )
      {
        if ( v99 )
        {
          Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
          v68 = v100;
        }
        Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v68);
      }
      goto LABEL_183;
    case 0x102u:
      v99 = 1;
      if ( (unsigned int)dword_180175000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180175000, 0x400000000000LL, v64) )
      {
        v110[0] = *((_DWORD *)v100 + 30);
        *(_OWORD *)v118 = *(_OWORD *)((char *)v100 + 88);
        v113 = (unsigned __int16 *)v118;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v110[0],
          (unsigned int)byte_18014A119,
          v69,
          v70,
          (__int64)&v113,
          (__int64)v110);
      }
      *v115 = 1;
      if ( a8 )
        *a8 = 128;
      if ( a9 )
        *a9 = 1460;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
      if ( hObject )
        CloseHandle(hObject);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
      if ( v103 )
        WindowsDeleteString(v103);
      if ( v56 )
        WindowsDeleteString(v56);
      break;
    case 1u:
      v72 = *((_DWORD *)v100 + 29);
      v73 = *((_DWORD *)v100 + 28);
      if ( (unsigned int)dword_180175000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180175000, 0x400000000000LL, v64) )
      {
        v110[0] = v73;
        v109 = v72;
        *(_OWORD *)v118 = *(_OWORD *)((char *)v100 + 88);
        v113 = (unsigned __int16 *)v118;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v74,
          (unsigned int)byte_18014A099,
          v75,
          v76,
          (__int64)&v113,
          (__int64)&v109,
          (__int64)v110);
      }
      *v115 = 1;
      if ( a8 )
        *a8 = v72;
      if ( a9 )
        *a9 = v73;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
      if ( hObject )
        CloseHandle(hObject);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
      if ( v103 )
        WindowsDeleteString(v103);
      if ( v56 )
        WindowsDeleteString(v56);
      break;
    default:
      if ( v63 )
      {
        v59 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x372,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)0x8000FFFFLL,
          bAlertablec);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
        if ( hObject )
          CloseHandle(hObject);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
        if ( v103 )
          WindowsDeleteString(v103);
        if ( v56 )
          WindowsDeleteString(v56);
        if ( v102 )
          Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v77);
        v78 = v100;
        if ( v100 )
        {
          if ( v99 )
          {
            Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
            v78 = v100;
          }
          Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v78);
        }
        goto LABEL_183;
      }
      v112 = 0;
      v111 = 0;
      v79 = *(_QWORD *)&v104[0].unused;
      v80 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)&v104[0].unused + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
      v81 = v80(v79, &v111);
      v59 = v81;
      if ( v81 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x377,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v81,
          bAlertablec);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
        if ( hObject )
          CloseHandle(hObject);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
        if ( v103 )
          WindowsDeleteString(v103);
        if ( v56 )
          WindowsDeleteString(v56);
        if ( v102 )
          Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v82);
        v83 = v100;
        if ( v100 )
        {
          if ( v99 )
          {
            Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
            v83 = v100;
          }
          Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v83);
        }
        goto LABEL_183;
      }
      v84 = v111;
      v85 = *(__int64 (__fastcall **)(__int64, _QWORD, Windows::Internal::Security::Authentication::TokenBroker **))(*(_QWORD *)v111 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
      v86 = v85(v84, 0, &v112);
      v59 = v86;
      if ( v86 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x378,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v86,
          bAlertablec);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
        if ( hObject )
          CloseHandle(hObject);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
        if ( v103 )
          WindowsDeleteString(v103);
        if ( v56 )
          WindowsDeleteString(v56);
        if ( v102 )
          Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v88);
        v89 = v100;
        if ( v100 )
        {
          if ( v99 )
          {
            Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
            v89 = v100;
          }
          Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v89);
        }
        goto LABEL_183;
      }
      BufferFromStreamReference = Windows::Internal::Security::Authentication::TokenBroker::ReadBufferFromStreamReference(
                                    v112,
                                    v118[0],
                                    v87);
      v59 = BufferFromStreamReference;
      if ( BufferFromStreamReference < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x379,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)BufferFromStreamReference,
          bAlertablec);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
        if ( hObject )
          CloseHandle(hObject);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
        if ( v103 )
          WindowsDeleteString(v103);
        if ( v56 )
          WindowsDeleteString(v56);
        if ( v102 )
          Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v91);
        v92 = v100;
        if ( v100 )
        {
          if ( v99 )
          {
            Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
            v92 = v100;
          }
          Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v92);
        }
        goto LABEL_183;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v106);
      if ( hObject )
        CloseHandle(hObject);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v108);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v104);
      if ( v103 )
        WindowsDeleteString(v103);
      if ( v56 )
        WindowsDeleteString(v56);
      break;
  }
  if ( v102 )
    Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v102, v71);
  v93 = v100;
  if ( v100 )
  {
    if ( v99 )
    {
      Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(v100);
      v93 = v100;
    }
    Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(v93);
  }
  v12 = 0;
LABEL_305:
  Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient>::InternalRelease(&v100);
  return v12;
}

```

## disassembly

```asm
0x180066608  push    rbp
0x18006660a  push    rbx
0x18006660b  push    rsi
0x18006660c  push    rdi
0x18006660d  push    r12
0x18006660f  push    r13
0x180066611  push    r14
0x180066613  push    r15
0x180066615  lea     rbp, [rsp-38h]
0x18006661a  sub     rsp, 138h
0x180066621  mov     rax, cs:__security_cookie
0x180066628  xor     rax, rsp
0x18006662b  mov     [rbp+70h+var_48], rax
0x18006662f  mov     [rbp+70h+var_C8], r9d
0x180066633  mov     rdi, r8
0x180066636  mov     [rbp+70h+var_A8], rdx
0x18006663a  mov     [rbp+70h+var_E8], rcx
0x18006663e  mov     r14, [rbp+70h+arg_20]
0x180066645  mov     rax, [rbp+70h+arg_28]
0x18006664c  mov     [rbp+70h+var_A0], rax
0x180066650  mov     r13, [rbp+70h+arg_30]
0x180066657  mov     r12, [rbp+70h+arg_38]
0x18006665e  mov     r15, [rbp+70h+arg_40]
0x180066665  mov     rcx, [rbp+70h+arg_48]
0x18006666c  mov     [rbp+70h+var_68], rcx
0x180066670  xor     esi, esi
0x180066672  mov     [rsp+170h+var_118], rsi
0x180066677  mov     [rsp+170h+var_120], sil
0x18006667c  mov     [rax], sil
0x18006667f  test    r13, r13
0x180066682  jz      short loc_18006668D
0x180066684  xorps   xmm0, xmm0
0x180066687  movdqu  xmmword ptr [r13+0], xmm0
0x18006668d  or      eax, 0FFFFFFFFh
0x180066690  test    r12, r12
0x180066693  jz      short loc_180066699
0x180066695  mov     [r12], eax
0x180066699  test    r15, r15
0x18006669c  jz      short loc_1800666A1
0x18006669e  mov     [r15], eax
0x1800666a1  mov     [rsp+170h+var_108], rsi
0x1800666a6  lea     rax, [rsp+170h+var_108]
0x1800666ab  mov     [rbp+70h+var_88], rax
0x1800666af  lea     rax, [rsp+170h+var_118]
0x1800666b4  mov     [rbp+70h+var_80], rax
0x1800666b8  lea     rax, [rsp+170h+var_120]
0x1800666bd  mov     [rbp+70h+var_78], rax
0x1800666c1  mov     [rbp+70h+var_70], 1
0x1800666c5  mov     [rsp+170h+var_110], sil
0x1800666ca  lea     rcx, [rsp+170h+var_110]; this
0x1800666cf  call    ?IsXboxSku@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEA_N@Z; Windows::Internal::Security::Authentication::TokenBroker::IsXboxSku(bool *)
0x1800666d4  mov     ebx, eax
0x1800666d6  test    eax, eax
0x1800666d8  jns     short loc_180066728
0x1800666da  mov     rcx, [rbp+78h]; this
0x1800666de  mov     r9d, eax; char *
0x1800666e1  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800666e8  mov     edx, 2BDh; void *
0x1800666ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800666f2  nop
0x1800666f3  mov     rcx, [rsp+170h+var_108]; this
0x1800666f8  test    rcx, rcx
0x1800666fb  jz      short loc_180066702
0x1800666fd  call    ?FreeTokenBindingContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_K@Z; Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(unsigned __int64)
0x180066702  mov     rcx, [rsp+170h+var_118]; this
0x180066707  test    rcx, rcx
0x18006670a  jz      short loc_180066723
0x18006670c  cmp     [rsp+170h+var_120], sil
0x180066711  jz      short loc_18006671D
0x180066713  call    ?CancelBackgroundTask@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(void)
0x180066718  mov     rcx, [rsp+170h+var_118]; this
0x18006671d  call    ?UnregisterCallbacks@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAXXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(void)
0x180066722  nop
0x180066723  jmp     loc_1800676F7
0x180066728  cmp     [rsp+170h+var_110], sil
0x18006672d  jnz     short loc_18006679B
0x18006672f  mov     rcx, r14; struct Windows::Internal::Security::Authentication::Web::CallerContext *
0x180066732  call    ?IsBIReadyForUser@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@SA_NPEAVCallerContext@23456@@Z; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::IsBIReadyForUser(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180066737  test    al, al
0x180066739  jnz     short loc_18006679B
0x18006673b  mov     eax, cs:dword_180175000
0x180066741  cmp     eax, 3
0x180066744  jbe     short loc_180066761
0x180066746  xor     r9d, r9d
0x180066749  xor     r8d, r8d
0x18006674c  lea     rdx, byte_18014A27F
0x180066753  lea     rcx, dword_180175000
0x18006675a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006675f  xor     esi, esi
0x180066761  mov     rcx, [rsp+170h+var_108]; this
0x180066766  test    rcx, rcx
0x180066769  jz      short loc_180066770
0x18006676b  call    ?FreeTokenBindingContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_K@Z; Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(unsigned __int64)
0x180066770  mov     rcx, [rsp+170h+var_118]; this
0x180066775  test    rcx, rcx
0x180066778  jz      short loc_180066791
0x18006677a  cmp     [rsp+170h+var_120], sil
0x18006677f  jz      short loc_18006678B
0x180066781  call    ?CancelBackgroundTask@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(void)
0x180066786  mov     rcx, [rsp+170h+var_118]; this
0x18006678b  call    ?UnregisterCallbacks@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAXXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(void)
0x180066790  nop
0x180066791  mov     ebx, 0D0000064h
0x180066796  jmp     loc_1800676F7
0x18006679b  mov     rdx, rdi; HSTRING
0x18006679e  mov     rcx, [r14+8]; unsigned __int64
0x1800667a2  call    ?TbEnsurePfnIsRegisteredForUser@@YAJ_KPEAUHSTRING__@@@Z; TbEnsurePfnIsRegisteredForUser(unsigned __int64,HSTRING__ *)
0x1800667a7  mov     ebx, eax
0x1800667a9  test    eax, eax
0x1800667ab  jns     short loc_1800667FB
0x1800667ad  mov     rcx, [rbp+78h]; this
0x1800667b1  mov     r9d, eax; char *
0x1800667b4  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800667bb  mov     edx, 2C9h; void *
0x1800667c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800667c5  nop
0x1800667c6  mov     rcx, [rsp+170h+var_108]; this
0x1800667cb  test    rcx, rcx
0x1800667ce  jz      short loc_1800667D5
0x1800667d0  call    ?FreeTokenBindingContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_K@Z; Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(unsigned __int64)
0x1800667d5  mov     rcx, [rsp+170h+var_118]; this
0x1800667da  test    rcx, rcx
0x1800667dd  jz      short loc_1800667F6
0x1800667df  cmp     [rsp+170h+var_120], sil
0x1800667e4  jz      short loc_1800667F0
0x1800667e6  call    ?CancelBackgroundTask@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(void)
0x1800667eb  mov     rcx, [rsp+170h+var_118]; this
0x1800667f0  call    ?UnregisterCallbacks@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAXXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(void)
0x1800667f5  nop
0x1800667f6  jmp     loc_1800676F7
0x1800667fb  mov     [rbp+70h+string], rsi
0x1800667ff  call    IsEnsurePackageRegisteredForMultiUserSessionPresent
0x180066804  lea     rsi, dword_180175000
0x18006680b  test    al, al
0x18006680d  jz      short loc_180066886
0x18006680f  lea     r8, [rbp+70h+string]; HSTRING *
0x180066813  mov     rdx, rdi; HSTRING
0x180066816  mov     rcx, r14; this
0x180066819  call    ?GetPluginPackageFullName@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@QEAUHSTRING__@@PEAPEAU9@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPackageFullName(Windows::Internal::Security::Authentication::Web::CallerContext *,HSTRING__ * const,HSTRING__ * *)
0x18006681e  mov     ebx, eax
0x180066820  test    eax, eax
0x180066822  jns     loc_180066956
0x180066828  mov     rcx, [rbp+78h]; this
0x18006682c  mov     r9d, eax; char *
0x18006682f  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180066836  mov     edx, 2D0h; void *
0x18006683b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066840  nop
0x180066841  mov     rcx, [rbp+70h+string]; string
0x180066845  test    rcx, rcx
0x180066848  jz      short loc_180066851
0x18006684a  call    cs:__imp_WindowsDeleteString
0x180066850  nop
0x180066851  mov     rcx, [rsp+170h+var_108]; this
0x180066856  test    rcx, rcx
0x180066859  jz      short loc_180066860
0x18006685b  call    ?FreeTokenBindingContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_K@Z; Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(unsigned __int64)
0x180066860  mov     rcx, [rsp+170h+var_118]; this
0x180066865  test    rcx, rcx
0x180066868  jz      short loc_180066881
0x18006686a  cmp     [rsp+170h+var_120], 0
0x18006686f  jz      short loc_18006687B
0x180066871  call    ?CancelBackgroundTask@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(void)
0x180066876  mov     rcx, [rsp+170h+var_118]; this
0x18006687b  call    ?UnregisterCallbacks@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAXXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(void)
0x180066880  nop
0x180066881  jmp     loc_1800676F7
0x180066886  xor     edx, edx; length
0x180066888  mov     rcx, rdi; string
0x18006688b  call    cs:__imp_WindowsGetStringRawBuffer
0x180066891  lea     r8, [rbp+70h+string]; struct Windows::Internal::String *
0x180066895  mov     rdx, rax; unsigned __int16 *
0x180066898  mov     rcx, r14; this
0x18006689b  call    ?GetSinglePackageFullNameFromPackageFamilyName@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEBGAEAVString@56@@Z; Windows::Internal::Security::Authentication::Web::CallerContext::GetSinglePackageFullNameFromPackageFamilyName(ushort const *,Windows::Internal::String &)
0x1800668a0  test    eax, eax
0x1800668a2  jns     loc_180066956
0x1800668a8  mov     ecx, cs:dword_180175000
0x1800668ae  cmp     ecx, 3
0x1800668b1  jbe     short loc_1800668D1
0x1800668b3  mov     [rbp+70h+var_D0], eax
0x1800668b6  lea     rax, [rbp+70h+var_D0]
0x1800668ba  mov     qword ptr [rsp+170h+bAlertable], rax; int
0x1800668bf  xor     r8d, r8d
0x1800668c2  lea     rdx, byte_18014A223
0x1800668c9  mov     rcx, rsi
0x1800668cc  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800668d1  mov     rcx, [rbp+70h+string]; string
0x1800668d5  call    cs:__imp_WindowsDeleteString
0x1800668db  mov     [rbp+70h+string], 0
0x1800668e3  lea     r8, [rbp+70h+string]; HSTRING *
0x1800668e7  mov     rdx, rdi; HSTRING
0x1800668ea  mov     rcx, r14; this
0x1800668ed  call    ?GetPluginPackageFullName@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@QEAUHSTRING__@@PEAPEAU9@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPackageFullName(Windows::Internal::Security::Authentication::Web::CallerContext *,HSTRING__ * const,HSTRING__ * *)
0x1800668f2  mov     ebx, eax
0x1800668f4  test    eax, eax
0x1800668f6  jns     short loc_180066956
0x1800668f8  mov     rcx, [rbp+78h]; this
0x1800668fc  mov     r9d, eax; char *
0x1800668ff  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180066906  mov     edx, 2DFh; void *
0x18006690b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066910  nop
0x180066911  mov     rcx, [rbp+70h+string]; string
0x180066915  test    rcx, rcx
0x180066918  jz      short loc_180066921
0x18006691a  call    cs:__imp_WindowsDeleteString
0x180066920  nop
0x180066921  mov     rcx, [rsp+170h+var_108]; this
0x180066926  test    rcx, rcx
0x180066929  jz      short loc_180066930
0x18006692b  call    ?FreeTokenBindingContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_K@Z; Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(unsigned __int64)
0x180066930  mov     rcx, [rsp+170h+var_118]; this
0x180066935  test    rcx, rcx
0x180066938  jz      short loc_180066951
0x18006693a  cmp     [rsp+170h+var_120], 0
0x18006693f  jz      short loc_18006694B
0x180066941  call    ?CancelBackgroundTask@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(void)
0x180066946  mov     rcx, [rsp+170h+var_118]; this
0x18006694b  call    ?UnregisterCallbacks@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAXXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(void)
0x180066950  nop
0x180066951  jmp     loc_1800676F7
0x180066956  mov     [rsp+170h+var_100], 0
0x18006695f  mov     [rbp+70h+var_B0], 0
0x180066967  lea     r8, [rsp+170h+var_100]; HSTRING *
0x18006696c  mov     rdx, rdi; HSTRING
0x18006696f  mov     rcx, r14; this
0x180066972  call    ?GetPluginEntryPoint@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@QEAUHSTRING__@@PEAPEAU9@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginEntryPoint(Windows::Internal::Security::Authentication::Web::CallerContext *,HSTRING__ * const,HSTRING__ * *)
0x180066977  mov     ebx, eax
0x180066979  test    eax, eax
0x18006697b  jns     short loc_1800669EC
0x18006697d  mov     rcx, [rbp+78h]; this
0x180066981  mov     r9d, eax; char *
0x180066984  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006698b  mov     edx, 2E6h; void *
0x180066990  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066995  nop
0x180066996  mov     rcx, [rsp+170h+var_100]; string
0x18006699b  test    rcx, rcx
0x18006699e  jz      short loc_1800669A7
0x1800669a0  call    cs:__imp_WindowsDeleteString
0x1800669a6  nop
0x1800669a7  mov     rcx, [rbp+70h+string]; string
0x1800669ab  test    rcx, rcx
0x1800669ae  jz      short loc_1800669B7
0x1800669b0  call    cs:__imp_WindowsDeleteString
0x1800669b6  nop
0x1800669b7  mov     rcx, [rsp+170h+var_108]; this
0x1800669bc  test    rcx, rcx
0x1800669bf  jz      short loc_1800669C6
0x1800669c1  call    ?FreeTokenBindingContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_K@Z; Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(unsigned __int64)
0x1800669c6  mov     rcx, [rsp+170h+var_118]; this
0x1800669cb  test    rcx, rcx
0x1800669ce  jz      short loc_1800669E7
0x1800669d0  cmp     [rsp+170h+var_120], 0
0x1800669d5  jz      short loc_1800669E1
0x1800669d7  call    ?CancelBackgroundTask@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(void)
0x1800669dc  mov     rcx, [rsp+170h+var_118]; this
0x1800669e1  call    ?UnregisterCallbacks@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAXXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(void)
0x1800669e6  nop
0x1800669e7  jmp     loc_1800676F7
0x1800669ec  lea     rdx, [rbp+70h+var_B0]; unsigned __int16 **
0x1800669f0  lea     rcx, [rsp+170h+var_100]; this
0x1800669f5  call    ?GetLpcwstr@String@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::String::GetLpcwstr(ushort const * *)
0x1800669fa  mov     ebx, eax
0x1800669fc  test    eax, eax
0x1800669fe  jns     short loc_180066A6F
0x180066a00  mov     rcx, [rbp+78h]; this
0x180066a04  mov     r9d, eax; char *
0x180066a07  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180066a0e  mov     edx, 2E7h; void *
0x180066a13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066a18  nop
0x180066a19  mov     rcx, [rsp+170h+var_100]; string
0x180066a1e  test    rcx, rcx
0x180066a21  jz      short loc_180066A2A
0x180066a23  call    cs:__imp_WindowsDeleteString
0x180066a29  nop
0x180066a2a  mov     rcx, [rbp+70h+string]; string
0x180066a2e  test    rcx, rcx
0x180066a31  jz      short loc_180066A3A
0x180066a33  call    cs:__imp_WindowsDeleteString
0x180066a39  nop
0x180066a3a  mov     rcx, [rsp+170h+var_108]; this
0x180066a3f  test    rcx, rcx
0x180066a42  jz      short loc_180066A49
0x180066a44  call    ?FreeTokenBindingContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_K@Z; Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(unsigned __int64)
0x180066a49  mov     rcx, [rsp+170h+var_118]; this
0x180066a4e  test    rcx, rcx
0x180066a51  jz      short loc_180066A6A
0x180066a53  cmp     [rsp+170h+var_120], 0
0x180066a58  jz      short loc_180066A64
0x180066a5a  call    ?CancelBackgroundTask@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::CancelBackgroundTask(void)
0x180066a5f  mov     rcx, [rsp+170h+var_118]; this
0x180066a64  call    ?UnregisterCallbacks@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAXXZ; Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::UnregisterCallbacks(void)
0x180066a69  nop
0x180066a6a  jmp     loc_1800676F7
0x180066a6f  mov     [rsp+170h+var_110], 0
0x180066a74  lea     r8, [rsp+170h+var_110]; bool *
0x180066a79  mov     rdx, rdi; HSTRING
0x180066a7c  mov     rcx, r14; struct Windows::Internal::Security::Authentication::Web::CallerContext *
  ... truncated ...
```
