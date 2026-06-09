# CMessagingNode::_WriteMessageAttachments(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,ISmMessage *)

- ea: `0x1800b7c98`
- end: `0x1800b8501`
- name: `?_WriteMessageAttachments@CMessagingNode@@AEBAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEAUISmMessage@@@Z`
- size: `2153`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800b8508`

## callees

- `0x180015050`
- `0x180030bd0`
- `0x180035e4c`
- `0x18006b108`
- `0x180084738`
- `0x1800848b4`
- `0x180084ab8`
- `0x18009201c`
- `0x1800b5cf4`
- `0x1800b5d68`
- `0x1800b5d9c`
- `0x1800b60b8`
- `0x1800b7c98`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800b8072`
- `msvcrt!_wcsnicmp` at `0x1800b8072`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800b8198`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800b8263`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800b8198`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800b8263`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b81ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b820a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b8286`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b8291`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b81ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b820a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b8286`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b8291`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b82e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b82e6`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x1800b80b5`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x1800b80b5`

## string_xrefs

- `0x1800b7ddd`: `Windows.Data.Json.JsonObject`
- `0x1800b7cd8`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
__int64 __fastcall CMessagingNode::_WriteMessageAttachments(__int64 a1, __int64 **a2, __int64 *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rax
  __int64 (__fastcall *v10)(__int64 *, __int64 *); // rbx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  __int64 v16; // rax
  int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // rsi
  __int64 v19; // rbx
  __int64 (__fastcall **v20)(_QWORD, GUID *, __int64); // rax
  __int64 (__fastcall *v21)(_QWORD, GUID *, __int64); // rdi
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, PVOID, __int64 *); // rbx
  char v25; // r8
  HSTRING_HEADER *v26; // rax
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64); // rsi
  __int64 v28; // rbx
  __int64 (__fastcall **v29)(_QWORD, GUID *, __int64); // rax
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64); // rdi
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, PVOID, __int64 *); // rbx
  char v34; // r8
  HSTRING_HEADER *v35; // rax
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64); // rsi
  __int64 v37; // rbx
  __int64 (__fastcall **v38)(_QWORD, GUID *, __int64); // rax
  __int64 (__fastcall *v39)(_QWORD, GUID *, __int64); // rdi
  int v40; // eax
  int v41; // eax
  __int64 *v42; // rdi
  __int64 v43; // rsi
  const WCHAR *v44; // rbx
  unsigned __int64 v45; // rcx
  signed int v46; // eax
  unsigned int v47; // eax
  __int64 (__fastcall ***v48)(_QWORD, GUID *, __int64); // rsi
  __int64 v49; // rbx
  __int64 (__fastcall **v50)(_QWORD, GUID *, __int64); // rax
  __int64 (__fastcall *v51)(_QWORD, GUID *, __int64); // rdi
  __int64 v52; // rcx
  int v53; // eax
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  int v57; // eax
  __int64 *v58; // rsi
  __int64 v59; // rbx
  __int64 v60; // rax
  __int64 (__fastcall *v61)(__int64 *, GUID *, __int64); // rdi
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  GUID *v64; // [rsp+48h] [rbp-B8h]
  __int64 v65; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v66; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v68; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v69)(_QWORD, GUID *, __int64); // [rsp+70h] [rbp-90h] BYREF
  wchar_t *String2; // [rsp+78h] [rbp-88h] BYREF
  __int64 v71; // [rsp+80h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v73[2]; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR sourceString; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v75; // [rsp+A0h] [rbp-60h] BYREF
  int v76; // [rsp+A4h] [rbp-5Ch] BYREF
  __int64 v77; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall ***v78[2])(_QWORD, GUID *, __int64); // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v79[264]; // [rsp+C0h] [rbp-40h] BYREF

  v78[0] = 0;
  v64 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonArray",
    0x1Cu,
    0x1Bu);
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>((__int64)v64, v78);
  v7 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent_99(v6);
LABEL_71:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v78);
    return v7;
  }
  v68 = 0;
  v8 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
         v78,
         (__int64)&v68);
  v7 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_99(v8);
LABEL_70:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
    goto LABEL_71;
  }
  v9 = *a3;
  v67 = 0;
  v10 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(v9 + 240);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  v11 = v10(a3, &v67);
  v7 = v11;
  if ( v11 < 0 )
  {
LABEL_6:
    Log_HREvent_99(v11);
LABEL_69:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
    goto LABEL_70;
  }
  while ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v67 + 24LL))(v67) )
  {
    v65 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 32LL))(v67, &v65);
    v7 = v12;
    if ( v12 < 0 )
    {
      Log_HREvent_99(v12);
      goto LABEL_44;
    }
    v69 = 0;
    v64 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v13 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
            (__int64)v64,
            &v69);
    v7 = v13;
    if ( v13 < 0
      || (v75 = 0,
          v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v65 + 144LL))(v65, &v75),
          v7 = v13,
          v13 < 0)
      || (v13 = StringCchPrintfW(v79, 0x104u, L"%lu", v75), v7 = v13, v13 < 0) )
    {
      Log_HREvent_99(v13);
      goto LABEL_43;
    }
    v14 = *(_QWORD *)(a1 + 136);
    v66 = 0;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v79);
    v17 = v15(v14, *(_QWORD *)(v16 + 24), &v66);
    v7 = v17;
    if ( v17 < 0 )
      goto LABEL_58;
    v18 = v69;
    v19 = v66;
    v20 = *v69;
    v64 = 0;
    v21 = v20[7];
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Id", 3u, 2u);
    v17 = v21(v18, v64, v19);
    v7 = v17;
    if ( v17 < 0 )
    {
LABEL_58:
      Log_HREvent_99(v17);
      goto LABEL_42;
    }
    String2 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v65 + 48LL))(v65, &String2);
    v7 = v22;
    if ( v22 < 0 )
      goto LABEL_55;
    v23 = *(_QWORD *)(a1 + 136);
    v24 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v23 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&String2, v25);
    v22 = v24(v23, v26[1].Reserved.Reserved1, &v66);
    v7 = v22;
    if ( v22 < 0 )
      goto LABEL_55;
    v27 = v69;
    v28 = v66;
    v29 = *v69;
    v64 = 0;
    v30 = v29[7];
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"MIME type", 0xAu, 9u);
    v22 = v30(v27, v64, v28);
    v7 = v22;
    if ( v22 < 0 )
    {
LABEL_55:
      Log_HREvent_99(v22);
      goto LABEL_41;
    }
    bstrString = 0;
    v31 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v65 + 152LL))(v65, &bstrString);
    v7 = v31;
    if ( v31 < 0 )
      goto LABEL_52;
    v32 = *(_QWORD *)(a1 + 136);
    v33 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v32 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&bstrString, v34);
    v31 = v33(v32, v35[1].Reserved.Reserved1, &v66);
    v7 = v31;
    if ( v31 < 0 )
      goto LABEL_52;
    v36 = v69;
    v37 = v66;
    v38 = *v69;
    v64 = 0;
    v39 = v38[7];
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Path", 5u, 4u);
    v31 = v39(v36, v64, v37);
    v7 = v31;
    if ( v31 < 0 )
    {
LABEL_52:
      Log_HREvent_99(v31);
      goto LABEL_40;
    }
    if ( !_wcsnicmp(L"text/plain", String2, 0xAu) )
    {
      v71 = 0;
      v40 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 24LL))(v65, 0, &v71);
      v7 = v40;
      if ( v40 < 0 )
      {
        Log_HREvent_99(v40);
        goto LABEL_38;
      }
      sourceString = 0;
      v41 = ReadStreamContent(v71, &sourceString, 0xFFFFFFFFLL);
      v7 = v41;
      if ( v41 < 0 )
        goto LABEL_36;
      v42 = *(__int64 **)(a1 + 136);
      v43 = *v42;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
      v44 = sourceString;
      v45 = -1;
      v64 = 0;
      v73[0] = 0;
      do
        ++v45;
      while ( sourceString[v45] );
      v46 = ULongLongToULong(v45, v73);
      if ( v46 < 0 )
      {
        RaiseException(v46, 1u, 0, 0);
        __debugbreak();
      }
      v47 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v73[0]);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v44, v47, v73[0]);
      v41 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(v43 + 80))(v42, v64, &v66);
      v7 = v41;
      if ( v41 < 0 )
        goto LABEL_36;
      v48 = v69;
      v49 = v66;
      v50 = *v69;
      v64 = 0;
      v51 = v50[7];
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Text", 5u, 4u);
      v41 = v51(v48, v64, v49);
      v7 = v41;
      if ( v41 < 0 )
      {
LABEL_36:
        Log_HREvent_99(v41);
        if ( sourceString )
          operator delete[]((void *)sourceString);
LABEL_38:
        v55 = v71;
        if ( v71 )
        {
          v71 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
        }
LABEL_40:
        SysFreeString(bstrString);
LABEL_41:
        SysFreeString(String2);
LABEL_42:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
LABEL_43:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
LABEL_44:
        v56 = v65;
        if ( v65 )
        {
          v65 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        }
        goto LABEL_69;
      }
      if ( sourceString )
        operator delete[]((void *)sourceString);
      v52 = v71;
      if ( v71 )
      {
        v71 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
    }
    v77 = 0;
    v53 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v69,
            (__int64)&v77);
    v7 = v53;
    if ( v53 < 0
      || (v53 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 104LL))(v68, v77), v7 = v53, v53 < 0) )
    {
      Log_HREvent_99(v53);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
      goto LABEL_40;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
    SysFreeString(bstrString);
    SysFreeString(String2);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
    v54 = v65;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
  }
  v76 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v68 + 56LL))(v68, &v76);
  v7 = v11;
  if ( v11 < 0 )
    goto LABEL_6;
  if ( v76 )
  {
    *(_QWORD *)v73 = 0;
    v57 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            v78,
            (__int64)v73);
    v7 = v57;
    if ( v57 < 0 )
      goto LABEL_68;
    v58 = *a2;
    v59 = *(_QWORD *)v73;
    v60 = **a2;
    v64 = 0;
    v61 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64))(v60 + 56);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Attachments", 0xCu, 0xBu);
    v57 = v61(v58, v64, v59);
    v7 = v57;
    if ( v57 < 0 )
    {
LABEL_68:
      Log_HREvent_99(v57);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v73);
      goto LABEL_69;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v73);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v78);
  return 0;
}

```

## disassembly

```asm
0x1800b7c98  push    rbp
0x1800b7c9a  push    rbx
0x1800b7c9b  push    rsi
0x1800b7c9c  push    rdi
0x1800b7c9d  push    r12
0x1800b7c9f  push    r14
0x1800b7ca1  push    r15
0x1800b7ca3  lea     rbp, [rsp-1E0h]
0x1800b7cab  sub     rsp, 2E0h
0x1800b7cb2  mov     rax, cs:__security_cookie
0x1800b7cb9  xor     rax, rsp
0x1800b7cbc  mov     [rbp+210h+var_40], rax
0x1800b7cc3  xor     r12d, r12d
0x1800b7cc6  mov     rdi, r8
0x1800b7cc9  mov     r15, rdx
0x1800b7ccc  mov     [rbp+210h+var_260], r12
0x1800b7cd0  mov     r14, rcx
0x1800b7cd3  mov     [rsp+310h+var_2C8], r12
0x1800b7cd8  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800b7cdf  lea     r9d, [r12+1Bh]; unsigned int
0x1800b7ce4  lea     r8d, [r12+1Ch]; unsigned int
0x1800b7ce9  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x1800b7cee  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b7cf3  mov     rcx, [rsp+310h+var_2C8]
0x1800b7cf8  lea     rdx, [rbp+210h+var_260]
0x1800b7cfc  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x1800b7d01  mov     ebx, eax
0x1800b7d03  test    eax, eax
0x1800b7d05  jns     short loc_1800B7D1E
0x1800b7d07  lea     edx, [r12+1]
0x1800b7d0c  mov     r9d, 209h
0x1800b7d12  mov     ecx, eax; int
0x1800b7d14  call    Log_HREvent_99
0x1800b7d19  jmp     loc_1800B84AB
0x1800b7d1e  lea     rdx, [rsp+310h+var_2A8]
0x1800b7d23  mov     [rsp+310h+var_2A8], r12
0x1800b7d28  lea     rcx, [rbp+210h+var_260]
0x1800b7d2c  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x1800b7d31  mov     ebx, eax
0x1800b7d33  test    eax, eax
0x1800b7d35  jns     short loc_1800B7D4E
0x1800b7d37  mov     edx, 1
0x1800b7d3c  mov     r9d, 20Ch
0x1800b7d42  mov     ecx, eax; int
0x1800b7d44  call    Log_HREvent_99
0x1800b7d49  jmp     loc_1800B84A1
0x1800b7d4e  mov     rax, [rdi]
0x1800b7d51  lea     rcx, [rsp+310h+var_2B0]
0x1800b7d56  mov     [rsp+310h+var_2B0], r12
0x1800b7d5b  mov     rbx, [rax+0F0h]
0x1800b7d62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b7d67  lea     rdx, [rsp+310h+var_2B0]
0x1800b7d6c  mov     rcx, rdi
0x1800b7d6f  mov     rax, rbx
0x1800b7d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d77  mov     ebx, eax
0x1800b7d79  test    eax, eax
0x1800b7d7b  jns     short loc_1800B7D94
0x1800b7d7d  mov     r9d, 20Fh
0x1800b7d83  mov     edx, 1
0x1800b7d88  mov     ecx, eax; int
0x1800b7d8a  call    Log_HREvent_99
0x1800b7d8f  jmp     loc_1800B8497
0x1800b7d94  mov     rcx, [rsp+310h+var_2B0]
0x1800b7d99  mov     rax, [rcx]
0x1800b7d9c  mov     rax, [rax+18h]
0x1800b7da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7da5  test    eax, eax
0x1800b7da7  jnz     loc_1800B83E2
0x1800b7dad  mov     rcx, [rsp+310h+var_2B0]
0x1800b7db2  lea     rdx, [rsp+310h+var_2C0]
0x1800b7db7  mov     [rsp+310h+var_2C0], r12
0x1800b7dbc  mov     rax, [rcx]
0x1800b7dbf  mov     rax, [rax+20h]
0x1800b7dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7dc8  mov     ebx, eax
0x1800b7dca  test    eax, eax
0x1800b7dcc  js      loc_1800B83CB
0x1800b7dd2  mov     r9d, 1Ch; unsigned int
0x1800b7dd8  mov     [rsp+310h+var_2A0], r12
0x1800b7ddd  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800b7de4  mov     [rsp+310h+var_2C8], r12
0x1800b7de9  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x1800b7dee  lea     r8d, [r9+1]; unsigned int
0x1800b7df2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b7df7  mov     rcx, [rsp+310h+var_2C8]
0x1800b7dfc  lea     rdx, [rsp+310h+var_2A0]
0x1800b7e01  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800b7e06  mov     ebx, eax
0x1800b7e08  test    eax, eax
0x1800b7e0a  js      loc_1800B83C3
0x1800b7e10  mov     rcx, [rsp+310h+var_2C0]
0x1800b7e15  lea     rdx, [rbp+210h+var_270]
0x1800b7e19  mov     [rbp+210h+var_270], r12d
0x1800b7e1d  mov     rax, [rcx]
0x1800b7e20  mov     rax, [rax+90h]
0x1800b7e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7e2c  mov     ebx, eax
0x1800b7e2e  test    eax, eax
0x1800b7e30  js      loc_1800B83BB
0x1800b7e36  mov     r9d, [rbp+210h+var_270]
0x1800b7e3a  lea     r8, aLu; "%lu"
0x1800b7e41  mov     edx, 104h; unsigned __int64
0x1800b7e46  lea     rcx, [rbp+210h+var_250]; unsigned __int16 *
0x1800b7e4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b7e4f  mov     ebx, eax
0x1800b7e51  test    eax, eax
0x1800b7e53  js      loc_1800B83A4
0x1800b7e59  mov     rdi, [r14+88h]
0x1800b7e60  lea     rcx, [rsp+310h+var_2B8]
0x1800b7e65  mov     [rsp+310h+var_2B8], r12
0x1800b7e6a  mov     rax, [rdi]
0x1800b7e6d  mov     rbx, [rax+50h]
0x1800b7e71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b7e76  lea     rdx, [rbp+210h+var_250]; sourceString
0x1800b7e7a  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x1800b7e7f  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x1800b7e84  lea     r8, [rsp+310h+var_2B8]
0x1800b7e89  mov     rcx, rdi
0x1800b7e8c  mov     rdx, [rax+18h]
0x1800b7e90  mov     rax, rbx
0x1800b7e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7e98  mov     ebx, eax
0x1800b7e9a  test    eax, eax
0x1800b7e9c  js      loc_1800B839C
0x1800b7ea2  mov     rsi, [rsp+310h+var_2A0]
0x1800b7ea7  lea     rdx, aId_0; "Id"
0x1800b7eae  mov     rbx, [rsp+310h+var_2B8]
0x1800b7eb3  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x1800b7eb8  mov     r9d, 2; unsigned int
0x1800b7ebe  mov     rax, [rsi]
0x1800b7ec1  mov     [rsp+310h+var_2C8], r12
0x1800b7ec6  lea     r8d, [r9+1]; unsigned int
0x1800b7eca  mov     rdi, [rax+38h]
0x1800b7ece  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b7ed3  mov     rdx, [rsp+310h+var_2C8]
0x1800b7ed8  mov     r8, rbx
0x1800b7edb  mov     rcx, rsi
0x1800b7ede  mov     rax, rdi
0x1800b7ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7ee6  mov     ebx, eax
0x1800b7ee8  test    eax, eax
0x1800b7eea  js      loc_1800B8385
0x1800b7ef0  mov     rcx, [rsp+310h+var_2C0]
0x1800b7ef5  lea     rdx, [rsp+310h+String2]
0x1800b7efa  mov     [rsp+310h+String2], r12
0x1800b7eff  mov     rax, [rcx]
0x1800b7f02  mov     rax, [rax+30h]
0x1800b7f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f0b  mov     ebx, eax
0x1800b7f0d  test    eax, eax
0x1800b7f0f  js      loc_1800B837D
0x1800b7f15  mov     rdi, [r14+88h]
0x1800b7f1c  lea     rcx, [rsp+310h+var_2B8]
0x1800b7f21  mov     rax, [rdi]
0x1800b7f24  mov     rbx, [rax+50h]
0x1800b7f28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b7f2d  lea     rdx, [rsp+310h+String2]
0x1800b7f32  lea     rcx, [rsp+310h+hstringHeader]
0x1800b7f37  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b7f3c  lea     r8, [rsp+310h+var_2B8]
0x1800b7f41  mov     rcx, rdi
0x1800b7f44  mov     rdx, [rax+18h]
0x1800b7f48  mov     rax, rbx
0x1800b7f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f50  mov     ebx, eax
0x1800b7f52  test    eax, eax
0x1800b7f54  js      loc_1800B8375
0x1800b7f5a  mov     rsi, [rsp+310h+var_2A0]
0x1800b7f5f  lea     rdx, aMimeType; "MIME type"
0x1800b7f66  mov     rbx, [rsp+310h+var_2B8]
0x1800b7f6b  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x1800b7f70  mov     r9d, 9; unsigned int
0x1800b7f76  mov     rax, [rsi]
0x1800b7f79  mov     [rsp+310h+var_2C8], r12
0x1800b7f7e  lea     r8d, [r9+1]; unsigned int
0x1800b7f82  mov     rdi, [rax+38h]
0x1800b7f86  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b7f8b  mov     rdx, [rsp+310h+var_2C8]
0x1800b7f90  mov     r8, rbx
0x1800b7f93  mov     rcx, rsi
0x1800b7f96  mov     rax, rdi
0x1800b7f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f9e  mov     ebx, eax
0x1800b7fa0  test    eax, eax
0x1800b7fa2  js      loc_1800B835E
0x1800b7fa8  mov     rcx, [rsp+310h+var_2C0]
0x1800b7fad  lea     rdx, [rbp+210h+bstrString]
0x1800b7fb1  mov     [rbp+210h+bstrString], r12
0x1800b7fb5  mov     rax, [rcx]
0x1800b7fb8  mov     rax, [rax+98h]
0x1800b7fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7fc4  mov     ebx, eax
0x1800b7fc6  test    eax, eax
0x1800b7fc8  js      loc_1800B8356
0x1800b7fce  mov     rdi, [r14+88h]
0x1800b7fd5  lea     rcx, [rsp+310h+var_2B8]
0x1800b7fda  mov     rax, [rdi]
0x1800b7fdd  mov     rbx, [rax+50h]
0x1800b7fe1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b7fe6  lea     rdx, [rbp+210h+bstrString]
0x1800b7fea  lea     rcx, [rsp+310h+hstringHeader]
0x1800b7fef  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b7ff4  lea     r8, [rsp+310h+var_2B8]
0x1800b7ff9  mov     rcx, rdi
0x1800b7ffc  mov     rdx, [rax+18h]
0x1800b8000  mov     rax, rbx
0x1800b8003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8008  mov     ebx, eax
0x1800b800a  test    eax, eax
0x1800b800c  js      loc_1800B834E
0x1800b8012  mov     rsi, [rsp+310h+var_2A0]
0x1800b8017  lea     rdx, aPath; "Path"
0x1800b801e  mov     rbx, [rsp+310h+var_2B8]
0x1800b8023  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x1800b8028  mov     r9d, 4; unsigned int
0x1800b802e  mov     rax, [rsi]
0x1800b8031  mov     [rsp+310h+var_2C8], r12
0x1800b8036  lea     r8d, [r9+1]; unsigned int
0x1800b803a  mov     rdi, [rax+38h]
0x1800b803e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b8043  mov     rdx, [rsp+310h+var_2C8]
0x1800b8048  mov     r8, rbx
0x1800b804b  mov     rcx, rsi
0x1800b804e  mov     rax, rdi
0x1800b8051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8056  mov     ebx, eax
0x1800b8058  test    eax, eax
0x1800b805a  js      loc_1800B8337
0x1800b8060  mov     rdx, [rsp+310h+String2]; String2
0x1800b8065  lea     rcx, aTextPlain_2; "text/plain"
0x1800b806c  mov     r8d, 0Ah; MaxCount
0x1800b8072  call    cs:__imp__wcsnicmp
0x1800b8078  test    eax, eax
0x1800b807a  jnz     loc_1800B81B7
0x1800b8080  mov     rcx, [rsp+310h+var_2C0]
0x1800b8085  lea     r8, [rbp+210h+var_290]
0x1800b8089  mov     [rbp+210h+var_290], r12
0x1800b808d  xor     edx, edx
0x1800b808f  mov     rax, [rcx]
0x1800b8092  mov     rax, [rax+18h]
0x1800b8096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b809b  mov     ebx, eax
0x1800b809d  test    eax, eax
0x1800b809f  js      loc_1800B82F8
0x1800b80a5  mov     rcx, [rbp+210h+var_290]
0x1800b80a9  lea     rdx, [rbp+210h+sourceString]
0x1800b80ad  or      r8d, 0FFFFFFFFh
0x1800b80b1  mov     [rbp+210h+sourceString], r12
0x1800b80b5  call    cs:__imp_ReadStreamContent
0x1800b80bb  mov     ebx, eax
0x1800b80bd  test    eax, eax
0x1800b80bf  js      loc_1800B82ED
0x1800b80c5  mov     rdi, [r14+88h]
0x1800b80cc  lea     rcx, [rsp+310h+var_2B8]
0x1800b80d1  mov     rsi, [rdi]
0x1800b80d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b80d9  mov     rbx, [rbp+210h+sourceString]
0x1800b80dd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b80e1  mov     [rsp+310h+var_2C8], r12
0x1800b80e6  mov     [rbp+210h+var_280], r12d
0x1800b80ea  inc     rcx; unsigned __int64
0x1800b80ed  cmp     [rbx+rcx*2], r12w
0x1800b80f2  jnz     short loc_1800B80EA
0x1800b80f4  lea     rdx, [rbp+210h+var_280]; unsigned int *
0x1800b80f8  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800b80fd  test    eax, eax
0x1800b80ff  js      loc_1800B82DA
0x1800b8105  mov     ecx, [rbp+210h+var_280]; unsigned int
0x1800b8108  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b810d  mov     r9d, [rbp+210h+var_280]; unsigned int
0x1800b8111  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x1800b8116  mov     r8d, eax; unsigned int
0x1800b8119  mov     rdx, rbx; sourceString
0x1800b811c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b8121  mov     rdx, [rsp+310h+var_2C8]
0x1800b8126  lea     r8, [rsp+310h+var_2B8]
0x1800b812b  mov     rax, [rsi+50h]
0x1800b812f  mov     rcx, rdi
0x1800b8132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8137  mov     ebx, eax
0x1800b8139  test    eax, eax
0x1800b813b  js      loc_1800B82CF
0x1800b8141  mov     rsi, [rsp+310h+var_2A0]
0x1800b8146  lea     rdx, aText_1; "Text"
0x1800b814d  mov     rbx, [rsp+310h+var_2B8]
0x1800b8152  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x1800b8157  mov     r9d, 4; unsigned int
0x1800b815d  mov     rax, [rsi]
0x1800b8160  mov     [rsp+310h+var_2C8], r12
0x1800b8165  lea     r8d, [r9+1]; unsigned int
0x1800b8169  mov     rdi, [rax+38h]
0x1800b816d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b8172  mov     rdx, [rsp+310h+var_2C8]
0x1800b8177  mov     r8, rbx
0x1800b817a  mov     rcx, rsi
0x1800b817d  mov     rax, rdi
0x1800b8180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8185  mov     ebx, eax
0x1800b8187  test    eax, eax
  ... truncated ...
```
