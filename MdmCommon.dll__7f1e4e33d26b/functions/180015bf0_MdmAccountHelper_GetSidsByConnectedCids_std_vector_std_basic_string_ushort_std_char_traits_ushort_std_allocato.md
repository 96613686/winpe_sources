# MdmAccountHelper::GetSidsByConnectedCids(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180015bf0`
- end: `0x1800166f0`
- name: `?GetSidsByConnectedCids@MdmAccountHelper@@SAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z`
- size: `2816`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003930`

## callees

- `0x180001520`
- `0x1800028e4`
- `0x180002de4`
- `0x180002e50`
- `0x180006548`
- `0x1800066b0`
- `0x180009710`
- `0x180014084`
- `0x180015bf0`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180016208`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016299`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016299`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015c86`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800160a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800160a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016677`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800160b7`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001637a`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800160b7`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001637a`

## string_xrefs

- `0x180015cb3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015dc2`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015eb1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015f65`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180016023`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800160e4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800162e6`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800163a7`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800162d2`: `CHR(spPropStore->GetValue(PKEY_Identity_PrimarySid, &propertyValue))`
- `0x180015c9f`: `CHR(CoCreateInstance( __uuidof(CoClassConnectedUserStore), nullptr, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLSCTX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(**(spUserStore.GetAddressOf())), IID_PPV_ARGS_Helper(spUserStore.GetAddressOf())))`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::GetSidsByConnectedCids(__int64 *a1, __int64 a2)
{
  char **v4; // rdi
  char **v5; // rbx
  int v6; // edx
  int v7; // ecx
  HRESULT v8; // ebx
  LPVOID v9; // rbx
  __int64 (__fastcall *v10)(LPVOID, _QWORD, _QWORD, _QWORD **); // rdi
  _QWORD *v11; // rcx
  int v12; // edx
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v21; // rcx
  int v22; // edx
  int v23; // ecx
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rcx
  int v27; // edx
  int v28; // ecx
  __int64 v29; // rcx
  _QWORD *v30; // rcx
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rcx
  int v32; // edx
  int v33; // ecx
  __int64 v34; // rcx
  _QWORD *v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rcx
  int v37; // edx
  int v38; // ecx
  __int64 v39; // r8
  __int64 v40; // rcx
  _QWORD *v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, _QWORD, _QWORD); // rcx
  unsigned __int64 v43; // rdx
  wchar_t **v44; // rdi
  __int64 v45; // rbx
  wchar_t *v46; // rcx
  wchar_t **v47; // rdi
  wchar_t **v48; // rdx
  wchar_t **v49; // r15
  wchar_t **v50; // rbx
  __int64 v51; // rdi
  __int64 i; // rbx
  wchar_t **v53; // rdx
  size_t v54; // r8
  const wchar_t *v55; // rax
  int v56; // edx
  int v57; // ecx
  __int64 v58; // rcx
  _QWORD *v59; // rcx
  __int64 (__fastcall ***v60)(_QWORD, _QWORD, _QWORD); // rcx
  int v61; // edx
  int v62; // ecx
  __int64 v63; // rcx
  _QWORD *v64; // rcx
  __int64 (__fastcall ***v65)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v66; // rax
  __int64 v67; // rdx
  int v68; // ecx
  __int64 v69; // rcx
  _QWORD *v70; // rcx
  __int64 (__fastcall ***v71)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v72; // rcx
  _QWORD *v73; // rcx
  __int64 (__fastcall ***v74)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v75; // rcx
  _QWORD *v76; // rcx
  __int64 (__fastcall ***v77)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v78; // rcx
  _QWORD *v79; // rcx
  __int64 (__fastcall ***v80)(_QWORD, _QWORD, _QWORD); // rcx
  char **v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  _QWORD *v84; // rcx
  LPVOID v85; // rcx
  _BYTE v87[32]; // [rsp+0h] [rbp-118h] BYREF
  _QWORD *v88; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v89; // [rsp+38h] [rbp-E0h] BYREF
  __int64 (__fastcall ***v90)(_QWORD, GUID *, _QWORD **); // [rsp+40h] [rbp-D8h] BYREF
  int v91; // [rsp+48h] [rbp-D0h]
  LPVOID pv; // [rsp+50h] [rbp-C8h] BYREF
  _QWORD *v93; // [rsp+58h] [rbp-C0h] BYREF
  int v94; // [rsp+60h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-B0h] BYREF
  __int128 v96; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v97; // [rsp+80h] [rbp-98h]
  PROPVARIANT propvar[2]; // [rsp+88h] [rbp-90h] BYREF
  __int64 v99; // [rsp+98h] [rbp-80h]
  wchar_t *S2[2]; // [rsp+A0h] [rbp-78h] BYREF
  unsigned __int64 v101; // [rsp+B0h] [rbp-68h]
  unsigned __int64 v102; // [rsp+B8h] [rbp-60h]
  char *v103[4]; // [rsp+C0h] [rbp-58h] BYREF

  ppv = 0;
  v93 = 0;
  pv = 0;
  v96 = 0;
  v97 = 0;
  v4 = *(char ***)(a2 + 8);
  v5 = *(char ***)a2;
  if ( *(char ***)a2 != v4 )
  {
    do
    {
      std::wstring::~wstring(v5);
      v5 += 4;
    }
    while ( v5 != v4 );
    *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
  }
  v8 = CoCreateInstance(
         &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
         0,
         0x17u,
         &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
         &ppv);
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        v8,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
        127,
        "CHR(CoCreateInstance( __uuidof(CoClassConnectedUserStore), nullptr, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER"
        "| CLSCTX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(**(spUserStore.GetAddressOf())), IID_PPV_ARGS_Helper(spUs"
        "erStore.GetAddressOf())))");
    goto LABEL_151;
  }
  v9 = ppv;
  v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD **))(*(_QWORD *)ppv + 24LL);
  v11 = v93;
  if ( v93 )
  {
    v93 = 0;
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v11 + 16LL))(v11, *v11);
  }
  v8 = v10(v9, 0, 0, &v93);
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v13,
        v12,
        v8,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
        132,
        "CHR(spUserStore->GetConnectedUserEnum( 0, nullptr, &spUserEnum))");
    goto LABEL_151;
  }
  while ( 1 )
  {
    v90 = 0;
    v88 = 0;
    v89 = 0;
    v94 = 0;
    *(_OWORD *)propvar = 0;
    v99 = 0;
    *(_OWORD *)S2 = 0;
    v101 = 0;
    v102 = 7;
    LOWORD(S2[0]) = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **), int *))(*v93 + 24LL))(
           v93,
           1,
           &v90,
           &v94);
    if ( v8 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v15,
          v14,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          143,
          "CHR(spUserEnum->Next(1, spUnknown.GetAddressOf(), &cFetch))");
      std::wstring::~wstring((char **)S2);
      v16 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v17 = v88;
      if ( v88 )
      {
        v88 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
      }
      v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
      if ( v90 )
      {
        v90 = 0;
        ((void (__fastcall *)(_QWORD))(*v18)[2])(v18);
      }
      goto LABEL_151;
    }
    if ( v8 == 1 || !v94 )
      break;
    v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
    v20 = **v90;
    v21 = v88;
    if ( v88 )
    {
      v88 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v21 + 16LL))(v21, *v21);
    }
    v8 = v20(v19, &GUID_9d5f2149_de8c_45f2_b313_6587a04f771d, &v88);
    if ( v8 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v23,
          v22,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          150,
          "CHR(spUnknown.As(&spUser))");
      std::wstring::~wstring((char **)S2);
      v24 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      v25 = v88;
      if ( v88 )
      {
        v88 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
      }
      v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
      if ( v90 )
      {
        v90 = 0;
        ((void (__fastcall *)(_QWORD))(*v26)[2])(v26);
      }
      goto LABEL_151;
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v88 + 24LL))(v88, &v89);
    if ( v8 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v28,
          v27,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          151,
          "CHR(spUser->GetConnectedUserInfo(spPropStore.GetAddressOf()))");
      std::wstring::~wstring((char **)S2);
      v29 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = v88;
      if ( v88 )
      {
        v88 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
      }
      v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
      if ( v90 )
      {
        v90 = 0;
        ((void (__fastcall *)(_QWORD))(*v31)[2])(v31);
      }
      goto LABEL_151;
    }
    v8 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v89 + 40LL))(
           v89,
           &PKEY_Identity_UniqueID,
           propvar);
    if ( v8 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v33,
          v32,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          154,
          "CHR(spPropStore->GetValue(PKEY_Identity_UniqueID, &propertyValue))");
      std::wstring::~wstring((char **)S2);
      v34 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v35 = v88;
      if ( v88 )
      {
        v88 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
      }
      v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
      if ( v90 )
      {
        v90 = 0;
        ((void (__fastcall *)(_QWORD))(*v36)[2])(v36);
      }
      goto LABEL_151;
    }
    if ( pv )
      CoTaskMemFree(pv);
    v8 = PropVariantToStringAlloc(propvar, (PWSTR *)&pv);
    if ( v8 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v38,
          v37,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          161,
          "CHR(PropVariantToStringAlloc(propertyValue, &pwszValue))");
      std::wstring::~wstring((char **)S2);
      v40 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      v41 = v88;
      if ( v88 )
      {
        v88 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v41 + 16LL))(v41);
      }
      v42 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
      if ( v90 )
      {
        v90 = 0;
        ((void (__fastcall *)(_QWORD))(*v42)[2])(v42);
      }
      goto LABEL_151;
    }
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)pv + v43) );
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( v43 > v102 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)S2,
          v43,
          v39,
          pv);
      }
      else
      {
        v44 = S2;
        if ( v102 > 7 )
          v44 = (wchar_t **)S2[0];
        v101 = v43;
        v45 = 2 * v43;
        memmove_0(v44, pv, 2 * v43);
        *(_WORD *)((char *)v44 + v45) = 0;
      }
      v46 = S2[0];
      if ( v102 <= 7 )
      {
        v47 = S2;
        v48 = S2;
      }
      else
      {
        v47 = (wchar_t **)S2[0];
        v48 = (wchar_t **)S2[0];
      }
      v49 = (wchar_t **)((char *)v48 + 2 * v101);
      v50 = S2;
      if ( v102 > 7 )
        v50 = (wchar_t **)S2[0];
      while ( v50 != v49 )
      {
        *(_WORD *)v47 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v50);
        v50 = (wchar_t **)((char *)v50 + 2);
        v47 = (wchar_t **)((char *)v47 + 2);
        v46 = S2[0];
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v91 = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)v46,
            (unsigned int)v87,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
            170,
            "CHR(((HRESULT)0x8007000EL))");
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180016558);
        std::wstring::~wstring((char **)S2);
        v75 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
        }
        v76 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v76 + 16LL))(v76);
        }
        v77 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
        if ( v90 )
        {
          v90 = 0;
          ((void (__fastcall *)(_QWORD))(*v77)[2])(v77);
        }
LABEL_142:
        v8 = v91;
        goto LABEL_151;
      }
    }
    v51 = a1[1];
    for ( i = *a1; i != v51; i += 32 )
    {
      v53 = S2;
      if ( v102 > 7 )
        v53 = (wchar_t **)v46;
      v54 = *(_QWORD *)(i + 16);
      if ( *(_QWORD *)(i + 24) <= 7u )
        v55 = (const wchar_t *)i;
      else
        v55 = *(const wchar_t **)i;
      if ( v54 == v101 )
      {
        if ( !v54 || !wmemcmp(v55, (const wchar_t *)v53, v54) )
          break;
        v46 = S2[0];
      }
    }
    if ( i != a1[1] )
    {
      PropVariantClear(propvar);
      v8 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v89 + 40LL))(
             v89,
             &PKEY_Identity_PrimarySid,
             propvar);
      if ( v8 < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v57,
            v56,
            v8,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
            178,
            "CHR(spPropStore->GetValue(PKEY_Identity_PrimarySid, &propertyValue))");
        std::wstring::~wstring((char **)S2);
        v58 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        }
        v59 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v59 + 16LL))(v59);
        }
        v60 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
        if ( v90 )
        {
          v90 = 0;
          ((void (__fastcall *)(_QWORD))(*v60)[2])(v60);
        }
        goto LABEL_151;
      }
      if ( pv )
        CoTaskMemFree(pv);
      v8 = PropVariantToStringAlloc(propvar, (PWSTR *)&pv);
      if ( v8 < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v62,
            v61,
            v8,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
            185,
            "CHR(PropVariantToStringAlloc(propertyValue, &pwszValue))");
        std::wstring::~wstring((char **)S2);
        v63 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        }
        v64 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
        }
        v65 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
        if ( v90 )
        {
          v90 = 0;
          ((void (__fastcall *)(_QWORD))(*v65)[2])(v65);
        }
        goto LABEL_151;
      }
      if ( __eh34_try(-1, 2) )
      {
        __eh34_scope_strut(2);
        v66 = std::wstring::wstring(v103, pv);
        v67 = *((_QWORD *)&v96 + 1);
        if ( *((_QWORD *)&v96 + 1) == v97 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v96, *((_QWORD *)&v96 + 1), v66);
        }
        else
        {
          **((_OWORD **)&v96 + 1) = 0;
          *(_QWORD *)(v67 + 16) = 0;
          *(_QWORD *)(v67 + 24) = 0;
          *(_OWORD *)v67 = *(_OWORD *)v66;
          *(_OWORD *)(v67 + 16) = *(_OWORD *)(v66 + 16);
          *(_QWORD *)(v66 + 16) = 0;
          *(_QWORD *)(v66 + 24) = 7;
          *(_WORD *)v66 = 0;
          *((_QWORD *)&v96 + 1) += 32LL;
        }
        std::wstring::~wstring(v103);
      }
      if ( __eh34_catch(2) )
      {
        if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          v91 = -2147024882;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v68,
              (unsigned int)v87,
              -2147024882,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
              193,
              "CHR(((HRESULT)0x8007000EL))");
          __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_1800164F2);
          std::wstring::~wstring((char **)S2);
          v72 = v89;
          if ( v89 )
          {
            v89 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
          }
          v73 = v88;
          if ( v88 )
          {
            v88 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v73 + 16LL))(v73);
          }
          v74 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
          if ( v90 )
          {
            v90 = 0;
            ((void (__fastcall *)(_QWORD))(*v74)[2])(v74);
          }
          goto LABEL_142;
        }
      }
    }
    std::wstring::~wstring((char **)S2);
    v69 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    }
    v70 = v88;
    if ( v88 )
    {
      v88 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v70 + 16LL))(v70);
    }
    v71 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
    if ( v90 )
    {
      v90 = 0;
      ((void (__fastcall *)(_QWORD))(*v71)[2])(v71);
    }
  }
  v8 = 0;
  std::wstring::~wstring((char **)S2);
  v78 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
  }
  v79 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v79 + 16LL))(v79);
  }
  v80 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v90;
  if ( v90 )
  {
    v90 = 0;
    ((void (__fastcall *)(_QWORD))(*v80)[2])(v80);
  }
  if ( (__int128 *)a2 != &v96 )
  {
    v81 = *(char ***)a2;
    *(_QWORD *)a2 = v96;
    *(_QWORD *)&v96 = v81;
    v82 = *(_QWORD *)(a2 + 8);
    *(_QWORD *)(a2 + 8) = *((_QWORD *)&v96 + 1);
    *((_QWORD *)&v96 + 1) = v82;
    v83 = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = v97;
    v97 = v83;
  }
LABEL_151:
  if ( pv )
    CoTaskMemFree(pv);
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v96);
  v84 = v93;
  if ( v93 )
  {
    v93 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
  }
  v85 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v85 + 16LL))(v85);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015bf0  mov     [rsp+arg_0], rbx
0x180015bf5  mov     [rsp+arg_10], rsi
0x180015bfa  push    rdi
0x180015bfb  push    r12
0x180015bfd  push    r13
0x180015bff  push    r14
0x180015c01  push    r15
0x180015c03  sub     rsp, 0F0h
0x180015c0a  mov     rax, cs:__security_cookie
0x180015c11  xor     rax, rsp
0x180015c14  mov     [rsp+118h+var_38], rax
0x180015c1c  mov     r14, rdx
0x180015c1f  mov     r12, rcx
0x180015c22  xor     esi, esi
0x180015c24  mov     [rsp+118h+var_B0], rsi
0x180015c29  mov     [rsp+118h+var_C0], rsi
0x180015c2e  mov     [rsp+118h+pv], rsi
0x180015c33  xorps   xmm0, xmm0
0x180015c36  movdqu  [rsp+118h+var_A8], xmm0
0x180015c3c  mov     [rsp+118h+var_98], rsi
0x180015c44  mov     rdi, [rdx+8]
0x180015c48  mov     rbx, [rdx]
0x180015c4b  cmp     rbx, rdi
0x180015c4e  jz      short loc_180015C68
0x180015c50  mov     rcx, rbx
0x180015c53  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015c58  add     rbx, 20h ; ' '
0x180015c5c  cmp     rbx, rdi
0x180015c5f  jnz     short loc_180015C50
0x180015c61  mov     rax, [r14]
0x180015c64  mov     [r14+8], rax
0x180015c68  lea     rax, [rsp+118h+var_B0]
0x180015c6d  mov     [rsp+118h+ppv], rax; ppv
0x180015c72  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x180015c79  xor     edx, edx; pUnkOuter
0x180015c7b  lea     r8d, [rdx+17h]; dwClsContext
0x180015c7f  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x180015c86  call    cs:__imp_CoCreateInstance
0x180015c8c  mov     ebx, eax
0x180015c8e  test    eax, eax
0x180015c90  jns     short loc_180015CC7
0x180015c92  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015c99  jz      loc_18001666D
0x180015c9f  lea     rax, aChrCocreateins_1; "CHR(CoCreateInstance( __uuidof(CoClassC"...
0x180015ca6  mov     [rsp+118h+var_F0], rax
0x180015cab  mov     dword ptr [rsp+118h+ppv], 17Fh
0x180015cb3  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180015cba  mov     r8d, ebx
0x180015cbd  call    McTemplateU0dsqs_EventWriteTransfer
0x180015cc2  jmp     loc_18001666D
0x180015cc7  mov     rbx, [rsp+118h+var_B0]
0x180015ccc  mov     rax, [rbx]
0x180015ccf  mov     rdi, [rax+18h]
0x180015cd3  mov     rcx, [rsp+118h+var_C0]
0x180015cd8  test    rcx, rcx
0x180015cdb  jz      short loc_180015CEF
0x180015cdd  mov     [rsp+118h+var_C0], rsi
0x180015ce2  mov     rdx, [rcx]
0x180015ce5  mov     rax, [rdx+10h]
0x180015ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cee  nop
0x180015cef  lea     r9, [rsp+118h+var_C0]
0x180015cf4  xor     r8d, r8d
0x180015cf7  xor     edx, edx
0x180015cf9  mov     rcx, rbx
0x180015cfc  mov     rax, rdi
0x180015cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d04  mov     ebx, eax
0x180015d06  test    eax, eax
0x180015d08  jns     short loc_180015D2D
0x180015d0a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015d11  jz      loc_18001666D
0x180015d17  lea     rax, aChrSpuserstore_0; "CHR(spUserStore->GetConnectedUserEnum( "...
0x180015d1e  mov     [rsp+118h+var_F0], rax
0x180015d23  mov     dword ptr [rsp+118h+ppv], 184h
0x180015d2b  jmp     short loc_180015CB3
0x180015d2d  mov     r13d, 7
0x180015d33  mov     [rsp+118h+var_D8], rsi
0x180015d38  mov     [rsp+118h+var_E8], rsi
0x180015d3d  mov     [rsp+118h+var_E0], rsi
0x180015d42  mov     [rsp+118h+var_B8], esi
0x180015d46  xorps   xmm0, xmm0
0x180015d49  xor     eax, eax
0x180015d4b  movups  xmmword ptr [rsp+118h+propvar], xmm0
0x180015d53  mov     [rsp+118h+var_80], rax
0x180015d5b  movups  xmmword ptr [rsp+118h+S2], xmm0
0x180015d63  mov     [rsp+118h+var_68], rsi
0x180015d6b  mov     [rsp+118h+var_60], r13
0x180015d73  mov     word ptr [rsp+118h+S2], si
0x180015d7b  mov     rcx, [rsp+118h+var_C0]
0x180015d80  mov     rax, [rcx]
0x180015d83  lea     r9, [rsp+118h+var_B8]
0x180015d88  lea     r8, [rsp+118h+var_D8]
0x180015d8d  mov     edx, 1
0x180015d92  mov     rax, [rax+18h]
0x180015d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d9b  mov     ebx, eax
0x180015d9d  test    eax, eax
0x180015d9f  jns     loc_180015E39
0x180015da5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015dac  jz      short loc_180015DD2
0x180015dae  lea     rax, aChrSpuserenumN; "CHR(spUserEnum->Next(1, spUnknown.GetAd"...
0x180015db5  mov     [rsp+118h+var_F0], rax
0x180015dba  mov     dword ptr [rsp+118h+ppv], 18Fh
0x180015dc2  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180015dc9  mov     r8d, ebx
0x180015dcc  call    McTemplateU0dsqs_EventWriteTransfer
0x180015dd1  nop
0x180015dd2  lea     rcx, [rsp+118h+S2]
0x180015dda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015ddf  nop
0x180015de0  mov     rcx, [rsp+118h+var_E0]
0x180015de5  test    rcx, rcx
0x180015de8  jz      short loc_180015DFC
0x180015dea  mov     [rsp+118h+var_E0], rsi
0x180015def  mov     rax, [rcx]
0x180015df2  mov     rax, [rax+10h]
0x180015df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dfb  nop
0x180015dfc  mov     rcx, [rsp+118h+var_E8]
0x180015e01  test    rcx, rcx
0x180015e04  jz      short loc_180015E18
0x180015e06  mov     [rsp+118h+var_E8], rsi
0x180015e0b  mov     rax, [rcx]
0x180015e0e  mov     rax, [rax+10h]
0x180015e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e17  nop
0x180015e18  mov     rcx, [rsp+118h+var_D8]
0x180015e1d  test    rcx, rcx
0x180015e20  jz      short loc_180015E34
0x180015e22  mov     [rsp+118h+var_D8], rsi
0x180015e27  mov     rax, [rcx]
0x180015e2a  mov     rax, [rax+10h]
0x180015e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e33  nop
0x180015e34  jmp     loc_18001666D
0x180015e39  cmp     ebx, 1
0x180015e3c  jz      loc_1800165C5
0x180015e42  cmp     [rsp+118h+var_B8], esi
0x180015e46  jz      loc_1800165C5
0x180015e4c  mov     rbx, [rsp+118h+var_D8]
0x180015e51  mov     rax, [rbx]
0x180015e54  mov     rdi, [rax]
0x180015e57  mov     rcx, [rsp+118h+var_E8]
0x180015e5c  test    rcx, rcx
0x180015e5f  jz      short loc_180015E73
0x180015e61  mov     [rsp+118h+var_E8], rsi
0x180015e66  mov     rdx, [rcx]
0x180015e69  mov     rax, [rdx+10h]
0x180015e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e72  nop
0x180015e73  lea     r8, [rsp+118h+var_E8]
0x180015e78  lea     rdx, _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d
0x180015e7f  mov     rcx, rbx
0x180015e82  mov     rax, rdi
0x180015e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e8a  mov     ebx, eax
0x180015e8c  test    eax, eax
0x180015e8e  jns     loc_180015F28
0x180015e94  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015e9b  jz      short loc_180015EC1
0x180015e9d  lea     rax, aChrSpunknownAs; "CHR(spUnknown.As(&spUser))"
0x180015ea4  mov     [rsp+118h+var_F0], rax
0x180015ea9  mov     dword ptr [rsp+118h+ppv], 196h
0x180015eb1  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180015eb8  mov     r8d, ebx
0x180015ebb  call    McTemplateU0dsqs_EventWriteTransfer
0x180015ec0  nop
0x180015ec1  lea     rcx, [rsp+118h+S2]
0x180015ec9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015ece  nop
0x180015ecf  mov     rcx, [rsp+118h+var_E0]
0x180015ed4  test    rcx, rcx
0x180015ed7  jz      short loc_180015EEB
0x180015ed9  mov     [rsp+118h+var_E0], rsi
0x180015ede  mov     rax, [rcx]
0x180015ee1  mov     rax, [rax+10h]
0x180015ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eea  nop
0x180015eeb  mov     rcx, [rsp+118h+var_E8]
0x180015ef0  test    rcx, rcx
0x180015ef3  jz      short loc_180015F07
0x180015ef5  mov     [rsp+118h+var_E8], rsi
0x180015efa  mov     rax, [rcx]
0x180015efd  mov     rax, [rax+10h]
0x180015f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f06  nop
0x180015f07  mov     rcx, [rsp+118h+var_D8]
0x180015f0c  test    rcx, rcx
0x180015f0f  jz      short loc_180015F23
0x180015f11  mov     [rsp+118h+var_D8], rsi
0x180015f16  mov     rax, [rcx]
0x180015f19  mov     rax, [rax+10h]
0x180015f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f22  nop
0x180015f23  jmp     loc_18001666D
0x180015f28  mov     rcx, [rsp+118h+var_E8]
0x180015f2d  mov     rax, [rcx]
0x180015f30  lea     rdx, [rsp+118h+var_E0]
0x180015f35  mov     rax, [rax+18h]
0x180015f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f3e  mov     ebx, eax
0x180015f40  test    eax, eax
0x180015f42  jns     loc_180015FDC
0x180015f48  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015f4f  jz      short loc_180015F75
0x180015f51  lea     rax, aChrSpuserGetco; "CHR(spUser->GetConnectedUserInfo(spProp"...
0x180015f58  mov     [rsp+118h+var_F0], rax
0x180015f5d  mov     dword ptr [rsp+118h+ppv], 197h
0x180015f65  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180015f6c  mov     r8d, ebx
0x180015f6f  call    McTemplateU0dsqs_EventWriteTransfer
0x180015f74  nop
0x180015f75  lea     rcx, [rsp+118h+S2]
0x180015f7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015f82  nop
0x180015f83  mov     rcx, [rsp+118h+var_E0]
0x180015f88  test    rcx, rcx
0x180015f8b  jz      short loc_180015F9F
0x180015f8d  mov     [rsp+118h+var_E0], rsi
0x180015f92  mov     rax, [rcx]
0x180015f95  mov     rax, [rax+10h]
0x180015f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f9e  nop
0x180015f9f  mov     rcx, [rsp+118h+var_E8]
0x180015fa4  test    rcx, rcx
0x180015fa7  jz      short loc_180015FBB
0x180015fa9  mov     [rsp+118h+var_E8], rsi
0x180015fae  mov     rax, [rcx]
0x180015fb1  mov     rax, [rax+10h]
0x180015fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fba  nop
0x180015fbb  mov     rcx, [rsp+118h+var_D8]
0x180015fc0  test    rcx, rcx
0x180015fc3  jz      short loc_180015FD7
0x180015fc5  mov     [rsp+118h+var_D8], rsi
0x180015fca  mov     rax, [rcx]
0x180015fcd  mov     rax, [rax+10h]
0x180015fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fd6  nop
0x180015fd7  jmp     loc_18001666D
0x180015fdc  mov     rcx, [rsp+118h+var_E0]
0x180015fe1  mov     rax, [rcx]
0x180015fe4  lea     r8, [rsp+118h+propvar]
0x180015fec  lea     rdx, PKEY_Identity_UniqueID
0x180015ff3  mov     rax, [rax+28h]
0x180015ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ffc  mov     ebx, eax
0x180015ffe  test    eax, eax
0x180016000  jns     loc_18001609A
0x180016006  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001600d  jz      short loc_180016033
0x18001600f  lea     rax, aChrSppropstore_1; "CHR(spPropStore->GetValue(PKEY_Identity"...
0x180016016  mov     [rsp+118h+var_F0], rax
0x18001601b  mov     dword ptr [rsp+118h+ppv], 19Ah
0x180016023  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001602a  mov     r8d, ebx
0x18001602d  call    McTemplateU0dsqs_EventWriteTransfer
0x180016032  nop
0x180016033  lea     rcx, [rsp+118h+S2]
0x18001603b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016040  nop
0x180016041  mov     rcx, [rsp+118h+var_E0]
0x180016046  test    rcx, rcx
0x180016049  jz      short loc_18001605D
0x18001604b  mov     [rsp+118h+var_E0], rsi
0x180016050  mov     rax, [rcx]
0x180016053  mov     rax, [rax+10h]
0x180016057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001605c  nop
0x18001605d  mov     rcx, [rsp+118h+var_E8]
0x180016062  test    rcx, rcx
0x180016065  jz      short loc_180016079
0x180016067  mov     [rsp+118h+var_E8], rsi
0x18001606c  mov     rax, [rcx]
0x18001606f  mov     rax, [rax+10h]
0x180016073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016078  nop
0x180016079  mov     rcx, [rsp+118h+var_D8]
0x18001607e  test    rcx, rcx
0x180016081  jz      short loc_180016095
0x180016083  mov     [rsp+118h+var_D8], rsi
0x180016088  mov     rax, [rcx]
0x18001608b  mov     rax, [rax+10h]
0x18001608f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016094  nop
0x180016095  jmp     loc_18001666D
0x18001609a  mov     rcx, [rsp+118h+pv]; pv
0x18001609f  test    rcx, rcx
0x1800160a2  jz      short loc_1800160AA
0x1800160a4  call    cs:__imp_CoTaskMemFree
0x1800160aa  lea     rdx, [rsp+118h+pv]; ppszOut
0x1800160af  lea     rcx, [rsp+118h+propvar]; propvar
0x1800160b7  call    cs:__imp_PropVariantToStringAlloc
0x1800160bd  mov     ebx, eax
0x1800160bf  test    eax, eax
0x1800160c1  jns     loc_18001615B
0x1800160c7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800160ce  jz      short loc_1800160F4
0x1800160d0  lea     rax, aChrPropvariant; "CHR(PropVariantToStringAlloc(propertyVa"...
  ... truncated ...
```
