# ChatServiceMessage::_PackMessageEnvelope(ISmMessage *,AsyncMediaServiceDocument *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180093d98`
- end: `0x1800948c0`
- name: `?_PackMessageEnvelope@ChatServiceMessage@@AEAAJPEAUISmMessage@@PEAVAsyncMediaServiceDocument@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `2856`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180092a60`

## callees

- `0x180005c50`
- `0x18000b6d4`
- `0x18000b7d4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x180091f30`
- `0x180091f70`
- `0x18009201c`
- `0x1800921dc`
- `0x180092840`
- `0x180093d98`
- `0x1800b05e8`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093e8b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093e8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800947f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800947f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094822`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094822`

## string_xrefs

- `0x180093e69`: `Windows.Data.Json.JsonValue`
- `0x180093dd8`: `Windows.Data.Json.JsonObject`
- `0x180094087`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
__int64 __fastcall ChatServiceMessage::_PackMessageEnvelope(
        __int64 a1,
        __int64 *a2,
        struct AsyncMediaServiceDocument *a3,
        __int64 a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int ActivationFactory; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  char v14; // r8
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v18; // rax
  __int64 v19; // rax
  int v20; // eax
  int v21; // ecx
  char v22; // r8
  const WCHAR *v23; // rdx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v26; // rax
  int v27; // eax
  char v28; // r8
  __int64 v29; // rsi
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v32; // rax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  unsigned int v37; // ebx
  int v38; // eax
  unsigned int v39; // edi
  int v40; // eax
  struct ISmAttachment *v41; // rcx
  struct ISmAttachment *v42; // rcx
  struct ISmAttachment *v43; // rcx
  int v44; // eax
  char v45; // r8
  __int64 v46; // rsi
  const WCHAR *v47; // rbx
  __int64 (__fastcall *v48)(__int64, PVOID, const WCHAR *, _BYTE *); // rdi
  HSTRING_HEADER *v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rcx
  int v53; // eax
  char v54; // r8
  __int64 v55; // rsi
  __int64 v56; // rbx
  __int64 (__fastcall *v57)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v58; // rax
  __int64 v59; // rax
  int v60; // eax
  int v61; // ecx
  char v62; // r8
  struct ChatServiceAttachment *v63; // rdx
  __int64 v64; // rdi
  __int64 (__fastcall *v65)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v66; // rax
  int v67; // eax
  char v68; // r8
  __int64 v69; // rsi
  __int64 v70; // rbx
  __int64 (__fastcall *v71)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v72; // rax
  char v73; // r8
  const WCHAR *v74; // rcx
  __int64 v75; // rdi
  __int64 (__fastcall *v76)(__int64, PVOID, struct ChatServiceAttachment **); // rbx
  HSTRING_HEADER *v77; // rax
  int v78; // eax
  char v79; // r8
  struct ChatServiceAttachment **v80; // rcx
  __int64 v81; // rsi
  struct ChatServiceAttachment *v82; // rbx
  __int64 (__fastcall *v83)(__int64, PVOID, struct ChatServiceAttachment *, _BYTE *); // rdi
  HSTRING_HEADER *v84; // rax
  __int64 v85; // rax
  __int64 v86; // rcx
  _BOOL8 v87; // rdx
  int v88; // eax
  char v89; // r8
  __int64 v90; // rsi
  __int64 v91; // rbx
  __int64 (__fastcall *v92)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v93; // rax
  __int64 v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rcx
  bool v97; // zf
  int v98; // eax
  char v99; // r8
  __int64 v100; // rsi
  __int64 v101; // rbx
  __int64 (__fastcall *v102)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v103; // rax
  int v104; // eax
  __int64 v105; // rdi
  __int64 (__fastcall *v106)(__int64, HSTRING *); // rbx
  int v107; // eax
  int v108; // ecx
  PCWSTR StringRawBuffer; // rax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v112; // [rsp+48h] [rbp-B8h]
  const WCHAR *v113; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v114; // [rsp+58h] [rbp-A8h]
  _BYTE v115[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v116; // [rsp+68h] [rbp-98h] BYREF
  __int64 v117; // [rsp+70h] [rbp-90h] BYREF
  __int64 v118; // [rsp+78h] [rbp-88h] BYREF
  __int64 v119; // [rsp+80h] [rbp-80h] BYREF
  __int64 v120; // [rsp+88h] [rbp-78h] BYREF
  __int64 v121; // [rsp+90h] [rbp-70h] BYREF
  __int64 v122; // [rsp+98h] [rbp-68h] BYREF
  __int64 v123; // [rsp+A0h] [rbp-60h] BYREF
  struct ChatServiceAttachment *v124; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall ***v125)(_QWORD, GUID *, __int64); // [rsp+B0h] [rbp-50h] BYREF
  __int64 v126; // [rsp+B8h] [rbp-48h] BYREF
  struct ISmAttachment *v127; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v128; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v129; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v131; // [rsp+E0h] [rbp-20h] BYREF
  const WCHAR *v132; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v133; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v134; // [rsp+F8h] [rbp-8h] BYREF
  int v135; // [rsp+FCh] [rbp-4h] BYREF
  unsigned int v136; // [rsp+100h] [rbp+0h] BYREF
  __int64 (__fastcall ***v137)(_QWORD, GUID *, __int64); // [rsp+108h] [rbp+8h] BYREF

  v114 = a4;
  v137 = 0;
  v112 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v7 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v112, &v137);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v116 = 0;
    v9 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
           &v137,
           (__int64)&v116);
    v8 = v9;
    if ( v9 < 0 )
    {
      Log_HREvent_68(v9);
LABEL_5:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      goto LABEL_92;
    }
    v117 = 0;
    v112 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = RoGetActivationFactory(v112, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v117);
    v8 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      Log_HREvent_68(ActivationFactory);
LABEL_8:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
      goto LABEL_5;
    }
    v12 = v117;
    *(_QWORD *)(a1 + 424) = 1;
    v118 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v12 + 72LL))(v12, v11, &v118);
    v8 = v13;
    if ( v13 < 0
      || (v15 = v116,
          v16 = v118,
          v115[0] = 0,
          v17 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v116 + 80LL),
          v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD6C8,
                  v14),
          v13 = v17(v15, v18[1].Reserved.Reserved1, v16, v115),
          v8 = v13,
          v13 < 0) )
    {
      Log_HREvent_68(v13);
LABEL_11:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
      goto LABEL_8;
    }
    v19 = *a2;
    v119 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 112))(a2, &v119);
    v8 = v20;
    if ( v20 < 0 )
    {
      v21 = v20;
LABEL_15:
      Log_HREvent_68(v21);
LABEL_16:
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v119);
      goto LABEL_11;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             a1 + 464,
                             v119) )
    {
      v8 = -2147024882;
      v21 = -2147024882;
      goto LABEL_15;
    }
    v23 = *(const WCHAR **)(a1 + 464);
    v24 = v117;
    v120 = 0;
    v132 = v23;
    v25 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v117 + 80LL);
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v132, v22);
    v27 = v25(v24, v26[1].Reserved.Reserved1, &v120);
    v8 = v27;
    if ( v27 < 0 )
      goto LABEL_20;
    v29 = v116;
    v30 = v120;
    v31 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v116 + 80LL);
    v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800FD700,
            v28);
    v27 = v31(v29, v32[1].Reserved.Reserved1, v30, v115);
    v8 = v27;
    if ( v27 < 0 )
      goto LABEL_20;
    if ( (unsigned __int8)utl::operator==<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                            a1 + 304,
                            L"RichText/Mms") )
    {
      v125 = 0;
      v112 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonArray",
        0x1Cu,
        0x1Bu);
      v33 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v112, &v125);
      v8 = v33;
      if ( v33 < 0 )
      {
        Log_HREvent_68(v33);
LABEL_26:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
        goto LABEL_21;
      }
      v129 = 0;
      v34 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
              &v125,
              (__int64)&v129);
      v8 = v34;
      if ( v34 < 0 )
      {
        Log_HREvent_68(v34);
LABEL_29:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
        goto LABEL_26;
      }
      v35 = *a2;
      v128 = 0;
      v36 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v35 + 240))(a2, &v128);
      v8 = v36;
      if ( v36 < 0 )
      {
        Log_HREvent_68(v36);
LABEL_32:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
        goto LABEL_29;
      }
      v37 = 0;
      while ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v128 + 24LL))(v128) )
      {
        v127 = 0;
        v38 = (*(__int64 (__fastcall **)(__int64, struct ISmAttachment **))(*(_QWORD *)v128 + 32LL))(v128, &v127);
        v39 = v38;
        if ( v38 < 0 )
        {
          Log_HREvent_68(v38);
          goto LABEL_45;
        }
        v124 = 0;
        v40 = ChatServiceAttachment::CreateInstance(v127, v37, a3, &v124);
        v39 = v40;
        if ( v40 < 0 )
        {
          Log_HREvent_68(v40);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v124);
LABEL_45:
          v43 = v127;
          if ( v127 )
          {
            v127 = 0;
            (*(void (__fastcall **)(struct ISmAttachment *))(*(_QWORD *)v43 + 16LL))(v43);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v120);
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v119);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
          v8 = v39;
          goto LABEL_92;
        }
        if ( !utl::vector<ATL::CComPtr<ChatServiceAttachment>,utl::allocator<ATL::CComPtr<ChatServiceAttachment>>>::emplace_back<ATL::CComPtr<ChatServiceAttachment> &,0>(
                (_QWORD *)(a1 + 504),
                &v124) )
        {
          v8 = -2147024882;
          Log_HREvent_68(-2147024882);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v124);
          v42 = v127;
          if ( v127 )
          {
            v127 = 0;
            (*(void (__fastcall **)(struct ISmAttachment *))(*(_QWORD *)v42 + 16LL))(v42);
          }
          goto LABEL_32;
        }
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v129 + 104LL))(v129, *((_QWORD *)v124 + 32));
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v124);
        v41 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(struct ISmAttachment *))(*(_QWORD *)v41 + 16LL))(v41);
        }
        ++v37;
      }
      v132 = 0;
      v44 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
              &v125,
              (__int64)&v132);
      v8 = v44;
      if ( v44 < 0
        || (v46 = v116,
            v47 = v132,
            v48 = *(__int64 (__fastcall **)(__int64, PVOID, const WCHAR *, _BYTE *))(*(_QWORD *)v116 + 80LL),
            v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    (const WCHAR **)off_1800FD6F0,
                    v45),
            v44 = v48(v46, v49[1].Reserved.Reserved1, v47, v115),
            v8 = v44,
            v44 < 0) )
      {
        Log_HREvent_68(v44);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
        goto LABEL_32;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
    }
    v50 = *a2;
    v134 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v50 + 192))(a2, &v134);
    v8 = v27;
    if ( v27 < 0 )
    {
LABEL_20:
      Log_HREvent_68(v27);
LABEL_21:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v120);
      goto LABEL_16;
    }
    v51 = v134;
    v52 = v117;
    *(_DWORD *)(a1 + 552) = v134;
    v121 = 0;
    v53 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v52 + 72LL))(v52, v51, &v121);
    v8 = v53;
    if ( v53 < 0
      || (v55 = v116,
          v56 = v121,
          v57 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v116 + 80LL),
          v58 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD6F8,
                  v54),
          v53 = v57(v55, v58[1].Reserved.Reserved1, v56, v115),
          v8 = v53,
          v53 < 0) )
    {
      Log_HREvent_68(v53);
LABEL_55:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
      goto LABEL_21;
    }
    v59 = *a2;
    v122 = 0;
    v60 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v59 + 688))(a2, &v122);
    v8 = v60;
    if ( v60 < 0 )
    {
      v61 = v60;
LABEL_59:
      Log_HREvent_68(v61);
LABEL_60:
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v122);
      goto LABEL_55;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             a1 + 560,
                             v122) )
    {
      v8 = -2147024882;
      v61 = -2147024882;
      goto LABEL_59;
    }
    v63 = *(struct ChatServiceAttachment **)(a1 + 560);
    v64 = v117;
    v123 = 0;
    v124 = v63;
    v65 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v117 + 80LL);
    v66 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&v124, v62);
    v67 = v65(v64, v66[1].Reserved.Reserved1, &v123);
    v8 = v67;
    if ( v67 >= 0 )
    {
      v69 = v116;
      v70 = v123;
      v71 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v116 + 80LL);
      v72 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_1800FD6E0,
              v68);
      v67 = v71(v69, v72[1].Reserved.Reserved1, v70, v115);
      v8 = v67;
      if ( v67 >= 0 )
      {
        v74 = *(const WCHAR **)(a1 + 184);
        if ( v74 != *(const WCHAR **)(a1 + 192) )
        {
          v75 = v117;
          v124 = 0;
          v113 = v74;
          v76 = *(__int64 (__fastcall **)(__int64, PVOID, struct ChatServiceAttachment **))(*(_QWORD *)v117 + 80LL);
          v77 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v113, v73);
          v78 = v76(v75, v77[1].Reserved.Reserved1, &v124);
          v8 = v78;
          if ( v78 < 0
            || (v81 = v116,
                v82 = v124,
                v83 = *(__int64 (__fastcall **)(__int64, PVOID, struct ChatServiceAttachment *, _BYTE *))(*(_QWORD *)v116 + 80LL),
                v84 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        (const WCHAR **)off_1800FD6E8,
                        v79),
                v78 = v83(v81, v84[1].Reserved.Reserved1, v82, v115),
                v8 = v78,
                v78 < 0) )
          {
            Log_HREvent_68(v78);
            v80 = &v124;
LABEL_70:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v80);
            goto LABEL_65;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
        }
        v85 = *a2;
        v135 = 0;
        v67 = (*(__int64 (__fastcall **)(__int64 *, int *))(v85 + 24))(a2, &v135);
        v8 = v67;
        if ( v67 >= 0 )
        {
          v86 = v117;
          v87 = v135 == 0;
          v126 = 0;
          *(_DWORD *)(a1 + 384) = v87;
          v88 = (*(__int64 (__fastcall **)(__int64, _BOOL8, __int64 *))(*(_QWORD *)v86 + 64LL))(v86, v87, &v126);
          v8 = v88;
          if ( v88 < 0 )
            goto LABEL_75;
          v90 = v116;
          v91 = v126;
          v92 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v116 + 80LL);
          v93 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD6D0,
                  v89);
          v88 = v92(v90, v93[1].Reserved.Reserved1, v91, v115);
          v8 = v88;
          if ( v88 < 0
            || (v94 = *a2,
                v136 = 0,
                v88 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v94 + 600))(a2, &v136),
                v8 = v88,
                v88 < 0) )
          {
LABEL_75:
            Log_HREvent_68(v88);
          }
          else
          {
            v95 = v136;
            v96 = v117;
            v97 = v136 == 0;
            *(_DWORD *)(a1 + 388) = v136;
            v131 = 0;
            LOBYTE(v95) = !v97;
            v98 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v96 + 64LL))(v96, v95, &v131);
            v8 = v98;
            if ( v98 < 0
              || (v100 = v116,
                  v101 = v131,
                  v102 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v116 + 80LL),
                  v103 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                           &hstringHeader,
                           (const WCHAR **)off_1800FD6D8,
                           v99),
                  v98 = v102(v100, v103[1].Reserved.Reserved1, v101, v115),
                  v8 = v98,
                  v98 < 0) )
            {
              Log_HREvent_68(v98);
            }
            else
            {
              v133 = 0;
              v104 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                       &v137,
                       (__int64)&v133);
              v8 = v104;
              if ( v104 >= 0 )
              {
                v105 = v133;
                string = 0;
                v106 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v133 + 56LL);
                WindowsDeleteString(0);
                string = 0;
                v107 = v106(v105, &string);
                v8 = v107;
                if ( v107 >= 0 )
                {
                  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                          v114,
                                          StringRawBuffer) )
                  {
                    WindowsDeleteString(string);
                    string = 0;
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
                    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v122);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v120);
                    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v119);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
                    v8 = 0;
                    goto LABEL_92;
                  }
                  v8 = -2147024882;
                  v108 = -2147024882;
                }
                else
                {
                  v108 = v107;
                }
                Log_HREvent_68(v108);
                WindowsDeleteString(string);
                string = 0;
              }
              else
              {
                Log_HREvent_68(v104);
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
          }
          v80 = (struct ChatServiceAttachment **)&v126;
          goto LABEL_70;
        }
      }
    }
    Log_HREvent_68(v67);
LABEL_65:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
    goto LABEL_60;
  }
  Log_HREvent_68(v7);
LABEL_92:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
  return v8;
}

```

## disassembly

```asm
0x180093d98  push    rbp
0x180093d9a  push    rbx
0x180093d9b  push    rsi
0x180093d9c  push    rdi
0x180093d9d  push    r12
0x180093d9f  push    r13
0x180093da1  push    r14
0x180093da3  push    r15
0x180093da5  lea     rbp, [rsp-28h]
0x180093daa  sub     rsp, 128h
0x180093db1  mov     rax, cs:__security_cookie
0x180093db8  xor     rax, rsp
0x180093dbb  mov     [rbp+60h+var_50], rax
0x180093dbf  xor     edi, edi
0x180093dc1  mov     [rsp+160h+var_108], r9
0x180093dc6  mov     r12, r8
0x180093dc9  mov     [rbp+60h+var_58], rdi
0x180093dcd  mov     r15, rdx
0x180093dd0  mov     [rsp+160h+var_118], rdi
0x180093dd5  mov     r13, rcx
0x180093dd8  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180093ddf  lea     esi, [rdi+1Ch]
0x180093de2  mov     r9d, esi; unsigned int
0x180093de5  lea     r8d, [rdi+1Dh]; unsigned int
0x180093de9  lea     rcx, [rsp+160h+hstringHeader]; hstringHeader
0x180093dee  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180093df3  mov     rcx, [rsp+160h+var_118]
0x180093df8  lea     rdx, [rbp+60h+var_58]
0x180093dfc  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180093e01  mov     ebx, eax
0x180093e03  test    eax, eax
0x180093e05  jns     short loc_180093E1C
0x180093e07  lea     edx, [rdi+1]
0x180093e0a  mov     r9d, 270h
0x180093e10  mov     ecx, eax; int
0x180093e12  call    Log_HREvent_68
0x180093e17  jmp     loc_180094895
0x180093e1c  lea     rdx, [rsp+160h+var_F8]
0x180093e21  mov     [rsp+160h+var_F8], rdi
0x180093e26  lea     rcx, [rbp+60h+var_58]
0x180093e2a  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180093e2f  mov     ebx, eax
0x180093e31  test    eax, eax
0x180093e33  jns     short loc_180093E56
0x180093e35  mov     edx, 1
0x180093e3a  mov     r9d, 273h
0x180093e40  mov     ecx, eax; int
0x180093e42  call    Log_HREvent_68
0x180093e47  lea     rcx, [rsp+160h+var_F8]
0x180093e4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093e51  jmp     loc_180094895
0x180093e56  mov     r9d, 1Bh; unsigned int
0x180093e5c  mov     [rsp+160h+var_F0], rdi
0x180093e61  mov     r8d, esi; unsigned int
0x180093e64  mov     [rsp+160h+var_118], rdi
0x180093e69  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180093e70  lea     rcx, [rsp+160h+hstringHeader]; hstringHeader
0x180093e75  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180093e7a  mov     rcx, [rsp+160h+var_118]
0x180093e7f  lea     r8, [rsp+160h+var_F0]
0x180093e84  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180093e8b  call    cs:__imp_RoGetActivationFactory
0x180093e91  mov     ebx, eax
0x180093e93  test    eax, eax
0x180093e95  jns     short loc_180093EB5
0x180093e97  mov     edx, 1
0x180093e9c  mov     r9d, 277h
0x180093ea2  mov     ecx, eax; int
0x180093ea4  call    Log_HREvent_68
0x180093ea9  lea     rcx, [rsp+160h+var_F0]
0x180093eae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093eb3  jmp     short loc_180093E47
0x180093eb5  mov     rcx, [rsp+160h+var_F0]
0x180093eba  lea     r8, [rsp+160h+var_E8]
0x180093ebf  movsd   xmm1, cs:__real@3ff0000000000000
0x180093ec7  mov     r14d, 1
0x180093ecd  mov     [r13+1A8h], r14
0x180093ed4  mov     [rsp+160h+var_E8], rdi
0x180093ed9  mov     rax, [rcx]
0x180093edc  mov     rax, [rax+48h]
0x180093ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ee5  mov     ebx, eax
0x180093ee7  test    eax, eax
0x180093ee9  jns     short loc_180093F07
0x180093eeb  mov     r9d, 280h
0x180093ef1  mov     edx, r14d
0x180093ef4  mov     ecx, eax; int
0x180093ef6  call    Log_HREvent_68
0x180093efb  lea     rcx, [rsp+160h+var_E8]
0x180093f00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093f05  jmp     short loc_180093EA9
0x180093f07  mov     rsi, [rsp+160h+var_F8]
0x180093f0c  lea     rdx, off_1800FD6C8; "version"
0x180093f13  mov     rbx, [rsp+160h+var_E8]
0x180093f18  lea     rcx, [rsp+160h+hstringHeader]
0x180093f1d  mov     [rsp+160h+var_100], dil
0x180093f22  mov     rax, [rsi]
0x180093f25  mov     rdi, [rax+50h]
0x180093f29  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180093f2e  lea     r9, [rsp+160h+var_100]
0x180093f33  mov     r8, rbx
0x180093f36  mov     rcx, rsi
0x180093f39  mov     rdx, [rax+18h]
0x180093f3d  mov     rax, rdi
0x180093f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f45  mov     ebx, eax
0x180093f47  test    eax, eax
0x180093f49  jns     short loc_180093F53
0x180093f4b  mov     r9d, 283h
0x180093f51  jmp     short loc_180093EF1
0x180093f53  mov     rax, [r15]
0x180093f56  lea     rdx, [rbp+60h+var_E0]
0x180093f5a  mov     rcx, r15
0x180093f5d  mov     [rbp+60h+var_E0], 0
0x180093f65  mov     rax, [rax+70h]
0x180093f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f6e  mov     ebx, eax
0x180093f70  test    eax, eax
0x180093f72  jns     short loc_180093F92
0x180093f74  mov     r9d, 287h
0x180093f7a  mov     edx, r14d
0x180093f7d  mov     ecx, eax; int
0x180093f7f  call    Log_HREvent_68
0x180093f84  lea     rcx, [rbp+60h+var_E0]
0x180093f88  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x180093f8d  jmp     loc_180093EFB
0x180093f92  mov     rdx, [rbp+60h+var_E0]
0x180093f96  lea     rsi, [r13+1D0h]
0x180093f9d  mov     rcx, rsi
0x180093fa0  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180093fa5  test    al, al
0x180093fa7  jnz     short loc_180093FBA
0x180093fa9  mov     ebx, 8007000Eh
0x180093fae  xor     edx, edx
0x180093fb0  mov     ecx, ebx
0x180093fb2  mov     r9d, 288h
0x180093fb8  jmp     short loc_180093F7F
0x180093fba  mov     rdx, [rsi]
0x180093fbd  lea     rcx, [rsp+160h+hstringHeader]
0x180093fc2  mov     rdi, [rsp+160h+var_F0]
0x180093fc7  mov     [rbp+60h+var_D8], 0
0x180093fcf  mov     [rbp+60h+var_78], rdx
0x180093fd3  lea     rdx, [rbp+60h+var_78]
0x180093fd7  mov     rax, [rdi]
0x180093fda  mov     rbx, [rax+50h]
0x180093fde  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180093fe3  lea     r8, [rbp+60h+var_D8]
0x180093fe7  mov     rcx, rdi
0x180093fea  mov     rdx, [rax+18h]
0x180093fee  mov     rax, rbx
0x180093ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ff6  mov     ebx, eax
0x180093ff8  test    eax, eax
0x180093ffa  jns     short loc_18009401A
0x180093ffc  mov     r9d, 28Bh
0x180094002  mov     edx, r14d
0x180094005  mov     ecx, eax; int
0x180094007  call    Log_HREvent_68
0x18009400c  lea     rcx, [rbp+60h+var_D8]
0x180094010  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180094015  jmp     loc_180093F84
0x18009401a  mov     rsi, [rsp+160h+var_F8]
0x18009401f  lea     rdx, off_1800FD700; "subject"
0x180094026  mov     rbx, [rbp+60h+var_D8]
0x18009402a  lea     rcx, [rsp+160h+hstringHeader]
0x18009402f  mov     rax, [rsi]
0x180094032  mov     rdi, [rax+50h]
0x180094036  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009403b  lea     r9, [rsp+160h+var_100]
0x180094040  mov     r8, rbx
0x180094043  mov     rcx, rsi
0x180094046  mov     rdx, [rax+18h]
0x18009404a  mov     rax, rdi
0x18009404d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094052  xor     esi, esi
0x180094054  mov     ebx, eax
0x180094056  test    eax, eax
0x180094058  jns     short loc_180094062
0x18009405a  mov     r9d, 28Dh
0x180094060  jmp     short loc_180094002
0x180094062  lea     rcx, [r13+130h]
0x180094069  lea     rdx, aRichtextMms; "RichText/Mms"
0x180094070  call    ??$?8GU?$char_traits@G@utl@@V?$allocator@G@1@@utl@@YA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@0@PEBG@Z; utl::operator==<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,ushort const *)
0x180094075  test    al, al
0x180094077  jz      loc_18009436E
0x18009407d  mov     r9d, 1Bh; unsigned int
0x180094083  mov     [rbp+60h+var_B0], rsi
0x180094087  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x18009408e  mov     [rsp+160h+var_118], rsi
0x180094093  lea     rcx, [rsp+160h+hstringHeader]; hstringHeader
0x180094098  lea     r8d, [r9+1]; unsigned int
0x18009409c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800940a1  mov     rcx, [rsp+160h+var_118]
0x1800940a6  lea     rdx, [rbp+60h+var_B0]
0x1800940aa  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x1800940af  mov     ebx, eax
0x1800940b1  test    eax, eax
0x1800940b3  jns     short loc_1800940D3
0x1800940b5  mov     r9d, 295h
0x1800940bb  mov     edx, r14d
0x1800940be  mov     ecx, eax; int
0x1800940c0  call    Log_HREvent_68
0x1800940c5  lea     rcx, [rbp+60h+var_B0]
0x1800940c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800940ce  jmp     loc_18009400C
0x1800940d3  lea     rdx, [rbp+60h+var_90]
0x1800940d7  mov     [rbp+60h+var_90], rsi
0x1800940db  lea     rcx, [rbp+60h+var_B0]
0x1800940df  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x1800940e4  mov     ebx, eax
0x1800940e6  test    eax, eax
0x1800940e8  jns     short loc_180094105
0x1800940ea  mov     r9d, 298h
0x1800940f0  mov     edx, r14d
0x1800940f3  mov     ecx, eax; int
0x1800940f5  call    Log_HREvent_68
0x1800940fa  lea     rcx, [rbp+60h+var_90]
0x1800940fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180094103  jmp     short loc_1800940C5
0x180094105  mov     rax, [r15]
0x180094108  lea     rdx, [rbp+60h+var_98]
0x18009410c  mov     rcx, r15
0x18009410f  mov     [rbp+60h+var_98], rsi
0x180094113  mov     rax, [rax+0F0h]
0x18009411a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009411f  mov     ebx, eax
0x180094121  test    eax, eax
0x180094123  jns     short loc_180094140
0x180094125  mov     r9d, 29Bh
0x18009412b  mov     edx, r14d
0x18009412e  mov     ecx, eax; int
0x180094130  call    Log_HREvent_68
0x180094135  lea     rcx, [rbp+60h+var_98]
0x180094139  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009413e  jmp     short loc_1800940FA
0x180094140  mov     ebx, esi
0x180094142  mov     rcx, [rbp+60h+var_98]
0x180094146  mov     rax, [rcx]
0x180094149  mov     rax, [rax+18h]
0x18009414d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094152  test    eax, eax
0x180094154  jnz     loc_1800942CA
0x18009415a  mov     rcx, [rbp+60h+var_98]
0x18009415e  lea     rdx, [rbp+60h+var_A0]
0x180094162  mov     [rbp+60h+var_A0], rsi
0x180094166  mov     rax, [rcx]
0x180094169  mov     rax, [rax+20h]
0x18009416d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094172  mov     edi, eax
0x180094174  test    eax, eax
0x180094176  js      loc_18009424F
0x18009417c  mov     rcx, [rbp+60h+var_A0]; struct ISmAttachment *
0x180094180  lea     r9, [rbp+60h+var_B8]; struct ChatServiceAttachment **
0x180094184  mov     r8, r12; struct AsyncMediaServiceDocument *
0x180094187  mov     [rbp+60h+var_B8], rsi
0x18009418b  mov     edx, ebx; unsigned int
0x18009418d  call    ?CreateInstance@ChatServiceAttachment@@SAJPEAUISmAttachment@@IPEAVAsyncMediaServiceDocument@@PEAPEAV1@@Z; ChatServiceAttachment::CreateInstance(ISmAttachment *,uint,AsyncMediaServiceDocument *,ChatServiceAttachment * *)
0x180094192  mov     edi, eax
0x180094194  test    eax, eax
0x180094196  js      loc_180094234
0x18009419c  lea     rcx, [r13+1F8h]
0x1800941a3  lea     rdx, [rbp+60h+var_B8]
0x1800941a7  call    ??$emplace_back@AEAV?$CComPtr@VChatServiceAttachment@@@ATL@@$0A@@?$vector@V?$CComPtr@VChatServiceAttachment@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceAttachment@@@ATL@@@utl@@@utl@@QEAA_NAEAV?$CComPtr@VChatServiceAttachment@@@ATL@@@Z; utl::vector<ATL::CComPtr<ChatServiceAttachment>,utl::allocator<ATL::CComPtr<ChatServiceAttachment>>>::emplace_back<ATL::CComPtr<ChatServiceAttachment> &,0>(ATL::CComPtr<ChatServiceAttachment> &)
0x1800941ac  test    al, al
0x1800941ae  jz      short loc_1800941F5
0x1800941b0  mov     rcx, [rbp+60h+var_90]
0x1800941b4  mov     rdx, [rbp+60h+var_B8]
0x1800941b8  mov     rax, [rcx]
0x1800941bb  mov     rdx, [rdx+100h]
0x1800941c2  mov     rax, [rax+68h]
0x1800941c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800941cb  lea     rcx, [rbp+60h+var_B8]
0x1800941cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800941d4  mov     rcx, [rbp+60h+var_A0]
0x1800941d8  test    rcx, rcx
0x1800941db  jz      short loc_1800941ED
0x1800941dd  mov     [rbp+60h+var_A0], rsi
0x1800941e1  mov     rax, [rcx]
0x1800941e4  mov     rax, [rax+10h]
0x1800941e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800941ed  add     ebx, r14d
0x1800941f0  jmp     loc_180094142
0x1800941f5  mov     ebx, 8007000Eh
0x1800941fa  xor     edx, edx
0x1800941fc  mov     ecx, ebx; int
0x1800941fe  mov     r9d, 2A6h
0x180094204  call    Log_HREvent_68
0x180094209  lea     rcx, [rbp+60h+var_B8]
0x18009420d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180094212  mov     rcx, [rbp+60h+var_A0]
0x180094216  test    rcx, rcx
0x180094219  jz      loc_180094135
0x18009421f  mov     [rbp+60h+var_A0], rsi
0x180094223  mov     rax, [rcx]
0x180094226  mov     rax, [rax+10h]
0x18009422a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009422f  jmp     loc_180094135
0x180094234  mov     r9d, 2A4h
0x18009423a  mov     edx, r14d
0x18009423d  mov     ecx, edi; int
  ... truncated ...
```
