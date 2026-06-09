# ViewActivator::CreateActivationOptionsMessageBlob(ViewActivationRequest const &,MsgBlob * *)

- ea: `0x18001d4e0`
- end: `0x18001e2f5`
- name: `?CreateActivationOptionsMessageBlob@ViewActivator@@CAJAEBUViewActivationRequest@@PEAPEAUMsgBlob@@@Z`
- size: `3605`
- prototype: `__int64 __fastcall(const struct ViewActivationRequest *, struct MsgBlob **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c4e0`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18001c14c`
- `0x18001d4e0`
- `0x18005ae90`
- `0x18005d2ad`
- `0x180077090`
- `0x1800826a0`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e1f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e23b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e24f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e26d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e281`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e295`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e1f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e23b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e24f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e26d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e281`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d87f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d8b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dbdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d87f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d8b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dbdf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d674`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d8d3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d674`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d8d3`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001d563`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001d563`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x18001d5ae`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x18001d5ae`
- `CoreMessaging!MsgBlobCreateShared` at `0x18001da59`
- `CoreMessaging!MsgBlobCreateShared` at `0x18001da59`

## string_xrefs

- `0x18001dbd8`: `AAMShim.CallingProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall ViewActivator::CreateActivationOptionsMessageBlob(
        const struct ViewActivationRequest *a1,
        struct MsgBlob **a2)
{
  HRESULT v4; // eax
  HSTRING v5; // rbx
  int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rbx
  unsigned int v12; // r14d
  HRESULT v13; // eax
  HSTRING v14; // r15
  HRESULT v15; // eax
  int ActivationFactory; // eax
  int v17; // edi
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r14
  int v22; // eax
  __int64 v23; // rcx
  __int64 (__fastcall ***v24)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v30; // rcx
  unsigned int v31; // edi
  __int64 v32; // rsi
  HRESULT v33; // eax
  HSTRING v34; // r14
  HRESULT v35; // eax
  int v36; // eax
  int v37; // edi
  int v38; // eax
  int v39; // eax
  __int64 v40; // rcx
  __int64 (__fastcall ***v41)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v42; // rcx
  int v43; // eax
  unsigned int v44; // ebx
  __int64 (__fastcall ***v45)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v46)(_QWORD, GUID *, __int64 *); // rdi
  int v47; // eax
  unsigned int v48; // ebx
  int Shared; // ebx
  int v50; // eax
  unsigned int v51; // ebx
  __int64 v52; // rcx
  __int64 (__fastcall ***v53)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v57; // rsi
  int v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 (__fastcall ***v61)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v62; // rcx
  HRESULT v63; // eax
  __int64 v64; // r8
  int v65; // eax
  unsigned int v66; // ebx
  __int64 v67; // rcx
  __int64 (__fastcall ***v68)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 (__fastcall ***v72)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 (__fastcall ***v75)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 (__fastcall ***v79)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v80; // rcx
  __int64 (__fastcall ***v81)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 (__fastcall ***v84)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  int v98; // eax
  __int64 v99; // rcx
  __int64 v100; // rcx
  __int64 (__fastcall ***v101)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rdx
  int v105; // [rsp+20h] [rbp-99h]
  _BYTE v106[8]; // [rsp+30h] [rbp-89h] BYREF
  __int64 v107; // [rsp+38h] [rbp-81h] BYREF
  __int64 v108; // [rsp+40h] [rbp-79h] BYREF
  __int64 v109; // [rsp+48h] [rbp-71h] BYREF
  __int64 (__fastcall ***v110)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-69h] BYREF
  __int64 v111; // [rsp+58h] [rbp-61h] BYREF
  __int64 v112; // [rsp+60h] [rbp-59h] BYREF
  __int64 (__fastcall ***v113)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-51h] BYREF
  __int64 v114; // [rsp+70h] [rbp-49h] BYREF
  __int64 v115; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v116; // [rsp+80h] [rbp-39h] BYREF
  __int64 v117; // [rsp+88h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-29h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-11h] BYREF
  HSTRING_HEADER v120; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING v121; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *a2 = 0;
  v107 = 0;
  v109 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v5 = string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v107);
  v107 = 0;
  v115 = 0;
  v6 = RoActivateInstance(v5, &v115);
  if ( v6 >= 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v107 = v115;
    }
    else
    {
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v115)(
             v115,
             &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
             &v107);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
    }
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AD,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      (const char *)(unsigned int)v6,
      v105);
    v96 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
    }
    v97 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    }
    return (unsigned int)v6;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v109);
  v7 = RoCreatePropertySetSerializer(&v109);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AE,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      (const char *)(unsigned int)v7,
      v105);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v109);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v107);
    return v8;
  }
  if ( *((_QWORD *)a1 + 10) )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v109 + 56LL))(v109, v107);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B2,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
        (const char *)(unsigned int)v9,
        v105);
      v91 = v109;
      if ( v109 )
      {
        v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      }
      v92 = v107;
      if ( v107 )
      {
        v107 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      }
      return v10;
    }
  }
  v11 = v107;
  v115 = v107;
  if ( v107 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 8LL))(v107);
  v12 = *((_DWORD *)a1 + 16);
  string = 0;
  v13 = WindowsCreateStringReference(L"AAMShim.ActivateOptionsInternal", 0x1Fu, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
    goto LABEL_178;
  }
  v14 = string;
  v108 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v108);
  v121 = 0;
  v15 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &v120, &v121);
  if ( v15 < 0 )
  {
LABEL_178:
    RaiseException(v15, 1u, 0, 0);
    goto LABEL_179;
  }
  ActivationFactory = RoGetActivationFactory(v121, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v108);
  v17 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
      (const char *)(unsigned int)ActivationFactory,
      v105);
    v86 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    }
  }
  else
  {
    v110 = 0;
    v18 =  Windows::Foundation::IPropertyValueStatics::`vcall'{88,{flat}}(v108, v12, &v110);
    v17 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
        (const char *)(unsigned int)v18,
        v105);
      v72 = v110;
      if ( v110 )
      {
        v110 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v72)[2])(v72);
      }
      v73 = v108;
      if ( v108 )
      {
        v108 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      }
    }
    else
    {
      v112 = 0;
      v19 = (**v110)(v110, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v112);
      v17 = v19;
      if ( v19 >= 0 )
      {
        v20 = 0;
        v111 = 0;
        if ( v11 )
        {
          v21 = v112;
          v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v11)(
                  v11,
                  &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                  &v111);
          v17 = v22;
          if ( v22 >= 0 )
          {
            v106[0] = 0;
            v26 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v111 + 80LL))(
                    v111,
                    v14,
                    v21,
                    v106);
            v17 = v26;
            if ( v26 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x48,
                (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
                (const char *)(unsigned int)v26,
                v105);
              v71 = v111;
              if ( v111 )
              {
                v111 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
              }
              goto LABEL_22;
            }
            v27 = v111;
            if ( v111 )
            {
              v111 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            }
            goto LABEL_33;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B,
            (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
            (const char *)(unsigned int)v22,
            v105);
          v20 = v111;
LABEL_19:
          if ( v20 )
          {
            v111 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          if ( v17 < 0 )
          {
LABEL_22:
            v23 = v112;
            if ( v112 )
            {
              v112 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            }
            v24 = v110;
            if ( v110 )
            {
              v110 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v24)[2])(v24);
            }
            v25 = v108;
            if ( v108 )
            {
              v108 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            }
            goto LABEL_40;
          }
LABEL_33:
          v28 = v112;
          if ( v112 )
          {
            v112 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
          v29 = v110;
          if ( v110 )
          {
            v110 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v29)[2])(v29);
          }
          v30 = v108;
          if ( v108 )
          {
            v108 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
          v17 = 0;
          goto LABEL_40;
        }
LABEL_179:
        v17 = -2147467261;
        goto LABEL_19;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
        (const char *)(unsigned int)v19,
        v105);
      v78 = v112;
      if ( v112 )
      {
        v112 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      }
      v79 = v110;
      if ( v110 )
      {
        v110 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v79)[2])(v79);
      }
      v80 = v108;
      if ( v108 )
      {
        v108 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      }
    }
  }
LABEL_40:
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      (const char *)(unsigned int)v17,
      v105);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v115);
    v89 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
    }
    v90 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    }
    return (unsigned int)v17;
  }
  v31 = *((_DWORD *)a1 + 19);
  if ( v31 )
  {
    v121 = 0;
    v63 = WindowsCreateStringReference(L"AAMShim.CallingProcessId", 0x18u, &v120, &v121);
    if ( v63 < 0 )
    {
      RaiseException(v63, 1u, 0, 0);
      __debugbreak();
    }
    v65 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(&v115, v121, v64, v31);
    v66 = v65;
    if ( v65 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BC,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
        (const char *)(unsigned int)v65,
        v105);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v115);
      v87 = v109;
      if ( v109 )
      {
        v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      }
      v88 = v107;
      if ( v107 )
      {
        v107 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      }
      return v66;
    }
    v11 = v115;
  }
  v32 = *(_QWORD *)a1;
  v121 = 0;
  v33 = WindowsCreateStringReference(L"AAMShim.ActivationId", 0x14u, &v120, &v121);
  if ( v33 < 0 )
  {
    RaiseException(v33, 1u, 0, 0);
    goto LABEL_182;
  }
  v34 = v121;
  v108 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v108);
  string = 0;
  v35 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v35 < 0 )
  {
LABEL_182:
    RaiseException(v35, 1u, 0, 0);
    goto LABEL_183;
  }
  v36 = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v108);
  v37 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
      (const char *)(unsigned int)v36,
      v105);
    v93 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
    }
  }
  else
  {
    v110 = 0;
    v38 =  Windows::Foundation::IPropertyValueStatics::`vcall'{104,{flat}}(v108, v32, &v110);
    v37 = v38;
    if ( v38 >= 0 )
    {
      v112 = 0;
      v39 = (**v110)(v110, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v112);
      v37 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
          (const char *)(unsigned int)v39,
          v105);
        v40 = v112;
        if ( v112 )
        {
          v112 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        }
        v41 = v110;
        if ( v110 )
        {
          v110 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v41)[2])(v41);
        }
        v42 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        }
        goto LABEL_53;
      }
      v57 = v112;
      v111 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v111);
      if ( v11 )
      {
        v58 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v11)(
                v11,
                &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                &v111);
        v37 = v58;
        if ( v58 >= 0 )
        {
          v106[0] = 0;
          v98 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v111 + 80LL))(
                  v111,
                  v34,
                  v57,
                  v106);
          v37 = v98;
          if ( v98 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x48,
              (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
              (const char *)(unsigned int)v98,
              v105);
            v103 = v111;
            if ( v111 )
            {
              v111 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
            }
            goto LABEL_76;
          }
          v99 = v111;
          if ( v111 )
          {
            v111 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
          }
          goto LABEL_165;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B,
          (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
          (const char *)(unsigned int)v58,
          v105);
LABEL_73:
        v59 = v111;
        if ( v111 )
        {
          v111 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
        }
        if ( v37 < 0 )
        {
LABEL_76:
          v60 = v112;
          if ( v112 )
          {
            v112 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          }
          v61 = v110;
          if ( v110 )
          {
            v110 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v61)[2])(v61);
          }
          v62 = v108;
          if ( v108 )
          {
            v108 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          }
          goto LABEL_53;
        }
LABEL_165:
        v100 = v112;
        if ( v112 )
        {
          v112 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
        }
        v101 = v110;
        if ( v110 )
        {
          v110 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v101)[2])(v101);
        }
        v102 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
        }
        v37 = 0;
        goto LABEL_53;
      }
LABEL_183:
      v37 = -2147467261;
      goto LABEL_73;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
      (const char *)(unsigned int)v38,
      v105);
    v84 = v110;
    if ( v110 )
    {
      v110 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v84)[2])(v84);
    }
    v85 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
  }
LABEL_53:
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BF,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      (const char *)(unsigned int)v37,
      v105);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v115);
    v94 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    }
    v95 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    }
    return (unsigned int)v37;
  }
  else
  {
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v113 = 0;
    v43 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v109 + 48LL))(v109, v107, &v113);
    v44 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C3,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
        (const char *)(unsigned int)v43,
        v105);
      v81 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v113;
      if ( v113 )
      {
        v113 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v81)[2])(v81);
      }
      v82 = v109;
      if ( v109 )
      {
        v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
      }
      v83 = v107;
      if ( v107 )
      {
        v107 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      }
      return v44;
    }
    else
    {
      v114 = 0;
      v116 = 0;
      v117 = 0;
      v45 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v113;
      v46 = **v113;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v114);
      v47 = v46(v45, &GUID_905a0fef_bc53_11df_8c49_001e4fc686da, &v114);
      v48 = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C9,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
          (const char *)(unsigned int)v47,
          v105);
        v74 = v114;
        if ( v114 )
        {
          v114 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        }
        v75 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v113;
        if ( v113 )
        {
          v113 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v75)[2])(v75);
        }
        v76 = v109;
        if ( v109 )
        {
          v109 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        }
        v77 = v107;
        if ( v107 )
        {
          v107 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        }
        return v48;
      }
      else
      {
        Shared = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), unsigned int *))(*v113)[7])(
                   v113,
                   &v116);
        if ( Shared < 0 )
        {
          v104 = 714;
          goto LABEL_186;
        }
        v50 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v114 + 24LL))(v114, &v117);
        v51 = v50;
        if ( v50 >= 0 )
        {
          Shared = MsgBlobCreateShared(v117, v116, a2);
          if ( Shared >= 0 )
          {
            v52 = v114;
            if ( v114 )
            {
              v114 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
            }
            v53 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v113;
            if ( v113 )
            {
              v113 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v53)[2])(v53);
            }
            v54 = v109;
            if ( v109 )
            {
              v109 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
            }
            v55 = v107;
            if ( v107 )
            {
              v107 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
            }
            return 0;
          }
          v104 = 716;
LABEL_186:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v104,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
            (const char *)(unsigned int)Shared,
            v105);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v114);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v113);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v109);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v107);
          return (unsigned int)Shared;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2CB,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
          (const char *)(unsigned int)v50,
          v105);
        v67 = v114;
        if ( v114 )
        {
          v114 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
        }
        v68 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v113;
        if ( v113 )
        {
          v113 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v68)[2])(v68);
        }
        v69 = v109;
        if ( v109 )
        {
          v109 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
        }
        v70 = v107;
        if ( v107 )
        {
          v107 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
        }
        return v51;
      }
    }
  }
}

```

## disassembly

```asm
0x18001d4e0  mov     [rsp-8+arg_10], rbx
0x18001d4e5  push    rbp
0x18001d4e6  push    rsi
0x18001d4e7  push    rdi
0x18001d4e8  push    r12
0x18001d4ea  push    r13
0x18001d4ec  push    r14
0x18001d4ee  push    r15
0x18001d4f0  lea     rbp, [rsp-27h]
0x18001d4f5  sub     rsp, 0E0h
0x18001d4fc  mov     rax, cs:__security_cookie
0x18001d503  xor     rax, rsp
0x18001d506  mov     [rbp+57h+var_40], rax
0x18001d50a  mov     r12, rdx
0x18001d50d  mov     rsi, rcx
0x18001d510  xor     r13d, r13d
0x18001d513  mov     [rdx], r13
0x18001d516  mov     [rsp+110h+var_D8], r13
0x18001d51b  mov     [rbp+57h+var_C8], r13
0x18001d51f  mov     [rbp+57h+string], r13
0x18001d523  lea     r9, [rbp+57h+string]; string
0x18001d527  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001d52b  mov     edx, 2Ah ; '*'; length
0x18001d530  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x18001d537  call    cs:__imp_WindowsCreateStringReference
0x18001d53d  test    eax, eax
0x18001d53f  js      loc_18001E1E6
0x18001d545  mov     rbx, [rbp+57h+string]
0x18001d549  lea     rcx, [rsp+110h+var_D8]
0x18001d54e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d553  mov     [rsp+110h+var_D8], r13
0x18001d558  mov     [rbp+57h+var_98], r13
0x18001d55c  lea     rdx, [rbp+57h+var_98]
0x18001d560  mov     rcx, rbx
0x18001d563  call    cs:__imp_RoActivateInstance
0x18001d569  mov     ebx, eax
0x18001d56b  test    eax, eax
0x18001d56d  js      short loc_18001D599
0x18001d56f  mov     r8d, 10h; Size
0x18001d575  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18001d57c  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x18001d583  call    memcmp_0
0x18001d588  mov     rcx, [rbp+57h+var_98]
0x18001d58c  test    eax, eax
0x18001d58e  jnz     loc_18001D78E
0x18001d594  mov     [rsp+110h+var_D8], rcx
0x18001d599  test    ebx, ebx
0x18001d59b  js      loc_18001E0C2
0x18001d5a1  lea     rcx, [rbp+57h+var_C8]
0x18001d5a5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d5aa  lea     rcx, [rbp+57h+var_C8]
0x18001d5ae  call    cs:__imp_RoCreatePropertySetSerializer
0x18001d5b4  mov     ebx, eax
0x18001d5b6  test    eax, eax
0x18001d5b8  js      loc_18001E1FA
0x18001d5be  mov     r8, [rsi+50h]
0x18001d5c2  test    r8, r8
0x18001d5c5  jz      short loc_18001D5E6
0x18001d5c7  mov     rcx, [rbp+57h+var_C8]
0x18001d5cb  mov     rax, [rcx]
0x18001d5ce  mov     rdx, [rsp+110h+var_D8]
0x18001d5d3  mov     rax, [rax+38h]
0x18001d5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5dc  mov     ebx, eax
0x18001d5de  test    eax, eax
0x18001d5e0  js      loc_18001DFD4
0x18001d5e6  mov     rbx, [rsp+110h+var_D8]
0x18001d5eb  mov     [rbp+57h+var_98], rbx
0x18001d5ef  test    rbx, rbx
0x18001d5f2  jz      short loc_18001D604
0x18001d5f4  mov     rax, [rbx]
0x18001d5f7  mov     rcx, rbx
0x18001d5fa  mov     rax, [rax+8]
0x18001d5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d603  nop
0x18001d604  mov     r14d, [rsi+40h]
0x18001d608  mov     [rbp+57h+string], r13
0x18001d60c  lea     r9, [rbp+57h+string]; string
0x18001d610  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001d614  mov     edx, 1Fh; length
0x18001d619  lea     rcx, aAamshimActivat; "AAMShim.ActivateOptionsInternal"
0x18001d620  call    cs:__imp_WindowsCreateStringReference
0x18001d626  test    eax, eax
0x18001d628  js      loc_18001E22E
0x18001d62e  mov     r15, [rbp+57h+string]
0x18001d632  mov     [rbp+57h+var_D0], r13
0x18001d636  lea     rcx, [rbp+57h+var_D0]
0x18001d63a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d63f  mov     [rbp+57h+var_48], r13
0x18001d643  lea     r9, [rbp+57h+var_48]; string
0x18001d647  lea     r8, [rbp+57h+var_60]; hstringHeader
0x18001d64b  mov     edx, 20h ; ' '; length
0x18001d650  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18001d657  call    cs:__imp_WindowsCreateStringReference
0x18001d65d  test    eax, eax
0x18001d65f  js      loc_18001E242
0x18001d665  lea     r8, [rbp+57h+var_D0]
0x18001d669  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18001d670  mov     rcx, [rbp+57h+var_48]
0x18001d674  call    cs:__imp_RoGetActivationFactory
0x18001d67a  mov     edi, eax
0x18001d67c  test    eax, eax
0x18001d67e  js      loc_18001DEDC
0x18001d684  mov     [rbp+57h+var_C0], r13
0x18001d688  lea     r8, [rbp+57h+var_C0]
0x18001d68c  mov     edx, r14d
0x18001d68f  mov     rcx, [rbp+57h+var_D0]
0x18001d693  call    ??_9IPropertyValueStatics@Foundation@Windows@@$BFI@AA; [thunk]: Windows::Foundation::IPropertyValueStatics::`vcall'{88,{flat}}
0x18001d698  mov     edi, eax
0x18001d69a  test    eax, eax
0x18001d69c  js      loc_18001DCD2
0x18001d6a2  mov     [rbp+57h+var_B0], r13
0x18001d6a6  mov     rcx, [rbp+57h+var_C0]
0x18001d6aa  mov     rax, [rcx]
0x18001d6ad  lea     r8, [rbp+57h+var_B0]
0x18001d6b1  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18001d6b8  mov     rax, [rax]
0x18001d6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6c0  mov     edi, eax
0x18001d6c2  test    eax, eax
0x18001d6c4  js      loc_18001DDAE
0x18001d6ca  mov     rcx, r13
0x18001d6cd  mov     [rbp+57h+var_B8], rcx
0x18001d6d1  test    rbx, rbx
0x18001d6d4  jz      loc_18001E256
0x18001d6da  mov     r14, [rbp+57h+var_B0]
0x18001d6de  mov     rax, [rbx]
0x18001d6e1  lea     r8, [rbp+57h+var_B8]
0x18001d6e5  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18001d6ec  mov     rcx, rbx
0x18001d6ef  mov     rax, [rax]
0x18001d6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6f7  mov     edi, eax
0x18001d6f9  test    eax, eax
0x18001d6fb  jns     loc_18001D7BC
0x18001d701  mov     rcx, [rbp+5Fh]; this
0x18001d705  mov     r9d, eax; char *
0x18001d708  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\property"...
0x18001d70f  mov     edx, 1Bh; void *
0x18001d714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d719  mov     rcx, [rbp+57h+var_B8]
0x18001d71d  test    rcx, rcx
0x18001d720  jz      short loc_18001D733
0x18001d722  mov     [rbp+57h+var_B8], r13
0x18001d726  mov     rax, [rcx]
0x18001d729  mov     rax, [rax+10h]
0x18001d72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d732  nop
0x18001d733  test    edi, edi
0x18001d735  jns     loc_18001D800
0x18001d73b  mov     rcx, [rbp+57h+var_B0]
0x18001d73f  test    rcx, rcx
0x18001d742  jz      short loc_18001D755
0x18001d744  mov     [rbp+57h+var_B0], r13
0x18001d748  mov     rax, [rcx]
0x18001d74b  mov     rax, [rax+10h]
0x18001d74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d754  nop
0x18001d755  mov     rcx, [rbp+57h+var_C0]
0x18001d759  test    rcx, rcx
0x18001d75c  jz      short loc_18001D76F
0x18001d75e  mov     [rbp+57h+var_C0], r13
0x18001d762  mov     rax, [rcx]
0x18001d765  mov     rax, [rax+10h]
0x18001d769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d76e  nop
0x18001d76f  mov     rcx, [rbp+57h+var_D0]
0x18001d773  test    rcx, rcx
0x18001d776  jz      short loc_18001D789
0x18001d778  mov     [rbp+57h+var_D0], r13
0x18001d77c  mov     rax, [rcx]
0x18001d77f  mov     rax, [rax+10h]
0x18001d783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d788  nop
0x18001d789  jmp     loc_18001D851
0x18001d78e  mov     rax, [rcx]
0x18001d791  lea     r8, [rsp+110h+var_D8]
0x18001d796  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x18001d79d  mov     rax, [rax]
0x18001d7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7a5  mov     ebx, eax
0x18001d7a7  mov     rcx, [rbp+57h+var_98]
0x18001d7ab  mov     rax, [rcx]
0x18001d7ae  mov     rax, [rax+10h]
0x18001d7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7b7  jmp     loc_18001D599
0x18001d7bc  mov     [rsp+110h+var_E0], 0
0x18001d7c1  mov     rcx, [rbp+57h+var_B8]
0x18001d7c5  mov     rax, [rcx]
0x18001d7c8  lea     r9, [rsp+110h+var_E0]
0x18001d7cd  mov     r8, r14
0x18001d7d0  mov     rdx, r15
0x18001d7d3  mov     rax, [rax+50h]
0x18001d7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7dc  mov     edi, eax
0x18001d7de  test    eax, eax
0x18001d7e0  js      loc_18001DC9A
0x18001d7e6  mov     rcx, [rbp+57h+var_B8]
0x18001d7ea  test    rcx, rcx
0x18001d7ed  jz      short loc_18001D800
0x18001d7ef  mov     [rbp+57h+var_B8], r13
0x18001d7f3  mov     rax, [rcx]
0x18001d7f6  mov     rax, [rax+10h]
0x18001d7fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ff  nop
0x18001d800  mov     rcx, [rbp+57h+var_B0]
0x18001d804  test    rcx, rcx
0x18001d807  jz      short loc_18001D81A
0x18001d809  mov     [rbp+57h+var_B0], r13
0x18001d80d  mov     rax, [rcx]
0x18001d810  mov     rax, [rax+10h]
0x18001d814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d819  nop
0x18001d81a  mov     rcx, [rbp+57h+var_C0]
0x18001d81e  test    rcx, rcx
0x18001d821  jz      short loc_18001D834
0x18001d823  mov     [rbp+57h+var_C0], r13
0x18001d827  mov     rax, [rcx]
0x18001d82a  mov     rax, [rax+10h]
0x18001d82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d833  nop
0x18001d834  mov     rcx, [rbp+57h+var_D0]
0x18001d838  test    rcx, rcx
0x18001d83b  jz      short loc_18001D84E
0x18001d83d  mov     [rbp+57h+var_D0], r13
0x18001d841  mov     rax, [rcx]
0x18001d844  mov     rax, [rax+10h]
0x18001d848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d84d  nop
0x18001d84e  mov     edi, r13d
0x18001d851  test    edi, edi
0x18001d853  js      loc_18001DF74
0x18001d859  mov     edi, [rsi+4Ch]
0x18001d85c  test    edi, edi
0x18001d85e  jnz     loc_18001DBC7
0x18001d864  mov     rsi, [rsi]
0x18001d867  mov     [rbp+57h+var_48], r13
0x18001d86b  lea     r9, [rbp+57h+var_48]; string
0x18001d86f  lea     r8, [rbp+57h+var_60]; hstringHeader
0x18001d873  mov     edx, 14h; length
0x18001d878  lea     rcx, aAamshimActivat_0; "AAMShim.ActivationId"
0x18001d87f  call    cs:__imp_WindowsCreateStringReference
0x18001d885  test    eax, eax
0x18001d887  js      loc_18001E274
0x18001d88d  mov     r14, [rbp+57h+var_48]
0x18001d891  mov     [rbp+57h+var_D0], r13
0x18001d895  lea     rcx, [rbp+57h+var_D0]
0x18001d899  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d89e  mov     [rbp+57h+string], r13
0x18001d8a2  lea     r9, [rbp+57h+string]; string
0x18001d8a6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001d8aa  mov     edx, 20h ; ' '; length
0x18001d8af  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18001d8b6  call    cs:__imp_WindowsCreateStringReference
0x18001d8bc  test    eax, eax
0x18001d8be  js      loc_18001E288
0x18001d8c4  lea     r8, [rbp+57h+var_D0]
0x18001d8c8  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18001d8cf  mov     rcx, [rbp+57h+string]
0x18001d8d3  call    cs:__imp_RoGetActivationFactory
0x18001d8d9  mov     edi, eax
0x18001d8db  test    eax, eax
0x18001d8dd  js      loc_18001E02A
0x18001d8e3  mov     [rbp+57h+var_C0], r13
0x18001d8e7  lea     r8, [rbp+57h+var_C0]
0x18001d8eb  mov     rdx, rsi
0x18001d8ee  mov     rcx, [rbp+57h+var_D0]
0x18001d8f2  call    ??_9IPropertyValueStatics@Foundation@Windows@@$BGI@AA; [thunk]: Windows::Foundation::IPropertyValueStatics::`vcall'{104,{flat}}
0x18001d8f7  mov     edi, eax
0x18001d8f9  test    eax, eax
0x18001d8fb  js      loc_18001DE8A
0x18001d901  mov     [rbp+57h+var_B0], r13
0x18001d905  mov     rcx, [rbp+57h+var_C0]
0x18001d909  mov     rax, [rcx]
0x18001d90c  lea     r8, [rbp+57h+var_B0]
0x18001d910  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18001d917  mov     rax, [rax]
0x18001d91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d91f  mov     edi, eax
0x18001d921  test    eax, eax
0x18001d923  jns     loc_18001DAFC
0x18001d929  mov     rcx, [rbp+5Fh]; this
0x18001d92d  mov     r9d, eax; char *
0x18001d930  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\property"...
0x18001d937  mov     edx, 54h ; 'T'; void *
0x18001d93c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d941  nop
0x18001d942  mov     rcx, [rbp+57h+var_B0]
0x18001d946  test    rcx, rcx
0x18001d949  jz      short loc_18001D95C
0x18001d94b  mov     [rbp+57h+var_B0], r13
0x18001d94f  mov     rax, [rcx]
0x18001d952  mov     rax, [rax+10h]
0x18001d956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d95b  nop
0x18001d95c  mov     rcx, [rbp+57h+var_C0]
0x18001d960  test    rcx, rcx
0x18001d963  jz      short loc_18001D976
0x18001d965  mov     [rbp+57h+var_C0], r13
0x18001d969  mov     rax, [rcx]
  ... truncated ...
```
