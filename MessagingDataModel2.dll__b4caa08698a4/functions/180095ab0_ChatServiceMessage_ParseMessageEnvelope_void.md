# ChatServiceMessage::_ParseMessageEnvelope(void)

- ea: `0x180095ab0`
- end: `0x1800963f7`
- name: `?_ParseMessageEnvelope@ChatServiceMessage@@AEAAJXZ`
- size: `2375`
- prototype: `__int64 __fastcall(ChatServiceMessage *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800948d0`

## callees

- `0x180005c50`
- `0x18000b7d4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x180084864`
- `0x18009201c`
- `0x1800921dc`
- `0x180092840`
- `0x180095ab0`
- `0x1800b052c`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180095b0d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180095b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095d20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096200`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095d20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096200`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095d0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095d4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800960bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800961bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009622f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095d0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095d4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800960bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800961bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009622f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096272`

## string_xrefs

- `0x180095adb`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceMessage::_ParseMessageEnvelope(ChatServiceMessage *this)
{
  int ActivationFactory; // eax
  char v3; // r8
  int v4; // ebx
  __int64 v5; // rcx
  void (*v6)(void); // rax
  struct ChatServiceAttachment *v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  char v14; // r8
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64); // rbx
  HSTRING_HEADER *v17; // rax
  char v18; // r8
  __int64 v19; // rdi
  unsigned int v20; // ecx
  __int64 (__fastcall *v21)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v22; // rax
  char v23; // r8
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v25)(_QWORD, GUID *, __int64); // rbx
  char v26; // r8
  HSTRING_HEADER *v27; // rax
  int v28; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v30; // rcx
  void (*v31)(void); // rax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v34; // rax
  char v35; // r8
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v37)(_QWORD, GUID *, __int64); // rbx
  HSTRING_HEADER *v38; // rax
  int v39; // eax
  unsigned int i; // ebx
  int v41; // eax
  unsigned int v42; // edi
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v47; // rax
  char v48; // r8
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v50)(_QWORD, GUID *, __int64); // rbx
  HSTRING_HEADER *v51; // rax
  __int64 v52; // rdi
  __int64 (__fastcall *v53)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v54; // rax
  char v55; // r8
  __int64 (__fastcall ***v56)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v57)(_QWORD, GUID *, __int64); // rbx
  char v58; // r8
  HSTRING_HEADER *v59; // rax
  PCWSTR v60; // rax
  __int64 v61; // rdi
  __int64 (__fastcall *v62)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v63; // rax
  char v64; // r8
  __int64 (__fastcall ***v65)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v66)(_QWORD, GUID *, __int64); // rbx
  char v67; // r8
  HSTRING_HEADER *v68; // rax
  PCWSTR v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rdi
  __int64 (__fastcall *v72)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v73; // rax
  char v74; // r8
  __int64 (__fastcall ***v75)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v76)(_QWORD, GUID *, __int64); // rbx
  HSTRING_HEADER *v77; // rax
  __int64 v78; // rdi
  __int64 (__fastcall *v79)(__int64, PVOID, _BYTE *); // rbx
  HSTRING_HEADER *v80; // rax
  char v81; // r8
  __int64 (__fastcall ***v82)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v83)(_QWORD, GUID *, __int64); // rbx
  HSTRING_HEADER *v84; // rax
  __int64 v85; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-69h] BYREF
  __int64 v87; // [rsp+50h] [rbp-51h]
  __int64 v88; // [rsp+58h] [rbp-49h] BYREF
  _BYTE v89[8]; // [rsp+60h] [rbp-41h] BYREF
  __int64 (__fastcall ***v90)(_QWORD, GUID *, __int64); // [rsp+68h] [rbp-39h] BYREF
  __int64 v91; // [rsp+70h] [rbp-31h] BYREF
  HSTRING v92; // [rsp+78h] [rbp-29h] BYREF
  char v93; // [rsp+80h] [rbp-21h] BYREF
  char v94; // [rsp+81h] [rbp-20h] BYREF
  char v95; // [rsp+82h] [rbp-1Fh] BYREF
  char v96; // [rsp+83h] [rbp-1Eh] BYREF
  char v97; // [rsp+84h] [rbp-1Dh] BYREF
  char v98; // [rsp+85h] [rbp-1Ch] BYREF
  _BYTE v99[2]; // [rsp+86h] [rbp-1Bh] BYREF
  HSTRING string; // [rsp+88h] [rbp-19h] BYREF
  struct ChatServiceAttachment *v101; // [rsp+90h] [rbp-11h] BYREF
  struct Windows::Data::Json::IJsonObject *v102; // [rsp+98h] [rbp-9h] BYREF
  unsigned int v103; // [rsp+A0h] [rbp-1h] BYREF
  double v104; // [rsp+A8h] [rbp+7h] BYREF

  v88 = 0;
  v87 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = RoGetActivationFactory(v87, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v88);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_68(ActivationFactory);
    v5 = v88;
    if ( !v88 )
      return (unsigned int)v4;
    v88 = 0;
    v6 = *(void (**)(void))(*(_QWORD *)v5 + 16LL);
LABEL_4:
    v6();
    return (unsigned int)v4;
  }
  v8 = (struct ChatServiceAttachment *)*((_QWORD *)this + 49);
  v9 = v88;
  v90 = 0;
  v101 = v8;
  v10 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD))(*(_QWORD *)v88 + 48LL);
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&v101, v3);
  v12 = v10(v9, v11[1].Reserved.Reserved1, &v90);
  v4 = v12;
  if ( v12 < 0 )
  {
    Log_HREvent_68(v12);
LABEL_8:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
    v13 = v88;
    if ( !v88 )
      return (unsigned int)v4;
    v88 = 0;
    v6 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
    goto LABEL_4;
  }
  v91 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
         &v90,
         (__int64)&v91);
  if ( v4 < 0 )
    goto LABEL_11;
  v15 = v90;
  v104 = 0.0;
  v16 = (*v90)[11];
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1800FD6C8, v14);
  v4 = v16(v15, (GUID *)v17[1].Reserved.Reserved1, (__int64)&v104);
  if ( v4 < 0 )
    goto LABEL_11;
  v19 = v91;
  v93 = 0;
  v20 = (int)(v104 * 10.0);
  *((_DWORD *)this + 106) = v20 / 0xA;
  *((_DWORD *)this + 107) = v20 % 0xA;
  v21 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)v19 + 64LL);
  v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1800FD700, v18);
  v4 = v21(v19, v22[1].Reserved.Reserved1, &v93);
  if ( v4 < 0 )
    goto LABEL_11;
  if ( v93 )
  {
    v24 = v90;
    string = 0;
    v25 = (*v90)[10];
    WindowsDeleteString(0);
    string = 0;
    v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800FD700,
            v26);
    v28 = v25(v24, (GUID *)v27[1].Reserved.Reserved1, (__int64)&string);
    v4 = v28;
    if ( v28 < 0 )
    {
      Log_HREvent_68(v28);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_12;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             (char *)this + 464,
                             StringRawBuffer) )
    {
      Log_HREvent_68(-2147024882);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_20;
    }
    WindowsDeleteString(string);
  }
  v32 = v91;
  v94 = 0;
  v33 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)v91 + 64LL);
  v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1800FD6F0, v23);
  v4 = v33(v32, v34[1].Reserved.Reserved1, &v94);
  if ( v4 < 0 )
    goto LABEL_11;
  if ( !v94 )
  {
LABEL_44:
    v45 = v91;
    v95 = 0;
    v46 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)v91 + 64LL);
    v47 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800FD6F8,
            v35);
    v4 = v46(v45, v47[1].Reserved.Reserved1, &v95);
    if ( v4 < 0 )
      goto LABEL_11;
    if ( v95 )
    {
      v49 = v90;
      *(double *)&v101 = 0.0;
      v50 = (*v90)[11];
      v51 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_1800FD6F8,
              v48);
      v4 = v50(v49, (GUID *)v51[1].Reserved.Reserved1, (__int64)&v101);
      if ( v4 < 0 )
        goto LABEL_11;
      *((_DWORD *)this + 138) = (int)*(double *)&v101;
    }
    v52 = v91;
    v96 = 0;
    v53 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)v91 + 64LL);
    v54 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800FD6E0,
            v48);
    v4 = v53(v52, v54[1].Reserved.Reserved1, &v96);
    if ( v4 < 0 )
      goto LABEL_11;
    if ( v96 )
    {
      v56 = v90;
      v92 = 0;
      v57 = (*v90)[10];
      WindowsDeleteString(0);
      v92 = 0;
      v59 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_1800FD6E0,
              v58);
      v4 = v57(v56, (GUID *)v59[1].Reserved.Reserved1, (__int64)&v92);
      if ( v4 < 0 )
      {
LABEL_52:
        Log_HREvent_68(v4);
        WindowsDeleteString(v92);
        v92 = 0;
        goto LABEL_12;
      }
      v60 = WindowsGetStringRawBuffer(v92, 0);
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               (char *)this + 560,
                               v60) )
      {
        Log_HREvent_68(-2147024882);
        WindowsDeleteString(v92);
        v92 = 0;
LABEL_20:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
        v30 = v88;
        if ( v88 )
        {
          v88 = 0;
          v31 = *(void (**)(void))(*(_QWORD *)v30 + 16LL);
LABEL_62:
          v31();
          return 2147942414LL;
        }
        return 2147942414LL;
      }
      WindowsDeleteString(v92);
    }
    v61 = v91;
    v97 = 0;
    v62 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)v91 + 64LL);
    v63 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800FD6E8,
            v55);
    v4 = v62(v61, v63[1].Reserved.Reserved1, &v97);
    if ( v4 < 0 )
      goto LABEL_11;
    if ( v97 )
    {
      v65 = v90;
      v92 = 0;
      v66 = (*v90)[10];
      WindowsDeleteString(0);
      v92 = 0;
      v68 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_1800FD6E8,
              v67);
      v4 = v66(v65, (GUID *)v68[1].Reserved.Reserved1, (__int64)&v92);
      if ( v4 < 0 )
        goto LABEL_52;
      v69 = WindowsGetStringRawBuffer(v92, 0);
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               (char *)this + 184,
                               v69) )
      {
        Log_HREvent_68(-2147024882);
        WindowsDeleteString(v92);
        v92 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
        v70 = v88;
        if ( v88 )
        {
          v88 = 0;
          v31 = *(void (**)(void))(*(_QWORD *)v70 + 16LL);
          goto LABEL_62;
        }
        return 2147942414LL;
      }
      WindowsDeleteString(v92);
    }
    v71 = v91;
    v98 = 0;
    v72 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)v91 + 64LL);
    v73 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800FD6D0,
            v64);
    v4 = v72(v71, v73[1].Reserved.Reserved1, &v98);
    if ( v4 >= 0 )
    {
      if ( v98 )
      {
        v75 = v90;
        v89[0] = 0;
        v76 = (*v90)[12];
        v77 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)off_1800FD6D0,
                v74);
        v4 = v76(v75, (GUID *)v77[1].Reserved.Reserved1, (__int64)v89);
        if ( v4 < 0 )
          goto LABEL_11;
        *((_DWORD *)this + 96) = v89[0];
      }
      v78 = v91;
      v99[0] = 0;
      v79 = *(__int64 (__fastcall **)(__int64, PVOID, _BYTE *))(*(_QWORD *)v91 + 64LL);
      v80 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_1800FD6D8,
              v74);
      v4 = v79(v78, v80[1].Reserved.Reserved1, v99);
      if ( v4 >= 0 )
      {
        if ( v99[0] )
        {
          v82 = v90;
          v89[0] = 0;
          v83 = (*v90)[12];
          v84 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD6D8,
                  v81);
          v4 = v83(v82, (GUID *)v84[1].Reserved.Reserved1, (__int64)v89);
          if ( v4 < 0 )
            goto LABEL_11;
          *((_DWORD *)this + 97) = v89[0];
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
        v85 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
        }
        return 0;
      }
    }
LABEL_11:
    Log_HREvent_68(v4);
LABEL_12:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91);
    goto LABEL_8;
  }
  v36 = v90;
  string = 0;
  v37 = (*v90)[9];
  v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1800FD6F0, v35);
  v39 = v37(v36, (GUID *)v38[1].Reserved.Reserved1, (__int64)&string);
  v4 = v39;
  if ( v39 < 0 )
  {
    Log_HREvent_68(v39);
LABEL_27:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
    goto LABEL_12;
  }
  v92 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&string,
         (__int64)&v92);
  if ( v4 < 0
    || (v103 = 0, v4 = (*(__int64 (__fastcall **)(HSTRING, unsigned int *))(*(_QWORD *)v92 + 56LL))(v92, &v103), v4 < 0) )
  {
    Log_HREvent_68(v4);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
    goto LABEL_27;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v103 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      goto LABEL_44;
    }
    v102 = 0;
    v41 = (*(__int64 (__fastcall **)(HSTRING, _QWORD, struct Windows::Data::Json::IJsonObject **))(*(_QWORD *)string
                                                                                                 + 48LL))(
            string,
            i,
            &v102);
    v42 = v41;
    if ( v41 < 0 )
      break;
    *(double *)&v101 = 0.0;
    v43 = ChatServiceAttachment::CreateInstance(v102, &v101);
    v42 = v43;
    if ( v43 < 0 )
    {
      Log_HREvent_68(v43);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v101);
      goto LABEL_40;
    }
    if ( !utl::vector<ATL::CComPtr<ChatServiceAttachment>,utl::allocator<ATL::CComPtr<ChatServiceAttachment>>>::emplace_back<ATL::CComPtr<ChatServiceAttachment> &,0>(
            (_QWORD *)this + 63,
            &v101) )
    {
      Log_HREvent_68(-2147024882);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v101);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      goto LABEL_20;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v101);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
  }
  Log_HREvent_68(v41);
LABEL_40:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
  v44 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  return v42;
}

```

## disassembly

```asm
0x180095ab0  mov     rax, rsp
0x180095ab3  push    rbp
0x180095ab4  push    rbx
0x180095ab5  push    rsi
0x180095ab6  push    rdi
0x180095ab7  push    r14
0x180095ab9  push    r15
0x180095abb  lea     rbp, [rax-5Fh]
0x180095abf  sub     rsp, 0C8h
0x180095ac6  movaps  xmmword ptr [rax-48h], xmm6
0x180095aca  mov     rax, cs:__security_cookie
0x180095ad1  xor     rax, rsp
0x180095ad4  mov     qword ptr [rbp+57h+var_48], rax
0x180095ad8  xor     r15d, r15d
0x180095adb  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180095ae2  mov     r14, rcx
0x180095ae5  mov     [rbp+57h+var_A0], r15
0x180095ae9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180095aed  mov     [rbp+57h+var_A8], r15
0x180095af1  lea     r9d, [r15+1Ch]; unsigned int
0x180095af5  lea     r8d, [r15+1Dh]; unsigned int
0x180095af9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180095afe  mov     rcx, [rbp+57h+var_A8]
0x180095b02  lea     r8, [rbp+57h+var_A0]
0x180095b06  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180095b0d  call    cs:__imp_RoGetActivationFactory
0x180095b13  mov     ebx, eax
0x180095b15  test    eax, eax
0x180095b17  jns     short loc_180095B4A
0x180095b19  lea     edx, [r15+1]
0x180095b1d  mov     r9d, 3DAh
0x180095b23  mov     ecx, eax; int
0x180095b25  call    Log_HREvent_68
0x180095b2a  mov     rcx, [rbp+57h+var_A0]
0x180095b2e  test    rcx, rcx
0x180095b31  jz      short loc_180095B43
0x180095b33  mov     [rbp+57h+var_A0], r15
0x180095b37  mov     rdx, [rcx]
0x180095b3a  mov     rax, [rdx+10h]
0x180095b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b43  mov     eax, ebx
0x180095b45  jmp     loc_1800963D3
0x180095b4a  mov     rdx, [r14+188h]
0x180095b51  lea     rcx, [rbp+57h+hstringHeader]
0x180095b55  mov     rdi, [rbp+57h+var_A0]
0x180095b59  mov     [rbp+57h+var_90], r15
0x180095b5d  mov     [rbp+57h+var_68], rdx
0x180095b61  lea     rdx, [rbp+57h+var_68]
0x180095b65  mov     rax, [rdi]
0x180095b68  mov     rbx, [rax+30h]
0x180095b6c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180095b71  lea     r8, [rbp+57h+var_90]
0x180095b75  mov     rcx, rdi
0x180095b78  mov     rdx, [rax+18h]
0x180095b7c  mov     rax, rbx
0x180095b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b84  mov     ebx, eax
0x180095b86  test    eax, eax
0x180095b88  jns     short loc_180095BBB
0x180095b8a  mov     edx, 1
0x180095b8f  mov     r9d, 3DDh
0x180095b95  mov     ecx, eax; int
0x180095b97  call    Log_HREvent_68
0x180095b9c  lea     rcx, [rbp+57h+var_90]
0x180095ba0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095ba5  mov     rcx, [rbp+57h+var_A0]
0x180095ba9  test    rcx, rcx
0x180095bac  jz      short loc_180095B43
0x180095bae  mov     [rbp+57h+var_A0], r15
0x180095bb2  mov     rax, [rcx]
0x180095bb5  mov     rax, [rax+10h]
0x180095bb9  jmp     short loc_180095B3E
0x180095bbb  lea     rdx, [rbp+57h+var_88]
0x180095bbf  mov     [rbp+57h+var_88], r15
0x180095bc3  lea     rcx, [rbp+57h+var_90]
0x180095bc7  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180095bcc  mov     ebx, eax
0x180095bce  test    eax, eax
0x180095bd0  jns     short loc_180095BEF
0x180095bd2  mov     r9d, 3E0h
0x180095bd8  mov     edx, 1
0x180095bdd  mov     ecx, ebx; int
0x180095bdf  call    Log_HREvent_68
0x180095be4  lea     rcx, [rbp+57h+var_88]
0x180095be8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095bed  jmp     short loc_180095B9C
0x180095bef  mov     rdi, [rbp+57h+var_90]
0x180095bf3  lea     rdx, off_1800FD6C8; "version"
0x180095bfa  xorps   xmm6, xmm6
0x180095bfd  lea     rcx, [rbp+57h+hstringHeader]
0x180095c01  movsd   [rbp+57h+var_50], xmm6
0x180095c06  mov     rax, [rdi]
0x180095c09  mov     rbx, [rax+58h]
0x180095c0d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180095c12  lea     r8, [rbp+57h+var_50]
0x180095c16  mov     rcx, rdi
0x180095c19  mov     rdx, [rax+18h]
0x180095c1d  mov     rax, rbx
0x180095c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095c25  mov     ebx, eax
0x180095c27  test    eax, eax
0x180095c29  jns     short loc_180095C33
0x180095c2b  mov     r9d, 3E4h
0x180095c31  jmp     short loc_180095BD8
0x180095c33  movsd   xmm0, [rbp+57h+var_50]
0x180095c38  mov     eax, 0CCCCCCCDh
0x180095c3d  mulsd   xmm0, cs:__real@4024000000000000
0x180095c45  mov     rdi, [rbp+57h+var_88]
0x180095c49  mov     [rbp+57h+var_78], r15b
0x180095c4d  cvttsd2si rcx, xmm0
0x180095c52  mul     ecx
0x180095c54  shr     edx, 3
0x180095c57  mov     [r14+1A8h], edx
0x180095c5e  lea     eax, [rdx+rdx*4]
0x180095c61  add     eax, eax
0x180095c63  lea     rdx, off_1800FD700; "subject"
0x180095c6a  sub     ecx, eax
0x180095c6c  mov     [r14+1ACh], ecx
0x180095c73  lea     rcx, [rbp+57h+hstringHeader]
0x180095c77  mov     rax, [rdi]
0x180095c7a  mov     rbx, [rax+40h]
0x180095c7e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180095c83  lea     r8, [rbp+57h+var_78]
0x180095c87  mov     rcx, rdi
0x180095c8a  mov     rdx, [rax+18h]
0x180095c8e  mov     rax, rbx
0x180095c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095c96  mov     ebx, eax
0x180095c98  test    eax, eax
0x180095c9a  jns     short loc_180095CA7
0x180095c9c  mov     r9d, 3EEh
0x180095ca2  jmp     loc_180095BD8
0x180095ca7  cmp     [rbp+57h+var_78], r15b
0x180095cab  jz      loc_180095D92
0x180095cb1  mov     rdi, [rbp+57h+var_90]
0x180095cb5  xor     ecx, ecx; string
0x180095cb7  mov     [rbp+57h+string], r15
0x180095cbb  mov     rax, [rdi]
0x180095cbe  mov     rbx, [rax+50h]
0x180095cc2  call    cs:__imp_WindowsDeleteString
0x180095cc8  lea     rdx, off_1800FD700; "subject"
0x180095ccf  mov     [rbp+57h+string], r15
0x180095cd3  lea     rcx, [rbp+57h+hstringHeader]
0x180095cd7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180095cdc  lea     r8, [rbp+57h+string]
0x180095ce0  mov     rcx, rdi
0x180095ce3  mov     rdx, [rax+18h]
0x180095ce7  mov     rax, rbx
0x180095cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095cef  mov     ebx, eax
0x180095cf1  test    eax, eax
0x180095cf3  jns     short loc_180095D1A
0x180095cf5  mov     edx, 1
0x180095cfa  mov     r9d, 3F3h
0x180095d00  mov     ecx, eax; int
0x180095d02  call    Log_HREvent_68
0x180095d07  mov     rcx, [rbp+57h+string]; string
0x180095d0b  call    cs:__imp_WindowsDeleteString
0x180095d11  mov     [rbp+57h+string], r15
0x180095d15  jmp     loc_180095BE4
0x180095d1a  mov     rcx, [rbp+57h+string]; string
0x180095d1e  xor     edx, edx; length
0x180095d20  call    cs:__imp_WindowsGetStringRawBuffer
0x180095d26  mov     rdx, rax
0x180095d29  lea     rcx, [r14+1D0h]
0x180095d30  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180095d35  test    al, al
0x180095d37  jnz     short loc_180095D88
0x180095d39  xor     edx, edx
0x180095d3b  mov     ecx, 8007000Eh; int
0x180095d40  mov     r9d, 3F5h
0x180095d46  call    Log_HREvent_68
0x180095d4b  mov     rcx, [rbp+57h+string]; string
0x180095d4f  call    cs:__imp_WindowsDeleteString
0x180095d55  mov     [rbp+57h+string], r15
0x180095d59  lea     rcx, [rbp+57h+var_88]
0x180095d5d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095d62  lea     rcx, [rbp+57h+var_90]
0x180095d66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095d6b  mov     rcx, [rbp+57h+var_A0]
0x180095d6f  test    rcx, rcx
0x180095d72  jz      loc_180096264
0x180095d78  mov     [rbp+57h+var_A0], r15
0x180095d7c  mov     rax, [rcx]
0x180095d7f  mov     rax, [rax+10h]
0x180095d83  jmp     loc_18009625F
0x180095d88  mov     rcx, [rbp+57h+string]; string
0x180095d8c  call    cs:__imp_WindowsDeleteString
0x180095d92  mov     rdi, [rbp+57h+var_88]
0x180095d96  lea     rdx, off_1800FD6F0; "content_list"
0x180095d9d  mov     [rbp+57h+var_77], r15b
0x180095da1  lea     rcx, [rbp+57h+hstringHeader]
0x180095da5  mov     rax, [rdi]
0x180095da8  mov     rbx, [rax+40h]
0x180095dac  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180095db1  lea     r8, [rbp+57h+var_77]
0x180095db5  mov     rcx, rdi
0x180095db8  mov     rdx, [rax+18h]
0x180095dbc  mov     rax, rbx
0x180095dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095dc4  mov     ebx, eax
0x180095dc6  test    eax, eax
0x180095dc8  jns     short loc_180095DD5
0x180095dca  mov     r9d, 3FAh
0x180095dd0  jmp     loc_180095BD8
0x180095dd5  mov     esi, 1
0x180095dda  cmp     [rbp+57h+var_77], r15b
0x180095dde  jz      loc_180095FC4
0x180095de4  mov     rdi, [rbp+57h+var_90]
0x180095de8  lea     rdx, off_1800FD6F0; "content_list"
0x180095def  mov     [rbp+57h+string], r15
0x180095df3  lea     rcx, [rbp+57h+hstringHeader]
0x180095df7  mov     rax, [rdi]
0x180095dfa  mov     rbx, [rax+48h]
0x180095dfe  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180095e03  lea     r8, [rbp+57h+string]
0x180095e07  mov     rcx, rdi
0x180095e0a  mov     rdx, [rax+18h]
0x180095e0e  mov     rax, rbx
0x180095e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095e16  mov     ebx, eax
0x180095e18  test    eax, eax
0x180095e1a  jns     short loc_180095E39
0x180095e1c  mov     r9d, 400h
0x180095e22  mov     edx, esi
0x180095e24  mov     ecx, eax; int
0x180095e26  call    Log_HREvent_68
0x180095e2b  lea     rcx, [rbp+57h+string]
0x180095e2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095e34  jmp     loc_180095BE4
0x180095e39  lea     rdx, [rbp+57h+var_80]
0x180095e3d  mov     [rbp+57h+var_80], r15
0x180095e41  lea     rcx, [rbp+57h+string]
0x180095e45  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180095e4a  mov     ebx, eax
0x180095e4c  test    eax, eax
0x180095e4e  jns     short loc_180095E6A
0x180095e50  mov     r9d, 403h
0x180095e56  mov     edx, esi
0x180095e58  mov     ecx, ebx; int
0x180095e5a  call    Log_HREvent_68
0x180095e5f  lea     rcx, [rbp+57h+var_80]
0x180095e63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095e68  jmp     short loc_180095E2B
0x180095e6a  mov     rcx, [rbp+57h+var_80]
0x180095e6e  lea     rdx, [rbp+57h+var_58]
0x180095e72  mov     [rbp+57h+var_58], r15d
0x180095e76  mov     rax, [rcx]
0x180095e79  mov     rax, [rax+38h]
0x180095e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095e82  mov     ebx, eax
0x180095e84  test    eax, eax
0x180095e86  jns     short loc_180095E90
0x180095e88  mov     r9d, 406h
0x180095e8e  jmp     short loc_180095E56
0x180095e90  mov     ebx, r15d
0x180095e93  cmp     ebx, [rbp+57h+var_58]
0x180095e96  jnb     loc_180095FB2
0x180095e9c  mov     rcx, [rbp+57h+string]
0x180095ea0  lea     r8, [rbp+57h+var_60]
0x180095ea4  mov     [rbp+57h+var_60], r15
0x180095ea8  mov     edx, ebx
0x180095eaa  mov     rax, [rcx]
0x180095ead  mov     rax, [rax+30h]
0x180095eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095eb6  mov     edi, eax
0x180095eb8  test    eax, eax
0x180095eba  js      loc_180095F56
0x180095ec0  mov     rcx, [rbp+57h+var_60]; struct Windows::Data::Json::IJsonObject *
0x180095ec4  lea     rdx, [rbp+57h+var_68]; struct ChatServiceAttachment **
0x180095ec8  mov     [rbp+57h+var_68], r15
0x180095ecc  call    ?CreateInstance@ChatServiceAttachment@@SAJPEAUIJsonObject@Json@Data@Windows@@PEAPEAV1@@Z; ChatServiceAttachment::CreateInstance(Windows::Data::Json::IJsonObject *,ChatServiceAttachment * *)
0x180095ed1  mov     edi, eax
0x180095ed3  test    eax, eax
0x180095ed5  js      short loc_180095F3C
0x180095ed7  lea     rcx, [r14+1F8h]
0x180095ede  lea     rdx, [rbp+57h+var_68]
0x180095ee2  call    ??$emplace_back@AEAV?$CComPtr@VChatServiceAttachment@@@ATL@@$0A@@?$vector@V?$CComPtr@VChatServiceAttachment@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceAttachment@@@ATL@@@utl@@@utl@@QEAA_NAEAV?$CComPtr@VChatServiceAttachment@@@ATL@@@Z; utl::vector<ATL::CComPtr<ChatServiceAttachment>,utl::allocator<ATL::CComPtr<ChatServiceAttachment>>>::emplace_back<ATL::CComPtr<ChatServiceAttachment> &,0>(ATL::CComPtr<ChatServiceAttachment> &)
0x180095ee7  test    al, al
0x180095ee9  jz      short loc_180095F01
0x180095eeb  lea     rcx, [rbp+57h+var_68]
0x180095eef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180095ef4  lea     rcx, [rbp+57h+var_60]
0x180095ef8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095efd  add     ebx, esi
0x180095eff  jmp     short loc_180095E93
0x180095f01  xor     edx, edx
0x180095f03  mov     ecx, 8007000Eh; int
0x180095f08  mov     r9d, 410h
0x180095f0e  call    Log_HREvent_68
0x180095f13  lea     rcx, [rbp+57h+var_68]
0x180095f17  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180095f1c  lea     rcx, [rbp+57h+var_60]
0x180095f20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095f25  lea     rcx, [rbp+57h+var_80]
0x180095f29  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095f2e  lea     rcx, [rbp+57h+string]
0x180095f32  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095f37  jmp     loc_180095D59
0x180095f3c  mov     r9d, 40Eh
  ... truncated ...
```
