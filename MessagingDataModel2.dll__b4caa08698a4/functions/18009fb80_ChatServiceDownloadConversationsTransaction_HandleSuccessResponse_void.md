# ChatServiceDownloadConversationsTransaction::_HandleSuccessResponse(void)

- ea: `0x18009fb80`
- end: `0x1800a04fa`
- name: `?_HandleSuccessResponse@ChatServiceDownloadConversationsTransaction@@EEAAJXZ`
- size: `2426`
- prototype: `__int64 __fastcall(ChatServiceDownloadConversationsTransaction *__hidden this)`
- caller_count: `0`
- callee_count: `24`
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
- `0x18008f744`
- `0x18009201c`
- `0x1800921dc`
- `0x18009d8a8`
- `0x18009f9f0`
- `0x18009fb80`
- `0x1800a2920`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009fd1d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009fd1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ff27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a01a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ff27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a01a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fc71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fcc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fefa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ff61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ffa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a007e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a017d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a01d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a038c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a049a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fc71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fcc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fefa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ff61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ffa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a007e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a017d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a01d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a038c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a049a`

## string_xrefs

- `0x18009fcf5`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceDownloadConversationsTransaction::_HandleSuccessResponse(
        ChatServiceDownloadConversationsTransaction *this)
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
  int v28; // eax
  __int64 *v29; // rcx
  __int64 v30; // rcx
  int (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v32; // rcx
  __int64 *v33; // rcx
  __int64 *v34; // rdi
  __int64 (__fastcall *v35)(__int64 *, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v36; // rax
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, PVOID, HSTRING *); // rbx
  char v40; // r8
  HSTRING_HEADER *v41; // rax
  int v42; // eax
  PCWSTR v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  int (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v47; // rbx
  __int64 v48; // r9
  __int64 v49; // rcx
  int (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v51; // rdx
  int v52; // eax
  __int64 v53; // rcx
  int (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v55; // rcx
  HSTRING_HEADER v56; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v57; // [rsp+50h] [rbp-B0h] BYREF
  int (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v61; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v64; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v65; // [rsp+90h] [rbp-70h] BYREF
  __int64 v66; // [rsp+98h] [rbp-68h] BYREF
  __int64 (__fastcall ***v67)(_QWORD, GUID *, __int64); // [rsp+A0h] [rbp-60h] BYREF
  __int64 v68; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v69; // [rsp+B0h] [rbp-50h] BYREF
  struct ChatServiceConversation *v70; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v72; // [rsp+D8h] [rbp-28h]
  _OWORD v73[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v74[2]; // [rsp+100h] [rbp+0h] BYREF

  v2 = *((_QWORD *)this + 2);
  v57 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 48LL))(v2, &v57);
  v4 = v3;
  if ( v3 < 0 )
  {
    Log_HREvent_76(v3);
LABEL_3:
    v5 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return (unsigned int)v4;
  }
  v58 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v57 + 80LL))(
         v57,
         &v58);
  v4 = v7;
  if ( v7 < 0 )
  {
    Log_HREvent_76(v7);
    v8 = v58;
    if ( v58 )
    {
      v58 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v8)[2])(v8);
    }
LABEL_9:
    v9 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return (unsigned int)v4;
  }
  string = 0;
  WindowsDeleteString(0);
  v10 = v58;
  string = 0;
  v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(v58);
  if ( v4 >= 0 )
    v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*v10)[10])(v10, &string);
  if ( v4 < 0 )
  {
    Log_HREvent_76(v4);
LABEL_15:
    WindowsDeleteString(string);
    v11 = v58;
    string = 0;
    if ( v58 )
    {
      v58 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v11)[2])(v11);
    }
    goto LABEL_9;
  }
  v60 = 0;
  v72 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = RoGetActivationFactory(v72, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v60);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_76(ActivationFactory);
    v13 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_15;
  }
  v61 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 **))(*(_QWORD *)v60 + 48LL))(v60, string, &v61);
  v4 = v14;
  if ( v14 < 0 )
  {
    Log_HREvent_76(v14);
    goto LABEL_22;
  }
  v16 = v61;
  v62 = 0;
  v17 = *v61;
  v72 = 0;
  v18 = *(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v17 + 72);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"conversations", 0xEu, 0xDu);
  v19 = v18(v16, v72, &v62);
  v4 = v19;
  if ( v19 < 0 )
  {
    Log_HREvent_76(v19);
LABEL_26:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
LABEL_22:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    v15 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_15;
  }
  v63 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
         &v62,
         (__int64)&v63);
  if ( v4 < 0
    || (v69 = 0, v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v63 + 56LL))(v63, &v69), v4 < 0) )
  {
    Log_HREvent_76(v4);
LABEL_29:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    goto LABEL_26;
  }
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>(&hstringHeader);
  for ( i = 0; i < v69; ++i )
  {
    v67 = 0;
    v22 = (*v62)[6](v62, (GUID *)i, (__int64)&v67);
    v4 = v22;
    if ( v22 < 0 )
    {
      Log_HREvent_76(v22);
      goto LABEL_52;
    }
    v68 = 0;
    v23 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v67,
            (__int64)&v68);
    v4 = v23;
    if ( v23 < 0 )
    {
      Log_HREvent_76(v23);
      goto LABEL_50;
    }
    v24 = v68;
    v65 = 0;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v68 + 56LL);
    WindowsDeleteString(0);
    v65 = 0;
    v26 = v25(v24, &v65);
    v4 = v26;
    if ( v26 < 0 )
    {
      Log_HREvent_76(v26);
LABEL_48:
      WindowsDeleteString(v65);
      v65 = 0;
LABEL_50:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
LABEL_52:
      v33 = (__int64 *)&v67;
LABEL_53:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v33);
      utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
      goto LABEL_29;
    }
    v70 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v65, 0);
    v28 = ChatServiceConversation::CreateInstance(StringRawBuffer, &v70);
    v4 = v28;
    if ( v28 < 0 )
    {
      Log_HREvent_76(v28);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
      goto LABEL_48;
    }
    if ( !utl::vector<ATL::CComPtr<ChatServiceAttachment>,utl::allocator<ATL::CComPtr<ChatServiceAttachment>>>::emplace_back<ATL::CComPtr<ChatServiceAttachment> &,0>(
            &hstringHeader,
            &v70) )
    {
      Log_HREvent_76(-2147024882);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
      WindowsDeleteString(v65);
      v65 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
      v29 = (__int64 *)&v67;
      goto LABEL_40;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
    WindowsDeleteString(v65);
    v65 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  }
  v34 = v61;
  v66 = 0;
  v35 = *(__int64 (__fastcall **)(__int64 *, PVOID, __int64 *))(*v61 + 64);
  v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v56, (const WCHAR **)off_1800FD7D0, v20);
  v37 = v35(v34, v36[1].Reserved.Reserved1, &v66);
  v4 = v37;
  if ( v37 < 0 )
  {
    Log_HREvent_76(v37);
LABEL_56:
    v33 = &v66;
    goto LABEL_53;
  }
  v38 = v66;
  v64 = 0;
  v39 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v66 + 80LL);
  WindowsDeleteString(0);
  v64 = 0;
  v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v56, (const WCHAR **)off_1800FD7C8, v40);
  v42 = v39(v38, v41[1].Reserved.Reserved1, &v64);
  v4 = v42;
  if ( v42 < 0 )
  {
    Log_HREvent_76(v42);
LABEL_59:
    WindowsDeleteString(v64);
    v64 = 0;
    goto LABEL_56;
  }
  memset(v73, 0, sizeof(v73));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v73);
  v43 = WindowsGetStringRawBuffer(v64, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v73,
                           v43) )
  {
    Log_HREvent_76(-2147024882);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v73);
    WindowsDeleteString(v64);
    v29 = &v66;
    v64 = 0;
LABEL_40:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
    utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    v30 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    WindowsDeleteString(string);
    v31 = v58;
    string = 0;
    if ( v58 )
    {
      v58 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v31)[2])(v31);
    }
    v32 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    return 2147942414LL;
  }
  v44 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
          v73,
          L"syncState=",
          0);
  if ( v44 == -1 )
  {
    v4 = -2147024809;
    Log_HREvent_76(-2147024809);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v73);
    WindowsDeleteString(v64);
    v64 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
    utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    v45 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    WindowsDeleteString(string);
    v46 = v58;
    string = 0;
    if ( v58 )
    {
      v58 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v46)[2])(v46);
    }
    goto LABEL_3;
  }
  v47 = v44 + 10;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find_first_of(
    v73,
    L"&",
    v44 + 10);
  memset(v74, 0, sizeof(v74));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v74);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v74,
                           v73,
                           v47,
                           v48) )
  {
    Log_HREvent_76(-2147024882);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v74);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v73);
    WindowsDeleteString(v64);
    v64 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
    utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    v49 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    WindowsDeleteString(string);
    v50 = v58;
    string = 0;
    if ( v58 )
    {
      v58 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v50)[2])(v50);
    }
    v51 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    return 2147942414LL;
  }
  utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>::operator=(
    (char *)this + 96,
    &hstringHeader);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    (char *)this + 120,
    v74);
  v52 = ChatServiceTransaction::_HandleSuccessResponse(this);
  v4 = v52;
  if ( v52 < 0 )
  {
    Log_HREvent_76(v52);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v74);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v73);
    goto LABEL_59;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v74);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v73);
  WindowsDeleteString(v64);
  v64 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
  utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&hstringHeader);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  v53 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  }
  WindowsDeleteString(string);
  v54 = v58;
  string = 0;
  if ( v58 )
  {
    v58 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v54)[2])(v54);
  }
  v55 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  }
  return 0;
}

```

## disassembly

```asm
0x18009fb80  push    rbp
0x18009fb82  push    rbx
0x18009fb83  push    rdi
0x18009fb84  push    r12
0x18009fb86  push    r14
0x18009fb88  push    r15
0x18009fb8a  lea     rbp, [rsp-38h]
0x18009fb8f  sub     rsp, 138h
0x18009fb96  mov     rax, cs:__security_cookie
0x18009fb9d  xor     rax, rsp
0x18009fba0  mov     [rbp+60h+var_40], rax
0x18009fba4  mov     r15, rcx
0x18009fba7  lea     rdx, [rsp+160h+var_110]
0x18009fbac  mov     rcx, [rcx+10h]
0x18009fbb0  xor     r12d, r12d
0x18009fbb3  mov     [rsp+160h+var_110], r12
0x18009fbb8  mov     rax, [rcx]
0x18009fbbb  mov     rax, [rax+30h]
0x18009fbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fbc4  mov     ebx, eax
0x18009fbc6  test    eax, eax
0x18009fbc8  jns     short loc_18009FC01
0x18009fbca  lea     edx, [r12+1]
0x18009fbcf  mov     r9d, 0ADh
0x18009fbd5  mov     ecx, eax; int
0x18009fbd7  call    Log_HREvent_76
0x18009fbdc  mov     rdx, [rsp+160h+var_110]
0x18009fbe1  test    rdx, rdx
0x18009fbe4  jz      short loc_18009FBFA
0x18009fbe6  mov     [rsp+160h+var_110], r12
0x18009fbeb  mov     rcx, [rdx]
0x18009fbee  mov     rax, [rcx+10h]
0x18009fbf2  mov     rcx, rdx
0x18009fbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fbfa  mov     eax, ebx
0x18009fbfc  jmp     loc_1800A04DD
0x18009fc01  mov     rcx, [rsp+160h+var_110]
0x18009fc06  lea     rdx, [rsp+160h+var_108]
0x18009fc0b  mov     [rsp+160h+var_108], r12
0x18009fc10  mov     rax, [rcx]
0x18009fc13  mov     rax, [rax+50h]
0x18009fc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fc1c  mov     ebx, eax
0x18009fc1e  test    eax, eax
0x18009fc20  jns     short loc_18009FC6A
0x18009fc22  mov     edx, 1
0x18009fc27  mov     r9d, 0B0h
0x18009fc2d  mov     ecx, eax; int
0x18009fc2f  call    Log_HREvent_76
0x18009fc34  mov     rdx, [rsp+160h+var_108]
0x18009fc39  test    rdx, rdx
0x18009fc3c  jz      short loc_18009FC52
0x18009fc3e  mov     [rsp+160h+var_108], r12
0x18009fc43  mov     rcx, [rdx]
0x18009fc46  mov     rax, [rcx+10h]
0x18009fc4a  mov     rcx, rdx
0x18009fc4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fc52  mov     rcx, [rsp+160h+var_110]
0x18009fc57  test    rcx, rcx
0x18009fc5a  jz      short loc_18009FBFA
0x18009fc5c  mov     [rsp+160h+var_110], r12
0x18009fc61  mov     rax, [rcx]
0x18009fc64  mov     rax, [rax+10h]
0x18009fc68  jmp     short loc_18009FBF5
0x18009fc6a  xor     ecx, ecx; string
0x18009fc6c  mov     [rsp+160h+string], r12
0x18009fc71  call    cs:__imp_WindowsDeleteString
0x18009fc77  mov     rdi, [rsp+160h+var_108]
0x18009fc7c  mov     rcx, rdi
0x18009fc7f  mov     [rsp+160h+string], r12
0x18009fc84  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x18009fc89  mov     ebx, eax
0x18009fc8b  test    eax, eax
0x18009fc8d  js      short loc_18009FCA5
0x18009fc8f  mov     rax, [rdi]
0x18009fc92  lea     rdx, [rsp+160h+string]
0x18009fc97  mov     rcx, rdi
0x18009fc9a  mov     rax, [rax+50h]
0x18009fc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fca3  mov     ebx, eax
0x18009fca5  test    ebx, ebx
0x18009fca7  jns     short loc_18009FCEA
0x18009fca9  mov     edx, 1
0x18009fcae  mov     r9d, 0B3h
0x18009fcb4  mov     ecx, ebx; int
0x18009fcb6  call    Log_HREvent_76
0x18009fcbb  mov     rcx, [rsp+160h+string]; string
0x18009fcc0  call    cs:__imp_WindowsDeleteString
0x18009fcc6  mov     rcx, [rsp+160h+var_108]
0x18009fccb  mov     [rsp+160h+string], r12
0x18009fcd0  test    rcx, rcx
0x18009fcd3  jz      loc_18009FC52
0x18009fcd9  mov     [rsp+160h+var_108], r12
0x18009fcde  mov     rax, [rcx]
0x18009fce1  mov     rax, [rax+10h]
0x18009fce5  jmp     loc_18009FC4D
0x18009fcea  mov     r9d, 1Ch; unsigned int
0x18009fcf0  mov     [rsp+160h+var_F8], r12
0x18009fcf5  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18009fcfc  mov     [rbp+60h+var_88], r12
0x18009fd00  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x18009fd04  lea     r8d, [r9+1]; unsigned int
0x18009fd08  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009fd0d  mov     rcx, [rbp+60h+var_88]
0x18009fd11  lea     r8, [rsp+160h+var_F8]
0x18009fd16  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18009fd1d  call    cs:__imp_RoGetActivationFactory
0x18009fd23  mov     ebx, eax
0x18009fd25  test    eax, eax
0x18009fd27  jns     short loc_18009FD62
0x18009fd29  mov     edx, 1
0x18009fd2e  mov     r9d, 0B8h
0x18009fd34  mov     ecx, eax; int
0x18009fd36  call    Log_HREvent_76
0x18009fd3b  mov     rdx, [rsp+160h+var_F8]
0x18009fd40  test    rdx, rdx
0x18009fd43  jz      loc_18009FCBB
0x18009fd49  mov     [rsp+160h+var_F8], r12
0x18009fd4e  mov     rcx, [rdx]
0x18009fd51  mov     rax, [rcx+10h]
0x18009fd55  mov     rcx, rdx
0x18009fd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fd5d  jmp     loc_18009FCBB
0x18009fd62  mov     rcx, [rsp+160h+var_F8]
0x18009fd67  lea     r8, [rsp+160h+var_F0]
0x18009fd6c  mov     rdx, [rsp+160h+string]
0x18009fd71  mov     [rsp+160h+var_F0], r12
0x18009fd76  mov     rax, [rcx]
0x18009fd79  mov     rax, [rax+30h]
0x18009fd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fd82  mov     ebx, eax
0x18009fd84  test    eax, eax
0x18009fd86  jns     short loc_18009FDC0
0x18009fd88  mov     edx, 1
0x18009fd8d  mov     r9d, 0BBh
0x18009fd93  mov     ecx, eax; int
0x18009fd95  call    Log_HREvent_76
0x18009fd9a  lea     rcx, [rsp+160h+var_F0]
0x18009fd9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009fda4  mov     rcx, [rsp+160h+var_F8]
0x18009fda9  test    rcx, rcx
0x18009fdac  jz      loc_18009FCBB
0x18009fdb2  mov     [rsp+160h+var_F8], r12
0x18009fdb7  mov     rax, [rcx]
0x18009fdba  mov     rax, [rax+10h]
0x18009fdbe  jmp     short loc_18009FD58
0x18009fdc0  mov     rdi, [rsp+160h+var_F0]
0x18009fdc5  lea     rdx, ?c_pRestApiConversationsUri@@3QBGB; "conversations"
0x18009fdcc  mov     [rsp+160h+var_E8], r12
0x18009fdd1  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x18009fdd5  mov     r9d, 0Dh; unsigned int
0x18009fddb  mov     rax, [rdi]
0x18009fdde  mov     [rbp+60h+var_88], r12
0x18009fde2  lea     r8d, [r9+1]; unsigned int
0x18009fde6  mov     rbx, [rax+48h]
0x18009fdea  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009fdef  mov     rdx, [rbp+60h+var_88]
0x18009fdf3  lea     r8, [rsp+160h+var_E8]
0x18009fdf8  mov     rcx, rdi
0x18009fdfb  mov     rax, rbx
0x18009fdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fe03  mov     ebx, eax
0x18009fe05  test    eax, eax
0x18009fe07  jns     short loc_18009FE2A
0x18009fe09  mov     edx, 1
0x18009fe0e  mov     r9d, 0BFh
0x18009fe14  mov     ecx, eax; int
0x18009fe16  call    Log_HREvent_76
0x18009fe1b  lea     rcx, [rsp+160h+var_E8]
0x18009fe20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009fe25  jmp     loc_18009FD9A
0x18009fe2a  lea     rdx, [rbp+60h+var_E0]
0x18009fe2e  mov     [rbp+60h+var_E0], r12
0x18009fe32  lea     rcx, [rsp+160h+var_E8]
0x18009fe37  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18009fe3c  mov     ebx, eax
0x18009fe3e  test    eax, eax
0x18009fe40  jns     short loc_18009FE5F
0x18009fe42  mov     r9d, 0C2h
0x18009fe48  mov     edx, 1
0x18009fe4d  mov     ecx, ebx; int
0x18009fe4f  call    Log_HREvent_76
0x18009fe54  lea     rcx, [rbp+60h+var_E0]
0x18009fe58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009fe5d  jmp     short loc_18009FE1B
0x18009fe5f  mov     rcx, [rbp+60h+var_E0]
0x18009fe63  lea     rdx, [rbp+60h+var_B0]
0x18009fe67  mov     [rbp+60h+var_B0], r12d
0x18009fe6b  mov     rax, [rcx]
0x18009fe6e  mov     rax, [rax+38h]
0x18009fe72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fe77  mov     ebx, eax
0x18009fe79  test    eax, eax
0x18009fe7b  jns     short loc_18009FE85
0x18009fe7d  mov     r9d, 0C5h
0x18009fe83  jmp     short loc_18009FE48
0x18009fe85  xor     eax, eax
0x18009fe87  lea     rcx, [rbp+60h+hstringHeader]
0x18009fe8b  xorps   xmm0, xmm0
0x18009fe8e  mov     qword ptr [rbp+60h+hstringHeader.Reserved+10h], rax
0x18009fe92  movups  xmmword ptr [rbp+60h+hstringHeader.Reserved], xmm0
0x18009fe96  call    ??0?$vector@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceMessage@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>(void)
0x18009fe9b  mov     r14d, r12d
0x18009fe9e  cmp     r14d, [rbp+60h+var_B0]
0x18009fea2  jnb     loc_1800A00D0
0x18009fea8  mov     rcx, [rsp+160h+var_E8]
0x18009fead  lea     r8, [rbp+60h+var_C0]
0x18009feb1  mov     [rbp+60h+var_C0], r12
0x18009feb5  mov     edx, r14d
0x18009feb8  mov     rax, [rcx]
0x18009febb  mov     rax, [rax+30h]
0x18009febf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fec4  mov     ebx, eax
0x18009fec6  test    eax, eax
0x18009fec8  js      loc_1800A00A7
0x18009fece  lea     rdx, [rbp+60h+var_B8]
0x18009fed2  mov     [rbp+60h+var_B8], r12
0x18009fed6  lea     rcx, [rbp+60h+var_C0]
0x18009feda  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18009fedf  mov     ebx, eax
0x18009fee1  test    eax, eax
0x18009fee3  js      loc_1800A008A
0x18009fee9  mov     rdi, [rbp+60h+var_B8]
0x18009feed  xor     ecx, ecx; string
0x18009feef  mov     [rbp+60h+var_D0], r12
0x18009fef3  mov     rax, [rdi]
0x18009fef6  mov     rbx, [rax+38h]
0x18009fefa  call    cs:__imp_WindowsDeleteString
0x18009ff00  lea     rdx, [rbp+60h+var_D0]
0x18009ff04  mov     [rbp+60h+var_D0], r12
0x18009ff08  mov     rcx, rdi
0x18009ff0b  mov     rax, rbx
0x18009ff0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ff13  mov     ebx, eax
0x18009ff15  test    eax, eax
0x18009ff17  js      loc_1800A0068
0x18009ff1d  mov     rcx, [rbp+60h+var_D0]; string
0x18009ff21  xor     edx, edx; length
0x18009ff23  mov     [rbp+60h+var_A8], r12
0x18009ff27  call    cs:__imp_WindowsGetStringRawBuffer
0x18009ff2d  mov     rcx, rax; unsigned __int16 *
0x18009ff30  lea     rdx, [rbp+60h+var_A8]; struct ChatServiceConversation **
0x18009ff34  call    ?CreateInstance@ChatServiceConversation@@SAJPEBGPEAPEAV1@@Z; ChatServiceConversation::CreateInstance(ushort const *,ChatServiceConversation * *)
0x18009ff39  mov     ebx, eax
0x18009ff3b  test    eax, eax
0x18009ff3d  js      loc_1800A004B
0x18009ff43  lea     rdx, [rbp+60h+var_A8]
0x18009ff47  lea     rcx, [rbp+60h+hstringHeader]
0x18009ff4b  call    ??$emplace_back@AEAV?$CComPtr@VChatServiceAttachment@@@ATL@@$0A@@?$vector@V?$CComPtr@VChatServiceAttachment@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceAttachment@@@ATL@@@utl@@@utl@@QEAA_NAEAV?$CComPtr@VChatServiceAttachment@@@ATL@@@Z; utl::vector<ATL::CComPtr<ChatServiceAttachment>,utl::allocator<ATL::CComPtr<ChatServiceAttachment>>>::emplace_back<ATL::CComPtr<ChatServiceAttachment> &,0>(ATL::CComPtr<ChatServiceAttachment> &)
0x18009ff50  test    al, al
0x18009ff52  jz      short loc_18009FF85
0x18009ff54  lea     rcx, [rbp+60h+var_A8]
0x18009ff58  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009ff5d  mov     rcx, [rbp+60h+var_D0]; string
0x18009ff61  call    cs:__imp_WindowsDeleteString
0x18009ff67  lea     rcx, [rbp+60h+var_B8]
0x18009ff6b  mov     [rbp+60h+var_D0], r12
0x18009ff6f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ff74  lea     rcx, [rbp+60h+var_C0]
0x18009ff78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ff7d  inc     r14d
0x18009ff80  jmp     loc_18009FE9E
0x18009ff85  xor     edx, edx
0x18009ff87  mov     ecx, 8007000Eh; int
0x18009ff8c  mov     r9d, 0D6h
0x18009ff92  call    Log_HREvent_76
0x18009ff97  lea     rcx, [rbp+60h+var_A8]
0x18009ff9b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009ffa0  mov     rcx, [rbp+60h+var_D0]; string
0x18009ffa4  call    cs:__imp_WindowsDeleteString
0x18009ffaa  lea     rcx, [rbp+60h+var_B8]
0x18009ffae  mov     [rbp+60h+var_D0], r12
0x18009ffb2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ffb7  lea     rcx, [rbp+60h+var_C0]
0x18009ffbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ffc0  lea     rcx, [rbp+60h+hstringHeader]
0x18009ffc4  call    ?_Uninit@?$vector@V?$CComPtr@VSlideInfo@@@ATL@@V?$allocator@V?$CComPtr@VSlideInfo@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(void)
0x18009ffc9  lea     rcx, [rbp+60h+var_E0]
0x18009ffcd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ffd2  lea     rcx, [rsp+160h+var_E8]
0x18009ffd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ffdc  lea     rcx, [rsp+160h+var_F0]
0x18009ffe1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ffe6  mov     rcx, [rsp+160h+var_F8]
0x18009ffeb  test    rcx, rcx
0x18009ffee  jz      short loc_1800A0001
0x18009fff0  mov     [rsp+160h+var_F8], r12
0x18009fff5  mov     rax, [rcx]
0x18009fff8  mov     rax, [rax+10h]
0x18009fffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0001  mov     rcx, [rsp+160h+string]; string
0x1800a0006  call    cs:__imp_WindowsDeleteString
0x1800a000c  mov     rcx, [rsp+160h+var_108]
0x1800a0011  mov     [rsp+160h+string], r12
0x1800a0016  test    rcx, rcx
0x1800a0019  jz      short loc_1800A002C
0x1800a001b  mov     [rsp+160h+var_108], r12
0x1800a0020  mov     rax, [rcx]
0x1800a0023  mov     rax, [rax+10h]
0x1800a0027  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
