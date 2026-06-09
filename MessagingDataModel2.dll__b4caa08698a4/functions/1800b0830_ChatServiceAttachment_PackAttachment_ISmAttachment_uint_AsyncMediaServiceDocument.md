# ChatServiceAttachment::_PackAttachment(ISmAttachment *,uint,AsyncMediaServiceDocument *)

- ea: `0x1800b0830`
- end: `0x1800b11f0`
- name: `?_PackAttachment@ChatServiceAttachment@@AEAAJPEAUISmAttachment@@IPEAVAsyncMediaServiceDocument@@@Z`
- size: `2496`
- prototype: `int(ChatServiceAttachment *__hidden this, struct ISmAttachment *, unsigned int, struct AsyncMediaServiceDocument *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

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
- `0x180096710`
- `0x180096d04`
- `0x1800b06a8`
- `0x1800b0830`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800b0f36`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800b102e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800b0f36`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800b102e`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x1800b0f0f`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x1800b0f0f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b091c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b091c`

## string_xrefs

- `0x1800b08fa`: `Windows.Data.Json.JsonValue`
- `0x1800b086e`: `Windows.Data.Json.JsonObject`
- `0x1800b0958`: `Windows.Data.Json.JsonObject`
- `0x1800b0adf`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceAttachment::_PackAttachment(
        ChatServiceAttachment *this,
        struct ISmAttachment *a2,
        unsigned int a3,
        struct AsyncMediaServiceDocument *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  int ActivationFactory; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  int v16; // ecx
  char v17; // r8
  const WCHAR *v18; // rdx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v21; // rax
  int v22; // eax
  char v23; // r8
  __int64 v24; // rsi
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v27; // rax
  int v28; // eax
  int v29; // eax
  struct AsyncMediaServiceDocument **v30; // rax
  char v31; // r8
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v34; // rax
  int v35; // eax
  char v36; // r8
  int v37; // ecx
  struct AsyncMediaServiceContent **v38; // rcx
  __int64 v39; // rsi
  __int64 v40; // rbx
  __int64 (__fastcall *v41)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v42; // rax
  char v43; // r8
  const WCHAR *v44; // rdx
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v47; // rax
  int v48; // eax
  char v49; // r8
  __int64 v50; // rsi
  __int64 v51; // rbx
  __int64 (__fastcall *v52)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v53; // rax
  int v54; // eax
  int v55; // ecx
  char v56; // r8
  const WCHAR *v57; // rdx
  __int64 v58; // rdi
  __int64 (__fastcall *v59)(__int64, PVOID, const WCHAR **); // rbx
  HSTRING_HEADER *v60; // rax
  int v61; // eax
  char v62; // r8
  __int64 v63; // rsi
  const WCHAR *v64; // rbx
  __int64 (__fastcall *v65)(__int64, PVOID, const WCHAR *, _BYTE *); // rdi
  HSTRING_HEADER *v66; // rax
  struct AsyncMediaServiceContent **v67; // rcx
  __int64 (__fastcall *v68)(__int64, PVOID, struct AsyncMediaServiceContent **); // rbx
  HSTRING_HEADER *v69; // rax
  int v70; // eax
  char v71; // r8
  __int64 v72; // rsi
  struct AsyncMediaServiceContent *v73; // rbx
  __int64 (__fastcall *v74)(__int64, PVOID, struct AsyncMediaServiceContent *, _BYTE *); // rdi
  HSTRING_HEADER *v75; // rax
  __int64 v76; // rax
  int v77; // eax
  __int64 v78; // rcx
  void (*v79)(void); // rax
  int v80; // eax
  int v81; // ecx
  __int64 v82; // rcx
  char v83; // r8
  const WCHAR *v84; // rdx
  __int64 v85; // rdi
  __int64 (__fastcall *v86)(__int64, PVOID, const WCHAR **); // rbx
  HSTRING_HEADER *v87; // rax
  int v88; // eax
  char v89; // r8
  __int64 v90; // rsi
  const WCHAR *v91; // rbx
  __int64 (__fastcall *v92)(__int64, PVOID, const WCHAR *, _BYTE *); // rdi
  HSTRING_HEADER *v93; // rax
  __int64 v94; // rcx
  int v95; // eax
  char v96; // r8
  __int64 v97; // rsi
  __int64 v98; // rbx
  __int64 (__fastcall *v99)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v100; // rax
  int v101; // eax
  char v102; // r8
  __int64 v103; // rsi
  __int64 v104; // rbx
  __int64 (__fastcall *v105)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v106; // rax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v109; // [rsp+48h] [rbp-91h]
  _BYTE v110[8]; // [rsp+50h] [rbp-89h] BYREF
  __int64 v111; // [rsp+58h] [rbp-81h] BYREF
  __int64 v112; // [rsp+60h] [rbp-79h] BYREF
  __int64 (__fastcall ***v113)(_QWORD, GUID *, __int64); // [rsp+68h] [rbp-71h] BYREF
  __int64 v114; // [rsp+70h] [rbp-69h] BYREF
  __int64 v115; // [rsp+78h] [rbp-61h] BYREF
  __int64 v116; // [rsp+80h] [rbp-59h] BYREF
  __int64 v117; // [rsp+88h] [rbp-51h] BYREF
  __int64 (__fastcall ***v118)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-49h] BYREF
  struct AsyncMediaServiceContent *v119; // [rsp+98h] [rbp-41h] BYREF
  __int64 v120; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v121; // [rsp+A8h] [rbp-31h] BYREF
  const WCHAR *v122; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v123; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v124; // [rsp+C0h] [rbp-19h] BYREF
  void *v125; // [rsp+C8h] [rbp-11h] BYREF
  const WCHAR *v126; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v127; // [rsp+D8h] [rbp-1h] BYREF
  __int64 (__fastcall ***v128)(_QWORD, GUID *, __int64); // [rsp+E0h] [rbp+7h] BYREF

  v128 = 0;
  v109 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v8 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v109, &v128);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v112 = 0;
    v10 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
            &v128,
            (__int64)&v112);
    v9 = v10;
    if ( v10 < 0 )
    {
      Log_HREvent_92(v10);
LABEL_5:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v112);
      goto LABEL_88;
    }
    v111 = 0;
    v109 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = RoGetActivationFactory(v109, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v111);
    v9 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      Log_HREvent_92(ActivationFactory);
LABEL_8:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
      goto LABEL_5;
    }
    v113 = 0;
    v109 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v12 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v109, &v113);
    v9 = v12;
    if ( v12 < 0 )
    {
      Log_HREvent_92(v12);
LABEL_11:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113);
      goto LABEL_8;
    }
    v114 = 0;
    v13 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
            &v113,
            (__int64)&v114);
    v9 = v13;
    if ( v13 < 0 )
    {
      Log_HREvent_92(v13);
LABEL_14:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114);
      goto LABEL_11;
    }
    v14 = *(_QWORD *)a2;
    v115 = 0;
    v15 = (*(__int64 (__fastcall **)(struct ISmAttachment *, __int64 *))(v14 + 48))(a2, &v115);
    v9 = v15;
    if ( v15 < 0 )
    {
      v16 = v15;
LABEL_17:
      Log_HREvent_92(v16);
LABEL_18:
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v115);
      goto LABEL_14;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             (char *)this + 24,
                             v115) )
    {
      v9 = -2147024882;
      v16 = -2147024882;
      goto LABEL_17;
    }
    v18 = (const WCHAR *)*((_QWORD *)this + 3);
    v117 = 0;
    v19 = v111;
    v122 = v18;
    v20 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v111 + 80LL);
    v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v122, v17);
    v22 = v20(v19, v21[1].Reserved.Reserved1, &v117);
    v9 = v22;
    if ( v22 < 0
      || (v24 = v114,
          v25 = v117,
          v110[0] = 0,
          v26 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v114 + 80LL),
          v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)&off_1800FD8A8,
                  v23),
          v22 = v26(v24, v27[1].Reserved.Reserved1, v25, v110),
          v9 = v22,
          v22 < 0) )
    {
      Log_HREvent_92(v22);
LABEL_23:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
      goto LABEL_18;
    }
    v118 = 0;
    v109 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v28 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v109, &v118);
    v9 = v28;
    if ( v28 < 0 )
    {
      Log_HREvent_92(v28);
LABEL_27:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
      goto LABEL_23;
    }
    v116 = 0;
    v29 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
            &v118,
            (__int64)&v116);
    v9 = v29;
    if ( v29 < 0 )
    {
      Log_HREvent_92(v29);
LABEL_30:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      goto LABEL_27;
    }
    LODWORD(v120) = a3;
    v30 = (struct AsyncMediaServiceDocument **)utl::_HashTable<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008,utl::pair<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 const,unsigned int>,utl::hash<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>,utl::equal_to<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>,utl::allocator<utl::pair<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 const,unsigned int>>,0>::_FindFirst<utl::_HashTable<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008,utl::pair<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 const,unsigned int>,utl::hash<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>,utl::equal_to<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>,utl::allocator<utl::pair<enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 const,unsigned int>>,0>::_FindFirstFind,enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>(
                                                 (char *)a4 + 56,
                                                 &v122,
                                                 &v120);
    v32 = v111;
    if ( (struct AsyncMediaServiceDocument *)((char *)a4 + 56) != *v30 )
    {
      v121 = 0;
      v33 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v111 + 80LL);
      v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_1800FD890,
              v31);
      v35 = v33(v32, v34[1].Reserved.Reserved1, &v121);
      v9 = v35;
      if ( v35 < 0
        || (v39 = v116,
            v40 = v121,
            v41 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v116 + 80LL),
            v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    (const WCHAR **)off_1800FD898,
                    v36),
            v35 = v41(v39, v42[1].Reserved.Reserved1, v40, v110),
            v9 = v35,
            v35 < 0) )
      {
        v37 = v35;
LABEL_34:
        Log_HREvent_92(v37);
LABEL_35:
        v38 = (struct AsyncMediaServiceContent **)&v121;
LABEL_36:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v38);
        goto LABEL_30;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               (char *)this + 96,
                               *((_QWORD *)a4 + 3)) )
      {
        v9 = -2147024882;
        v37 = -2147024882;
        goto LABEL_34;
      }
      v44 = (const WCHAR *)*((_QWORD *)this + 12);
      v45 = v111;
      v123 = 0;
      v122 = v44;
      v46 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v111 + 80LL);
      v47 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v122, v43);
      v48 = v46(v45, v47[1].Reserved.Reserved1, &v123);
      v9 = v48;
      if ( v48 < 0
        || (v50 = v116,
            v51 = v123,
            v52 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v116 + 80LL),
            v53 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    (const WCHAR **)off_1800FD878,
                    v49),
            v48 = v52(v50, v53[1].Reserved.Reserved1, v51, v110),
            v9 = v48,
            v48 < 0) )
      {
        Log_HREvent_92(v48);
LABEL_42:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
        goto LABEL_35;
      }
      v119 = 0;
      v54 = AsyncMediaServiceDocument::LookupContent(a4, a3, &v119);
      v9 = v54;
      if ( v54 < 0 )
      {
        v55 = v54;
LABEL_46:
        Log_HREvent_92(v55);
LABEL_47:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v119);
        goto LABEL_42;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               (char *)this + 128,
                               *((_QWORD *)v119 + 3)) )
      {
        v9 = -2147024882;
        v55 = -2147024882;
        goto LABEL_46;
      }
      v57 = (const WCHAR *)*((_QWORD *)this + 16);
      v58 = v111;
      v126 = 0;
      v122 = v57;
      v59 = *(__int64 (__fastcall **)(__int64, PVOID, const WCHAR **))(*(_QWORD *)v111 + 80LL);
      v60 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v122, v56);
      v61 = v59(v58, v60[1].Reserved.Reserved1, &v126);
      v9 = v61;
      if ( v61 < 0
        || (v63 = v116,
            v64 = v126,
            v65 = *(__int64 (__fastcall **)(__int64, PVOID, const WCHAR *, _BYTE *))(*(_QWORD *)v116 + 80LL),
            v66 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    (const WCHAR **)off_1800FD880,
                    v62),
            v61 = v65(v63, v66[1].Reserved.Reserved1, v64, v110),
            v9 = v61,
            v61 < 0) )
      {
        Log_HREvent_92(v61);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
        goto LABEL_47;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v119);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
      v67 = (struct AsyncMediaServiceContent **)&v121;
LABEL_79:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v67);
      v124 = 0;
      v95 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
              &v113,
              (__int64)&v124);
      v9 = v95;
      if ( v95 < 0
        || (v97 = v112,
            v98 = v124,
            v99 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v112 + 80LL),
            v100 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                     &hstringHeader,
                     (const WCHAR **)off_1800FD870,
                     v96),
            v95 = v99(v97, v100[1].Reserved.Reserved1, v98, v110),
            v9 = v95,
            v95 < 0) )
      {
        Log_HREvent_92(v95);
      }
      else
      {
        v127 = 0;
        v101 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                 &v118,
                 (__int64)&v127);
        v9 = v101;
        if ( v101 >= 0 )
        {
          v103 = v112;
          v104 = v127;
          v105 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v112 + 80LL);
          v106 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                   &hstringHeader,
                   (const WCHAR **)off_1800FD858,
                   v102);
          v101 = v105(v103, v106[1].Reserved.Reserved1, v104, v110);
          v9 = v101;
          if ( v101 >= 0 )
          {
            v101 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                     &v128,
                     (__int64)this + 256);
            v9 = v101;
            if ( v101 >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
              tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v115);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v112);
              v9 = 0;
              goto LABEL_88;
            }
          }
        }
        Log_HREvent_92(v101);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      }
      v38 = (struct AsyncMediaServiceContent **)&v124;
      goto LABEL_36;
    }
    v119 = 0;
    v68 = *(__int64 (__fastcall **)(__int64, PVOID, struct AsyncMediaServiceContent **))(*(_QWORD *)v111 + 80LL);
    v69 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800FD888,
            v31);
    v70 = v68(v32, v69[1].Reserved.Reserved1, &v119);
    v9 = v70;
    if ( v70 < 0
      || (v72 = v116,
          v73 = v119,
          v74 = *(__int64 (__fastcall **)(__int64, PVOID, struct AsyncMediaServiceContent *, _BYTE *))(*(_QWORD *)v116 + 80LL),
          v75 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD898,
                  v71),
          v70 = v74(v72, v75[1].Reserved.Reserved1, v73, v110),
          v9 = v70,
          v70 < 0) )
    {
      Log_HREvent_92(v70);
      goto LABEL_56;
    }
    v76 = *(_QWORD *)a2;
    v120 = 0;
    v77 = (*(__int64 (__fastcall **)(struct ISmAttachment *, _QWORD, __int64 *))(v76 + 24))(a2, 0, &v120);
    v9 = v77;
    if ( v77 < 0 )
    {
      Log_HREvent_92(v77);
      v78 = v120;
      if ( v120 )
      {
        v120 = 0;
        v79 = *(void (**)(void))(*(_QWORD *)v78 + 16LL);
LABEL_61:
        v79();
      }
LABEL_56:
      v38 = &v119;
      goto LABEL_36;
    }
    v125 = 0;
    v80 = ReadStreamContent(v120, &v125, 0xFFFFFFFFLL);
    v9 = v80;
    if ( v80 >= 0 )
    {
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              (char *)this + 64,
                              v125) )
      {
        v84 = (const WCHAR *)*((_QWORD *)this + 8);
        v85 = v111;
        v122 = 0;
        v126 = v84;
        v86 = *(__int64 (__fastcall **)(__int64, PVOID, const WCHAR **))(*(_QWORD *)v111 + 80LL);
        v87 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v126, v83);
        v88 = v86(v85, v87[1].Reserved.Reserved1, &v122);
        v9 = v88;
        if ( v88 >= 0 )
        {
          v90 = v116;
          v91 = v122;
          v92 = *(__int64 (__fastcall **)(__int64, PVOID, const WCHAR *, _BYTE *))(*(_QWORD *)v116 + 80LL);
          v93 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD860,
                  v89);
          v88 = v92(v90, v93[1].Reserved.Reserved1, v91, v110);
          v9 = v88;
          if ( v88 >= 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
            if ( v125 )
              operator delete[](v125);
            v94 = v120;
            if ( v120 )
            {
              v120 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
            }
            v67 = &v119;
            goto LABEL_79;
          }
        }
        Log_HREvent_92(v88);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
        goto LABEL_65;
      }
      v9 = -2147024882;
      v81 = -2147024882;
    }
    else
    {
      v81 = v80;
    }
    Log_HREvent_92(v81);
LABEL_65:
    if ( v125 )
      operator delete[](v125);
    v82 = v120;
    if ( !v120 )
      goto LABEL_56;
    v120 = 0;
    v79 = *(void (**)(void))(*(_QWORD *)v82 + 16LL);
    goto LABEL_61;
  }
  Log_HREvent_92(v8);
LABEL_88:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
  return v9;
}

```

## disassembly

```asm
0x1800b0830  push    rbp
0x1800b0832  push    rbx
0x1800b0833  push    rsi
0x1800b0834  push    rdi
0x1800b0835  push    r12
0x1800b0837  push    r13
0x1800b0839  push    r14
0x1800b083b  push    r15
0x1800b083d  lea     rbp, [rsp-1Fh]
0x1800b0842  sub     rsp, 0F8h
0x1800b0849  mov     rax, cs:__security_cookie
0x1800b0850  xor     rax, rsp
0x1800b0853  mov     [rbp+57h+var_48], rax
0x1800b0857  xor     edi, edi
0x1800b0859  mov     r13, r9
0x1800b085c  mov     r12d, r8d
0x1800b085f  mov     [rbp+57h+var_50], rdi
0x1800b0863  mov     r15, rdx
0x1800b0866  mov     [rsp+130h+var_E8], rdi
0x1800b086b  mov     r14, rcx
0x1800b086e  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800b0875  lea     esi, [rdi+1Ch]
0x1800b0878  mov     r9d, esi; unsigned int
0x1800b087b  lea     r8d, [rdi+1Dh]; unsigned int
0x1800b087f  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x1800b0884  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b0889  mov     rcx, [rsp+130h+var_E8]
0x1800b088e  lea     rdx, [rbp+57h+var_50]
0x1800b0892  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800b0897  mov     ebx, eax
0x1800b0899  test    eax, eax
0x1800b089b  jns     short loc_1800B08B0
0x1800b089d  lea     edx, [rdi+1]
0x1800b08a0  mov     ecx, eax; int
0x1800b08a2  lea     r9d, [rsi+68h]
0x1800b08a6  call    Log_HREvent_92
0x1800b08ab  jmp     loc_1800B11C5
0x1800b08b0  lea     rdx, [rbp+57h+var_D0]
0x1800b08b4  mov     [rbp+57h+var_D0], rdi
0x1800b08b8  lea     rcx, [rbp+57h+var_50]
0x1800b08bc  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x1800b08c1  mov     ebx, eax
0x1800b08c3  test    eax, eax
0x1800b08c5  jns     short loc_1800B08E7
0x1800b08c7  mov     edx, 1
0x1800b08cc  mov     r9d, 87h
0x1800b08d2  mov     ecx, eax; int
0x1800b08d4  call    Log_HREvent_92
0x1800b08d9  lea     rcx, [rbp+57h+var_D0]
0x1800b08dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b08e2  jmp     loc_1800B11C5
0x1800b08e7  mov     r9d, 1Bh; unsigned int
0x1800b08ed  mov     [rsp+130h+var_D8], rdi
0x1800b08f2  mov     r8d, esi; unsigned int
0x1800b08f5  mov     [rsp+130h+var_E8], rdi
0x1800b08fa  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800b0901  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x1800b0906  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b090b  mov     rcx, [rsp+130h+var_E8]
0x1800b0910  lea     r8, [rsp+130h+var_D8]
0x1800b0915  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800b091c  call    cs:__imp_RoGetActivationFactory
0x1800b0922  mov     ebx, eax
0x1800b0924  test    eax, eax
0x1800b0926  jns     short loc_1800B0946
0x1800b0928  mov     edx, 1
0x1800b092d  mov     r9d, 8Bh
0x1800b0933  mov     ecx, eax; int
0x1800b0935  call    Log_HREvent_92
0x1800b093a  lea     rcx, [rsp+130h+var_D8]
0x1800b093f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b0944  jmp     short loc_1800B08D9
0x1800b0946  mov     r9d, esi; unsigned int
0x1800b0949  mov     [rbp+57h+var_C8], rdi
0x1800b094d  mov     r8d, 1Dh; unsigned int
0x1800b0953  mov     [rsp+130h+var_E8], rdi
0x1800b0958  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800b095f  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x1800b0964  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b0969  mov     rcx, [rsp+130h+var_E8]
0x1800b096e  lea     rdx, [rbp+57h+var_C8]
0x1800b0972  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800b0977  mov     ebx, eax
0x1800b0979  test    eax, eax
0x1800b097b  jns     short loc_1800B099A
0x1800b097d  mov     edx, 1
0x1800b0982  mov     r9d, 8Fh
0x1800b0988  mov     ecx, eax; int
0x1800b098a  call    Log_HREvent_92
0x1800b098f  lea     rcx, [rbp+57h+var_C8]
0x1800b0993  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b0998  jmp     short loc_1800B093A
0x1800b099a  lea     rdx, [rbp+57h+var_C0]
0x1800b099e  mov     [rbp+57h+var_C0], rdi
0x1800b09a2  lea     rcx, [rbp+57h+var_C8]
0x1800b09a6  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x1800b09ab  mov     ebx, eax
0x1800b09ad  test    eax, eax
0x1800b09af  jns     short loc_1800B09CE
0x1800b09b1  mov     edx, 1
0x1800b09b6  mov     r9d, 92h
0x1800b09bc  mov     ecx, eax; int
0x1800b09be  call    Log_HREvent_92
0x1800b09c3  lea     rcx, [rbp+57h+var_C0]
0x1800b09c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b09cc  jmp     short loc_1800B098F
0x1800b09ce  mov     rax, [r15]
0x1800b09d1  lea     rdx, [rbp+57h+var_B8]
0x1800b09d5  mov     rcx, r15
0x1800b09d8  mov     [rbp+57h+var_B8], rdi
0x1800b09dc  mov     rax, [rax+30h]
0x1800b09e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b09e5  mov     ebx, eax
0x1800b09e7  test    eax, eax
0x1800b09e9  jns     short loc_1800B0A08
0x1800b09eb  mov     edx, 1
0x1800b09f0  mov     r9d, 96h
0x1800b09f6  mov     ecx, eax; int
0x1800b09f8  call    Log_HREvent_92
0x1800b09fd  lea     rcx, [rbp+57h+var_B8]
0x1800b0a01  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x1800b0a06  jmp     short loc_1800B09C3
0x1800b0a08  mov     rdx, [rbp+57h+var_B8]
0x1800b0a0c  lea     rcx, [r14+18h]
0x1800b0a10  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800b0a15  test    al, al
0x1800b0a17  jnz     short loc_1800B0A2A
0x1800b0a19  mov     ebx, 8007000Eh
0x1800b0a1e  xor     edx, edx
0x1800b0a20  mov     ecx, ebx
0x1800b0a22  mov     r9d, 97h
0x1800b0a28  jmp     short loc_1800B09F8
0x1800b0a2a  mov     rdx, [r14+18h]
0x1800b0a2e  lea     rcx, [rsp+130h+hstringHeader]
0x1800b0a33  mov     [rbp+57h+var_A8], rdi
0x1800b0a37  mov     rdi, [rsp+130h+var_D8]
0x1800b0a3c  mov     [rbp+57h+var_80], rdx
0x1800b0a40  lea     rdx, [rbp+57h+var_80]
0x1800b0a44  mov     rax, [rdi]
0x1800b0a47  mov     rbx, [rax+50h]
0x1800b0a4b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b0a50  lea     r8, [rbp+57h+var_A8]
0x1800b0a54  mov     rcx, rdi
0x1800b0a57  mov     rdx, [rax+18h]
0x1800b0a5b  mov     rax, rbx
0x1800b0a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a63  mov     ebx, eax
0x1800b0a65  test    eax, eax
0x1800b0a67  jns     short loc_1800B0A89
0x1800b0a69  mov     r9d, 9Bh
0x1800b0a6f  mov     edx, 1
0x1800b0a74  mov     ecx, eax; int
0x1800b0a76  call    Log_HREvent_92
0x1800b0a7b  lea     rcx, [rbp+57h+var_A8]
0x1800b0a7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b0a84  jmp     loc_1800B09FD
0x1800b0a89  mov     rsi, [rbp+57h+var_C0]
0x1800b0a8d  lea     rdx, off_1800FD8A8; "content_type"
0x1800b0a94  mov     rbx, [rbp+57h+var_A8]
0x1800b0a98  lea     rcx, [rsp+130h+hstringHeader]
0x1800b0a9d  mov     [rsp+130h+var_E0], 0
0x1800b0aa2  mov     rax, [rsi]
0x1800b0aa5  mov     rdi, [rax+50h]
0x1800b0aa9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b0aae  lea     r9, [rsp+130h+var_E0]
0x1800b0ab3  mov     r8, rbx
0x1800b0ab6  mov     rcx, rsi
0x1800b0ab9  mov     rdx, [rax+18h]
0x1800b0abd  mov     rax, rdi
0x1800b0ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0ac5  xor     esi, esi
0x1800b0ac7  mov     ebx, eax
0x1800b0ac9  test    eax, eax
0x1800b0acb  jns     short loc_1800B0AD5
0x1800b0acd  mov     r9d, 9Eh
0x1800b0ad3  jmp     short loc_1800B0A6F
0x1800b0ad5  mov     r9d, 1Ch; unsigned int
0x1800b0adb  mov     [rbp+57h+var_A0], rsi
0x1800b0adf  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800b0ae6  mov     [rsp+130h+var_E8], rsi
0x1800b0aeb  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x1800b0af0  lea     r8d, [r9+1]; unsigned int
0x1800b0af4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b0af9  mov     rcx, [rsp+130h+var_E8]
0x1800b0afe  lea     rdx, [rbp+57h+var_A0]
0x1800b0b02  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800b0b07  mov     ebx, eax
0x1800b0b09  test    eax, eax
0x1800b0b0b  jns     short loc_1800B0B2D
0x1800b0b0d  mov     edx, 1
0x1800b0b12  mov     r9d, 0A3h
0x1800b0b18  mov     ecx, eax; int
0x1800b0b1a  call    Log_HREvent_92
0x1800b0b1f  lea     rcx, [rbp+57h+var_A0]
0x1800b0b23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b0b28  jmp     loc_1800B0A7B
0x1800b0b2d  lea     rdx, [rbp+57h+var_B0]
0x1800b0b31  mov     [rbp+57h+var_B0], rsi
0x1800b0b35  lea     rcx, [rbp+57h+var_A0]
0x1800b0b39  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x1800b0b3e  mov     ebx, eax
0x1800b0b40  test    eax, eax
0x1800b0b42  jns     short loc_1800B0B61
0x1800b0b44  mov     edx, 1
0x1800b0b49  mov     r9d, 0A6h
0x1800b0b4f  mov     ecx, eax; int
0x1800b0b51  call    Log_HREvent_92
0x1800b0b56  lea     rcx, [rbp+57h+var_B0]
0x1800b0b5a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b0b5f  jmp     short loc_1800B0B1F
0x1800b0b61  lea     rbx, [r13+38h]
0x1800b0b65  mov     dword ptr [rbp+57h+var_90], r12d
0x1800b0b69  mov     rcx, rbx
0x1800b0b6c  lea     r8, [rbp+57h+var_90]
0x1800b0b70  lea     rdx, [rbp+57h+var_80]
0x1800b0b74  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@W4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@U?$pair@$$CBW4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@I@utl@@U?$hash@W4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@@4@U?$equal_to@W4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@@4@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@I@utl@@@4@$0A@@utl@@W4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@@?$_HashTable@W4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@U?$pair@$$CBW4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@I@utl@@U?$hash@W4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@@4@U?$equal_to@W4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@@4@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@I@utl@@@4@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBW4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@@Z; utl::_HashTable<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008,utl::pair<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 const,uint>,utl::hash<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>,utl::equal_to<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>,utl::allocator<utl::pair<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 const,uint>>,0>::_FindFirst<utl::_HashTable<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008,utl::pair<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 const,uint>,utl::hash<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>,utl::equal_to<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>,utl::allocator<utl::pair<Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 const,uint>>,0>::_FindFirstFind,Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008>(Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 const &)
0x1800b0b79  mov     rdi, [rsp+130h+var_D8]
0x1800b0b7e  lea     rcx, [rsp+130h+hstringHeader]
0x1800b0b83  cmp     rbx, [rax]
0x1800b0b86  jz      loc_1800B0E16
0x1800b0b8c  xor     r15d, r15d
0x1800b0b8f  lea     rdx, off_1800FD890; "AMS"
0x1800b0b96  mov     [rbp+57h+var_88], r15
0x1800b0b9a  mov     rax, [rdi]
0x1800b0b9d  mov     rbx, [rax+50h]
0x1800b0ba1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b0ba6  lea     r8, [rbp+57h+var_88]
0x1800b0baa  mov     rcx, rdi
0x1800b0bad  mov     rdx, [rax+18h]
0x1800b0bb1  mov     rax, rbx
0x1800b0bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0bb9  mov     ebx, eax
0x1800b0bbb  test    eax, eax
0x1800b0bbd  jns     short loc_1800B0BDF
0x1800b0bbf  mov     r9d, 0ADh
0x1800b0bc5  mov     edx, 1
0x1800b0bca  mov     ecx, eax; int
0x1800b0bcc  call    Log_HREvent_92
0x1800b0bd1  lea     rcx, [rbp+57h+var_88]
0x1800b0bd5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b0bda  jmp     loc_1800B0B56
0x1800b0bdf  mov     rsi, [rbp+57h+var_B0]
0x1800b0be3  lea     rdx, off_1800FD898; "location"
0x1800b0bea  mov     rbx, [rbp+57h+var_88]
0x1800b0bee  lea     rcx, [rsp+130h+hstringHeader]
0x1800b0bf3  mov     rax, [rsi]
0x1800b0bf6  mov     rdi, [rax+50h]
0x1800b0bfa  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b0bff  lea     r9, [rsp+130h+var_E0]
0x1800b0c04  mov     r8, rbx
0x1800b0c07  mov     rcx, rsi
0x1800b0c0a  mov     rdx, [rax+18h]
0x1800b0c0e  mov     rax, rdi
0x1800b0c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c16  mov     ebx, eax
0x1800b0c18  test    eax, eax
0x1800b0c1a  jns     short loc_1800B0C24
0x1800b0c1c  mov     r9d, 0B0h
0x1800b0c22  jmp     short loc_1800B0BC5
0x1800b0c24  mov     rdx, [r13+18h]
0x1800b0c28  lea     rcx, [r14+60h]
0x1800b0c2c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800b0c31  test    al, al
0x1800b0c33  jnz     short loc_1800B0C46
0x1800b0c35  mov     ebx, 8007000Eh
0x1800b0c3a  xor     edx, edx
0x1800b0c3c  mov     ecx, ebx
0x1800b0c3e  mov     r9d, 0B3h
0x1800b0c44  jmp     short loc_1800B0BCC
0x1800b0c46  mov     rdx, [r14+60h]
0x1800b0c4a  lea     rcx, [rsp+130h+hstringHeader]
0x1800b0c4f  mov     rdi, [rsp+130h+var_D8]
0x1800b0c54  mov     [rbp+57h+var_78], r15
0x1800b0c58  mov     [rbp+57h+var_80], rdx
0x1800b0c5c  lea     rdx, [rbp+57h+var_80]
0x1800b0c60  mov     rax, [rdi]
0x1800b0c63  mov     rbx, [rax+50h]
0x1800b0c67  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b0c6c  lea     r8, [rbp+57h+var_78]
0x1800b0c70  mov     rcx, rdi
0x1800b0c73  mov     rdx, [rax+18h]
0x1800b0c77  mov     rax, rbx
0x1800b0c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c7f  mov     ebx, eax
0x1800b0c81  test    eax, eax
0x1800b0c83  jns     short loc_1800B0CA5
0x1800b0c85  mov     r9d, 0B6h
0x1800b0c8b  mov     edx, 1
0x1800b0c90  mov     ecx, eax; int
0x1800b0c92  call    Log_HREvent_92
0x1800b0c97  lea     rcx, [rbp+57h+var_78]
0x1800b0c9b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b0ca0  jmp     loc_1800B0BD1
0x1800b0ca5  mov     rsi, [rbp+57h+var_B0]
0x1800b0ca9  lea     rdx, off_1800FD878; "object_id"
0x1800b0cb0  mov     rbx, [rbp+57h+var_78]
0x1800b0cb4  lea     rcx, [rsp+130h+hstringHeader]
0x1800b0cb9  mov     rax, [rsi]
0x1800b0cbc  mov     rdi, [rax+50h]
0x1800b0cc0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
  ... truncated ...
```
