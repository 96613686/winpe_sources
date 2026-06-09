# _anonymous_namespace_::AppendRetryAttemptDataToJsonVector

- ea: `0x14003bf88`
- end: `0x14003c87c`
- name: `_anonymous_namespace_::AppendRetryAttemptDataToJsonVector`
- size: `2292`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003ca4c`

## callees

- `0x140008de4`
- `0x14003bf88`
- `0x14003cda0`
- `0x14003cf98`
- `0x14003cfb0`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003bfdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003c0aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003bfdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003c0aa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14003c016`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14003c016`

## string_xrefs

- `0x14003bfd5`: `Windows.Data.Json.JsonValue`
- `0x14003c0a3`: `Windows.Data.Json.JsonObject`
- `0x14003c029`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003c0d6`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003c1a2`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003c262`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003c34f`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003c40f`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003c500`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003c5c0`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003c6a7`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003c748`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall anonymous_namespace_::AppendRetryAttemptDataToJsonVector(__int64 a1, HSTRING a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  HSTRING v7; // rbx
  __int64 v8; // rcx
  int ActivationFactory; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  __int64 v13; // rcx
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // eax
  __int64 v19; // rdx
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v26; // rcx
  int v27; // eax
  unsigned int v28; // r8d
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v30; // rcx
  _QWORD *v31; // rcx
  __int64 v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v35; // rdi
  HSTRING_HEADER *v36; // rax
  int v37; // eax
  __int64 (__fastcall ***v38)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v39; // rcx
  _QWORD *v40; // rcx
  __int64 v41; // rcx
  _QWORD *v42; // rdx
  __int64 v43; // rbx
  __int64 (__fastcall *v44)(__int64, _QWORD *, _QWORD **); // rdi
  int v45; // eax
  unsigned int v46; // r8d
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v48; // rcx
  _QWORD *v49; // rcx
  __int64 v50; // rcx
  __int64 (__fastcall ***v51)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v52)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v53; // rdi
  HSTRING_HEADER *v54; // rax
  int v55; // eax
  __int64 (__fastcall ***v56)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v57; // rcx
  _QWORD *v58; // rcx
  __int64 v59; // rcx
  _QWORD *v60; // rdx
  __int64 v61; // rbx
  __int64 (__fastcall *v62)(__int64, _BYTE *, _QWORD **); // rdi
  _BYTE *v63; // rdx
  int v64; // eax
  unsigned int v65; // r8d
  __int64 (__fastcall ***v66)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v67; // rcx
  _QWORD *v68; // rcx
  __int64 v69; // rcx
  __int64 (__fastcall ***v70)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v71)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v72; // rdi
  HSTRING_HEADER *v73; // rax
  int v74; // eax
  __int64 (__fastcall ***v75)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v76; // rcx
  _QWORD *v77; // rcx
  __int64 v78; // rcx
  __int64 (__fastcall ***v79)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v80)(_QWORD, GUID *, _QWORD **); // rdi
  int v81; // eax
  __int64 (__fastcall ***v82)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v83; // rcx
  _QWORD *v84; // rcx
  __int64 v85; // rcx
  int v86; // eax
  __int64 (__fastcall ***v87)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v88; // rcx
  _QWORD *v89; // rcx
  __int64 v90; // rcx
  _QWORD *v91; // rcx
  __int64 (__fastcall ***v92)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v93; // rcx
  _QWORD *v94; // rcx
  __int64 v95; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string[2]; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v98; // [rsp+48h] [rbp-28h] BYREF
  __int64 v99; // [rsp+50h] [rbp-20h] BYREF
  __int64 (__fastcall ***v100)(_QWORD, GUID *, _QWORD **); // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  string[1] = a2;
  v98 = 0;
  v99 = 0;
  string[0] = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, string);
  if ( v4 < 0 )
  {
LABEL_130:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x14003C87BLL);
  }
  v7 = string[0];
  v8 = v99;
  if ( v99 )
  {
    v99 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  ActivationFactory = RoGetActivationFactory(v7, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v99);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
    v11 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
    }
    v13 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_QWORD *)a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v10;
  }
  v100 = 0;
  string[0] = 0;
  v15 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, string);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    goto LABEL_130;
  }
  v18 = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(
          (__int64)string[0],
          (__int64 *)&v100);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v18,
      (int)hstringHeader.Reserved.Reserved1);
    v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
    if ( v100 )
    {
      v100 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v20)[2])(v20);
    }
    v21 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
    }
    v23 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_QWORD *)a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v10;
  }
  v24 = v99;
  v25 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v99 + 72LL);
  v26 = v98;
  if ( v98 )
  {
    v98 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
  }
  v27 = v25(v24, v19, &v98);
  v10 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v27,
      (int)hstringHeader.Reserved.Reserved1);
    v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
    if ( v100 )
    {
      v100 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v29)[2])(v29);
    }
    v30 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
    }
    v32 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_QWORD *)a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    return v10;
  }
  v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
  v34 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v100)[7];
  v35 = v98;
  v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &hstringHeader,
          (const WCHAR **)&off_14006E480,
          v28);
  v37 = v34(v33, (GUID *)v36[1].Reserved.Reserved1, v35);
  v10 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v37,
      (int)hstringHeader.Reserved.Reserved1);
    v38 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
    if ( v100 )
    {
      v100 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v38)[2])(v38);
    }
    v39 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
    }
    v41 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_QWORD *)a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    return v10;
  }
  v42 = v98;
  if ( v98 )
  {
    v98 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v42 + 16LL))(v42);
    v42 = v98;
  }
  v43 = v99;
  v44 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD **))(*(_QWORD *)v99 + 72LL);
  if ( v42 )
  {
    v98 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v42 + 16LL))(v42);
  }
  v45 = v44(v43, v42, &v98);
  v10 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v45,
      (int)hstringHeader.Reserved.Reserved1);
    v47 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
    if ( v100 )
    {
      v100 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v47)[2])(v47);
    }
    v48 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    v49 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
    }
    v50 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_QWORD *)a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    return v10;
  }
  v51 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
  v52 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v100)[7];
  v53 = v98;
  v54 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_14006E470, v46);
  v55 = v52(v51, (GUID *)v54[1].Reserved.Reserved1, v53);
  v10 = v55;
  if ( v55 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v55,
      (int)hstringHeader.Reserved.Reserved1);
    v56 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
    if ( v100 )
    {
      v100 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v56)[2])(v56);
    }
    v57 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    v58 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v58 + 16LL))(v58);
    }
    v59 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_QWORD *)a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    return v10;
  }
  v60 = v98;
  if ( v98 )
  {
    v98 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
    v60 = v98;
  }
  if ( *(_QWORD *)(a1 + 24) )
  {
    v61 = v99;
    v62 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD **))(*(_QWORD *)v99 + 64LL);
    if ( v60 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
    }
    v63 = *(_BYTE **)(a1 + 24);
    LOBYTE(v63) = *v63;
    v64 = v62(v61, v63, &v98);
    v10 = v64;
    if ( v64 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v64,
        (int)hstringHeader.Reserved.Reserved1);
      v66 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
      if ( v100 )
      {
        v100 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v66)[2])(v66);
      }
      v67 = v99;
      if ( v99 )
      {
        v99 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      }
      v68 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v68 + 16LL))(v68);
      }
      v69 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_QWORD *)a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
      }
      return v10;
    }
    v70 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
    v71 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v100)[7];
    v72 = v98;
    v73 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_14006E478,
            v65);
    v74 = v71(v70, (GUID *)v73[1].Reserved.Reserved1, v72);
    v10 = v74;
    if ( v74 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v74,
        (int)hstringHeader.Reserved.Reserved1);
      v75 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
      if ( v100 )
      {
        v100 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v75)[2])(v75);
      }
      v76 = v99;
      if ( v99 )
      {
        v99 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      }
      v77 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v77 + 16LL))(v77);
      }
      v78 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_QWORD *)a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      }
      return v10;
    }
    v60 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
      v60 = v98;
    }
  }
  v79 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
  v80 = **v100;
  if ( v60 )
  {
    v98 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
  }
  v81 = v80(v79, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v98);
  v10 = v81;
  if ( v81 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v81,
      (int)hstringHeader.Reserved.Reserved1);
    v82 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
    if ( v100 )
    {
      v100 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v82)[2])(v82);
    }
    v83 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    }
    v84 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    }
    v85 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_QWORD *)a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
    return v10;
  }
  v86 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)a2 + 104LL))(*(_QWORD *)a2, v98);
  v10 = v86;
  if ( v86 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v86,
      (int)hstringHeader.Reserved.Reserved1);
    v87 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
    if ( v100 )
    {
      v100 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v87)[2])(v87);
    }
    v88 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    }
    v89 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v89 + 16LL))(v89);
    }
    v90 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_QWORD *)a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    }
    return v10;
  }
  v91 = v98;
  if ( v98 )
  {
    v98 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v91 + 16LL))(v91);
  }
  v92 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v100;
  if ( v100 )
  {
    v100 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v92)[2])(v92);
  }
  v93 = v99;
  if ( v99 )
  {
    v99 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
  }
  v94 = v98;
  if ( v98 )
  {
    v98 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v94 + 16LL))(v94);
  }
  v95 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 )
  {
    *(_QWORD *)a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
  }
  return 0;
}

```

## disassembly

```asm
0x14003bf88  mov     [rsp-28h+arg_10], rbx
0x14003bf8d  mov     [rsp-28h+arg_18], rsi
0x14003bf92  push    rbp
0x14003bf93  push    rdi
0x14003bf94  push    r12
0x14003bf96  push    r14
0x14003bf98  push    r15
0x14003bf9a  mov     rbp, rsp
0x14003bf9d  sub     rsp, 70h
0x14003bfa1  mov     rax, cs:__security_cookie
0x14003bfa8  xor     rax, rsp
0x14003bfab  mov     [rbp+var_10], rax
0x14003bfaf  mov     r14, rdx
0x14003bfb2  mov     r15, rcx
0x14003bfb5  mov     [rbp+var_30], rdx
0x14003bfb9  xor     r12d, r12d
0x14003bfbc  mov     [rbp+var_28], r12
0x14003bfc0  mov     [rbp+var_20], r12
0x14003bfc4  mov     [rbp+string], r12
0x14003bfc8  lea     r9, [rbp+string]; string
0x14003bfcc  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14003bfd0  lea     edx, [r12+1Bh]; length
0x14003bfd5  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x14003bfdc  call    cs:__imp_WindowsCreateStringReference
0x14003bfe2  test    eax, eax
0x14003bfe4  js      loc_14003C874
0x14003bfea  mov     rbx, [rbp+string]
0x14003bfee  mov     rcx, [rbp+var_20]
0x14003bff2  test    rcx, rcx
0x14003bff5  jz      short loc_14003C008
0x14003bff7  mov     [rbp+var_20], r12
0x14003bffb  mov     rax, [rcx]
0x14003bffe  mov     rax, [rax+10h]
0x14003c002  call    _guard_dispatch_icall
0x14003c007  nop
0x14003c008  lea     r8, [rbp+var_20]
0x14003c00c  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x14003c013  mov     rcx, rbx
0x14003c016  call    cs:__imp_RoGetActivationFactory
0x14003c01c  mov     ebx, eax
0x14003c01e  test    eax, eax
0x14003c020  jns     short loc_14003C08E
0x14003c022  mov     rcx, [rbp+28h]; this
0x14003c026  mov     r9d, eax; char *
0x14003c029  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003c030  mov     edx, 31h ; '1'; void *
0x14003c035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003c03a  nop
0x14003c03b  mov     rcx, [rbp+var_20]
0x14003c03f  test    rcx, rcx
0x14003c042  jz      short loc_14003C055
0x14003c044  mov     [rbp+var_20], r12
0x14003c048  mov     rax, [rcx]
0x14003c04b  mov     rax, [rax+10h]
0x14003c04f  call    _guard_dispatch_icall
0x14003c054  nop
0x14003c055  mov     rcx, [rbp+var_28]
0x14003c059  test    rcx, rcx
0x14003c05c  jz      short loc_14003C06F
0x14003c05e  mov     [rbp+var_28], r12
0x14003c062  mov     rax, [rcx]
0x14003c065  mov     rax, [rax+10h]
0x14003c069  call    _guard_dispatch_icall
0x14003c06e  nop
0x14003c06f  mov     rcx, [r14]
0x14003c072  test    rcx, rcx
0x14003c075  jz      short loc_14003C087
0x14003c077  mov     [r14], r12
0x14003c07a  mov     rax, [rcx]
0x14003c07d  mov     rax, [rax+10h]
0x14003c081  call    _guard_dispatch_icall
0x14003c086  nop
0x14003c087  mov     eax, ebx
0x14003c089  jmp     loc_14003C847
0x14003c08e  mov     [rbp+var_18], r12
0x14003c092  mov     [rbp+string], r12
0x14003c096  lea     r9, [rbp+string]; string
0x14003c09a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14003c09e  mov     edx, 1Ch; length
0x14003c0a3  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x14003c0aa  call    cs:__imp_WindowsCreateStringReference
0x14003c0b0  test    eax, eax
0x14003c0b2  js      loc_14003C86C
0x14003c0b8  lea     rdx, [rbp+var_18]
0x14003c0bc  mov     rcx, [rbp+string]
0x14003c0c0  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>)
0x14003c0c5  mov     ebx, eax
0x14003c0c7  test    eax, eax
0x14003c0c9  jns     loc_14003C153
0x14003c0cf  mov     rcx, [rbp+28h]; this
0x14003c0d3  mov     r9d, eax; char *
0x14003c0d6  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003c0dd  mov     edx, 35h ; '5'; void *
0x14003c0e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003c0e7  nop
0x14003c0e8  mov     rcx, [rbp+var_18]
0x14003c0ec  test    rcx, rcx
0x14003c0ef  jz      short loc_14003C102
0x14003c0f1  mov     [rbp+var_18], r12
0x14003c0f5  mov     rax, [rcx]
0x14003c0f8  mov     rax, [rax+10h]
0x14003c0fc  call    _guard_dispatch_icall
0x14003c101  nop
0x14003c102  mov     rcx, [rbp+var_20]
0x14003c106  test    rcx, rcx
0x14003c109  jz      short loc_14003C11C
0x14003c10b  mov     [rbp+var_20], r12
0x14003c10f  mov     rax, [rcx]
0x14003c112  mov     rax, [rax+10h]
0x14003c116  call    _guard_dispatch_icall
0x14003c11b  nop
0x14003c11c  mov     rcx, [rbp+var_28]
0x14003c120  test    rcx, rcx
0x14003c123  jz      short loc_14003C136
0x14003c125  mov     [rbp+var_28], r12
0x14003c129  mov     rax, [rcx]
0x14003c12c  mov     rax, [rax+10h]
0x14003c130  call    _guard_dispatch_icall
0x14003c135  nop
0x14003c136  mov     rcx, [r14]
0x14003c139  test    rcx, rcx
0x14003c13c  jz      short loc_14003C14E
0x14003c13e  mov     [r14], r12
0x14003c141  mov     rax, [rcx]
0x14003c144  mov     rax, [rax+10h]
0x14003c148  call    _guard_dispatch_icall
0x14003c14d  nop
0x14003c14e  jmp     loc_14003C087
0x14003c153  mov     rbx, [rbp+var_20]
0x14003c157  mov     rax, [rbx]
0x14003c15a  mov     rdi, [rax+48h]
0x14003c15e  mov     rcx, [rbp+var_28]
0x14003c162  test    rcx, rcx
0x14003c165  jz      short loc_14003C178
0x14003c167  mov     [rbp+var_28], r12
0x14003c16b  mov     rdx, [rcx]
0x14003c16e  mov     rax, [rdx+10h]
0x14003c172  call    _guard_dispatch_icall
0x14003c177  nop
0x14003c178  movd    xmm1, dword ptr [r15+10h]
0x14003c17e  cvtdq2pd xmm1, xmm1
0x14003c182  lea     r8, [rbp+var_28]
0x14003c186  mov     rcx, rbx
0x14003c189  mov     rax, rdi
0x14003c18c  call    _guard_dispatch_icall
0x14003c191  mov     ebx, eax
0x14003c193  test    eax, eax
0x14003c195  jns     loc_14003C21F
0x14003c19b  mov     rcx, [rbp+28h]; this
0x14003c19f  mov     r9d, eax; char *
0x14003c1a2  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003c1a9  mov     edx, 37h ; '7'; void *
0x14003c1ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003c1b3  nop
0x14003c1b4  mov     rcx, [rbp+var_18]
0x14003c1b8  test    rcx, rcx
0x14003c1bb  jz      short loc_14003C1CE
0x14003c1bd  mov     [rbp+var_18], r12
0x14003c1c1  mov     rax, [rcx]
0x14003c1c4  mov     rax, [rax+10h]
0x14003c1c8  call    _guard_dispatch_icall
0x14003c1cd  nop
0x14003c1ce  mov     rcx, [rbp+var_20]
0x14003c1d2  test    rcx, rcx
0x14003c1d5  jz      short loc_14003C1E8
0x14003c1d7  mov     [rbp+var_20], r12
0x14003c1db  mov     rax, [rcx]
0x14003c1de  mov     rax, [rax+10h]
0x14003c1e2  call    _guard_dispatch_icall
0x14003c1e7  nop
0x14003c1e8  mov     rcx, [rbp+var_28]
0x14003c1ec  test    rcx, rcx
0x14003c1ef  jz      short loc_14003C202
0x14003c1f1  mov     [rbp+var_28], r12
0x14003c1f5  mov     rax, [rcx]
0x14003c1f8  mov     rax, [rax+10h]
0x14003c1fc  call    _guard_dispatch_icall
0x14003c201  nop
0x14003c202  mov     rcx, [r14]
0x14003c205  test    rcx, rcx
0x14003c208  jz      short loc_14003C21A
0x14003c20a  mov     [r14], r12
0x14003c20d  mov     rax, [rcx]
0x14003c210  mov     rax, [rax+10h]
0x14003c214  call    _guard_dispatch_icall
0x14003c219  nop
0x14003c21a  jmp     loc_14003C087
0x14003c21f  mov     rbx, [rbp+var_18]
0x14003c223  mov     rax, [rbx]
0x14003c226  mov     rsi, [rax+38h]
0x14003c22a  mov     rdi, [rbp+var_28]
0x14003c22e  lea     rdx, off_14006E480; "StatusCode"
0x14003c235  lea     rcx, [rbp+hstringHeader]
0x14003c239  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003c23e  nop
0x14003c23f  mov     r8, rdi
0x14003c242  mov     rdx, [rax+18h]
0x14003c246  mov     rcx, rbx
0x14003c249  mov     rax, rsi
0x14003c24c  call    _guard_dispatch_icall
0x14003c251  mov     ebx, eax
0x14003c253  test    eax, eax
0x14003c255  jns     loc_14003C2DF
0x14003c25b  mov     rcx, [rbp+28h]; this
0x14003c25f  mov     r9d, eax; char *
0x14003c262  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003c269  mov     edx, 38h ; '8'; void *
0x14003c26e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003c273  nop
0x14003c274  mov     rcx, [rbp+var_18]
0x14003c278  test    rcx, rcx
0x14003c27b  jz      short loc_14003C28E
0x14003c27d  mov     [rbp+var_18], r12
0x14003c281  mov     rax, [rcx]
0x14003c284  mov     rax, [rax+10h]
0x14003c288  call    _guard_dispatch_icall
0x14003c28d  nop
0x14003c28e  mov     rcx, [rbp+var_20]
0x14003c292  test    rcx, rcx
0x14003c295  jz      short loc_14003C2A8
0x14003c297  mov     [rbp+var_20], r12
0x14003c29b  mov     rax, [rcx]
0x14003c29e  mov     rax, [rax+10h]
0x14003c2a2  call    _guard_dispatch_icall
0x14003c2a7  nop
0x14003c2a8  mov     rcx, [rbp+var_28]
0x14003c2ac  test    rcx, rcx
0x14003c2af  jz      short loc_14003C2C2
0x14003c2b1  mov     [rbp+var_28], r12
0x14003c2b5  mov     rax, [rcx]
0x14003c2b8  mov     rax, [rax+10h]
0x14003c2bc  call    _guard_dispatch_icall
0x14003c2c1  nop
0x14003c2c2  mov     rcx, [r14]
0x14003c2c5  test    rcx, rcx
0x14003c2c8  jz      short loc_14003C2DA
0x14003c2ca  mov     [r14], r12
0x14003c2cd  mov     rax, [rcx]
0x14003c2d0  mov     rax, [rax+10h]
0x14003c2d4  call    _guard_dispatch_icall
0x14003c2d9  nop
0x14003c2da  jmp     loc_14003C087
0x14003c2df  mov     rdx, [rbp+var_28]
0x14003c2e3  test    rdx, rdx
0x14003c2e6  jz      short loc_14003C2FF
0x14003c2e8  mov     [rbp+var_28], r12
0x14003c2ec  mov     rax, [rdx]
0x14003c2ef  mov     rcx, rdx
0x14003c2f2  mov     rax, [rax+10h]
0x14003c2f6  call    _guard_dispatch_icall
0x14003c2fb  mov     rdx, [rbp+var_28]
0x14003c2ff  mov     rbx, [rbp+var_20]
0x14003c303  mov     rax, [rbx]
0x14003c306  mov     rdi, [rax+48h]
0x14003c30a  test    rdx, rdx
0x14003c30d  jz      short loc_14003C323
0x14003c30f  mov     [rbp+var_28], r12
0x14003c313  mov     rcx, [rdx]
0x14003c316  mov     rax, [rcx+10h]
0x14003c31a  mov     rcx, rdx
0x14003c31d  call    _guard_dispatch_icall
0x14003c322  nop
0x14003c323  mov     ecx, [r15+14h]
0x14003c327  xorps   xmm1, xmm1
0x14003c32a  cvtsi2sd xmm1, rcx
0x14003c32f  lea     r8, [rbp+var_28]
0x14003c333  mov     rcx, rbx
0x14003c336  mov     rax, rdi
0x14003c339  call    _guard_dispatch_icall
0x14003c33e  mov     ebx, eax
0x14003c340  test    eax, eax
0x14003c342  jns     loc_14003C3CC
0x14003c348  mov     rcx, [rbp+28h]; this
0x14003c34c  mov     r9d, eax; char *
0x14003c34f  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003c356  mov     edx, 3Bh ; ';'; void *
0x14003c35b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003c360  nop
0x14003c361  mov     rcx, [rbp+var_18]
0x14003c365  test    rcx, rcx
0x14003c368  jz      short loc_14003C37B
0x14003c36a  mov     [rbp+var_18], r12
0x14003c36e  mov     rax, [rcx]
0x14003c371  mov     rax, [rax+10h]
0x14003c375  call    _guard_dispatch_icall
0x14003c37a  nop
0x14003c37b  mov     rcx, [rbp+var_20]
0x14003c37f  test    rcx, rcx
0x14003c382  jz      short loc_14003C395
0x14003c384  mov     [rbp+var_20], r12
0x14003c388  mov     rax, [rcx]
0x14003c38b  mov     rax, [rax+10h]
0x14003c38f  call    _guard_dispatch_icall
0x14003c394  nop
0x14003c395  mov     rcx, [rbp+var_28]
0x14003c399  test    rcx, rcx
0x14003c39c  jz      short loc_14003C3AF
0x14003c39e  mov     [rbp+var_28], r12
0x14003c3a2  mov     rax, [rcx]
0x14003c3a5  mov     rax, [rax+10h]
  ... truncated ...
```
