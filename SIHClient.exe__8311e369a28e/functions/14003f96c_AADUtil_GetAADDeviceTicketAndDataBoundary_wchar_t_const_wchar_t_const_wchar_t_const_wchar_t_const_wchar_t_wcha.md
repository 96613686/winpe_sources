# AADUtil::GetAADDeviceTicketAndDataBoundary(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *,wchar_t * *)

- ea: `0x14003f96c`
- end: `0x140040214`
- name: `?GetAADDeviceTicketAndDataBoundary@AADUtil@@YAJPEB_W000PEAPEA_W1@Z`
- size: `2216`
- prototype: `__int64 __fastcall(const WCHAR *this, wchar_t *, wchar_t *, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400364ac`

## callees

- `0x140008de4`
- `0x1400374b0`
- `0x14003cf98`
- `0x14003cfb0`
- `0x14003f590`
- `0x14003f96c`
- `0x14004021c`
- `0x1400402a4`
- `0x140040574`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140040072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140040072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003faa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003fc07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003fdf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003fe84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003ff07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003ff35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003faa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003fc07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003fdf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003fe84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003ff07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003ff35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003fecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003fedb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003fffc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400400a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400400b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400401ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400401bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003fecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003fedb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003fffc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400400a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400400b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400401ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400401bc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14003fae1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14003fc42`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14003fae1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14003fc42`

## string_xrefs

- `0x14003fc00`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x14003fa9f`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x14003ff2e`: `client_TokenType`

## pseudocode

```c
__int64 __fastcall AADUtil::GetAADDeviceTicketAndDataBoundary(
        const WCHAR *this,
        wchar_t *a2,
        wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        wchar_t **a6)
{
  int v9; // ebx
  __int64 v10; // rdx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  HSTRING v14; // rbx
  void (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  int ActivationFactory; // eax
  void (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, PVOID, __int64 *); // rdi
  unsigned int v22; // r8d
  HSTRING_HEADER *v23; // rax
  int v24; // eax
  __int64 v25; // rdi
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  HSTRING v29; // rbx
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // r8d
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, __int64, PVOID, HSTRING); // rsi
  HSTRING v35; // rdi
  HSTRING_HEADER *v36; // rax
  int v37; // eax
  int v38; // eax
  unsigned int v39; // r8d
  __int64 v40; // rdx
  HSTRING v41; // rbx
  __int64 (__fastcall *v42)(HSTRING, PVOID); // rdi
  HSTRING_HEADER *v43; // rax
  HSTRING v44; // rcx
  HSTRING v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rbx
  __int64 (__fastcall *v48)(__int64, HSTRING, HSTRING, _BYTE *); // rsi
  HSTRING v49; // rdi
  HRESULT v50; // eax
  int v51; // edx
  unsigned int v52; // r8d
  unsigned __int64 v53; // r9
  HRESULT v54; // eax
  __int64 v55; // rdx
  __int64 v56; // rbx
  __int64 (__fastcall *v57)(__int64, HSTRING, HSTRING, _BYTE *); // rsi
  HSTRING v58; // rdi
  HRESULT v59; // eax
  int v60; // edx
  unsigned int v61; // r8d
  __int64 v62; // rbx
  __int64 (__fastcall *v63)(__int64, HSTRING, HSTRING, _BYTE *); // rsi
  HRESULT v64; // eax
  int v65; // edx
  unsigned int v66; // r8d
  HSTRING v67; // rdi
  HRESULT v68; // eax
  int v69; // edx
  unsigned int v70; // r8d
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rdi
  HSTRING v74; // rcx
  __int64 v75; // rdx
  char *StringRawBuffer; // rax
  const char *v77; // r9
  __int64 v78; // rcx
  HSTRING v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  void (__fastcall ***v86)(_QWORD, _QWORD, _QWORD); // rcx
  int v88; // [rsp+20h] [rbp-E0h]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER v91; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v92; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v93; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v94; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v95; // [rsp+90h] [rbp-70h] BYREF
  const WCHAR *v96; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v97[8]; // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall ***v98)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-58h] BYREF
  __int64 v99; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v100; // [rsp+B8h] [rbp-48h]
  __int64 v101; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v102; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v103; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v104; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v105; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v106; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v107; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v108; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v109; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v110; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v94 = this;
  v93 = (HSTRING)a2;
  v95 = a3;
  v96 = a4;
  if ( a6 )
  {
    *a6 = 0;
    v109 = 0;
    v104 = 0;
    if ( a2 && *a2 )
    {
      v9 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v109, (const WCHAR **)&v93);
      if ( v9 < 0 )
      {
        v10 = 173;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v9,
          v88);
LABEL_103:
        WindowsDeleteString(v104);
        v104 = 0;
        WindowsDeleteString(v109);
        return (unsigned int)v9;
      }
    }
    else
    {
      v9 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v109, (const WCHAR **)off_14006F220);
      if ( v9 < 0 )
      {
        v10 = 178;
        goto LABEL_15;
      }
    }
    if ( this && *this )
    {
      v9 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v104, &v94);
      if ( v9 < 0 )
      {
        v10 = 183;
        goto LABEL_15;
      }
    }
    else
    {
      v9 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v104, (const WCHAR **)off_14006F210);
      if ( v9 < 0 )
      {
        v10 = 188;
        goto LABEL_15;
      }
    }
    v98 = 0;
    v102 = 0;
    string = 0;
    v11 = WindowsCreateStringReference(
            L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
            0x45u,
            &hstringHeader,
            &string);
    if ( v11 >= 0 )
    {
      v14 = string;
      v15 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v98;
      if ( v98 )
      {
        v98 = 0;
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
      }
      ActivationFactory = RoGetActivationFactory(v14, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v98);
      v9 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC4,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v88);
LABEL_99:
        v85 = v102;
        if ( v102 )
        {
          v102 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
        }
        v86 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v98;
        if ( v98 )
        {
          v98 = 0;
          ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v86)[2])(v86);
        }
        goto LABEL_103;
      }
      v17 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v98;
      v18 = **v98;
      v19 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v18(v17, &GUID_54e633fe_96e0_41e8_9832_1298897c2aaf, &v102);
      v108 = 0;
      v20 = v102;
      v21 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v102 + 64LL);
      v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, (const WCHAR **)&off_14006F228, v22);
      v24 = v21(v20, v23[1].Reserved.Reserved1, &v108);
      v9 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v24,
          v88);
LABEL_97:
        v84 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
        }
        goto LABEL_99;
      }
      v107 = 0;
      v25 = v108;
      v9 = wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>(v108);
      if ( v9 >= 0 )
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 64LL))(v25, &v107);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v9,
          v88);
LABEL_95:
        v83 = v107;
        if ( v107 )
        {
          v107 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
        }
        goto LABEL_97;
      }
      v101 = 0;
      string = 0;
      v26 = WindowsCreateStringReference(
              L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
              0x38u,
              &hstringHeader,
              &string);
      if ( v26 < 0 )
        goto LABEL_107;
      v29 = string;
      v30 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v31 = RoGetActivationFactory(v29, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v101);
      v9 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD1,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v31,
          v88);
LABEL_93:
        v82 = v101;
        if ( v101 )
        {
          v101 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
        }
        goto LABEL_95;
      }
      v94 = &OutputString;
      v100 = 0;
      v33 = v101;
      v34 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, HSTRING))(*(_QWORD *)v101 + 56LL);
      v35 = v109;
      v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, &v94, v32);
      v37 = v34(v33, v107, v36[1].Reserved.Reserved1, v35);
      v9 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDB,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v37,
          0);
LABEL_91:
        v81 = v100;
        if ( v100 )
        {
          v100 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
        }
        goto LABEL_93;
      }
      if ( a4 && *a4 )
      {
        v93 = 0;
        v38 = (**(__int64 (__fastcall ***)(__int64, GUID *, HSTRING *))v100)(
                v100,
                &GUID_5a755b51_3bb1_41a5_a63d_90bc32c7db9a,
                &v93);
        v9 = v38;
        if ( v38 < 0 )
        {
          v40 = 225;
          goto LABEL_42;
        }
        v41 = v93;
        v42 = *(__int64 (__fastcall **)(HSTRING, PVOID))(*(_QWORD *)v93 + 56LL);
        v43 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, &v96, v39);
        v38 = v42(v41, v43[1].Reserved.Reserved1);
        v9 = v38;
        if ( v38 < 0 )
        {
          v40 = 226;
LABEL_42:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v40,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
            (const char *)(unsigned int)v38,
            0);
          v44 = v93;
          if ( v93 )
          {
            v93 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v44 + 16LL))(v44);
          }
          goto LABEL_91;
        }
        v45 = v93;
        if ( v93 )
        {
          v93 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v45 + 16LL))(v45);
        }
      }
      v99 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v100 + 80LL))(v100, &v99);
      if ( v9 < 0 )
      {
        v46 = 230;
LABEL_52:
        v53 = (unsigned int)v9;
LABEL_66:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v46,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)v53,
          0);
LABEL_89:
        v80 = v99;
        if ( v99 )
        {
          v99 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        }
        goto LABEL_91;
      }
      v97[0] = 0;
      v47 = v99;
      v48 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v99 + 80LL);
      v49 = v104;
      string = 0;
      v50 = WindowsCreateStringReference(L"resource", 8u, &hstringHeader, &string);
      if ( v50 < 0 )
        goto LABEL_108;
      v9 = v48(v47, string, v49, v97);
      if ( v9 < 0 )
      {
        v46 = 235;
        goto LABEL_52;
      }
      if ( a3 && *a3 )
      {
        v93 = 0;
        v54 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v93, (const WCHAR **)&v95);
        v9 = v54;
        if ( v54 < 0 )
        {
          v55 = 241;
LABEL_60:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v55,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
            (const char *)(unsigned int)v54,
            0);
          WindowsDeleteString(v93);
          goto LABEL_89;
        }
        v56 = v99;
        v57 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v99 + 80LL);
        v58 = v93;
        string = 0;
        v59 = WindowsCreateStringReference(L"authority", 9u, &hstringHeader, &string);
        if ( v59 < 0 )
          goto LABEL_109;
        v54 = v57(v56, string, v58, v97);
        v9 = v54;
        if ( v54 < 0 )
        {
          v55 = 243;
          goto LABEL_60;
        }
        WindowsDeleteString(v93);
      }
      v62 = v99;
      v63 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v99 + 80LL);
      string = 0;
      v64 = WindowsCreateStringReference(L"DeviceAuth", 0xAu, &hstringHeader, &string);
      if ( v64 < 0 )
      {
LABEL_110:
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v64, v65, v66);
        JUMPOUT(0x140040213LL);
      }
      v67 = string;
      v92 = 0;
      v68 = WindowsCreateStringReference(L"client_TokenType", 0x10u, &v91, &v92);
      if ( v68 >= 0 )
      {
        v71 = v63(v62, v92, v67, v97);
        v9 = v71;
        if ( v71 < 0 )
        {
          v53 = (unsigned int)v71;
          v46 = 248;
          goto LABEL_66;
        }
        v106 = 0;
        v105 = 0;
        v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))(*v98)[6])(v98, v100, &v105);
        if ( v9 < 0 )
        {
          v72 = 252;
LABEL_73:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v72,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
            (const char *)(unsigned int)v9,
            0);
LABEL_85:
          v78 = v105;
          if ( v105 )
          {
            v105 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
          }
          v79 = v106;
          if ( v106 )
          {
            v106 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v79 + 16LL))(v79);
          }
          goto LABEL_89;
        }
        v73 = v105;
        v9 = wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(v105);
        if ( v9 >= 0 )
          v9 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v73 + 64LL))(v73, &v106);
        if ( v9 < 0 )
        {
          v72 = 254;
          goto LABEL_73;
        }
        v110 = 0;
        v103 = 0;
        WindowsDeleteString(0);
        v103 = 0;
        v93 = v106;
        if ( v106 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v106 + 8LL))(v106);
        v9 = AADUtil::ExtractAADDeviceTicketAndDataBoundary(&v93, 0, &v103);
        v74 = v93;
        if ( v93 )
        {
          v93 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v74 + 16LL))(v74);
        }
        if ( v9 >= 0 )
        {
          StringRawBuffer = (char *)WindowsGetStringRawBuffer(v103, 0);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &v95,
            StringRawBuffer,
            0xFFFFFFFFFFFFFFFFuLL,
            v77);
          if ( v95 )
          {
            *a6 = v95;
            v9 = 0;
            goto LABEL_84;
          }
          v9 = -2147024882;
          v75 = 273;
        }
        else
        {
          v75 = 260;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v75,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
          (const char *)(unsigned int)v9,
          0);
LABEL_84:
        WindowsDeleteString(v103);
        v103 = 0;
        WindowsDeleteString(v110);
        v110 = 0;
        goto LABEL_85;
      }
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v68, v69, v70);
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
LABEL_107:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
LABEL_108:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v50, v51, v52);
LABEL_109:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v59, v60, v61);
    goto LABEL_110;
  }
  v9 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9B,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
    (const char *)0x80004003LL,
    v88);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14003f96c  push    rbp
0x14003f96e  push    rbx
0x14003f96f  push    rsi
0x14003f970  push    rdi
0x14003f971  push    r12
0x14003f973  push    r13
0x14003f975  push    r14
0x14003f977  push    r15
0x14003f979  lea     rbp, [rsp-28h]
0x14003f97e  sub     rsp, 128h
0x14003f985  mov     rax, cs:__security_cookie
0x14003f98c  xor     rax, rsp
0x14003f98f  mov     [rbp+60h+var_50], rax
0x14003f993  mov     r14, r9
0x14003f996  mov     r15, r8
0x14003f999  mov     rdi, rcx
0x14003f99c  mov     [rbp+60h+var_D8], rcx
0x14003f9a0  mov     [rbp+60h+var_E0], rdx
0x14003f9a4  mov     [rbp+60h+var_D0], r8
0x14003f9a8  mov     [rbp+60h+var_C8], r9
0x14003f9ac  mov     r12, [rbp+60h+arg_28]
0x14003f9b3  xor     r13d, r13d
0x14003f9b6  test    r12, r12
0x14003f9b9  jnz     short loc_14003F9DD
0x14003f9bb  mov     rcx, [rbp+68h]; this
0x14003f9bf  mov     ebx, 80004003h
0x14003f9c4  mov     r9d, ebx; char *
0x14003f9c7  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003f9ce  mov     edx, 9Bh; void *
0x14003f9d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f9d8  jmp     loc_1400401C2
0x14003f9dd  mov     [r12], r13
0x14003f9e1  mov     [rbp+60h+var_60], r13
0x14003f9e5  mov     [rbp+60h+var_88], r13
0x14003f9e9  test    rdx, rdx
0x14003f9ec  jz      short loc_14003FA0E
0x14003f9ee  cmp     [rdx], r13w
0x14003f9f2  jz      short loc_14003FA0E
0x14003f9f4  lea     rdx, [rbp+60h+var_E0]
0x14003f9f8  lea     rcx, [rbp+60h+var_60]; string
0x14003f9fc  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003fa01  mov     ebx, eax
0x14003fa03  test    eax, eax
0x14003fa05  jns     short loc_14003FA2B
0x14003fa07  mov     edx, 0ADh
0x14003fa0c  jmp     short loc_14003FA6B
0x14003fa0e  lea     rdx, off_14006F220; "d1580516-bbf9-47df-9eda-207f2540e83d"
0x14003fa15  lea     rcx, [rbp+60h+var_60]; string
0x14003fa19  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003fa1e  mov     ebx, eax
0x14003fa20  test    eax, eax
0x14003fa22  jns     short loc_14003FA2B
0x14003fa24  mov     edx, 0B2h
0x14003fa29  jmp     short loc_14003FA6B
0x14003fa2b  test    rdi, rdi
0x14003fa2e  jz      short loc_14003FA50
0x14003fa30  cmp     [rdi], r13w
0x14003fa34  jz      short loc_14003FA50
0x14003fa36  lea     rdx, [rbp+60h+var_D8]
0x14003fa3a  lea     rcx, [rbp+60h+var_88]; string
0x14003fa3e  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003fa43  mov     ebx, eax
0x14003fa45  test    eax, eax
0x14003fa47  jns     short loc_14003FA83
0x14003fa49  mov     edx, 0B7h
0x14003fa4e  jmp     short loc_14003FA6B
0x14003fa50  lea     rdx, off_14006F210; "https://login.windows.local"
0x14003fa57  lea     rcx, [rbp+60h+var_88]; string
0x14003fa5b  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003fa60  mov     ebx, eax
0x14003fa62  test    eax, eax
0x14003fa64  jns     short loc_14003FA83
0x14003fa66  mov     edx, 0BCh; void *
0x14003fa6b  mov     rcx, [rbp+68h]; this
0x14003fa6f  mov     r9d, ebx; char *
0x14003fa72  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003fa79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fa7e  jmp     loc_1400401AA
0x14003fa83  mov     [rbp+60h+var_B8], r13
0x14003fa87  mov     [rbp+60h+var_98], r13
0x14003fa8b  mov     [rsp+160h+string], r13
0x14003fa90  lea     r9, [rsp+160h+string]; string
0x14003fa95  lea     r8, [rsp+160h+hstringHeader]; hstringHeader
0x14003fa9a  mov     edx, 45h ; 'E'; length
0x14003fa9f  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QB_WB; "Windows.Security.Authentication.Web.Cor"...
0x14003faa6  call    cs:__imp_WindowsCreateStringReference
0x14003faac  test    eax, eax
0x14003faae  js      loc_1400401EC
0x14003fab4  mov     rbx, [rsp+160h+string]
0x14003fab9  mov     rcx, [rbp+60h+var_B8]
0x14003fabd  test    rcx, rcx
0x14003fac0  jz      short loc_14003FAD3
0x14003fac2  mov     [rbp+60h+var_B8], r13
0x14003fac6  mov     rax, [rcx]
0x14003fac9  mov     rax, [rax+10h]
0x14003facd  call    _guard_dispatch_icall
0x14003fad2  nop
0x14003fad3  lea     r8, [rbp+60h+var_B8]
0x14003fad7  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x14003fade  mov     rcx, rbx
0x14003fae1  call    cs:__imp_RoGetActivationFactory
0x14003fae7  mov     ebx, eax
0x14003fae9  test    eax, eax
0x14003faeb  jns     short loc_14003FB0A
0x14003faed  mov     rcx, [rbp+68h]; this
0x14003faf1  mov     r9d, eax; char *
0x14003faf4  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003fafb  mov     edx, 0C4h; void *
0x14003fb00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fb05  jmp     loc_140040176
0x14003fb0a  mov     rbx, [rbp+60h+var_B8]
0x14003fb0e  mov     rax, [rbx]
0x14003fb11  mov     rdi, [rax]
0x14003fb14  mov     rcx, [rbp+60h+var_98]
0x14003fb18  test    rcx, rcx
0x14003fb1b  jz      short loc_14003FB2E
0x14003fb1d  mov     [rbp+60h+var_98], r13
0x14003fb21  mov     rdx, [rcx]
0x14003fb24  mov     rax, [rdx+10h]
0x14003fb28  call    _guard_dispatch_icall
0x14003fb2d  nop
0x14003fb2e  lea     r8, [rbp+60h+var_98]
0x14003fb32  lea     rdx, _GUID_54e633fe_96e0_41e8_9832_1298897c2aaf
0x14003fb39  mov     rcx, rbx
0x14003fb3c  mov     rax, rdi
0x14003fb3f  call    _guard_dispatch_icall
0x14003fb44  nop
0x14003fb45  mov     [rbp+60h+var_68], r13
0x14003fb49  mov     rbx, [rbp+60h+var_98]
0x14003fb4d  mov     rax, [rbx]
0x14003fb50  mov     rdi, [rax+40h]
0x14003fb54  lea     rdx, off_14006F228; "https://login.windows.net"
0x14003fb5b  lea     rcx, [rsp+160h+var_100]
0x14003fb60  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003fb65  nop
0x14003fb66  lea     r8, [rbp+60h+var_68]
0x14003fb6a  mov     rdx, [rax+18h]
0x14003fb6e  mov     rcx, rbx
0x14003fb71  mov     rax, rdi
0x14003fb74  call    _guard_dispatch_icall
0x14003fb79  mov     ebx, eax
0x14003fb7b  test    eax, eax
0x14003fb7d  jns     short loc_14003FB9C
0x14003fb7f  mov     rcx, [rbp+68h]; this
0x14003fb83  mov     r9d, eax; char *
0x14003fb86  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003fb8d  mov     edx, 0C9h; void *
0x14003fb92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fb97  jmp     loc_14004015C
0x14003fb9c  mov     [rbp+60h+var_70], r13
0x14003fba0  mov     rdi, [rbp+60h+var_68]
0x14003fba4  mov     rcx, rdi
0x14003fba7  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x14003fbac  mov     ebx, eax
0x14003fbae  test    eax, eax
0x14003fbb0  js      short loc_14003FBC7
0x14003fbb2  mov     rax, [rdi]
0x14003fbb5  lea     rdx, [rbp+60h+var_70]
0x14003fbb9  mov     rcx, rdi
0x14003fbbc  mov     rax, [rax+40h]
0x14003fbc0  call    _guard_dispatch_icall
0x14003fbc5  mov     ebx, eax
0x14003fbc7  test    ebx, ebx
0x14003fbc9  jns     short loc_14003FBE8
0x14003fbcb  mov     rcx, [rbp+68h]; this
0x14003fbcf  mov     r9d, ebx; char *
0x14003fbd2  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003fbd9  mov     edx, 0CCh; void *
0x14003fbde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fbe3  jmp     loc_140040142
0x14003fbe8  mov     [rbp+60h+var_A0], r13
0x14003fbec  mov     [rsp+160h+string], r13
0x14003fbf1  lea     r9, [rsp+160h+string]; string
0x14003fbf6  lea     r8, [rsp+160h+hstringHeader]; hstringHeader
0x14003fbfb  mov     edx, 38h ; '8'; length
0x14003fc00  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QB_WB; "Windows.Security.Authentication.Web.Cor"...
0x14003fc07  call    cs:__imp_WindowsCreateStringReference
0x14003fc0d  test    eax, eax
0x14003fc0f  js      loc_1400401F4
0x14003fc15  mov     rbx, [rsp+160h+string]
0x14003fc1a  mov     rcx, [rbp+60h+var_A0]
0x14003fc1e  test    rcx, rcx
0x14003fc21  jz      short loc_14003FC34
0x14003fc23  mov     [rbp+60h+var_A0], r13
0x14003fc27  mov     rax, [rcx]
0x14003fc2a  mov     rax, [rax+10h]
0x14003fc2e  call    _guard_dispatch_icall
0x14003fc33  nop
0x14003fc34  lea     r8, [rbp+60h+var_A0]
0x14003fc38  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x14003fc3f  mov     rcx, rbx
0x14003fc42  call    cs:__imp_RoGetActivationFactory
0x14003fc48  mov     ebx, eax
0x14003fc4a  test    eax, eax
0x14003fc4c  jns     short loc_14003FC6B
0x14003fc4e  mov     rcx, [rbp+68h]; this
0x14003fc52  mov     r9d, eax; char *
0x14003fc55  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003fc5c  mov     edx, 0D1h; void *
0x14003fc61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fc66  jmp     loc_140040128
0x14003fc6b  lea     rax, OutputString
0x14003fc72  mov     [rbp+60h+var_D8], rax
0x14003fc76  mov     [rbp+60h+var_A8], r13
0x14003fc7a  mov     rbx, [rbp+60h+var_A0]
0x14003fc7e  mov     rax, [rbx]
0x14003fc81  mov     rsi, [rax+38h]
0x14003fc85  mov     rdi, [rbp+60h+var_60]
0x14003fc89  lea     rdx, [rbp+60h+var_D8]
0x14003fc8d  lea     rcx, [rsp+160h+var_100]
0x14003fc92  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003fc97  nop
0x14003fc98  lea     rcx, [rbp+60h+var_A8]
0x14003fc9c  mov     [rsp+160h+var_138], rcx
0x14003fca1  mov     [rsp+160h+var_140], r13d; int
0x14003fca6  mov     r9, rdi
0x14003fca9  mov     r8, [rax+18h]
0x14003fcad  mov     rdx, [rbp+60h+var_70]
0x14003fcb1  mov     rcx, rbx
0x14003fcb4  mov     rax, rsi
0x14003fcb7  call    _guard_dispatch_icall
0x14003fcbc  mov     ebx, eax
0x14003fcbe  test    eax, eax
0x14003fcc0  jns     short loc_14003FCDF
0x14003fcc2  mov     rcx, [rbp+68h]; this
0x14003fcc6  mov     r9d, eax; char *
0x14003fcc9  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003fcd0  mov     edx, 0DBh; void *
0x14003fcd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fcda  jmp     loc_14004010E
0x14003fcdf  test    r14, r14
0x14003fce2  jz      loc_14003FD9E
0x14003fce8  cmp     [r14], r13w
0x14003fcec  jz      loc_14003FD9E
0x14003fcf2  mov     [rbp+60h+var_E0], r13
0x14003fcf6  mov     rcx, [rbp+60h+var_A8]
0x14003fcfa  mov     rax, [rcx]
0x14003fcfd  lea     r8, [rbp+60h+var_E0]
0x14003fd01  lea     rdx, _GUID_5a755b51_3bb1_41a5_a63d_90bc32c7db9a
0x14003fd08  mov     rax, [rax]
0x14003fd0b  call    _guard_dispatch_icall
0x14003fd10  mov     ebx, eax
0x14003fd12  test    eax, eax
0x14003fd14  jns     short loc_14003FD1D
0x14003fd16  mov     edx, 0E1h
0x14003fd1b  jmp     short loc_14003FD51
0x14003fd1d  mov     rbx, [rbp+60h+var_E0]
0x14003fd21  mov     rax, [rbx]
0x14003fd24  mov     rdi, [rax+38h]
0x14003fd28  lea     rdx, [rbp+60h+var_C8]
0x14003fd2c  lea     rcx, [rsp+160h+var_100]
0x14003fd31  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003fd36  nop
0x14003fd37  mov     rdx, [rax+18h]
0x14003fd3b  mov     rcx, rbx
0x14003fd3e  mov     rax, rdi
0x14003fd41  call    _guard_dispatch_icall
0x14003fd46  mov     ebx, eax
0x14003fd48  test    eax, eax
0x14003fd4a  jns     short loc_14003FD84
0x14003fd4c  mov     edx, 0E2h; void *
0x14003fd51  mov     r9d, eax; char *
0x14003fd54  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003fd5b  mov     rcx, [rbp+68h]; this
0x14003fd5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fd64  nop
0x14003fd65  mov     rcx, [rbp+60h+var_E0]
0x14003fd69  test    rcx, rcx
0x14003fd6c  jz      short loc_14003FD7F
0x14003fd6e  mov     [rbp+60h+var_E0], r13
0x14003fd72  mov     rax, [rcx]
0x14003fd75  mov     rax, [rax+10h]
0x14003fd79  call    _guard_dispatch_icall
0x14003fd7e  nop
0x14003fd7f  jmp     loc_14004010E
0x14003fd84  mov     rcx, [rbp+60h+var_E0]
0x14003fd88  test    rcx, rcx
0x14003fd8b  jz      short loc_14003FD9E
0x14003fd8d  mov     [rbp+60h+var_E0], r13
0x14003fd91  mov     rax, [rcx]
0x14003fd94  mov     rax, [rax+10h]
0x14003fd98  call    _guard_dispatch_icall
0x14003fd9d  nop
0x14003fd9e  mov     [rbp+60h+var_B0], r13
0x14003fda2  mov     rcx, [rbp+60h+var_A8]
0x14003fda6  mov     rax, [rcx]
0x14003fda9  lea     rdx, [rbp+60h+var_B0]
0x14003fdad  mov     rax, [rax+50h]
0x14003fdb1  call    _guard_dispatch_icall
0x14003fdb6  mov     ebx, eax
0x14003fdb8  test    eax, eax
0x14003fdba  jns     short loc_14003FDC3
0x14003fdbc  mov     edx, 0E6h
0x14003fdc1  jmp     short loc_14003FE21
0x14003fdc3  mov     [rbp+60h+var_C0], r13b
0x14003fdc7  mov     rbx, [rbp+60h+var_B0]
0x14003fdcb  mov     rax, [rbx]
0x14003fdce  mov     rsi, [rax+50h]
0x14003fdd2  mov     rdi, [rbp+60h+var_88]
0x14003fdd6  mov     [rsp+160h+string], r13
  ... truncated ...
```
