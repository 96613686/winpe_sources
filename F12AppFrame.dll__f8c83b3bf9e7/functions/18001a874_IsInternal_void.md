# IsInternal(void)

- ea: `0x18001a874`
- end: `0x18001b3d1`
- name: `?IsInternal@@YAJXZ`
- size: `2909`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001b510`

## callees

- `0x180001800`
- `0x180006e00`
- `0x1800189c8`
- `0x18001a874`
- `0x18001c4c4`
- `0x180032abc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001aa47`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001aa47`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001a938`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ad02`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001a938`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ad02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001a8b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001a8b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a8a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a8a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a8fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001aa0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ace5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a8fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001aa0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ace5`

## string_xrefs

- `0x18001aa05`: `Windows.Web.Http.Filters.HttpBaseProtocolFilter`
- `0x18001a8f7`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 IsInternal(void)
{
  HRESULT v0; // eax
  signed int v1; // ebx
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  HRESULT v29; // eax
  int v30; // edx
  unsigned int v31; // r8d
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  int v45; // eax
  DWORD v46; // edx
  int v47; // r8d
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  int v64; // eax
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v91; // [rsp+20h] [rbp-29h] BYREF
  __int64 v92; // [rsp+28h] [rbp-21h] BYREF
  __int64 v93; // [rsp+30h] [rbp-19h] BYREF
  _BYTE v94[8]; // [rsp+38h] [rbp-11h] BYREF
  __int64 v95; // [rsp+40h] [rbp-9h] BYREF
  __int64 v96; // [rsp+48h] [rbp-1h] BYREF
  __int64 v97; // [rsp+50h] [rbp+7h] BYREF
  __int64 v98; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v99; // [rsp+60h] [rbp+17h] BYREF
  HSTRING string; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v101; // [rsp+70h] [rbp+27h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+2Fh] BYREF
  HSTRING v103; // [rsp+90h] [rbp+47h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  v0 = WindowsCreateString(L"http://hrweb/Pages/default.aspx", 0x1Fu, &string);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v0,
      v91);
    goto LABEL_166;
  }
  v92 = 0;
  v103 = 0;
  v2 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &v103);
  if ( v2 < 0 )
    goto LABEL_168;
  ActivationFactory = RoGetActivationFactory(v103, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v92);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v91);
    v6 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    goto LABEL_166;
  }
  v93 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v92 + 48LL))(v92, string, &v93);
  v1 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v7,
      v91);
    v8 = v93;
    if ( v93 )
    {
      v93 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_166;
  }
  v91 = 0;
  v103 = 0;
  v10 = WindowsCreateStringReference(L"Windows.Web.Http.Filters.HttpBaseProtocolFilter", 0x2Fu, &hstringHeader, &v103);
  if ( v10 < 0 )
  {
LABEL_169:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    JUMPOUT(0x18001B3D0LL);
  }
  v91 = 0;
  v101 = 0;
  v1 = RoActivateInstance(v103, &v101);
  if ( v1 >= 0 )
  {
    if ( !memcmp_0(&GUID_71c89b09_e131_4b54_a53c_eb43ff37e9bb, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v91 = v101;
    }
    else
    {
      v1 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v101)(
             v101,
             &GUID_71c89b09_e131_4b54_a53c_eb43ff37e9bb,
             &v91);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
    }
  }
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v1,
      v91);
    v13 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v93;
    if ( v93 )
    {
      v93 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_166;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 72LL))(v91, 0);
  v1 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v16,
      v91);
    v17 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v93;
    if ( v93 )
    {
      v93 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_166;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 56LL))(v91, 0);
  v1 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v20,
      v91);
    v21 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v93;
    if ( v93 )
    {
      v93 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_166;
  }
  v95 = 0;
  v24 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v91)(
          v91,
          &GUID_a4cb6dd5_0902_439e_bfd7_e12552b165ce,
          &v95);
  v1 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v24,
      v91);
    v25 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v93;
    if ( v93 )
    {
      v93 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    goto LABEL_166;
  }
  v96 = 0;
  v103 = 0;
  v29 = WindowsCreateStringReference(L"Windows.Web.Http.HttpClient", 0x1Bu, &hstringHeader, &v103);
  if ( v29 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v31);
LABEL_168:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    goto LABEL_169;
  }
  v32 = RoGetActivationFactory(v103, &GUID_c30c4eca_e3fa_4f99_afb4_63cc65009462, &v96);
  v1 = v32;
  if ( v32 >= 0 )
  {
    v97 = 0;
    v38 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v96 + 48LL))(v96, v95, &v97);
    v1 = v38;
    if ( v38 >= 0 )
    {
      v98 = 0;
      v45 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v97 + 56LL))(v97, v93, &v98);
      v1 = v45;
      if ( v45 >= 0 )
      {
        v99 = 0;
        v55 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *>(
                v98,
                v46,
                v47);
        v1 = v55;
        if ( v55 >= 0 )
        {
          v64 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v98 + 80LL))(v98, &v99);
          v1 = v64;
          if ( v64 >= 0 )
          {
            v94[0] = 0;
            v73 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v99 + 72LL))(v99, v94);
            v1 = v73;
            if ( v73 >= 0 )
            {
              v1 = v94[0] == 0 ? 0x80070005 : 0;
              v82 = v99;
              if ( v99 )
              {
                v99 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
              }
              v83 = v98;
              if ( v98 )
              {
                v98 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
              }
              v84 = v97;
              if ( v97 )
              {
                v97 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
              }
              v85 = v96;
              if ( v96 )
              {
                v96 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
              }
              v86 = v95;
              if ( v95 )
              {
                v95 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
              }
              v87 = v91;
              if ( v91 )
              {
                v91 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
              }
              v88 = v93;
              if ( v93 )
              {
                v93 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
              }
              v89 = v92;
              if ( v92 )
              {
                v92 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC7,
                (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
                (const char *)(unsigned int)v73,
                v91);
              v74 = v99;
              if ( v99 )
              {
                v99 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
              }
              v75 = v98;
              if ( v98 )
              {
                v98 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
              }
              v76 = v97;
              if ( v97 )
              {
                v97 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
              }
              v77 = v96;
              if ( v96 )
              {
                v96 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
              }
              v78 = v95;
              if ( v95 )
              {
                v95 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
              }
              v79 = v91;
              if ( v91 )
              {
                v91 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
              }
              v80 = v93;
              if ( v93 )
              {
                v93 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
              }
              v81 = v92;
              if ( v92 )
              {
                v92 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
              }
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC4,
              (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
              (const char *)(unsigned int)v64,
              v91);
            v65 = v99;
            if ( v99 )
            {
              v99 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
            }
            v66 = v98;
            if ( v98 )
            {
              v98 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
            }
            v67 = v97;
            if ( v97 )
            {
              v97 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
            }
            v68 = v96;
            if ( v96 )
            {
              v96 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
            }
            v69 = v95;
            if ( v95 )
            {
              v95 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
            }
            v70 = v91;
            if ( v91 )
            {
              v91 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
            }
            v71 = v93;
            if ( v93 )
            {
              v93 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
            }
            v72 = v92;
            if ( v92 )
            {
              v92 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC3,
            (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
            (const char *)(unsigned int)v55,
            v91);
          v56 = v99;
          if ( v99 )
          {
            v99 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
          }
          v57 = v98;
          if ( v98 )
          {
            v98 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
          }
          v58 = v97;
          if ( v97 )
          {
            v97 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
          v59 = v96;
          if ( v96 )
          {
            v96 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          }
          v60 = v95;
          if ( v95 )
          {
            v95 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          }
          v61 = v91;
          if ( v91 )
          {
            v91 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
          }
          v62 = v93;
          if ( v93 )
          {
            v93 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          }
          v63 = v92;
          if ( v92 )
          {
            v92 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
          (const char *)(unsigned int)v45,
          v91);
        v48 = v98;
        if ( v98 )
        {
          v98 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        }
        v49 = v97;
        if ( v97 )
        {
          v97 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
        v50 = v96;
        if ( v96 )
        {
          v96 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        }
        v51 = v95;
        if ( v95 )
        {
          v95 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
        v52 = v91;
        if ( v91 )
        {
          v91 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        }
        v53 = v93;
        if ( v93 )
        {
          v93 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        }
        v54 = v92;
        if ( v92 )
        {
          v92 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
        (const char *)(unsigned int)v38,
        v91);
      v39 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      }
      v40 = v96;
      if ( v96 )
      {
        v96 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      v41 = v95;
      if ( v95 )
      {
        v95 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = v91;
      if ( v91 )
      {
        v91 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v43 = v93;
      if ( v93 )
      {
        v93 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      v44 = v92;
      if ( v92 )
      {
        v92 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v32,
      v91);
    v33 = v96;
    if ( v96 )
    {
      v96 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v93;
    if ( v93 )
    {
      v93 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
  }
LABEL_166:
  WindowsDeleteString(string);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001a874  mov     [rsp-8+arg_0], rbx
0x18001a879  mov     [rsp-8+arg_8], rdi
0x18001a87e  push    rbp
0x18001a87f  lea     rbp, [rsp-57h]
0x18001a884  sub     rsp, 0A0h
0x18001a88b  mov     rax, cs:__security_cookie
0x18001a892  xor     rax, rsp
0x18001a895  mov     [rbp+57h+var_8], rax
0x18001a899  xor     edi, edi
0x18001a89b  mov     [rbp+57h+string], rdi
0x18001a89f  xor     ecx, ecx; string
0x18001a8a1  call    cs:__imp_WindowsDeleteString
0x18001a8a7  mov     [rbp+57h+string], rdi
0x18001a8ab  lea     r8, [rbp+57h+string]; string
0x18001a8af  lea     edx, [rdi+1Fh]; length
0x18001a8b2  lea     rcx, sourceString; "http://hrweb/Pages/default.aspx"
0x18001a8b9  call    cs:__imp_WindowsCreateString
0x18001a8bf  mov     ebx, eax
0x18001a8c1  test    eax, eax
0x18001a8c3  jns     short loc_18001A8E2
0x18001a8c5  mov     rcx, [rbp+5Fh]; this
0x18001a8c9  mov     r9d, eax; char *
0x18001a8cc  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001a8d3  mov     edx, 0A8h; void *
0x18001a8d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a8dd  jmp     loc_18001B38C
0x18001a8e2  mov     [rbp+57h+var_78], rdi
0x18001a8e6  mov     [rbp+57h+var_10], rdi
0x18001a8ea  lea     r9, [rbp+57h+var_10]; string
0x18001a8ee  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001a8f2  mov     edx, 16h; length
0x18001a8f7  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18001a8fe  call    cs:__imp_WindowsCreateStringReference
0x18001a904  test    eax, eax
0x18001a906  js      loc_18001B3C1
0x18001a90c  mov     rbx, [rbp+57h+var_10]
0x18001a910  mov     rcx, [rbp+57h+var_78]
0x18001a914  test    rcx, rcx
0x18001a917  jz      short loc_18001A92A
0x18001a919  mov     [rbp+57h+var_78], rdi
0x18001a91d  mov     rax, [rcx]
0x18001a920  mov     rax, [rax+10h]
0x18001a924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a929  nop
0x18001a92a  lea     r8, [rbp+57h+var_78]
0x18001a92e  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18001a935  mov     rcx, rbx
0x18001a938  call    cs:__imp_RoGetActivationFactory
0x18001a93e  mov     ebx, eax
0x18001a940  test    eax, eax
0x18001a942  jns     short loc_18001A97C
0x18001a944  mov     rcx, [rbp+5Fh]; this
0x18001a948  mov     r9d, eax; char *
0x18001a94b  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001a952  mov     edx, 0ABh; void *
0x18001a957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a95c  nop
0x18001a95d  mov     rcx, [rbp+57h+var_78]
0x18001a961  test    rcx, rcx
0x18001a964  jz      short loc_18001A977
0x18001a966  mov     [rbp+57h+var_78], rdi
0x18001a96a  mov     rax, [rcx]
0x18001a96d  mov     rax, [rax+10h]
0x18001a971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a976  nop
0x18001a977  jmp     loc_18001B38C
0x18001a97c  mov     [rbp+57h+var_70], rdi
0x18001a980  mov     rcx, [rbp+57h+var_78]
0x18001a984  mov     rax, [rcx]
0x18001a987  lea     r8, [rbp+57h+var_70]
0x18001a98b  mov     rdx, [rbp+57h+string]
0x18001a98f  mov     rax, [rax+30h]
0x18001a993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a998  mov     ebx, eax
0x18001a99a  test    eax, eax
0x18001a99c  jns     short loc_18001A9F0
0x18001a99e  mov     rcx, [rbp+5Fh]; this
0x18001a9a2  mov     r9d, eax; char *
0x18001a9a5  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001a9ac  mov     edx, 0AEh; void *
0x18001a9b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9b6  nop
0x18001a9b7  mov     rcx, [rbp+57h+var_70]
0x18001a9bb  test    rcx, rcx
0x18001a9be  jz      short loc_18001A9D1
0x18001a9c0  mov     [rbp+57h+var_70], rdi
0x18001a9c4  mov     rax, [rcx]
0x18001a9c7  mov     rax, [rax+10h]
0x18001a9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9d0  nop
0x18001a9d1  mov     rcx, [rbp+57h+var_78]
0x18001a9d5  test    rcx, rcx
0x18001a9d8  jz      short loc_18001A9EB
0x18001a9da  mov     [rbp+57h+var_78], rdi
0x18001a9de  mov     rax, [rcx]
0x18001a9e1  mov     rax, [rax+10h]
0x18001a9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9ea  nop
0x18001a9eb  jmp     loc_18001B38C
0x18001a9f0  mov     [rbp+57h+var_80], rdi
0x18001a9f4  mov     [rbp+57h+var_10], rdi
0x18001a9f8  lea     r9, [rbp+57h+var_10]; string
0x18001a9fc  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001aa00  mov     edx, 2Fh ; '/'; length
0x18001aa05  lea     rcx, ?RuntimeClass_Windows_Web_Http_Filters_HttpBaseProtocolFilter@@3QBGB; "Windows.Web.Http.Filters.HttpBaseProtoc"...
0x18001aa0c  call    cs:__imp_WindowsCreateStringReference
0x18001aa12  test    eax, eax
0x18001aa14  js      loc_18001B3C9
0x18001aa1a  mov     rbx, [rbp+57h+var_10]
0x18001aa1e  mov     rcx, [rbp+57h+var_80]
0x18001aa22  test    rcx, rcx
0x18001aa25  jz      short loc_18001AA38
0x18001aa27  mov     [rbp+57h+var_80], rdi
0x18001aa2b  mov     rax, [rcx]
0x18001aa2e  mov     rax, [rax+10h]
0x18001aa32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa37  nop
0x18001aa38  mov     [rbp+57h+var_80], rdi
0x18001aa3c  mov     [rbp+57h+var_30], rdi
0x18001aa40  lea     rdx, [rbp+57h+var_30]
0x18001aa44  mov     rcx, rbx
0x18001aa47  call    cs:__imp_RoActivateInstance
0x18001aa4d  mov     ebx, eax
0x18001aa4f  test    eax, eax
0x18001aa51  js      short loc_18001AAA3
0x18001aa53  mov     r8d, 10h; Size
0x18001aa59  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18001aa60  lea     rcx, _GUID_71c89b09_e131_4b54_a53c_eb43ff37e9bb; Buf1
0x18001aa67  call    memcmp_0
0x18001aa6c  mov     rcx, [rbp+57h+var_30]
0x18001aa70  test    eax, eax
0x18001aa72  jnz     short loc_18001AA7A
0x18001aa74  mov     [rbp+57h+var_80], rcx
0x18001aa78  jmp     short loc_18001AAA3
0x18001aa7a  mov     rax, [rcx]
0x18001aa7d  lea     r8, [rbp+57h+var_80]
0x18001aa81  lea     rdx, _GUID_71c89b09_e131_4b54_a53c_eb43ff37e9bb
0x18001aa88  mov     rax, [rax]
0x18001aa8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa90  mov     ebx, eax
0x18001aa92  mov     rcx, [rbp+57h+var_30]
0x18001aa96  mov     rax, [rcx]
0x18001aa99  mov     rax, [rax+10h]
0x18001aa9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaa2  nop
0x18001aaa3  test    ebx, ebx
0x18001aaa5  jns     short loc_18001AB13
0x18001aaa7  mov     rcx, [rbp+5Fh]; this
0x18001aaab  mov     r9d, ebx; char *
0x18001aaae  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001aab5  mov     edx, 0B1h; void *
0x18001aaba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aabf  nop
0x18001aac0  mov     rcx, [rbp+57h+var_80]
0x18001aac4  test    rcx, rcx
0x18001aac7  jz      short loc_18001AADA
0x18001aac9  mov     [rbp+57h+var_80], rdi
0x18001aacd  mov     rax, [rcx]
0x18001aad0  mov     rax, [rax+10h]
0x18001aad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aad9  nop
0x18001aada  mov     rcx, [rbp+57h+var_70]
0x18001aade  test    rcx, rcx
0x18001aae1  jz      short loc_18001AAF4
0x18001aae3  mov     [rbp+57h+var_70], rdi
0x18001aae7  mov     rax, [rcx]
0x18001aaea  mov     rax, [rax+10h]
0x18001aaee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaf3  nop
0x18001aaf4  mov     rcx, [rbp+57h+var_78]
0x18001aaf8  test    rcx, rcx
0x18001aafb  jz      short loc_18001AB0E
0x18001aafd  mov     [rbp+57h+var_78], rdi
0x18001ab01  mov     rax, [rcx]
0x18001ab04  mov     rax, [rax+10h]
0x18001ab08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab0d  nop
0x18001ab0e  jmp     loc_18001B38C
0x18001ab13  mov     rcx, [rbp+57h+var_80]
0x18001ab17  mov     rax, [rcx]
0x18001ab1a  xor     edx, edx
0x18001ab1c  mov     rax, [rax+48h]
0x18001ab20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab25  mov     ebx, eax
0x18001ab27  test    eax, eax
0x18001ab29  jns     short loc_18001AB97
0x18001ab2b  mov     rcx, [rbp+5Fh]; this
0x18001ab2f  mov     r9d, eax; char *
0x18001ab32  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001ab39  mov     edx, 0B3h; void *
0x18001ab3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ab43  nop
0x18001ab44  mov     rcx, [rbp+57h+var_80]
0x18001ab48  test    rcx, rcx
0x18001ab4b  jz      short loc_18001AB5E
0x18001ab4d  mov     [rbp+57h+var_80], rdi
0x18001ab51  mov     rax, [rcx]
0x18001ab54  mov     rax, [rax+10h]
0x18001ab58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab5d  nop
0x18001ab5e  mov     rcx, [rbp+57h+var_70]
0x18001ab62  test    rcx, rcx
0x18001ab65  jz      short loc_18001AB78
0x18001ab67  mov     [rbp+57h+var_70], rdi
0x18001ab6b  mov     rax, [rcx]
0x18001ab6e  mov     rax, [rax+10h]
0x18001ab72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab77  nop
0x18001ab78  mov     rcx, [rbp+57h+var_78]
0x18001ab7c  test    rcx, rcx
0x18001ab7f  jz      short loc_18001AB92
0x18001ab81  mov     [rbp+57h+var_78], rdi
0x18001ab85  mov     rax, [rcx]
0x18001ab88  mov     rax, [rax+10h]
0x18001ab8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab91  nop
0x18001ab92  jmp     loc_18001B38C
0x18001ab97  mov     rcx, [rbp+57h+var_80]
0x18001ab9b  mov     rax, [rcx]
0x18001ab9e  xor     edx, edx
0x18001aba0  mov     rax, [rax+38h]
0x18001aba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aba9  mov     ebx, eax
0x18001abab  test    eax, eax
0x18001abad  jns     short loc_18001AC1B
0x18001abaf  mov     rcx, [rbp+5Fh]; this
0x18001abb3  mov     r9d, eax; char *
0x18001abb6  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001abbd  mov     edx, 0B4h; void *
0x18001abc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001abc7  nop
0x18001abc8  mov     rcx, [rbp+57h+var_80]
0x18001abcc  test    rcx, rcx
0x18001abcf  jz      short loc_18001ABE2
0x18001abd1  mov     [rbp+57h+var_80], rdi
0x18001abd5  mov     rax, [rcx]
0x18001abd8  mov     rax, [rax+10h]
0x18001abdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abe1  nop
0x18001abe2  mov     rcx, [rbp+57h+var_70]
0x18001abe6  test    rcx, rcx
0x18001abe9  jz      short loc_18001ABFC
0x18001abeb  mov     [rbp+57h+var_70], rdi
0x18001abef  mov     rax, [rcx]
0x18001abf2  mov     rax, [rax+10h]
0x18001abf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abfb  nop
0x18001abfc  mov     rcx, [rbp+57h+var_78]
0x18001ac00  test    rcx, rcx
0x18001ac03  jz      short loc_18001AC16
0x18001ac05  mov     [rbp+57h+var_78], rdi
0x18001ac09  mov     rax, [rcx]
0x18001ac0c  mov     rax, [rax+10h]
0x18001ac10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac15  nop
0x18001ac16  jmp     loc_18001B38C
0x18001ac1b  mov     [rbp+57h+var_60], rdi
0x18001ac1f  mov     rcx, [rbp+57h+var_80]
0x18001ac23  mov     rax, [rcx]
0x18001ac26  lea     r8, [rbp+57h+var_60]
0x18001ac2a  lea     rdx, _GUID_a4cb6dd5_0902_439e_bfd7_e12552b165ce
0x18001ac31  mov     rax, [rax]
0x18001ac34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac39  mov     ebx, eax
0x18001ac3b  test    eax, eax
0x18001ac3d  jns     loc_18001ACC9
0x18001ac43  mov     rcx, [rbp+5Fh]; this
0x18001ac47  mov     r9d, eax; char *
0x18001ac4a  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001ac51  mov     edx, 0B7h; void *
0x18001ac56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ac5b  nop
0x18001ac5c  mov     rcx, [rbp+57h+var_60]
0x18001ac60  test    rcx, rcx
0x18001ac63  jz      short loc_18001AC76
0x18001ac65  mov     [rbp+57h+var_60], rdi
0x18001ac69  mov     rax, [rcx]
0x18001ac6c  mov     rax, [rax+10h]
0x18001ac70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac75  nop
0x18001ac76  mov     rcx, [rbp+57h+var_80]
0x18001ac7a  test    rcx, rcx
0x18001ac7d  jz      short loc_18001AC90
0x18001ac7f  mov     [rbp+57h+var_80], rdi
0x18001ac83  mov     rax, [rcx]
0x18001ac86  mov     rax, [rax+10h]
0x18001ac8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac8f  nop
0x18001ac90  mov     rcx, [rbp+57h+var_70]
0x18001ac94  test    rcx, rcx
0x18001ac97  jz      short loc_18001ACAA
0x18001ac99  mov     [rbp+57h+var_70], rdi
0x18001ac9d  mov     rax, [rcx]
0x18001aca0  mov     rax, [rax+10h]
0x18001aca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aca9  nop
0x18001acaa  mov     rcx, [rbp+57h+var_78]
0x18001acae  test    rcx, rcx
0x18001acb1  jz      short loc_18001ACC4
0x18001acb3  mov     [rbp+57h+var_78], rdi
  ... truncated ...
```
