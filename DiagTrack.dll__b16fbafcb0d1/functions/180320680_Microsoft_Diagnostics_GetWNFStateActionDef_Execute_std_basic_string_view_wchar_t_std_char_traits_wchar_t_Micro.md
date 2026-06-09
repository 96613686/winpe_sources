# Microsoft::Diagnostics::GetWNFStateActionDef::Execute(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState &,Microsoft::Diagnostics::ScenarioInst const &)

- ea: `0x180320680`
- end: `0x18032114b`
- name: `?Execute@GetWNFStateActionDef@Diagnostics@Microsoft@@UEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVEscalationWorkItemState@23@AEBVScenarioInst@23@@Z`
- size: `2763`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x18001a644`
- `0x18001a8f0`
- `0x18001b010`
- `0x18001b24c`
- `0x18001b434`
- `0x18001b510`
- `0x18001b52c`
- `0x180020150`
- `0x180022570`
- `0x180027c28`
- `0x180027e50`
- `0x18002ac10`
- `0x18002b7c0`
- `0x18002df00`
- `0x18003119c`
- `0x180064e6c`
- `0x180064e8c`
- `0x18009c8c0`
- `0x1800a8ed4`
- `0x1800c4b14`
- `0x1800df5d0`
- `0x1800f7b34`
- `0x180102bbc`
- `0x180105ad8`
- `0x18010e55c`
- `0x18010f9b8`
- `0x18011bccc`
- `0x18011d2bc`
- `0x180135800`
- `0x180142fcc`
- `0x18016323c`
- `0x1801dc068`
- `0x18020aac0`
- `0x180312c78`
- `0x180313400`
- `0x180320680`
- `0x180321154`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x180320900`
- `ntdll!NtQueryWnfStateData` at `0x180320a21`
- `ntdll!NtQueryWnfStateData` at `0x180320900`
- `ntdll!NtQueryWnfStateData` at `0x180320a21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803207f6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18032083f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18032083f`

## string_xrefs

- `0x1803206ee`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180320851`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x1803209a7`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180320a8e`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180320cec`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180320feb`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180321095`: `XML written to file: `

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetWNFStateActionDef::Execute(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r8
  __int16 v8; // ax
  int *v9; // rsi
  const WCHAR *v10; // rcx
  const char *v11; // r9
  unsigned int LastError; // ebx
  void *v13; // rbx
  __int64 v14; // r12
  int WnfStateData; // r15d
  __int64 v16; // rax
  const struct std::nothrow_t *v17; // rdx
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // ebx
  const struct std::nothrow_t *v21; // rdx
  int v22; // r15d
  int v23; // r8d
  int v24; // r9d
  unsigned int v25; // ebx
  const struct std::nothrow_t *v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  __int64 v28; // r13
  _DWORD *v29; // rbx
  unsigned int v30; // r15d
  const wchar_t *v31; // r14
  int SizeFromTdhType; // eax
  unsigned int v33; // r12d
  const struct std::nothrow_t *v34; // rdx
  __m128i *v35; // rax
  wil *v36; // rcx
  const struct std::nothrow_t *v37; // rdx
  int appended; // eax
  __int64 v39; // r8
  unsigned int v40; // ebx
  __int64 v41; // rax
  __int64 v42; // r8
  int v43; // eax
  int v44; // [rsp+20h] [rbp-1E8h]
  int v45; // [rsp+20h] [rbp-1E8h]
  int v46; // [rsp+20h] [rbp-1E8h]
  int v47; // [rsp+20h] [rbp-1E8h]
  int v48; // [rsp+20h] [rbp-1E8h]
  int v49; // [rsp+30h] [rbp-1D8h] BYREF
  unsigned int v50; // [rsp+34h] [rbp-1D4h] BYREF
  int v51; // [rsp+38h] [rbp-1D0h] BYREF
  PSID Sid; // [rsp+40h] [rbp-1C8h] BYREF
  void *v53; // [rsp+48h] [rbp-1C0h] BYREF
  _DWORD v54[4]; // [rsp+50h] [rbp-1B8h] BYREF
  __m128i v55; // [rsp+60h] [rbp-1A8h] BYREF
  _DWORD *v56; // [rsp+70h] [rbp-198h] BYREF
  int v57; // [rsp+78h] [rbp-190h] BYREF
  const wchar_t *v58; // [rsp+80h] [rbp-188h] BYREF
  __int64 v59; // [rsp+88h] [rbp-180h]
  __m128i v60; // [rsp+90h] [rbp-178h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-168h]
  _BYTE v62[16]; // [rsp+A8h] [rbp-160h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-150h]
  __int64 v64; // [rsp+C0h] [rbp-148h]
  __int64 v65; // [rsp+C8h] [rbp-140h]
  __int64 v66; // [rsp+D0h] [rbp-138h]
  _BYTE v67[80]; // [rsp+E0h] [rbp-128h] BYREF
  __m128i v68; // [rsp+130h] [rbp-D8h] BYREF
  LPCWSTR StringSid[4]; // [rsp+150h] [rbp-B8h] BYREF
  _BYTE v70[32]; // [rsp+170h] [rbp-98h] BYREF
  _BYTE v71[48]; // [rsp+190h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v61 = a3;
  v64 = a2;
  v65 = a2;
  v66 = a3;
  v63 = a3;
  if ( !*(_QWORD *)(a2 + 8) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
      (const char *)0x8007010BLL,
      v45);
    return 2147942667LL;
  }
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)v71);
  Microsoft::Diagnostics::XmlWriterFacade::XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v67);
  v68.m128i_i64[0] = (__int64)L"result";
  v68.m128i_i64[1] = 6;
  Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v67, v62, &v68);
  Sid = 0;
  v57 = 0;
  v68 = *(__m128i *)std::wstring::operator std::wstring_view(a1 + 192, &v55, v7);
  Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a4, StringSid, &v68);
  v8 = *(_WORD *)(a1 + 224);
  if ( v8 == 1 )
  {
    v57 = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(StringSid);
    v9 = &v57;
  }
  else
  {
    v9 = 0;
    if ( v8 == 2 )
    {
      Sid = 0;
      v10 = (const WCHAR *)StringSid;
      if ( StringSid[3] > (LPCWSTR)7 )
        v10 = StringSid[0];
      if ( !ConvertStringSidToSidW(v10, &Sid) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x3C,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
                      v11);
        std::wstring::_Tidy_deallocate(StringSid);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
        Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v62);
        Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v67);
        std::wstring::_Tidy_deallocate(v71);
        return LastError;
      }
      v9 = (int *)Sid;
    }
  }
  std::wstring::_Tidy_deallocate(StringSid);
  v50 = 0;
  v54[0] = 0;
  v13 = 0;
  v53 = 0;
  v14 = (a1 + 168) & -(__int64)(*(_BYTE *)(a1 + 184) != 0);
  v46 = 0;
  WnfStateData = NtQueryWnfStateData(a1 + 160, v14, v9, v54);
  if ( WnfStateData == -1073741789 )
  {
    v16 = std::make_unique<unsigned char [0],0>(&v56, v50);
    std::unique_ptr<enum gsl::byte [0]>::operator=<std::default_delete<enum gsl::byte [0]>,0>(&v53, v16);
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&v56, v17);
    v13 = v53;
  }
  else if ( WnfStateData < 0 )
  {
    if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
    {
      v51 = 1;
      v49 = WnfStateData;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)&dword_180403084,
        v18,
        v19,
        (__int64)&v49,
        (__int64)&v51);
    }
    v20 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x5A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
            (const char *)(unsigned int)WnfStateData,
            v46);
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v53, v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v62);
    Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v67);
    std::wstring::_Tidy_deallocate(v71);
    return v20;
  }
  v47 = (int)v13;
  v22 = NtQueryWnfStateData(a1 + 160, v14, v9, v54);
  if ( v22 >= 0 )
  {
    gsl::span<enum gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
      &v60,
      v13,
      v50);
    v68.m128i_i64[0] = (__int64)L"changestamp";
    v68.m128i_i64[1] = 11;
    v58 = L"info";
    v59 = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
      (unsigned int)v67,
      (unsigned int)&v58,
      (unsigned int)&v68,
      (unsigned int)v54,
      0);
    v68.m128i_i64[0] = (__int64)L"wnfmessagesize";
    v68.m128i_i64[1] = 14;
    v58 = L"info";
    v59 = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
      (unsigned int)v67,
      (unsigned int)&v58,
      (unsigned int)&v68,
      (unsigned int)&v50,
      0);
    if ( *(_BYTE *)(a1 + 128) )
    {
      v68 = v60;
      Microsoft::Diagnostics::Utils::String::ConvertBufferToHexString(StringSid, &v68);
      v68.m128i_i64[0] = (__int64)L"wnfhex";
      v68.m128i_i64[1] = 6;
      v60.m128i_i64[0] = (__int64)L"info";
      v60.m128i_i64[1] = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(v67, &v60, &v68);
      std::wstring::_Tidy_deallocate(StringSid);
      v28 = v61;
    }
    else
    {
      v29 = *(_DWORD **)(a1 + 136);
      v56 = v29;
      v30 = 0;
      v51 = 0;
      v58 = L"wnfstructure";
      v59 = 12;
      Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v67, &v68, &v58);
      v31 = (const wchar_t *)(a1 + 144);
      while ( v30 < v60.m128i_i32[0] )
      {
        v31 = (const wchar_t *)(a1 + 144);
        v58 = (const wchar_t *)(a1 + 144);
        if ( v29 == *(_DWORD **)(a1 + 144) )
          break;
        v49 = 0;
        v55 = 0;
        SizeFromTdhType = Microsoft::Diagnostics::Utils::Xml::GetSizeFromTdhType((unsigned int)*v29, &v55, &v49);
        v33 = SizeFromTdhType;
        if ( SizeFromTdhType < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
            (const char *)(unsigned int)SizeFromTdhType,
            v48);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v68);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v53, v34);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v62);
          Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v67);
          std::wstring::_Tidy_deallocate(v71);
          return v33;
        }
        v35 = (__m128i *)gsl::span<enum gsl::byte const,-1>::subspan(&v60, StringSid, v30);
        try
        {
          v55 = *v35;
          Microsoft::Diagnostics::XmlWriterFacade::WriteTdhBufferToXml(
            (__int64)v67,
            *v29,
            (unsigned int)v49,
            (__int64)&v55);
          v30 += v49;
          v51 = v30;
          v56 = ++v29;
        }
        catch ( ... )
        {
          v43 = wil::ResultFromCaughtException(v36);
          v49 = v43;
          if ( v43 == -2147024785 )
          {
            v31 = v58;
            v29 = v56;
            v30 = v51;
            v64 = v65;
            v28 = v66;
            goto LABEL_32;
          }
          if ( v43 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
              (const char *)(unsigned int)v43,
              v44);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v68);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v53, v37);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v62);
          Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v67);
          std::wstring::_Tidy_deallocate(v71);
          return (unsigned int)v49;
        }
      }
      v28 = v61;
LABEL_32:
      Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v68);
      if ( v29 != *(_DWORD **)v31 )
        goto LABEL_38;
      if ( v30 >= v50 )
        goto LABEL_42;
      if ( v29 == *(_DWORD **)v31 )
      {
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v63 + 168));
        if ( (unsigned int)dword_1804543B0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1804543B0,
            &dword_180403054);
      }
      else
      {
LABEL_38:
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v63 + 168));
        if ( (unsigned int)dword_1804543B0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1804543B0,
            &word_180403026);
      }
      v55 = v60;
      Microsoft::Diagnostics::Utils::String::ConvertBufferToHexString(StringSid, &v55);
      v68.m128i_i64[0] = (__int64)L"wnfhex";
      v68.m128i_i64[1] = 6;
      v60.m128i_i64[0] = (__int64)L"info";
      v60.m128i_i64[1] = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(v67, &v60, &v68);
      std::wstring::_Tidy_deallocate(StringSid);
    }
LABEL_42:
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v53, v27);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v62);
    std::wstring::wstring(v70, v64);
    v55 = *(__m128i *)&Microsoft::Diagnostics::GetWNFStateActionDef::k_wnfInfoOutputFileName;
    appended = Microsoft::Diagnostics::Utils::String::AppendPath(v70, &v55);
    v40 = appended;
    if ( appended >= 0 )
    {
      v55 = *(__m128i *)std::wstring::operator std::wstring_view(v70, StringSid, v39);
      Microsoft::Diagnostics::XmlWriterFacade::WriteToFile((__int64)v67, &v55);
      v55 = *(__m128i *)std::wstring::operator std::wstring_view(v70, StringSid, 5);
      Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(v28, &v55);
      Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v28 + 168));
      v41 = std::operator+<wchar_t>(&v68, v70, L"\r\n");
      v55 = *(__m128i *)std::wstring::operator std::wstring_view(v41, StringSid, v42);
      Microsoft::Diagnostics::WideStringStream::AppendString((void *)(v28 + 168));
      std::wstring::_Tidy_deallocate(&v68);
      std::wstring::_Tidy_deallocate(v70);
      Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v67);
      std::wstring::_Tidy_deallocate(v71);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
        (const char *)(unsigned int)appended,
        v48);
      std::wstring::_Tidy_deallocate(v70);
      Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v67);
      std::wstring::_Tidy_deallocate(v71);
      return v40;
    }
  }
  else
  {
    if ( (unsigned int)dword_1804543B0 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
      {
        v51 = 2;
        v49 = v22;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1804543B0,
          (unsigned int)byte_1804030CD,
          v23,
          v24,
          (__int64)&v49,
          (__int64)&v51);
      }
    }
    v25 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x67,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
            (const char *)(unsigned int)v22,
            v47);
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v53, v26);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v62);
    Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v67);
    std::wstring::_Tidy_deallocate(v71);
    return v25;
  }
}

```

## disassembly

```asm
0x180320680  push    rbx
0x180320682  push    rsi
0x180320683  push    rdi
0x180320684  push    r12
0x180320686  push    r13
0x180320688  push    r14
0x18032068a  push    r15
0x18032068c  sub     rsp, 1D0h
0x180320693  mov     rax, cs:__security_cookie
0x18032069a  xor     rax, rsp
0x18032069d  mov     [rsp+208h+var_48], rax
0x1803206a5  mov     rbx, r9
0x1803206a8  mov     rax, r8
0x1803206ab  mov     [rsp+208h+var_168], rax
0x1803206b3  mov     [rsp+208h+var_148], rdx
0x1803206bb  mov     r13, rcx
0x1803206be  mov     [rsp+208h+var_140], rdx
0x1803206c6  mov     [rsp+208h+var_138], rax
0x1803206ce  mov     [rsp+208h+var_150], rax
0x1803206d6  xor     edi, edi
0x1803206d8  cmp     [rdx+8], rdi
0x1803206dc  jnz     short loc_180320704
0x1803206de  mov     rcx, [rsp+208h]; this
0x1803206e6  mov     ebx, 8007010Bh
0x1803206eb  mov     r9d, ebx; char *
0x1803206ee  lea     r8, aOnecoreBaseTel_152; "onecore\\base\\telemetry\\utc\\service"...
0x1803206f5  lea     edx, [rdi+22h]; void *
0x1803206f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803206fd  mov     eax, ebx
0x1803206ff  jmp     loc_180321127
0x180320704  lea     rcx, [rsp+208h+var_78]; this
0x18032070c  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x180320711  nop
0x180320712  lea     rcx, [rsp+208h+var_128]; this
0x18032071a  call    ??0XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::XmlWriterFacade(void)
0x18032071f  nop
0x180320720  lea     rax, aResult_0; "result"
0x180320727  mov     qword ptr [rsp+208h+var_D8], rax
0x18032072f  mov     qword ptr [rsp+208h+var_D8+8], 6
0x18032073b  lea     r8, [rsp+208h+var_D8]
0x180320743  lea     rdx, [rsp+208h+var_160]
0x18032074b  lea     rcx, [rsp+208h+var_128]
0x180320753  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x180320758  nop
0x180320759  mov     [rsp+208h+Sid], rdi
0x18032075e  mov     [rsp+208h+var_190], edi
0x180320762  lea     rcx, [r13+0C0h]
0x180320769  lea     rdx, [rsp+208h+var_1A8]
0x18032076e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180320773  movups  xmm0, xmmword ptr [rax]
0x180320776  movdqu  [rsp+208h+var_D8], xmm0
0x18032077f  lea     r8, [rsp+208h+var_D8]
0x180320787  lea     rdx, [rsp+208h+StringSid]
0x18032078f  mov     rcx, rbx
0x180320792  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x180320797  movzx   eax, word ptr [r13+0E0h]
0x18032079f  mov     ecx, 1
0x1803207a4  cmp     ax, cx
0x1803207a7  jnz     short loc_1803207CA
0x1803207a9  lea     rcx, [rsp+208h+StringSid]
0x1803207b1  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x1803207b6  mov     [rsp+208h+var_190], eax
0x1803207ba  lea     rsi, [rsp+208h+var_190]
0x1803207bf  mov     r14d, 2
0x1803207c5  jmp     loc_1803208B0
0x1803207ca  mov     rsi, rdi
0x1803207cd  mov     r14d, 2
0x1803207d3  cmp     ax, r14w
0x1803207d7  jnz     loc_1803208B0
0x1803207dd  mov     rax, [rsp+208h+Sid]
0x1803207e2  test    rax, rax
0x1803207e5  jz      short loc_18032081B
0x1803207e7  mov     [rsp+208h+var_198], rax
0x1803207ec  lea     rcx, [rsp+208h+var_1D0]; this
0x1803207f1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1803207f6  mov     rax, cs:__imp_LocalFree
0x1803207fd  mov     [rsp+208h+var_1C0], rax
0x180320802  lea     rdx, [rsp+208h+var_198]
0x180320807  lea     rcx, [rsp+208h+var_1C0]
0x18032080c  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x180320811  lea     rcx, [rsp+208h+var_1D0]; this
0x180320816  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18032081b  mov     [rsp+208h+Sid], rdi
0x180320820  lea     rcx, [rsp+208h+StringSid]
0x180320828  cmp     [rsp+208h+var_A0], 7
0x180320831  cmova   rcx, [rsp+208h+StringSid]; StringSid
0x18032083a  lea     rdx, [rsp+208h+Sid]; Sid
0x18032083f  call    cs:__imp_ConvertStringSidToSidW
0x180320845  test    eax, eax
0x180320847  jnz     short loc_1803208AB
0x180320849  mov     rcx, [rsp+208h]; this
0x180320851  lea     r8, aOnecoreBaseTel_152; "onecore\\base\\telemetry\\utc\\service"...
0x180320858  lea     edx, [rax+3Ch]; void *
0x18032085b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180320860  mov     ebx, eax
0x180320862  lea     rcx, [rsp+208h+StringSid]
0x18032086a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18032086f  nop
0x180320870  lea     rcx, [rsp+208h+Sid]
0x180320875  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18032087a  nop
0x18032087b  lea     rcx, [rsp+208h+var_160]; this
0x180320883  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x180320888  nop
0x180320889  lea     rcx, [rsp+208h+var_128]; this
0x180320891  call    ??1XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade(void)
0x180320896  nop
0x180320897  lea     rcx, [rsp+208h+var_78]
0x18032089f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803208a4  mov     eax, ebx
0x1803208a6  jmp     loc_180321127
0x1803208ab  mov     rsi, [rsp+208h+Sid]
0x1803208b0  lea     rcx, [rsp+208h+StringSid]
0x1803208b8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803208bd  mov     [rsp+208h+var_1D4], edi
0x1803208c1  mov     [rsp+208h+var_1B8], edi
0x1803208c5  mov     rbx, rdi
0x1803208c8  mov     [rsp+208h+var_1C0], rbx
0x1803208cd  lea     rcx, [r13+0A8h]
0x1803208d4  mov     al, [rcx+10h]
0x1803208d7  neg     al
0x1803208d9  sbb     r12, r12
0x1803208dc  and     r12, rcx
0x1803208df  lea     rcx, [rsp+208h+var_1D4]
0x1803208e4  mov     [rsp+208h+var_1E0], rcx
0x1803208e9  mov     qword ptr [rsp+208h+var_1E8], rdi
0x1803208ee  lea     r9, [rsp+208h+var_1B8]
0x1803208f3  mov     r8, rsi
0x1803208f6  mov     rdx, r12
0x1803208f9  lea     rcx, [r13+0A0h]
0x180320900  call    cs:__imp_NtQueryWnfStateData
0x180320906  mov     r15d, eax
0x180320909  cmp     eax, 0C0000023h
0x18032090e  jnz     short loc_18032093F
0x180320910  mov     edx, [rsp+208h+var_1D4]
0x180320914  lea     rcx, [rsp+208h+var_198]
0x180320919  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18032091e  mov     rdx, rax
0x180320921  lea     rcx, [rsp+208h+var_1C0]
0x180320926  call    ??$?4U?$default_delete@$$BY0A@W4byte@gsl@@@std@@$0A@@?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<gsl::byte [0]>::operator=<std::default_delete<gsl::byte [0]>,0>(std::unique_ptr<gsl::byte [0]> &&)
0x18032092b  lea     rcx, [rsp+208h+var_198]
0x180320930  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180320935  mov     rbx, [rsp+208h+var_1C0]
0x18032093a  jmp     loc_180320A00
0x18032093f  test    r15d, r15d
0x180320942  jns     loc_180320A00
0x180320948  mov     eax, cs:dword_1804543B0
0x18032094e  cmp     eax, r14d
0x180320951  jbe     short loc_18032099C
0x180320953  mov     edx, 4
0x180320958  lea     rcx, dword_1804543B0
0x18032095f  call    _tlgKeywordOn
0x180320964  test    al, al
0x180320966  jz      short loc_18032099C
0x180320968  mov     [rsp+208h+var_1D0], 1
0x180320970  mov     [rsp+208h+var_1D8], r15d
0x180320975  lea     rax, [rsp+208h+var_1D0]
0x18032097a  mov     [rsp+208h+var_1E0], rax
0x18032097f  lea     rax, [rsp+208h+var_1D8]
0x180320984  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x180320989  lea     rdx, dword_180403084
0x180320990  lea     rcx, dword_1804543B0
0x180320997  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18032099c  mov     rcx, [rsp+208h]; this
0x1803209a4  mov     r9d, r15d; char *
0x1803209a7  lea     r8, aOnecoreBaseTel_152; "onecore\\base\\telemetry\\utc\\service"...
0x1803209ae  mov     edx, 5Ah ; 'Z'; void *
0x1803209b3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1803209b8  mov     ebx, eax
0x1803209ba  lea     rcx, [rsp+208h+var_1C0]
0x1803209bf  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1803209c4  nop
0x1803209c5  lea     rcx, [rsp+208h+Sid]
0x1803209ca  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1803209cf  nop
0x1803209d0  lea     rcx, [rsp+208h+var_160]; this
0x1803209d8  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x1803209dd  nop
0x1803209de  lea     rcx, [rsp+208h+var_128]; this
0x1803209e6  call    ??1XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade(void)
0x1803209eb  nop
0x1803209ec  lea     rcx, [rsp+208h+var_78]
0x1803209f4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803209f9  mov     eax, ebx
0x1803209fb  jmp     loc_180321127
0x180320a00  lea     rax, [rsp+208h+var_1D4]
0x180320a05  mov     [rsp+208h+var_1E0], rax
0x180320a0a  mov     qword ptr [rsp+208h+var_1E8], rbx
0x180320a0f  lea     r9, [rsp+208h+var_1B8]
0x180320a14  mov     r8, rsi
0x180320a17  mov     rdx, r12
0x180320a1a  lea     rcx, [r13+0A0h]
0x180320a21  call    cs:__imp_NtQueryWnfStateData
0x180320a27  mov     r15d, eax
0x180320a2a  test    eax, eax
0x180320a2c  jns     loc_180320AE7
0x180320a32  mov     ecx, cs:dword_1804543B0
0x180320a38  cmp     ecx, r14d
0x180320a3b  jbe     short loc_180320A83
0x180320a3d  mov     edx, 4
0x180320a42  lea     rcx, dword_1804543B0
0x180320a49  call    _tlgKeywordOn
0x180320a4e  test    al, al
0x180320a50  jz      short loc_180320A83
0x180320a52  mov     [rsp+208h+var_1D0], r14d
0x180320a57  mov     [rsp+208h+var_1D8], r15d
0x180320a5c  lea     rax, [rsp+208h+var_1D0]
0x180320a61  mov     [rsp+208h+var_1E0], rax
0x180320a66  lea     rax, [rsp+208h+var_1D8]
0x180320a6b  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x180320a70  lea     rdx, byte_1804030CD
0x180320a77  lea     rcx, dword_1804543B0
0x180320a7e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180320a83  mov     rcx, [rsp+208h]; this
0x180320a8b  mov     r9d, r15d; char *
0x180320a8e  lea     r8, aOnecoreBaseTel_152; "onecore\\base\\telemetry\\utc\\service"...
0x180320a95  mov     edx, 67h ; 'g'; void *
0x180320a9a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180320a9f  mov     ebx, eax
0x180320aa1  lea     rcx, [rsp+208h+var_1C0]
0x180320aa6  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180320aab  nop
0x180320aac  lea     rcx, [rsp+208h+Sid]
0x180320ab1  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180320ab6  nop
0x180320ab7  lea     rcx, [rsp+208h+var_160]; this
0x180320abf  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x180320ac4  nop
0x180320ac5  lea     rcx, [rsp+208h+var_128]; this
0x180320acd  call    ??1XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade(void)
0x180320ad2  nop
0x180320ad3  lea     rcx, [rsp+208h+var_78]
0x180320adb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180320ae0  mov     eax, ebx
0x180320ae2  jmp     loc_180321127
0x180320ae7  mov     r8d, [rsp+208h+var_1D4]
0x180320aec  mov     rdx, rbx
0x180320aef  lea     rcx, [rsp+208h+var_178]
0x180320af7  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEAA@PEBW4byte@2@_K@Z; gsl::span<gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(gsl::byte const *,unsigned __int64)
0x180320afc  lea     rax, aChangestamp; "changestamp"
0x180320b03  mov     qword ptr [rsp+208h+var_D8], rax
0x180320b0b  mov     qword ptr [rsp+208h+var_D8+8], 0Bh
0x180320b17  lea     r12, aInfo_0; "info"
0x180320b1e  mov     [rsp+208h+var_188], r12
0x180320b26  mov     esi, 4
0x180320b2b  mov     [rsp+208h+var_180], rsi
0x180320b33  mov     byte ptr [rsp+208h+var_1E8], dil
0x180320b38  lea     r9, [rsp+208h+var_1B8]
0x180320b3d  lea     r8, [rsp+208h+var_D8]
0x180320b45  lea     rdx, [rsp+208h+var_188]
0x180320b4d  lea     rcx, [rsp+208h+var_128]
0x180320b55  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x180320b5a  lea     rax, aWnfmessagesize; "wnfmessagesize"
0x180320b61  mov     qword ptr [rsp+208h+var_D8], rax
0x180320b69  mov     qword ptr [rsp+208h+var_D8+8], 0Eh
0x180320b75  mov     [rsp+208h+var_188], r12
0x180320b7d  mov     [rsp+208h+var_180], rsi
0x180320b85  mov     byte ptr [rsp+208h+var_1E8], dil; int
0x180320b8a  lea     r9, [rsp+208h+var_1D4]
0x180320b8f  lea     r8, [rsp+208h+var_D8]
0x180320b97  lea     rdx, [rsp+208h+var_188]
0x180320b9f  lea     rcx, [rsp+208h+var_128]
0x180320ba7  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x180320bac  lea     rdx, [rsp+208h+var_D8]
0x180320bb4  cmp     [r13+80h], dil
0x180320bbb  jz      loc_180320C4B
0x180320bc1  movaps  xmm0, [rsp+208h+var_178]
0x180320bc9  movdqa  [rsp+208h+var_D8], xmm0
0x180320bd2  lea     rcx, [rsp+208h+StringSid]
0x180320bda  call    ?ConvertBufferToHexString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; Microsoft::Diagnostics::Utils::String::ConvertBufferToHexString(gsl::span<gsl::byte const,-1>)
0x180320bdf  nop
0x180320be0  lea     rax, aWnfhex; "wnfhex"
0x180320be7  mov     qword ptr [rsp+208h+var_D8], rax
0x180320bef  mov     qword ptr [rsp+208h+var_D8+8], 6
0x180320bfb  mov     qword ptr [rsp+208h+var_178], r12
0x180320c03  mov     qword ptr [rsp+208h+var_178+8], rsi
0x180320c0b  lea     r9, [rsp+208h+StringSid]
0x180320c13  lea     r8, [rsp+208h+var_D8]
0x180320c1b  lea     rdx, [rsp+208h+var_178]
0x180320c23  lea     rcx, [rsp+208h+var_128]
0x180320c2b  call    ??$WriteInfoElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(std::wstring_view,std::wstring_view,std::wstring const &,bool)
0x180320c30  nop
0x180320c31  lea     rcx, [rsp+208h+StringSid]
0x180320c39  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180320c3e  mov     r13, [rsp+208h+var_168]
0x180320c46  jmp     loc_180320F82
0x180320c4b  mov     rbx, [r13+88h]
0x180320c52  mov     [rsp+208h+var_198], rbx
0x180320c57  mov     r15d, edi
0x180320c5a  mov     [rsp+208h+var_1D0], edi
0x180320c5e  lea     rax, aWnfstructure; "wnfstructure"
0x180320c65  mov     [rsp+208h+var_188], rax
0x180320c6d  mov     [rsp+208h+var_180], 0Ch
0x180320c79  lea     r8, [rsp+208h+var_188]
0x180320c81  lea     rcx, [rsp+208h+var_128]
0x180320c89  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x180320c8e  nop
0x180320c8f  lea     r14, [r13+90h]
0x180320c96  cmp     r15d, dword ptr [rsp+208h+var_178]
0x180320c9e  jnb     loc_180320E3E
  ... truncated ...
```
