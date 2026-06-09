# FindTokenCacheEntry(HSTRING__ * const,Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *,__int64 *)

- ea: `0x18010a528`
- end: `0x18010afeb`
- name: `?FindTokenCacheEntry@@YAJQEAUHSTRING__@@PEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@7@W4StoredObjectType@TokenBroker@56Internal@7@AEAVStoredObjectId@TokenBroker@56Internal@7@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAKPEA_J@Z`
- size: `2755`
- prototype: `__int64 __usercall@<rax>(HSTRING string2@<rcx>, Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010b384`
- `0x18010b53c`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18001a510`
- `0x180026a5c`
- `0x18002eac4`
- `0x1800344b8`
- `0x180045454`
- `0x18004c014`
- `0x18004dc68`
- `0x1800506f8`
- `0x180053cfc`
- `0x18005fd50`
- `0x180070660`
- `0x18007f6e0`
- `0x18010a528`
- `0x18010bf74`
- `0x18010c554`
- `0x18010dbac`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010adcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010ae0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010adcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010ae0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010acde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010adb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ae8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010aeb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010acde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010adb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ae8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010aeb1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010ae60`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010ae60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010a76c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010ab48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010af5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010afcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010a76c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010ab48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010af5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010afcf`

## string_xrefs

- `0x18010a5a8`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010a65a`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010a6ce`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010a7bd`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010a80d`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010a87e`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010a963`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010a9b3`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010aa02`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010aa7a`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010aad2`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010ab95`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010abeb`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010ac3c`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010ac81`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010acc3`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010ad19`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010ad54`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010ad96`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010adea`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall FindTokenCacheEntry(
        HSTRING string2,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3,
        unsigned int a4,
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *a5,
        __int64 a6,
        _DWORD *a7,
        _QWORD *a8)
{
  char v12; // r14
  int v13; // ebx
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(_QWORD, GUID *, HSTRING *); // rbx
  __int64 v16; // rdx
  int StoredObjectInfo; // eax
  HLOCAL v18; // rcx
  HLOCAL v19; // rcx
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  int v24; // eax
  struct Windows::Storage::Streams::IBuffer **v25; // r9
  int BufferFromByteArray; // eax
  __int64 (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rbx
  int v28; // eax
  int v29; // eax
  unsigned __int8 *v30; // rbx
  int v31; // eax
  unsigned int v32; // edi
  HLOCAL v33; // rcx
  __int64 (__fastcall *v35)(unsigned __int8 *, GUID *, __int64 *); // rdi
  int v36; // eax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD, __int64 *); // rbx
  int v39; // eax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v42; // eax
  int v43; // eax
  int v44; // eax
  __int64 (__fastcall *v45)(__int64, _QWORD, _QWORD); // rbx
  int v46; // eax
  int v47; // eax
  int v48; // eax
  PCWSTR StringRawBuffer; // rax
  int v50; // eax
  PCWSTR v51; // rax
  const WCHAR *v52; // rcx
  const WCHAR *v53; // r8
  __int64 v54; // rdx
  HLOCAL v55; // rcx
  bool v56; // zf
  unsigned __int16 *v57; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v64; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v65[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 *v66; // [rsp+70h] [rbp-90h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v67; // [rsp+78h] [rbp-88h] BYREF
  __int64 v68; // [rsp+80h] [rbp-80h] BYREF
  __int64 v69; // [rsp+88h] [rbp-78h] BYREF
  __int64 v70; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  __int64 v72; // [rsp+A0h] [rbp-60h] BYREF
  __int64 (__fastcall ***v73)(_QWORD, GUID *, __int64); // [rsp+A8h] [rbp-58h] BYREF
  __int64 v74; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v75; // [rsp+B8h] [rbp-48h] BYREF
  size_t Size; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v77; // [rsp+C8h] [rbp-38h] BYREF
  __int64 (__fastcall ***v78)(_QWORD, GUID *, __int64); // [rsp+D0h] [rbp-30h] BYREF
  int v79; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v80; // [rsp+E0h] [rbp-20h] BYREF
  LPCWCH lpString1; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v82; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v83; // [rsp+F8h] [rbp-8h]
  int v84; // [rsp+100h] [rbp+0h] BYREF
  int v85; // [rsp+104h] [rbp+4h] BYREF
  _QWORD v86[9]; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v12 = 0;
  hMem = 0;
  LODWORD(Size) = 0;
  lpString1 = (LPCWCH)&hMem;
  v82 = 0;
  LOBYTE(v83) = 1;
  v13 = CreateRequestHash(a2, a3, 0, 1, &Size, &v82);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&lpString1);
  if ( v13 < 0 )
  {
    v14 = 1061;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
LABEL_113:
    v18 = hMem;
    hMem = 0;
    goto LABEL_114;
  }
  v13 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromBytes(
          a5,
          (unsigned __int8 *)hMem,
          (unsigned int)Size);
  if ( v13 < 0 )
  {
    v14 = 1067;
    goto LABEL_3;
  }
  v84 = 0;
  if ( a3 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 56LL))(a3, &v84);
    if ( v13 < 0 )
    {
      v14 = 1072;
      goto LABEL_3;
    }
  }
  v63 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl) )
  {
    v75 = 0;
    string = 0;
    v15 = (__int64 (__fastcall *)(_QWORD, GUID *, HSTRING *))**a2;
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&string);
    v13 = v15(a2, &GUID_c8423c1d_aa94_48ea_86e5_4502f998ab78, &string);
    if ( v13 < 0 )
    {
      v16 = 1088;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&string);
LABEL_112:
      std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>(&v63);
      goto LABEL_113;
    }
    v13 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 48LL))(string, &v75);
    if ( v13 < 0 )
    {
      v16 = 1090;
      goto LABEL_12;
    }
    v12 = v75 != 0;
    StoredObjectInfo = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(
                         a4,
                         a5,
                         string2,
                         &v63,
                         0,
                         v75 != 0);
    v13 = StoredObjectInfo;
    if ( StoredObjectInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44F,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
        (const char *)(unsigned int)StoredObjectInfo,
        bIgnoreCasea);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&string);
LABEL_17:
      std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>(&v63);
      v18 = hMem;
      hMem = 0;
LABEL_114:
      if ( v18 )
        LocalFree(v18);
      return (unsigned int)v13;
    }
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&string);
  }
  else
  {
    v21 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(
            a4,
            a5,
            string2,
            &v63,
            0,
            0);
    v13 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45B,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCasea);
      goto LABEL_112;
    }
  }
  v64 = 0;
  v79 = 0;
  v86[0] = 0;
  LOBYTE(bIgnoreCasea) = 1;
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, int *, _QWORD *))(*(_QWORD *)v63 + 8LL))(
          v63,
          &v64,
          &v79,
          v86);
  if ( v13 != -2147024894 )
    goto LABEL_108;
  if ( v84 == 1 )
  {
    v19 = hMem;
    hMem = 0;
    if ( v19 )
      LocalFree(v19);
    lpString1 = (LPCWCH)&hMem;
    v82 = 0;
    LOBYTE(v83) = 1;
    v13 = CreateRequestHash(a2, 0, 1, 0, &Size, &v82);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&lpString1);
    if ( v13 < 0 )
    {
      v20 = 1140;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCaseb);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v64);
      goto LABEL_17;
    }
    v13 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromBytes(
            a5,
            (unsigned __int8 *)hMem,
            (unsigned int)Size);
    if ( v13 < 0 )
    {
      v20 = 1141;
      goto LABEL_25;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl) )
    {
      v13 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(
              a4,
              a5,
              string2,
              &v63,
              0,
              v12);
      if ( v13 < 0 )
      {
        v22 = 1153;
LABEL_33:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)v13,
          bIgnoreCasea);
LABEL_111:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v64);
        goto LABEL_112;
      }
    }
    else
    {
      v13 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(
              a4,
              a5,
              string2,
              &v63,
              0,
              0);
      if ( v13 < 0 )
      {
        v22 = 1163;
        goto LABEL_33;
      }
    }
    LOBYTE(bIgnoreCasea) = 1;
    v23 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, int *, _QWORD *))(*(_QWORD *)v63 + 8LL))(
            v63,
            &v64,
            &v79,
            v86);
    v13 = v23;
    if ( v23 != -2147024894 )
    {
      if ( v23 < 0 )
      {
        v22 = 1168;
        goto LABEL_33;
      }
      v70 = 0;
      v65[0] = 0;
      v75 = 0;
      LODWORD(v68) = 0;
      v67 = 0;
      LODWORD(v66) = 0;
      v24 = ReadTokenCacheEntry(
              v64,
              3 - (unsigned int)(a4 != 2),
              (__int64)a5,
              (__int64)&v70,
              (int *)v65,
              &v75,
              &v68,
              (__int64)&v67,
              (int *)&v66);
      v13 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4AC,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)v24,
          bIgnoreCasec);
LABEL_41:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v67);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v70);
        goto LABEL_111;
      }
      *(_QWORD *)v65 = 0;
      BufferFromByteArray = Windows::Internal::Security::Authentication::TokenBroker::GetBufferFromByteArray(
                              v67,
                              (unsigned __int8 *)(unsigned int)v66,
                              (unsigned int)v65,
                              v25);
      v13 = BufferFromByteArray;
      if ( BufferFromByteArray < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B5,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)BufferFromByteArray,
          bIgnoreCasec);
LABEL_44:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v65);
        goto LABEL_41;
      }
      v69 = 0;
      v27 = (*a2)[6];
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      v28 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v27)(a2, &v69);
      v13 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B8,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)v28,
          bIgnoreCasec);
LABEL_47:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        goto LABEL_44;
      }
      v75 = 0;
      v66 = 0;
      v72 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
      v29 = Windows::Internal::Security::Authentication::TokenBroker::DeSerializeWebTokenResponsesWithStatus(
              string2,
              (__int64)&v68,
              (__int64)&v75,
              (__int64)&v72,
              (__int64)&v66);
      v13 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4C8,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)v29,
          bIgnoreCasea);
LABEL_50:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
        goto LABEL_47;
      }
      v85 = 0;
      v30 = v66;
      v31 = (*(__int64 (__fastcall **)(unsigned __int8 *, int *))(*(_QWORD *)v66 + 56LL))(v66, &v85);
      v32 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4CB,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)v31,
          bIgnoreCasea);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v65);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v67);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v70);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v64);
        std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>(&v63);
        v33 = hMem;
        hMem = 0;
        if ( v33 )
          LocalFree(v33);
        return v32;
      }
      if ( v85 == 1 )
      {
        v68 = 0;
        v35 = **(__int64 (__fastcall ***)(unsigned __int8 *, GUID *, __int64 *))v30;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        v36 = v35(v30, &GUID_58dc4e4c_a84d_5ad6_a6d9_6ee477329c9f, &v68);
        v13 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4D4,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
            (const char *)(unsigned int)v36,
            bIgnoreCasea);
LABEL_58:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
          goto LABEL_50;
        }
        v74 = 0;
        v37 = v68;
        v38 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v68 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
        v39 = v38(v37, 0, &v74);
        v13 = v39;
        if ( v39 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4D7,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
            (const char *)(unsigned int)v39,
            bIgnoreCasea);
LABEL_61:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
          goto LABEL_58;
        }
        v73 = 0;
        v40 = v74;
        v41 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v74 + 64LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
        v42 = v41(v40, &v73);
        v13 = v42;
        if ( v42 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4DA,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
            (const char *)(unsigned int)v42,
            bIgnoreCasea);
LABEL_64:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
          goto LABEL_61;
        }
        if ( v73 )
        {
          v77 = 0;
          v43 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                  &v73,
                  (__int64)&v77);
          v13 = v43;
          if ( v43 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4DF,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
              (const char *)(unsigned int)v43,
              bIgnoreCasea);
LABEL_68:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
            goto LABEL_64;
          }
          string = 0;
          v44 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v77 + 48LL))(v77, &string);
          v13 = v44;
          if ( v44 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4E2,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
              (const char *)(unsigned int)v44,
              bIgnoreCasea);
            goto LABEL_71;
          }
          v78 = 0;
          v45 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a3 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
          v46 = v45(a3, 0, &v78);
          v13 = v46;
          if ( v46 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4E9,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
              (const char *)(unsigned int)v46,
              bIgnoreCasea);
LABEL_75:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
LABEL_71:
            if ( string )
              WindowsDeleteString(string);
            goto LABEL_68;
          }
          v80 = 0;
          v47 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                  &v78,
                  (__int64)&v80);
          v13 = v47;
          if ( v47 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4EC,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
              (const char *)(unsigned int)v47,
              bIgnoreCasea);
LABEL_78:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
            goto LABEL_75;
          }
          v75 = 0;
          v48 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v80 + 48LL))(v80, &v75);
          v13 = v48;
          if ( v48 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4EF,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
              (const char *)(unsigned int)v48,
              bIgnoreCasea);
            goto LABEL_81;
          }
          lpString1 = 0;
          v82 = 0;
          v83 = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v50 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  &lpString1,
                  StringRawBuffer);
          v13 = v50;
          if ( v50 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4F5,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
              (const char *)(unsigned int)v50,
              bIgnoreCasea);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
LABEL_81:
            if ( v75 )
              WindowsDeleteString(v75);
            goto LABEL_78;
          }
          v51 = WindowsGetStringRawBuffer(v75, 0);
          v52 = &word_1801330B0;
          v53 = &word_1801330B0;
          if ( v51 )
            v53 = v51;
          v54 = v82;
          if ( v82 == -1 )
          {
            if ( lpString1 )
            {
              do
                ++v54;
              while ( lpString1[v54] );
            }
            else
            {
              LODWORD(v54) = 0;
            }
          }
          if ( lpString1 )
            v52 = lpString1;
          if ( CompareStringOrdinal(v52, v54, v53, -(v51 != 0), 1) != 2 )
            v13 = -2147024894;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
          if ( v75 )
            WindowsDeleteString(v75);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
          if ( string )
            WindowsDeleteString(string);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
        }
        else
        {
          v13 = -2147024894;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      }
      else
      {
        v13 = -2147024894;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v65);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v67);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v70);
      if ( v13 != -2147024894 )
      {
LABEL_108:
        if ( v13 >= 0 )
        {
          v57 = v64;
          v64 = 0;
          std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter>::reset(
            a6,
            v57);
          *a7 = v79;
          *a8 = v86[0];
          goto LABEL_111;
        }
        v22 = 1289;
        goto LABEL_33;
      }
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v64);
  std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>(&v63);
  v55 = hMem;
  v56 = hMem == 0;
  hMem = 0;
  if ( !v56 )
    LocalFree(v55);
  return 2147942402LL;
}

```

## disassembly

```asm
0x18010a528  push    rbp
0x18010a52a  push    rbx
0x18010a52b  push    rsi
0x18010a52c  push    rdi
0x18010a52d  push    r12
0x18010a52f  push    r13
0x18010a531  push    r14
0x18010a533  push    r15
0x18010a535  lea     rbp, [rsp-18h]
0x18010a53a  sub     rsp, 118h
0x18010a541  mov     edi, r9d
0x18010a544  mov     r12, r8
0x18010a547  mov     r13, rdx
0x18010a54a  mov     r15, rcx
0x18010a54d  xor     r14d, r14d
0x18010a550  mov     [rsp+150h+hMem], r14
0x18010a555  mov     dword ptr [rbp+50h+Size], r14d
0x18010a559  lea     rax, [rsp+150h+hMem]
0x18010a55e  mov     [rbp+50h+lpString1], rax
0x18010a562  mov     [rbp+50h+var_60], r14
0x18010a566  mov     byte ptr [rbp+50h+var_58], 1
0x18010a56a  lea     rax, [rbp+50h+var_60]
0x18010a56e  mov     [rsp+150h+var_128], rax
0x18010a573  lea     rax, [rbp+50h+Size]
0x18010a577  mov     qword ptr [rsp+150h+bIgnoreCase], rax; int
0x18010a57c  mov     r9b, 1
0x18010a57f  xor     r8d, r8d
0x18010a582  mov     rdx, r12
0x18010a585  mov     rcx, r13
0x18010a588  call    ?CreateRequestHash@@YAJPEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@6@_N2PEAKPEAPEAE@Z; CreateRequestHash(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,bool,bool,ulong *,uchar * *)
0x18010a58d  mov     ebx, eax
0x18010a58f  lea     rcx, [rbp+50h+lpString1]
0x18010a593  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18010a598  test    ebx, ebx
0x18010a59a  jns     short loc_18010A5B9
0x18010a59c  mov     edx, 425h; void *
0x18010a5a1  mov     rcx, [rbp+58h]; this
0x18010a5a5  mov     r9d, ebx; char *
0x18010a5a8  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010a5af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a5b4  jmp     loc_18010AFC0
0x18010a5b9  mov     r8d, dword ptr [rbp+50h+Size]; Size
0x18010a5bd  mov     rdx, [rsp+150h+hMem]; Src
0x18010a5c2  mov     rsi, [rbp+50h+arg_20]
0x18010a5c9  mov     rcx, rsi; this
0x18010a5cc  call    ?InitializeFromBytes@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAEK@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromBytes(uchar *,ulong)
0x18010a5d1  mov     ebx, eax
0x18010a5d3  test    eax, eax
0x18010a5d5  jns     short loc_18010A5DE
0x18010a5d7  mov     edx, 42Bh
0x18010a5dc  jmp     short loc_18010A5A1
0x18010a5de  mov     [rbp+50h+var_50], r14d
0x18010a5e2  test    r12, r12
0x18010a5e5  jz      short loc_18010A608
0x18010a5e7  mov     rax, [r12]
0x18010a5eb  lea     rdx, [rbp+50h+var_50]
0x18010a5ef  mov     rcx, r12
0x18010a5f2  mov     rax, [rax+38h]
0x18010a5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a5fb  mov     ebx, eax
0x18010a5fd  test    eax, eax
0x18010a5ff  jns     short loc_18010A608
0x18010a601  mov     edx, 430h
0x18010a606  jmp     short loc_18010A5A1
0x18010a608  mov     [rsp+150h+var_F8], r14
0x18010a60d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests> `wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl(void)'::`2'::impl
0x18010a614  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(void)
0x18010a619  test    al, al
0x18010a61b  jz      loc_18010A7E0
0x18010a621  mov     [rbp+50h+var_98], r14
0x18010a625  mov     [rbp+50h+string], r14
0x18010a629  mov     rax, [r13+0]
0x18010a62d  mov     rbx, [rax]
0x18010a630  lea     rcx, [rbp+50h+string]
0x18010a634  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18010a639  lea     r8, [rbp+50h+string]
0x18010a63d  lea     rdx, _GUID_c8423c1d_aa94_48ea_86e5_4502f998ab78
0x18010a644  mov     rcx, r13
0x18010a647  mov     rax, rbx
0x18010a64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a64f  mov     ebx, eax
0x18010a651  test    eax, eax
0x18010a653  jns     short loc_18010A67C
0x18010a655  mov     edx, 440h; void *
0x18010a65a  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010a661  mov     r9d, ebx; char *
0x18010a664  mov     rcx, [rbp+58h]; this
0x18010a668  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a66d  nop
0x18010a66e  lea     rcx, [rbp+50h+string]
0x18010a672  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18010a677  jmp     loc_18010AFB5
0x18010a67c  mov     rcx, [rbp+50h+string]
0x18010a680  mov     rax, [rcx]
0x18010a683  lea     rdx, [rbp+50h+var_98]
0x18010a687  mov     rax, [rax+30h]
0x18010a68b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a690  mov     ebx, eax
0x18010a692  test    eax, eax
0x18010a694  jns     short loc_18010A69D
0x18010a696  mov     edx, 442h
0x18010a69b  jmp     short loc_18010A65A
0x18010a69d  cmp     [rbp+50h+var_98], r14
0x18010a6a1  setnz   r14b
0x18010a6a5  mov     byte ptr [rsp+150h+var_128], r14b
0x18010a6aa  mov     byte ptr [rsp+150h+bIgnoreCase], 0; int
0x18010a6af  lea     r9, [rsp+150h+var_F8]
0x18010a6b4  mov     r8, r15
0x18010a6b7  mov     rdx, rsi
0x18010a6ba  mov     ecx, edi
0x18010a6bc  call    ?GetStoredObjectInfo@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@AEAVStoredObjectId@23456@QEAUHSTRING__@@AEAV?$unique_ptr@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@_N4@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ * const,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo> &,bool,bool)
0x18010a6c1  mov     ebx, eax
0x18010a6c3  test    eax, eax
0x18010a6c5  jns     short loc_18010A708
0x18010a6c7  mov     rcx, [rbp+58h]; this
0x18010a6cb  mov     r9d, eax; char *
0x18010a6ce  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010a6d5  mov     edx, 44Fh; void *
0x18010a6da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a6df  nop
0x18010a6e0  lea     rcx, [rbp+50h+string]
0x18010a6e4  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18010a6e9  nop
0x18010a6ea  lea     rcx, [rsp+150h+var_F8]
0x18010a6ef  call    ??1?$unique_ptr@VStoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VStoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache>(void)
0x18010a6f4  nop
0x18010a6f5  mov     rcx, [rsp+150h+hMem]
0x18010a6fa  mov     [rsp+150h+hMem], 0
0x18010a703  jmp     loc_18010AFCA
0x18010a708  lea     rcx, [rbp+50h+string]
0x18010a70c  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18010a711  xor     eax, eax
0x18010a713  mov     [rsp+150h+var_F0], rax
0x18010a718  mov     [rbp+50h+var_78], eax
0x18010a71b  mov     [rbp+50h+var_48], rax
0x18010a71f  mov     rcx, [rsp+150h+var_F8]
0x18010a724  mov     rax, [rcx]
0x18010a727  mov     byte ptr [rsp+150h+bIgnoreCase], 1
0x18010a72c  lea     r9, [rbp+50h+var_48]
0x18010a730  lea     r8, [rbp+50h+var_78]
0x18010a734  lea     rdx, [rsp+150h+var_F0]
0x18010a739  mov     rax, [rax+8]
0x18010a73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a742  mov     ebx, eax
0x18010a744  cmp     eax, 80070002h
0x18010a749  jnz     loc_18010AF69
0x18010a74f  cmp     [rbp+50h+var_50], 1
0x18010a753  jnz     loc_18010AF34
0x18010a759  mov     rcx, [rsp+150h+hMem]; hMem
0x18010a75e  mov     [rsp+150h+hMem], 0
0x18010a767  test    rcx, rcx
0x18010a76a  jz      short loc_18010A772
0x18010a76c  call    cs:__imp_LocalFree
0x18010a772  lea     rax, [rsp+150h+hMem]
0x18010a777  mov     [rbp+50h+lpString1], rax
0x18010a77b  mov     [rbp+50h+var_60], 0
0x18010a783  mov     byte ptr [rbp+50h+var_58], 1
0x18010a787  lea     rax, [rbp+50h+var_60]
0x18010a78b  mov     [rsp+150h+var_128], rax
0x18010a790  lea     rax, [rbp+50h+Size]
0x18010a794  mov     qword ptr [rsp+150h+bIgnoreCase], rax; int
0x18010a799  xor     r9d, r9d
0x18010a79c  mov     r8b, 1
0x18010a79f  xor     edx, edx
0x18010a7a1  mov     rcx, r13
0x18010a7a4  call    ?CreateRequestHash@@YAJPEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@6@_N2PEAKPEAPEAE@Z; CreateRequestHash(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,bool,bool,ulong *,uchar * *)
0x18010a7a9  mov     ebx, eax
0x18010a7ab  lea     rcx, [rbp+50h+lpString1]
0x18010a7af  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18010a7b4  test    ebx, ebx
0x18010a7b6  jns     short loc_18010A823
0x18010a7b8  mov     edx, 474h; void *
0x18010a7bd  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010a7c4  mov     r9d, ebx; char *
0x18010a7c7  mov     rcx, [rbp+58h]; this
0x18010a7cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a7d0  nop
0x18010a7d1  lea     rcx, [rsp+150h+var_F0]
0x18010a7d6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18010a7db  jmp     loc_18010A6EA
0x18010a7e0  mov     byte ptr [rsp+150h+var_128], r14b
0x18010a7e5  mov     byte ptr [rsp+150h+bIgnoreCase], r14b; int
0x18010a7ea  lea     r9, [rsp+150h+var_F8]
0x18010a7ef  mov     r8, r15
0x18010a7f2  mov     rdx, rsi
0x18010a7f5  mov     ecx, edi
0x18010a7f7  call    ?GetStoredObjectInfo@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@AEAVStoredObjectId@23456@QEAUHSTRING__@@AEAV?$unique_ptr@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@_N4@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ * const,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo> &,bool,bool)
0x18010a7fc  mov     ebx, eax
0x18010a7fe  test    eax, eax
0x18010a800  jns     loc_18010A711
0x18010a806  mov     rcx, [rbp+58h]; this
0x18010a80a  mov     r9d, eax; char *
0x18010a80d  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010a814  mov     edx, 45Bh; void *
0x18010a819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a81e  jmp     loc_18010AFB5
0x18010a823  mov     r8d, dword ptr [rbp+50h+Size]; Size
0x18010a827  mov     rdx, [rsp+150h+hMem]; Src
0x18010a82c  mov     rcx, rsi; this
0x18010a82f  call    ?InitializeFromBytes@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAEK@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromBytes(uchar *,ulong)
0x18010a834  mov     ebx, eax
0x18010a836  test    eax, eax
0x18010a838  jns     short loc_18010A844
0x18010a83a  mov     edx, 475h
0x18010a83f  jmp     loc_18010A7BD
0x18010a844  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests> `wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl(void)'::`2'::impl
0x18010a84b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(void)
0x18010a850  lea     r9, [rsp+150h+var_F8]
0x18010a855  mov     r8, r15
0x18010a858  mov     rdx, rsi
0x18010a85b  mov     ecx, edi
0x18010a85d  test    al, al
0x18010a85f  jz      short loc_18010A896
0x18010a861  mov     byte ptr [rsp+150h+var_128], r14b
0x18010a866  xor     r14d, r14d
0x18010a869  mov     byte ptr [rsp+150h+bIgnoreCase], r14b; int
0x18010a86e  call    ?GetStoredObjectInfo@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@AEAVStoredObjectId@23456@QEAUHSTRING__@@AEAV?$unique_ptr@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@_N4@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ * const,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo> &,bool,bool)
0x18010a873  mov     ebx, eax
0x18010a875  test    eax, eax
0x18010a877  jns     short loc_18010A8B5
0x18010a879  mov     edx, 481h; void *
0x18010a87e  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010a885  mov     r9d, ebx; char *
0x18010a888  mov     rcx, [rbp+58h]; this
0x18010a88c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a891  jmp     loc_18010AFAA
0x18010a896  xor     r14d, r14d
0x18010a899  mov     byte ptr [rsp+150h+var_128], r14b
0x18010a89e  mov     byte ptr [rsp+150h+bIgnoreCase], r14b
0x18010a8a3  call    ?GetStoredObjectInfo@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@AEAVStoredObjectId@23456@QEAUHSTRING__@@AEAV?$unique_ptr@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@_N4@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetStoredObjectInfo(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ * const,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo> &,bool,bool)
0x18010a8a8  mov     ebx, eax
0x18010a8aa  test    eax, eax
0x18010a8ac  jns     short loc_18010A8B5
0x18010a8ae  mov     edx, 48Bh
0x18010a8b3  jmp     short loc_18010A87E
0x18010a8b5  mov     rcx, [rsp+150h+var_F8]
0x18010a8ba  mov     rax, [rcx]
0x18010a8bd  mov     byte ptr [rsp+150h+bIgnoreCase], 1
0x18010a8c2  lea     r9, [rbp+50h+var_48]
0x18010a8c6  lea     r8, [rbp+50h+var_78]
0x18010a8ca  lea     rdx, [rsp+150h+var_F0]
0x18010a8cf  mov     rax, [rax+8]
0x18010a8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a8d8  mov     ebx, eax
0x18010a8da  cmp     eax, 80070002h
0x18010a8df  jz      loc_18010AF37
0x18010a8e5  test    eax, eax
0x18010a8e7  jns     short loc_18010A8F0
0x18010a8e9  mov     edx, 490h
0x18010a8ee  jmp     short loc_18010A87E
0x18010a8f0  mov     [rbp+50h+var_C0], r14
0x18010a8f4  mov     [rsp+150h+var_E8], r14d
0x18010a8f9  mov     [rbp+50h+var_98], r14
0x18010a8fd  mov     dword ptr [rbp+50h+var_D0], r14d
0x18010a901  mov     [rsp+150h+var_D8], r14
0x18010a906  mov     dword ptr [rsp+150h+var_E0], r14d
0x18010a90b  sub     edi, 2
0x18010a90e  neg     edi
0x18010a910  sbb     edx, edx
0x18010a912  add     edx, 3
0x18010a915  lea     rax, [rsp+150h+var_E0]
0x18010a91a  mov     [rsp+150h+var_110], rax; __int64
0x18010a91f  lea     rax, [rsp+150h+var_D8]
0x18010a924  mov     [rsp+150h+var_118], rax; __int64
0x18010a929  lea     rax, [rbp+50h+var_D0]
0x18010a92d  mov     [rsp+150h+var_120], rax; __int64
0x18010a932  lea     rax, [rbp+50h+var_98]
0x18010a936  mov     [rsp+150h+var_128], rax; __int64
0x18010a93b  lea     rax, [rsp+150h+var_E8]
0x18010a940  mov     qword ptr [rsp+150h+bIgnoreCase], rax; int
0x18010a945  lea     r9, [rbp+50h+var_C0]
0x18010a949  mov     r8, rsi
0x18010a94c  mov     rcx, [rsp+150h+var_F0]; unsigned __int16 *
0x18010a951  call    ?ReadTokenCacheEntry@@YAJPEBGW4SerializedObjectType@TokenBroker@Authentication@Security@Internal@Windows@@AEAVStoredObjectId@23456@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAKPEA_JPEAW4WebTokenRequestStatus@Core@Web@346@34@Z; ReadTokenCacheEntry(ushort const *,Windows::Internal::Security::Authentication::TokenBroker::SerializedObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *,__int64 *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus *,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *)
0x18010a956  mov     ebx, eax
0x18010a958  test    eax, eax
0x18010a95a  jns     short loc_18010A98E
0x18010a95c  mov     rcx, [rbp+58h]; this
0x18010a960  mov     r9d, eax; char *
0x18010a963  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010a96a  mov     edx, 4ACh; void *
0x18010a96f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a974  nop
0x18010a975  lea     rcx, [rsp+150h+var_D8]
0x18010a97a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18010a97f  nop
0x18010a980  lea     rcx, [rbp+50h+var_C0]
0x18010a984  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18010a989  jmp     loc_18010AFAA
0x18010a98e  mov     qword ptr [rsp+150h+var_E8], r14
0x18010a993  lea     r8, [rsp+150h+var_E8]; unsigned int
0x18010a998  mov     edx, dword ptr [rsp+150h+var_E0]; unsigned __int8 *
0x18010a99c  mov     rcx, [rsp+150h+var_D8]; this
0x18010a9a1  call    ?GetBufferFromByteArray@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAEIPEAPEAUIBuffer@Streams@Storage@5@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetBufferFromByteArray(uchar *,uint,Windows::Storage::Streams::IBuffer * *)
0x18010a9a6  mov     ebx, eax
0x18010a9a8  test    eax, eax
0x18010a9aa  jns     short loc_18010A9D1
0x18010a9ac  mov     rcx, [rbp+58h]; this
0x18010a9b0  mov     r9d, eax; char *
0x18010a9b3  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
  ... truncated ...
```
