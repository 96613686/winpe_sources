# ChatServiceDownloadConversationTransaction::_HandleSuccessResponse(void)

- ea: `0x18009e390`
- end: `0x18009ed25`
- name: `?_HandleSuccessResponse@ChatServiceDownloadConversationTransaction@@EEAAJXZ`
- size: `2453`
- prototype: `__int64 __fastcall(ChatServiceDownloadConversationTransaction *__hidden this)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005c50`
- `0x180008870`
- `0x1800088c4`
- `0x18000a754`
- `0x18000b7d4`
- `0x18000bf7c`
- `0x1800242c4`
- `0x18002c7bc`
- `0x180030bd0`
- `0x18006b108`
- `0x180080528`
- `0x180084738`
- `0x1800848b4`
- `0x18008f260`
- `0x18008f290`
- `0x18009201c`
- `0x1800921dc`
- `0x180092644`
- `0x180092700`
- `0x18009d8a8`
- `0x18009df48`
- `0x18009e390`
- `0x1800a2920`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009e52d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009e52d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e9ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e9ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e4d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e70a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e7ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e84e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e8a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e95e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e9a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ea03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ea54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eaad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eb5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ebb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ec6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ecc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e4d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e70a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e7ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e84e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e8a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e95e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e9a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ea03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ea54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eaad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eb5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ebb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ec6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ecc5`

## string_xrefs

- `0x18009e505`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceDownloadConversationTransaction::_HandleSuccessResponse(
        ChatServiceDownloadConversationTransaction *this)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rdx
  int v7; // eax
  int (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rdx
  __int64 v9; // rcx
  int (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  int ActivationFactory; // eax
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rcx
  __int64 *v16; // rdi
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64 *, __int64, _QWORD); // rbx
  int v19; // eax
  char v20; // r8
  unsigned int i; // r14d
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v28; // rax
  int v29; // eax
  __int64 *v30; // rcx
  __int64 v31; // rcx
  int (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v33; // rcx
  __int64 *v34; // rcx
  __int64 *v35; // rdi
  __int64 (__fastcall *v36)(__int64 *, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v37; // rax
  int v38; // eax
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, PVOID, HSTRING *); // rbx
  char v41; // r8
  HSTRING_HEADER *v42; // rax
  int v43; // eax
  PCWSTR v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  int (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v48; // rbx
  __int64 v49; // r9
  __int64 v50; // rcx
  int (__fastcall ***v51)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v52; // rdx
  int v53; // eax
  __int64 v54; // rcx
  int (__fastcall ***v55)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v56; // rcx
  HSTRING_HEADER v57; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v58; // [rsp+50h] [rbp-B0h] BYREF
  int (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v61; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v62; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v63)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp-88h] BYREF
  __int64 v64; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v65; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v66; // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  __int64 (__fastcall ***v68)(_QWORD, GUID *, __int64); // [rsp+A0h] [rbp-60h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  struct ChatServiceMessage *v70; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v71; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-28h]
  _OWORD v74[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v75[2]; // [rsp+100h] [rbp+0h] BYREF

  v2 = *((_QWORD *)this + 2);
  v58 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 48LL))(v2, &v58);
  v4 = v3;
  if ( v3 < 0 )
  {
    Log_HREvent_75(v3);
LABEL_3:
    v5 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return (unsigned int)v4;
  }
  v59 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v58 + 80LL))(
         v58,
         &v59);
  v4 = v7;
  if ( v7 < 0 )
  {
    Log_HREvent_75(v7);
    v8 = v59;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v8)[2])(v8);
    }
LABEL_9:
    v9 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return (unsigned int)v4;
  }
  string = 0;
  WindowsDeleteString(0);
  v10 = v59;
  string = 0;
  v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(v59);
  if ( v4 >= 0 )
    v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*v10)[10])(v10, &string);
  if ( v4 < 0 )
  {
    Log_HREvent_75(v4);
LABEL_15:
    WindowsDeleteString(string);
    v11 = v59;
    string = 0;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v11)[2])(v11);
    }
    goto LABEL_9;
  }
  v61 = 0;
  v73 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = RoGetActivationFactory(v73, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v61);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_75(ActivationFactory);
    v13 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_15;
  }
  v62 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 **))(*(_QWORD *)v61 + 48LL))(v61, string, &v62);
  v4 = v14;
  if ( v14 < 0 )
  {
    Log_HREvent_75(v14);
    goto LABEL_22;
  }
  v16 = v62;
  v63 = 0;
  v17 = *v62;
  v73 = 0;
  v18 = *(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v17 + 72);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"messages", 9u, 8u);
  v19 = v18(v16, v73, &v63);
  v4 = v19;
  if ( v19 < 0 )
  {
    Log_HREvent_75(v19);
LABEL_26:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
LABEL_22:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    v15 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_15;
  }
  v64 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
         &v63,
         (__int64)&v64);
  if ( v4 < 0
    || (v71 = 0, v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v64 + 56LL))(v64, &v71), v4 < 0) )
  {
    Log_HREvent_75(v4);
LABEL_29:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    goto LABEL_26;
  }
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>(&hstringHeader);
  for ( i = 0; i < v71; ++i )
  {
    v68 = 0;
    v22 = (*v63)[6](v63, (GUID *)i, (__int64)&v68);
    v4 = v22;
    if ( v22 < 0 )
    {
      Log_HREvent_75(v22);
      goto LABEL_53;
    }
    v69 = 0;
    v23 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v68,
            (__int64)&v69);
    v4 = v23;
    if ( v23 < 0 )
    {
      Log_HREvent_75(v23);
      goto LABEL_51;
    }
    v24 = v69;
    v66 = 0;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v69 + 56LL);
    WindowsDeleteString(0);
    v66 = 0;
    v26 = v25(v24, &v66);
    v4 = v26;
    if ( v26 < 0 )
    {
      Log_HREvent_75(v26);
LABEL_49:
      WindowsDeleteString(v66);
      v66 = 0;
LABEL_51:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
LABEL_53:
      v34 = (__int64 *)&v68;
LABEL_54:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
      utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
      goto LABEL_29;
    }
    v70 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v66, 0);
    if ( (int)ChatServiceMessage::CreateInstance(StringRawBuffer, &v70) < 0 )
    {
      v28 = WindowsGetStringRawBuffer(v66, 0);
      v29 = ChatServiceMessage::CreateUnknownInstance(v28, &v70);
      v4 = v29;
      if ( v29 < 0 )
      {
        Log_HREvent_75(v29);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
        goto LABEL_49;
      }
    }
    if ( !utl::vector<ATL::CComPtr<ChatServiceAttachment>,utl::allocator<ATL::CComPtr<ChatServiceAttachment>>>::emplace_back<ATL::CComPtr<ChatServiceAttachment> &,0>(
            &hstringHeader,
            &v70) )
    {
      Log_HREvent_75(-2147024882);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
      WindowsDeleteString(v66);
      v66 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
      v30 = (__int64 *)&v68;
      goto LABEL_42;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
    WindowsDeleteString(v66);
    v66 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
  }
  v35 = v62;
  v67 = 0;
  v36 = *(__int64 (__fastcall **)(__int64 *, PVOID, __int64 *))(*v62 + 64);
  v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v57, (const WCHAR **)off_1800FD7B8, v20);
  v38 = v36(v35, v37[1].Reserved.Reserved1, &v67);
  v4 = v38;
  if ( v38 < 0 )
  {
    Log_HREvent_75(v38);
LABEL_57:
    v34 = &v67;
    goto LABEL_54;
  }
  v39 = v67;
  v65 = 0;
  v40 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v67 + 80LL);
  WindowsDeleteString(0);
  v65 = 0;
  v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v57, (const WCHAR **)off_1800FD7C0, v41);
  v43 = v40(v39, v42[1].Reserved.Reserved1, &v65);
  v4 = v43;
  if ( v43 < 0 )
  {
    Log_HREvent_75(v43);
LABEL_60:
    WindowsDeleteString(v65);
    v65 = 0;
    goto LABEL_57;
  }
  memset(v74, 0, sizeof(v74));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v74);
  v44 = WindowsGetStringRawBuffer(v65, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v74,
                           v44) )
  {
    Log_HREvent_75(-2147024882);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v74);
    WindowsDeleteString(v65);
    v30 = &v67;
    v65 = 0;
LABEL_42:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v30);
    utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    v31 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    WindowsDeleteString(string);
    v32 = v59;
    string = 0;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v32)[2])(v32);
    }
    v33 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return 2147942414LL;
  }
  v45 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
          v74,
          L"syncState=",
          0);
  if ( v45 == -1 )
  {
    v4 = -2147024809;
    Log_HREvent_75(-2147024809);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v74);
    WindowsDeleteString(v65);
    v65 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
    utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    v46 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    WindowsDeleteString(string);
    v47 = v59;
    string = 0;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v47)[2])(v47);
    }
    goto LABEL_3;
  }
  v48 = v45 + 10;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find_first_of(
    v74,
    L"&",
    v45 + 10);
  memset(v75, 0, sizeof(v75));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v75);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v75,
                           v74,
                           v48,
                           v49) )
  {
    Log_HREvent_75(-2147024882);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v75);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v74);
    WindowsDeleteString(v65);
    v65 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
    utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    v50 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    WindowsDeleteString(string);
    v51 = v59;
    string = 0;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v51)[2])(v51);
    }
    v52 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    return 2147942414LL;
  }
  utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>::operator=(
    (char *)this + 96,
    &hstringHeader);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    (char *)this + 120,
    v75);
  v53 = ChatServiceTransaction::_HandleSuccessResponse(this);
  v4 = v53;
  if ( v53 < 0 )
  {
    Log_HREvent_75(v53);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v75);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v74);
    goto LABEL_60;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v75);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v74);
  WindowsDeleteString(v65);
  v65 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  v54 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  }
  WindowsDeleteString(string);
  v55 = v59;
  string = 0;
  if ( v59 )
  {
    v59 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v55)[2])(v55);
  }
  v56 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  }
  return 0;
}

```

## disassembly

```asm
0x18009e390  push    rbp
0x18009e392  push    rbx
0x18009e393  push    rdi
0x18009e394  push    r12
0x18009e396  push    r14
0x18009e398  push    r15
0x18009e39a  lea     rbp, [rsp-38h]
0x18009e39f  sub     rsp, 138h
0x18009e3a6  mov     rax, cs:__security_cookie
0x18009e3ad  xor     rax, rsp
0x18009e3b0  mov     [rbp+60h+var_40], rax
0x18009e3b4  mov     r15, rcx
0x18009e3b7  lea     rdx, [rsp+160h+var_110]
0x18009e3bc  mov     rcx, [rcx+10h]
0x18009e3c0  xor     r12d, r12d
0x18009e3c3  mov     [rsp+160h+var_110], r12
0x18009e3c8  mov     rax, [rcx]
0x18009e3cb  mov     rax, [rax+30h]
0x18009e3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e3d4  mov     ebx, eax
0x18009e3d6  test    eax, eax
0x18009e3d8  jns     short loc_18009E411
0x18009e3da  lea     edx, [r12+1]
0x18009e3df  mov     r9d, 0ADh
0x18009e3e5  mov     ecx, eax; int
0x18009e3e7  call    Log_HREvent_75
0x18009e3ec  mov     rdx, [rsp+160h+var_110]
0x18009e3f1  test    rdx, rdx
0x18009e3f4  jz      short loc_18009E40A
0x18009e3f6  mov     [rsp+160h+var_110], r12
0x18009e3fb  mov     rcx, [rdx]
0x18009e3fe  mov     rax, [rcx+10h]
0x18009e402  mov     rcx, rdx
0x18009e405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e40a  mov     eax, ebx
0x18009e40c  jmp     loc_18009ED08
0x18009e411  mov     rcx, [rsp+160h+var_110]
0x18009e416  lea     rdx, [rsp+160h+var_108]
0x18009e41b  mov     [rsp+160h+var_108], r12
0x18009e420  mov     rax, [rcx]
0x18009e423  mov     rax, [rax+50h]
0x18009e427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e42c  mov     ebx, eax
0x18009e42e  test    eax, eax
0x18009e430  jns     short loc_18009E47A
0x18009e432  mov     edx, 1
0x18009e437  mov     r9d, 0B0h
0x18009e43d  mov     ecx, eax; int
0x18009e43f  call    Log_HREvent_75
0x18009e444  mov     rdx, [rsp+160h+var_108]
0x18009e449  test    rdx, rdx
0x18009e44c  jz      short loc_18009E462
0x18009e44e  mov     [rsp+160h+var_108], r12
0x18009e453  mov     rcx, [rdx]
0x18009e456  mov     rax, [rcx+10h]
0x18009e45a  mov     rcx, rdx
0x18009e45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e462  mov     rcx, [rsp+160h+var_110]
0x18009e467  test    rcx, rcx
0x18009e46a  jz      short loc_18009E40A
0x18009e46c  mov     [rsp+160h+var_110], r12
0x18009e471  mov     rax, [rcx]
0x18009e474  mov     rax, [rax+10h]
0x18009e478  jmp     short loc_18009E405
0x18009e47a  xor     ecx, ecx; string
0x18009e47c  mov     [rsp+160h+string], r12
0x18009e481  call    cs:__imp_WindowsDeleteString
0x18009e487  mov     rdi, [rsp+160h+var_108]
0x18009e48c  mov     rcx, rdi
0x18009e48f  mov     [rsp+160h+string], r12
0x18009e494  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x18009e499  mov     ebx, eax
0x18009e49b  test    eax, eax
0x18009e49d  js      short loc_18009E4B5
0x18009e49f  mov     rax, [rdi]
0x18009e4a2  lea     rdx, [rsp+160h+string]
0x18009e4a7  mov     rcx, rdi
0x18009e4aa  mov     rax, [rax+50h]
0x18009e4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e4b3  mov     ebx, eax
0x18009e4b5  test    ebx, ebx
0x18009e4b7  jns     short loc_18009E4FA
0x18009e4b9  mov     edx, 1
0x18009e4be  mov     r9d, 0B3h
0x18009e4c4  mov     ecx, ebx; int
0x18009e4c6  call    Log_HREvent_75
0x18009e4cb  mov     rcx, [rsp+160h+string]; string
0x18009e4d0  call    cs:__imp_WindowsDeleteString
0x18009e4d6  mov     rcx, [rsp+160h+var_108]
0x18009e4db  mov     [rsp+160h+string], r12
0x18009e4e0  test    rcx, rcx
0x18009e4e3  jz      loc_18009E462
0x18009e4e9  mov     [rsp+160h+var_108], r12
0x18009e4ee  mov     rax, [rcx]
0x18009e4f1  mov     rax, [rax+10h]
0x18009e4f5  jmp     loc_18009E45D
0x18009e4fa  mov     r9d, 1Ch; unsigned int
0x18009e500  mov     [rsp+160h+var_F8], r12
0x18009e505  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18009e50c  mov     [rbp+60h+var_88], r12
0x18009e510  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x18009e514  lea     r8d, [r9+1]; unsigned int
0x18009e518  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009e51d  mov     rcx, [rbp+60h+var_88]
0x18009e521  lea     r8, [rsp+160h+var_F8]
0x18009e526  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18009e52d  call    cs:__imp_RoGetActivationFactory
0x18009e533  mov     ebx, eax
0x18009e535  test    eax, eax
0x18009e537  jns     short loc_18009E572
0x18009e539  mov     edx, 1
0x18009e53e  mov     r9d, 0B8h
0x18009e544  mov     ecx, eax; int
0x18009e546  call    Log_HREvent_75
0x18009e54b  mov     rdx, [rsp+160h+var_F8]
0x18009e550  test    rdx, rdx
0x18009e553  jz      loc_18009E4CB
0x18009e559  mov     [rsp+160h+var_F8], r12
0x18009e55e  mov     rcx, [rdx]
0x18009e561  mov     rax, [rcx+10h]
0x18009e565  mov     rcx, rdx
0x18009e568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e56d  jmp     loc_18009E4CB
0x18009e572  mov     rcx, [rsp+160h+var_F8]
0x18009e577  lea     r8, [rsp+160h+var_F0]
0x18009e57c  mov     rdx, [rsp+160h+string]
0x18009e581  mov     [rsp+160h+var_F0], r12
0x18009e586  mov     rax, [rcx]
0x18009e589  mov     rax, [rax+30h]
0x18009e58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e592  mov     ebx, eax
0x18009e594  test    eax, eax
0x18009e596  jns     short loc_18009E5D0
0x18009e598  mov     edx, 1
0x18009e59d  mov     r9d, 0BBh
0x18009e5a3  mov     ecx, eax; int
0x18009e5a5  call    Log_HREvent_75
0x18009e5aa  lea     rcx, [rsp+160h+var_F0]
0x18009e5af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e5b4  mov     rcx, [rsp+160h+var_F8]
0x18009e5b9  test    rcx, rcx
0x18009e5bc  jz      loc_18009E4CB
0x18009e5c2  mov     [rsp+160h+var_F8], r12
0x18009e5c7  mov     rax, [rcx]
0x18009e5ca  mov     rax, [rax+10h]
0x18009e5ce  jmp     short loc_18009E568
0x18009e5d0  mov     rdi, [rsp+160h+var_F0]
0x18009e5d5  lea     rdx, ?c_pRestApiMessagesUri@@3QBGB; "messages"
0x18009e5dc  mov     [rsp+160h+var_E8], r12
0x18009e5e1  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x18009e5e5  mov     r9d, 8; unsigned int
0x18009e5eb  mov     rax, [rdi]
0x18009e5ee  mov     [rbp+60h+var_88], r12
0x18009e5f2  lea     r8d, [r9+1]; unsigned int
0x18009e5f6  mov     rbx, [rax+48h]
0x18009e5fa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009e5ff  mov     rdx, [rbp+60h+var_88]
0x18009e603  lea     r8, [rsp+160h+var_E8]
0x18009e608  mov     rcx, rdi
0x18009e60b  mov     rax, rbx
0x18009e60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e613  mov     ebx, eax
0x18009e615  test    eax, eax
0x18009e617  jns     short loc_18009E63A
0x18009e619  mov     edx, 1
0x18009e61e  mov     r9d, 0BEh
0x18009e624  mov     ecx, eax; int
0x18009e626  call    Log_HREvent_75
0x18009e62b  lea     rcx, [rsp+160h+var_E8]
0x18009e630  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e635  jmp     loc_18009E5AA
0x18009e63a  lea     rdx, [rbp+60h+var_E0]
0x18009e63e  mov     [rbp+60h+var_E0], r12
0x18009e642  lea     rcx, [rsp+160h+var_E8]
0x18009e647  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18009e64c  mov     ebx, eax
0x18009e64e  test    eax, eax
0x18009e650  jns     short loc_18009E66F
0x18009e652  mov     r9d, 0C1h
0x18009e658  mov     edx, 1
0x18009e65d  mov     ecx, ebx; int
0x18009e65f  call    Log_HREvent_75
0x18009e664  lea     rcx, [rbp+60h+var_E0]
0x18009e668  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e66d  jmp     short loc_18009E62B
0x18009e66f  mov     rcx, [rbp+60h+var_E0]
0x18009e673  lea     rdx, [rbp+60h+var_A8]
0x18009e677  mov     [rbp+60h+var_A8], r12d
0x18009e67b  mov     rax, [rcx]
0x18009e67e  mov     rax, [rax+38h]
0x18009e682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e687  mov     ebx, eax
0x18009e689  test    eax, eax
0x18009e68b  jns     short loc_18009E695
0x18009e68d  mov     r9d, 0C4h
0x18009e693  jmp     short loc_18009E658
0x18009e695  xor     eax, eax
0x18009e697  lea     rcx, [rbp+60h+hstringHeader]
0x18009e69b  xorps   xmm0, xmm0
0x18009e69e  mov     qword ptr [rbp+60h+hstringHeader.Reserved+10h], rax
0x18009e6a2  movups  xmmword ptr [rbp+60h+hstringHeader.Reserved], xmm0
0x18009e6a6  call    ??0?$vector@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceMessage@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>(void)
0x18009e6ab  mov     r14d, r12d
0x18009e6ae  cmp     r14d, [rbp+60h+var_A8]
0x18009e6b2  jnb     loc_18009E8FB
0x18009e6b8  mov     rcx, [rsp+160h+var_E8]
0x18009e6bd  lea     r8, [rbp+60h+var_C0]
0x18009e6c1  mov     [rbp+60h+var_C0], r12
0x18009e6c5  mov     edx, r14d
0x18009e6c8  mov     rax, [rcx]
0x18009e6cb  mov     rax, [rax+30h]
0x18009e6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e6d4  mov     ebx, eax
0x18009e6d6  test    eax, eax
0x18009e6d8  js      loc_18009E8D2
0x18009e6de  lea     rdx, [rbp+60h+var_B8]
0x18009e6e2  mov     [rbp+60h+var_B8], r12
0x18009e6e6  lea     rcx, [rbp+60h+var_C0]
0x18009e6ea  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18009e6ef  mov     ebx, eax
0x18009e6f1  test    eax, eax
0x18009e6f3  js      loc_18009E8B5
0x18009e6f9  mov     rdi, [rbp+60h+var_B8]
0x18009e6fd  xor     ecx, ecx; string
0x18009e6ff  mov     [rbp+60h+var_D0], r12
0x18009e703  mov     rax, [rdi]
0x18009e706  mov     rbx, [rax+38h]
0x18009e70a  call    cs:__imp_WindowsDeleteString
0x18009e710  lea     rdx, [rbp+60h+var_D0]
0x18009e714  mov     [rbp+60h+var_D0], r12
0x18009e718  mov     rcx, rdi
0x18009e71b  mov     rax, rbx
0x18009e71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e723  mov     ebx, eax
0x18009e725  test    eax, eax
0x18009e727  js      loc_18009E893
0x18009e72d  mov     rcx, [rbp+60h+var_D0]; string
0x18009e731  xor     edx, edx; length
0x18009e733  mov     [rbp+60h+var_B0], r12
0x18009e737  call    cs:__imp_WindowsGetStringRawBuffer
0x18009e73d  mov     rcx, rax; unsigned __int16 *
0x18009e740  lea     rdx, [rbp+60h+var_B0]; struct ChatServiceMessage **
0x18009e744  call    ?CreateInstance@ChatServiceMessage@@SAJPEBGPEAPEAV1@@Z; ChatServiceMessage::CreateInstance(ushort const *,ChatServiceMessage * *)
0x18009e749  test    eax, eax
0x18009e74b  jns     short loc_18009E76B
0x18009e74d  mov     rcx, [rbp+60h+var_D0]; string
0x18009e751  xor     edx, edx; length
0x18009e753  call    cs:__imp_WindowsGetStringRawBuffer
0x18009e759  mov     rcx, rax; unsigned __int16 *
0x18009e75c  lea     rdx, [rbp+60h+var_B0]; struct ChatServiceMessage **
0x18009e760  call    ?CreateUnknownInstance@ChatServiceMessage@@SAJPEBGPEAPEAV1@@Z; ChatServiceMessage::CreateUnknownInstance(ushort const *,ChatServiceMessage * *)
0x18009e765  mov     ebx, eax
0x18009e767  test    eax, eax
0x18009e769  js      short loc_18009E7AD
0x18009e76b  lea     rdx, [rbp+60h+var_B0]
0x18009e76f  lea     rcx, [rbp+60h+hstringHeader]
0x18009e773  call    ??$emplace_back@AEAV?$CComPtr@VChatServiceAttachment@@@ATL@@$0A@@?$vector@V?$CComPtr@VChatServiceAttachment@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceAttachment@@@ATL@@@utl@@@utl@@QEAA_NAEAV?$CComPtr@VChatServiceAttachment@@@ATL@@@Z; utl::vector<ATL::CComPtr<ChatServiceAttachment>,utl::allocator<ATL::CComPtr<ChatServiceAttachment>>>::emplace_back<ATL::CComPtr<ChatServiceAttachment> &,0>(ATL::CComPtr<ChatServiceAttachment> &)
0x18009e778  test    al, al
0x18009e77a  jz      short loc_18009E7CD
0x18009e77c  lea     rcx, [rbp+60h+var_B0]
0x18009e780  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009e785  mov     rcx, [rbp+60h+var_D0]; string
0x18009e789  call    cs:__imp_WindowsDeleteString
0x18009e78f  lea     rcx, [rbp+60h+var_B8]
0x18009e793  mov     [rbp+60h+var_D0], r12
0x18009e797  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e79c  lea     rcx, [rbp+60h+var_C0]
0x18009e7a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e7a5  inc     r14d
0x18009e7a8  jmp     loc_18009E6AE
0x18009e7ad  mov     edx, 1
0x18009e7b2  mov     r9d, 0D7h
0x18009e7b8  mov     ecx, ebx; int
0x18009e7ba  call    Log_HREvent_75
0x18009e7bf  lea     rcx, [rbp+60h+var_B0]
0x18009e7c3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009e7c8  jmp     loc_18009E8A5
0x18009e7cd  xor     edx, edx
0x18009e7cf  mov     ecx, 8007000Eh; int
0x18009e7d4  mov     r9d, 0DAh
0x18009e7da  call    Log_HREvent_75
0x18009e7df  lea     rcx, [rbp+60h+var_B0]
0x18009e7e3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009e7e8  mov     rcx, [rbp+60h+var_D0]; string
0x18009e7ec  call    cs:__imp_WindowsDeleteString
0x18009e7f2  lea     rcx, [rbp+60h+var_B8]
0x18009e7f6  mov     [rbp+60h+var_D0], r12
0x18009e7fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e7ff  lea     rcx, [rbp+60h+var_C0]
0x18009e803  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e808  lea     rcx, [rbp+60h+hstringHeader]
0x18009e80c  call    ?_Uninit@?$vector@V?$CComPtr@VSlideInfo@@@ATL@@V?$allocator@V?$CComPtr@VSlideInfo@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(void)
0x18009e811  lea     rcx, [rbp+60h+var_E0]
0x18009e815  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e81a  lea     rcx, [rsp+160h+var_E8]
0x18009e81f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e824  lea     rcx, [rsp+160h+var_F0]
0x18009e829  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e82e  mov     rcx, [rsp+160h+var_F8]
0x18009e833  test    rcx, rcx
  ... truncated ...
```
