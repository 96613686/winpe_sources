# CMidiSessionTracker::GetSessionList(ushort * *)

- ea: `0x14003a960`
- end: `0x14003b201`
- name: `?GetSessionList@CMidiSessionTracker@@UEAAJPEAPEAG@Z`
- size: `2209`
- prototype: `int(CMidiSessionTracker *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x14000183c`
- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000ca00`
- `0x14000cc2c`
- `0x140022e58`
- `0x14002654c`
- `0x140039188`
- `0x140039910`
- `0x14003a3b8`
- `0x14003a474`
- `0x14003a534`
- `0x14003a960`
- `0x14003b478`
- `0x14003b55c`
- `0x14003b784`
- `0x14003be6c`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b0b3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b0ba`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b0c1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b0c8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b0b3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b0ba`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b0c1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b0c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b183`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b1b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b183`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b1b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003a9d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003a9d6`

## string_xrefs

- `0x14003ac4c`: `clientProcessId`

## pseudocode

```c
__int64 __fastcall CMidiSessionTracker::GetSessionList(CMidiSessionTracker *this, unsigned __int16 **a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  void (__fastcall ***v7)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 i; // rsi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 StringValue; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int v15; // r8d
  _WORD *v16; // r9
  __int128 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rbx
  void (__fastcall ***v20)(_QWORD, __int64 *, __int64 **); // rcx
  _QWORD *v21; // rdi
  __int64 v22; // rbx
  __int64 NumberValue; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  void (__fastcall **v27)(_QWORD, __int64 *, void (__fastcall **)(__int64, __int64 *)); // rax
  __int64 **v28; // rcx
  __int64 j; // rax
  __int64 *k; // rcx
  int v31; // eax
  void (__fastcall *v32)(__int64, __int64 *); // rcx
  __int64 v33; // rax
  int v34; // eax
  void (__fastcall *v35)(__int64, __int64 *); // rbx
  void (__fastcall **v36)(__int64 (__fastcall ***)(_QWORD, __int64 *, void (__fastcall **)(__int64, __int64 *)), __int64 *, void (__fastcall **)(__int64, __int64 *)); // rax
  void (__fastcall **v37)(_QWORD, __int64 *, void (__fastcall **)(__int64, __int64 *)); // rax
  void (__fastcall *v38)(__int64, __int64 *); // rbx
  void (__fastcall **v39)(_QWORD, __int64 *, void (__fastcall **)(__int64, __int64 *)); // rax
  unsigned __int16 **v40; // r8
  void (__fastcall *v42)(__int64, __int64 *); // [rsp+30h] [rbp-D0h] BYREF
  void (__fastcall ***v43)(_QWORD, __int64 *, void (__fastcall **)(__int64, __int64 *)); // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall *v44)(__int64, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall *v45)(__int64, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  const char **v46; // [rsp+50h] [rbp-B0h] BYREF
  const char *v47; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h]
  __int128 *v49; // [rsp+68h] [rbp-98h]
  void (__fastcall ***v50)(_QWORD, __int64 *, void (__fastcall **)(__int64, __int64 *)); // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, __int64 *, void (__fastcall **)(__int64, __int64 *)); // [rsp+78h] [rbp-88h] BYREF
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  void (__fastcall ***v53)(_QWORD, __int64 *, void (__fastcall **)(__int64, __int64 *)); // [rsp+88h] [rbp-78h] BYREF
  void (__fastcall *v54)(__int64, __int64 *); // [rsp+90h] [rbp-70h] BYREF
  const char *v55; // [rsp+98h] [rbp-68h] BYREF
  int *v56; // [rsp+A0h] [rbp-60h] BYREF
  int v57; // [rsp+A8h] [rbp-58h] BYREF
  int v58; // [rsp+ACh] [rbp-54h]
  const wchar_t *v59; // [rsp+B8h] [rbp-48h]
  __int64 v60; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v61; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v62; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v63; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v64; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v65; // [rsp+F0h] [rbp-10h]
  _BYTE v66[6]; // [rsp+12Ah] [rbp+2Ah] BYREF

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v42 = (void (__fastcall *)(__int64, __int64 *))this;
    v55 = "CMidiSessionTracker::GetSessionList";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v4,
      (__int64)&word_14008AD76,
      v5,
      v6,
      &v55);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v52);
  _InterlockedIncrement64(&qword_140096A58);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::Data::Json::JsonArray::JsonArray'::`1'::_lambda_23__::operator()(
      (__int64)v7,
      &v50,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_140096A58);
  }
  else
  {
    _InterlockedDecrement64(&qword_140096A58);
    v42 = (void (__fastcall *)(__int64, __int64 *))`winrt::Windows::Data::Json::JsonArray::JsonArray'::`1'::_lambda_23__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonArray (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v7,
      (__int64)&v50,
      &v42);
  }
  for ( i = *((_QWORD *)this + 3); i != *((_QWORD *)this + 4); i += 144 )
  {
    winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v43);
    v64 = 0;
    v65 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v64, L"id", 2u);
    WindowsMidiServicesInternal::JsonSetGuidProperty(&v43, &v64, i);
    std::wstring::~wstring((char **)&v64);
    v9 = (_QWORD *)(i + 72);
    v10 = *(_QWORD *)(i + 88);
    if ( *(_QWORD *)(i + 96) > 7u )
      v9 = (_QWORD *)*v9;
    if ( (_DWORD)v10 )
    {
      if ( *((_WORD *)v9 + (unsigned int)v10) )
        abort();
      LODWORD(v47) = 1;
      v46 = &v47;
      HIDWORD(v47) = v10;
      v49 = (__int128 *)v9;
    }
    else
    {
      v46 = 0;
    }
    StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v60);
    v57 = 1;
    v59 = L"name";
    v58 = 4;
    v56 = &v57;
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v43,
      &v56,
      StringValue);
    if ( v60 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v60);
    v12 = (_QWORD *)(i + 40);
    v13 = *(_QWORD *)(i + 56);
    if ( *(_QWORD *)(i + 64) > 7u )
      v12 = (_QWORD *)*v12;
    if ( (_DWORD)v13 )
    {
      if ( *((_WORD *)v12 + (unsigned int)v13) )
        abort();
      LODWORD(v47) = 1;
      v46 = &v47;
      HIDWORD(v47) = v13;
      v49 = (__int128 *)v12;
    }
    else
    {
      v46 = 0;
    }
    v14 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v61);
    v57 = 1;
    v59 = L"processName";
    v58 = 11;
    v56 = &v57;
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v43,
      &v56,
      v14);
    if ( v61 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v61);
    v15 = *(_DWORD *)(i + 16);
    v16 = v66;
    do
    {
      *--v16 = v15 % 0xA + 48;
      v15 /= 0xAu;
    }
    while ( v15 );
    std::wstring::wstring(&v64, v16, v66);
    v17 = &v64;
    if ( *((_QWORD *)&v65 + 1) > 7u )
      v17 = (__int128 *)v64;
    if ( (_DWORD)v65 )
    {
      if ( *((_WORD *)v17 + (unsigned int)v65) )
        abort();
      LODWORD(v47) = 1;
      v46 = &v47;
      HIDWORD(v47) = v65;
      v49 = v17;
    }
    else
    {
      v46 = 0;
    }
    v18 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v62);
    v57 = 1;
    v59 = L"clientProcessId";
    v58 = 15;
    v56 = &v57;
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v43,
      &v56,
      v18);
    if ( v62 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v62);
    std::wstring::~wstring((char **)&v64);
    v19 = *(_QWORD *)(i + 32);
    v64 = 0;
    v65 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v64, L"startTime", 9u);
    WindowsMidiServicesInternal::JsonSetDateTimeProperty(&v43, &v64, v19);
    std::wstring::~wstring((char **)&v64);
    _InterlockedIncrement64(&qword_140096A58);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> )
    {
      `winrt::Windows::Data::Json::JsonArray::JsonArray'::`1'::_lambda_23__::operator()(
        (__int64)v20,
        &v51,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>);
      _InterlockedDecrement64(&qword_140096A58);
    }
    else
    {
      _InterlockedDecrement64(&qword_140096A58);
      v42 = (void (__fastcall *)(__int64, __int64 *))`winrt::Windows::Data::Json::JsonArray::JsonArray'::`1'::_lambda_23__::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonArray (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        v20,
        (__int64)&v51,
        &v42);
    }
    v21 = **(_QWORD ***)(i + 104);
    while ( v21 != *(_QWORD **)(i + 104) )
    {
      winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v53);
      v22 = v21[12];
      v64 = 0;
      v65 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v64, L"earliestStartTime", 0x11u);
      WindowsMidiServicesInternal::JsonSetDateTimeProperty(&v43, &v64, v22);
      std::wstring::~wstring((char **)&v64);
      NumberValue = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
      *((_QWORD *)&v64 + 1) = 0xD00000001LL;
      *((_QWORD *)&v65 + 1) = L"instanceCount";
      *(_QWORD *)&v64 = (char *)&v64 + 8;
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        &v53,
        &v64,
        NumberValue);
      if ( v63 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v63);
      v24 = v21 + 8;
      v25 = v21[10];
      if ( v21[11] > 7u )
        v24 = (_QWORD *)*v24;
      if ( (_DWORD)v25 )
      {
        if ( *((_WORD *)v24 + (unsigned int)v25) )
          abort();
        LODWORD(v47) = 1;
        v46 = &v47;
        HIDWORD(v47) = v25;
        v49 = (__int128 *)v24;
      }
      else
      {
        v46 = 0;
      }
      v26 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v55);
      *((_QWORD *)&v64 + 1) = 0xA00000001LL;
      *((_QWORD *)&v65 + 1) = L"endpointId";
      *(_QWORD *)&v64 = (char *)&v64 + 8;
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        &v53,
        &v64,
        v26);
      if ( v55 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v55);
      if ( v53 )
      {
        v27 = *v53;
        v44 = 0;
        (*v27)(v53, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v44);
        v54 = v44;
      }
      else
      {
        v54 = 0;
      }
      winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
        &v51,
        &v54);
      if ( v54 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v54);
      if ( v53 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v53);
      v28 = (__int64 **)v21[2];
      if ( *((_BYTE *)v28 + 25) )
      {
        for ( j = v21[1]; !*(_BYTE *)(j + 25) && v21 == *(_QWORD **)(j + 16); j = *(_QWORD *)(j + 8) )
          v21 = (_QWORD *)j;
        v21 = (_QWORD *)j;
      }
      else
      {
        v21 = (_QWORD *)v21[2];
        for ( k = *v28; !*((_BYTE *)k + 25); k = (__int64 *)*k )
          v21 = k;
      }
    }
    LODWORD(v44) = 0;
    v42 = 0;
    if ( v51 )
    {
      v31 = (**v51)(
              v51,
              winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>,
              &v42);
      v32 = v42;
    }
    else
    {
      v31 = 0;
      v32 = 0;
    }
    LODWORD(v46) = 577;
    v47 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v48 = 0;
    if ( v31 < 0 )
      winrt::throw_hresult((unsigned int)v31, &v46);
    v33 = *(_QWORD *)v32;
    LODWORD(v46) = 579;
    v47 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v48 = 0;
    v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v33 + 56))(v32, &v44);
    if ( v34 < 0 )
      winrt::throw_hresult((unsigned int)v34, &v46);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
    if ( (_DWORD)v44 )
    {
      if ( v51 )
      {
        v36 = (void (__fastcall **)(__int64 (__fastcall ***)(_QWORD, __int64 *, void (__fastcall **)(__int64, __int64 *)), __int64 *, void (__fastcall **)(__int64, __int64 *)))*v51;
        v42 = 0;
        (*v36)(v51, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v42);
        v35 = v42;
        v44 = v42;
      }
      else
      {
        v44 = 0;
        v35 = 0;
      }
      *((_QWORD *)&v64 + 1) = 0xB00000001LL;
      *((_QWORD *)&v65 + 1) = L"connections";
      *(_QWORD *)&v64 = (char *)&v64 + 8;
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        &v43,
        &v64,
        &v44);
      if ( v35 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
    }
    if ( v43 )
    {
      v37 = *v43;
      v42 = 0;
      (*v37)(v43, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v42);
      v45 = v42;
    }
    else
    {
      v45 = 0;
    }
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
      &v50,
      &v45);
    if ( v45 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v45);
    if ( v51 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
    if ( v43 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v43);
  }
  if ( v50 )
  {
    v39 = *v50;
    v42 = 0;
    (*v39)(v50, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v42);
    v38 = v42;
    v45 = v42;
  }
  else
  {
    v45 = 0;
    v38 = 0;
  }
  *((_QWORD *)&v64 + 1) = 0x800000001LL;
  *((_QWORD *)&v65 + 1) = L"sessions";
  *(_QWORD *)&v64 = (char *)&v64 + 8;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v52,
    &v64,
    &v45);
  if ( v38 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v45);
  if ( WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(
         (WindowsMidiServicesInternal *)&v52,
         (const struct winrt::Windows::Data::Json::JsonObject *)a2,
         v40) )
  {
    if ( v50 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v50);
    if ( v52 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v52);
    if ( this != (CMidiSessionTracker *)-48LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    return 0;
  }
  else
  {
    if ( v50 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v50);
    if ( v52 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v52);
    if ( this != (CMidiSessionTracker *)-48LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x14003a960  mov     [rsp-8+arg_10], rbx
0x14003a965  push    rbp
0x14003a966  push    rsi
0x14003a967  push    rdi
0x14003a968  push    r12
0x14003a96a  push    r13
0x14003a96c  push    r14
0x14003a96e  push    r15
0x14003a970  lea     rbp, [rsp-40h]
0x14003a975  sub     rsp, 140h
0x14003a97c  mov     rax, cs:__security_cookie
0x14003a983  xor     rax, rsp
0x14003a986  mov     [rbp+70h+var_40], rax
0x14003a98a  mov     r12, rdx
0x14003a98d  mov     r15, rcx
0x14003a990  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003a995  mov     rcx, [rax+8]
0x14003a999  mov     eax, [rcx]
0x14003a99b  cmp     eax, 4
0x14003a99e  jbe     short loc_14003A9CF
0x14003a9a0  lea     rax, aCmidisessiontr; "CMidiSessionTracker::GetSessionList"
0x14003a9a7  mov     [rsp+170h+var_140], r15
0x14003a9ac  mov     [rbp+70h+var_D8], rax
0x14003a9b0  lea     rdx, word_14008AD76
0x14003a9b7  lea     rax, [rsp+170h+var_140]
0x14003a9bc  mov     [rsp+170h+var_148], rax
0x14003a9c1  lea     rax, [rbp+70h+var_D8]
0x14003a9c5  mov     [rsp+170h+var_150], rax
0x14003a9ca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x14003a9cf  lea     r14, [r15+30h]
0x14003a9d3  mov     rcx, r14; lpCriticalSection
0x14003a9d6  call    cs:__imp_EnterCriticalSection
0x14003a9dc  lea     rcx, [rbp+70h+var_F0]; this
0x14003a9e0  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x14003a9e5  lock inc cs:qword_140096A58
0x14003a9ed  xor     r13d, r13d
0x14003a9f0  lea     rdi, ?_lambda_invoker_cdecl_@_lambda_23__@?0???0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@56@@Z; `winrt::Windows::Data::Json::JsonArray::JsonArray(void)'::`1'::_lambda_23__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x14003a9f7  cmp     cs:??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, r13; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x14003a9fe  lea     rdx, [rsp+170h+var_100]
0x14003aa03  jz      short loc_14003AA1B
0x14003aa05  lea     r8, ??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x14003aa0c  call    ??R_lambda_23__@?0???0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Data::Json::JsonArray::JsonArray(void)'::`1'::_lambda_23__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x14003aa11  lock dec cs:qword_140096A58
0x14003aa19  jmp     short loc_14003AA32
0x14003aa1b  lock dec cs:qword_140096A58
0x14003aa23  lea     r8, [rsp+170h+var_140]
0x14003aa28  mov     [rsp+170h+var_140], rdi
0x14003aa2d  call    ??$call@P6A?AUJsonArray@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonArray@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x14003aa32  mov     rsi, [r15+18h]
0x14003aa36  cmp     rsi, [r15+20h]
0x14003aa3a  jz      loc_14003B0CF
0x14003aa40  lea     rcx, [rsp+170h+var_138]; this
0x14003aa45  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x14003aa4a  xorps   xmm0, xmm0
0x14003aa4d  lea     rdx, aId; "id"
0x14003aa54  xorps   xmm1, xmm1
0x14003aa57  lea     rcx, [rbp+70h+var_90]
0x14003aa5b  mov     r8d, 2
0x14003aa61  movups  [rbp+70h+var_90], xmm0
0x14003aa65  movdqu  [rbp+70h+var_80], xmm1
0x14003aa6a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003aa6f  mov     r8, rsi
0x14003aa72  lea     rdx, [rbp+70h+var_90]
0x14003aa76  lea     rcx, [rsp+170h+var_138]
0x14003aa7b  call    ?JsonSetGuidProperty@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; WindowsMidiServicesInternal::JsonSetGuidProperty(winrt::Windows::Data::Json::JsonObject const &,std::wstring const &,_GUID const &)
0x14003aa80  lea     rcx, [rbp+70h+var_90]; void *
0x14003aa84  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003aa89  cmp     qword ptr [rsi+60h], 7
0x14003aa8e  lea     rcx, [rsi+48h]
0x14003aa92  mov     rdx, [rsi+58h]
0x14003aa96  jbe     short loc_14003AA9B
0x14003aa98  mov     rcx, [rcx]
0x14003aa9b  test    edx, edx
0x14003aa9d  jnz     short loc_14003AAA6
0x14003aa9f  mov     [rsp+170h+var_120], r13
0x14003aaa4  jmp     short loc_14003AACE
0x14003aaa6  mov     eax, edx
0x14003aaa8  cmp     [rcx+rax*2], r13w
0x14003aaad  jnz     loc_14003B0C8
0x14003aab3  lea     rax, [rsp+170h+var_118]
0x14003aab8  mov     dword ptr [rsp+170h+var_118], 1
0x14003aac0  mov     [rsp+170h+var_120], rax
0x14003aac5  mov     dword ptr [rsp+170h+var_118+4], edx
0x14003aac9  mov     [rsp+170h+var_108], rcx
0x14003aace  lea     rdx, [rsp+170h+var_120]
0x14003aad3  lea     rcx, [rbp+70h+var_B0]; struct winrt::param::hstring *
0x14003aad7  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003aadc  lea     rcx, aName; "name"
0x14003aae3  mov     [rbp+70h+var_C8], 1
0x14003aaea  mov     [rbp+70h+var_B8], rcx
0x14003aaee  lea     rdx, [rbp+70h+var_D0]
0x14003aaf2  lea     rcx, [rbp+70h+var_C8]
0x14003aaf6  mov     [rbp+70h+var_C4], 4
0x14003aafd  mov     [rbp+70h+var_D0], rcx
0x14003ab01  mov     r8, rax
0x14003ab04  lea     rcx, [rsp+170h+var_138]
0x14003ab09  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003ab0e  cmp     [rbp+70h+var_B0], r13
0x14003ab12  jz      short loc_14003AB1D
0x14003ab14  lea     rcx, [rbp+70h+var_B0]
0x14003ab18  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003ab1d  cmp     qword ptr [rsi+40h], 7
0x14003ab22  lea     rcx, [rsi+28h]
0x14003ab26  mov     rdx, [rsi+38h]
0x14003ab2a  jbe     short loc_14003AB2F
0x14003ab2c  mov     rcx, [rcx]
0x14003ab2f  test    edx, edx
0x14003ab31  jnz     short loc_14003AB3A
0x14003ab33  mov     [rsp+170h+var_120], r13
0x14003ab38  jmp     short loc_14003AB62
0x14003ab3a  mov     eax, edx
0x14003ab3c  cmp     [rcx+rax*2], r13w
0x14003ab41  jnz     loc_14003B0C1
0x14003ab47  lea     rax, [rsp+170h+var_118]
0x14003ab4c  mov     dword ptr [rsp+170h+var_118], 1
0x14003ab54  mov     [rsp+170h+var_120], rax
0x14003ab59  mov     dword ptr [rsp+170h+var_118+4], edx
0x14003ab5d  mov     [rsp+170h+var_108], rcx
0x14003ab62  lea     rdx, [rsp+170h+var_120]
0x14003ab67  lea     rcx, [rbp+70h+var_A8]; struct winrt::param::hstring *
0x14003ab6b  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003ab70  lea     rcx, aProcessname; "processName"
0x14003ab77  mov     [rbp+70h+var_C8], 1
0x14003ab7e  mov     [rbp+70h+var_B8], rcx
0x14003ab82  lea     rdx, [rbp+70h+var_D0]
0x14003ab86  lea     rcx, [rbp+70h+var_C8]
0x14003ab8a  mov     [rbp+70h+var_C4], 0Bh
0x14003ab91  mov     [rbp+70h+var_D0], rcx
0x14003ab95  mov     r8, rax
0x14003ab98  lea     rcx, [rsp+170h+var_138]
0x14003ab9d  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003aba2  cmp     [rbp+70h+var_A8], r13
0x14003aba6  jz      short loc_14003ABB1
0x14003aba8  lea     rcx, [rbp+70h+var_A8]
0x14003abac  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003abb1  mov     r8d, [rsi+10h]
0x14003abb5  lea     r9, [rbp+70h+var_46]
0x14003abb9  sub     r9, 2
0x14003abbd  mov     eax, 0CCCCCCCDh
0x14003abc2  mul     r8d
0x14003abc5  shr     edx, 3
0x14003abc8  movzx   eax, dx
0x14003abcb  shl     ax, 2
0x14003abcf  lea     ecx, [rax+rdx]
0x14003abd2  add     cx, cx
0x14003abd5  sub     r8w, cx
0x14003abd9  add     r8w, 30h ; '0'
0x14003abde  mov     [r9], r8w
0x14003abe2  mov     r8d, edx
0x14003abe5  test    edx, edx
0x14003abe7  jnz     short loc_14003ABB9
0x14003abe9  lea     r8, [rbp+70h+var_46]
0x14003abed  mov     rdx, r9
0x14003abf0  lea     rcx, [rbp+70h+var_90]
0x14003abf4  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x14003abf9  cmp     qword ptr [rbp+70h+var_80+8], 7
0x14003abfe  lea     rcx, [rbp+70h+var_90]
0x14003ac02  mov     rdx, qword ptr [rbp+70h+var_80]
0x14003ac06  cmova   rcx, qword ptr [rbp+70h+var_90]
0x14003ac0b  test    edx, edx
0x14003ac0d  jnz     short loc_14003AC16
0x14003ac0f  mov     [rsp+170h+var_120], r13
0x14003ac14  jmp     short loc_14003AC3E
0x14003ac16  mov     eax, edx
0x14003ac18  cmp     [rcx+rax*2], r13w
0x14003ac1d  jnz     loc_14003B0BA
0x14003ac23  lea     rax, [rsp+170h+var_118]
0x14003ac28  mov     dword ptr [rsp+170h+var_118], 1
0x14003ac30  mov     [rsp+170h+var_120], rax
0x14003ac35  mov     dword ptr [rsp+170h+var_118+4], edx
0x14003ac39  mov     [rsp+170h+var_108], rcx
0x14003ac3e  lea     rdx, [rsp+170h+var_120]
0x14003ac43  lea     rcx, [rbp+70h+var_A0]; struct winrt::param::hstring *
0x14003ac47  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003ac4c  lea     rcx, aClientprocessi; "clientProcessId"
0x14003ac53  mov     [rbp+70h+var_C8], 1
0x14003ac5a  mov     [rbp+70h+var_B8], rcx
0x14003ac5e  lea     rdx, [rbp+70h+var_D0]
0x14003ac62  lea     rcx, [rbp+70h+var_C8]
0x14003ac66  mov     [rbp+70h+var_C4], 0Fh
0x14003ac6d  mov     [rbp+70h+var_D0], rcx
0x14003ac71  mov     r8, rax
0x14003ac74  lea     rcx, [rsp+170h+var_138]
0x14003ac79  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003ac7e  cmp     [rbp+70h+var_A0], r13
0x14003ac82  jz      short loc_14003AC8D
0x14003ac84  lea     rcx, [rbp+70h+var_A0]
0x14003ac88  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003ac8d  lea     rcx, [rbp+70h+var_90]; void *
0x14003ac91  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003ac96  mov     rbx, [rsi+20h]
0x14003ac9a  lea     rdx, aStarttime; "startTime"
0x14003aca1  xorps   xmm0, xmm0
0x14003aca4  lea     rcx, [rbp+70h+var_90]
0x14003aca8  xorps   xmm1, xmm1
0x14003acab  mov     r8d, 9
0x14003acb1  movups  [rbp+70h+var_90], xmm0
0x14003acb5  movdqu  [rbp+70h+var_80], xmm1
0x14003acba  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003acbf  mov     r8, rbx
0x14003acc2  lea     rdx, [rbp+70h+var_90]
0x14003acc6  lea     rcx, [rsp+170h+var_138]
0x14003accb  call    ?JsonSetDateTimeProperty@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@8@@Z; WindowsMidiServicesInternal::JsonSetDateTimeProperty(winrt::Windows::Data::Json::JsonObject const &,std::wstring const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>)
0x14003acd0  lea     rcx, [rbp+70h+var_90]; void *
0x14003acd4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003acd9  lock inc cs:qword_140096A58
0x14003ace1  cmp     cs:??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, r13; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x14003ace8  lea     rdx, [rsp+170h+var_F8]
0x14003aced  jz      short loc_14003AD05
0x14003acef  lea     r8, ??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x14003acf6  call    ??R_lambda_23__@?0???0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Data::Json::JsonArray::JsonArray(void)'::`1'::_lambda_23__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x14003acfb  lock dec cs:qword_140096A58
0x14003ad03  jmp     short loc_14003AD1C
0x14003ad05  lock dec cs:qword_140096A58
0x14003ad0d  lea     r8, [rsp+170h+var_140]
0x14003ad12  mov     [rsp+170h+var_140], rdi
0x14003ad17  call    ??$call@P6A?AUJsonArray@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonArray@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x14003ad1c  mov     rdi, [rsi+68h]
0x14003ad20  mov     rdi, [rdi]
0x14003ad23  cmp     rdi, [rsi+68h]
0x14003ad27  jz      loc_14003AF10
0x14003ad2d  lea     rcx, [rbp+70h+var_E8]; this
0x14003ad31  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x14003ad36  mov     rbx, [rdi+60h]
0x14003ad3a  lea     rdx, aEarlieststartt; "earliestStartTime"
0x14003ad41  xorps   xmm0, xmm0
0x14003ad44  lea     rcx, [rbp+70h+var_90]
0x14003ad48  xorps   xmm1, xmm1
0x14003ad4b  mov     r8d, 11h
0x14003ad51  movups  [rbp+70h+var_90], xmm0
0x14003ad55  movdqu  [rbp+70h+var_80], xmm1
0x14003ad5a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003ad5f  mov     r8, rbx
0x14003ad62  lea     rdx, [rbp+70h+var_90]
0x14003ad66  lea     rcx, [rsp+170h+var_138]
0x14003ad6b  call    ?JsonSetDateTimeProperty@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@8@@Z; WindowsMidiServicesInternal::JsonSetDateTimeProperty(winrt::Windows::Data::Json::JsonObject const &,std::wstring const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>)
0x14003ad70  lea     rcx, [rbp+70h+var_90]; void *
0x14003ad74  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003ad79  movzx   eax, word ptr [rdi+68h]
0x14003ad7d  lea     rcx, [rbp+70h+var_98]
0x14003ad81  movd    xmm1, eax
0x14003ad85  cvtdq2pd xmm1, xmm1
0x14003ad89  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x14003ad8e  lea     rcx, aInstancecount; "instanceCount"
0x14003ad95  mov     dword ptr [rbp+70h+var_90+8], 1
0x14003ad9c  mov     qword ptr [rbp+70h+var_80+8], rcx
0x14003ada0  lea     rdx, [rbp+70h+var_90]
0x14003ada4  lea     rcx, [rbp+70h+var_90+8]
0x14003ada8  mov     dword ptr [rbp+70h+var_90+0Ch], 0Dh
0x14003adaf  mov     qword ptr [rbp+70h+var_90], rcx
0x14003adb3  mov     r8, rax
0x14003adb6  lea     rcx, [rbp+70h+var_E8]
0x14003adba  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003adbf  cmp     [rbp+70h+var_98], r13
0x14003adc3  jz      short loc_14003ADCE
0x14003adc5  lea     rcx, [rbp+70h+var_98]
0x14003adc9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003adce  cmp     qword ptr [rdi+58h], 7
0x14003add3  lea     rcx, [rdi+40h]
0x14003add7  mov     rdx, [rdi+50h]
0x14003addb  jbe     short loc_14003ADE0
0x14003addd  mov     rcx, [rcx]
0x14003ade0  test    edx, edx
0x14003ade2  jnz     short loc_14003ADEB
0x14003ade4  mov     [rsp+170h+var_120], r13
0x14003ade9  jmp     short loc_14003AE13
0x14003adeb  mov     eax, edx
0x14003aded  cmp     [rcx+rax*2], r13w
0x14003adf2  jnz     loc_14003B0B3
0x14003adf8  lea     rax, [rsp+170h+var_118]
0x14003adfd  mov     dword ptr [rsp+170h+var_118], 1
0x14003ae05  mov     [rsp+170h+var_120], rax
0x14003ae0a  mov     dword ptr [rsp+170h+var_118+4], edx
0x14003ae0e  mov     [rsp+170h+var_108], rcx
0x14003ae13  lea     rdx, [rsp+170h+var_120]
0x14003ae18  lea     rcx, [rbp+70h+var_D8]; struct winrt::param::hstring *
0x14003ae1c  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003ae21  lea     rcx, aEndpointid; "endpointId"
0x14003ae28  mov     dword ptr [rbp+70h+var_90+8], 1
0x14003ae2f  mov     qword ptr [rbp+70h+var_80+8], rcx
0x14003ae33  lea     rdx, [rbp+70h+var_90]
0x14003ae37  lea     rcx, [rbp+70h+var_90+8]
0x14003ae3b  mov     dword ptr [rbp+70h+var_90+0Ch], 0Ah
0x14003ae42  mov     qword ptr [rbp+70h+var_90], rcx
0x14003ae46  mov     r8, rax
0x14003ae49  lea     rcx, [rbp+70h+var_E8]
0x14003ae4d  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003ae52  cmp     [rbp+70h+var_D8], r13
0x14003ae56  jz      short loc_14003AE61
0x14003ae58  lea     rcx, [rbp+70h+var_D8]
0x14003ae5c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003ae61  mov     rcx, [rbp+70h+var_E8]
0x14003ae65  test    rcx, rcx
0x14003ae68  jnz     short loc_14003AE70
0x14003ae6a  mov     [rbp+70h+var_E0], r13
0x14003ae6e  jmp     short loc_14003AE95
0x14003ae70  mov     rax, [rcx]
0x14003ae73  lea     r8, [rsp+170h+var_130]
0x14003ae78  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x14003ae7f  mov     [rsp+170h+var_130], r13
  ... truncated ...
```
