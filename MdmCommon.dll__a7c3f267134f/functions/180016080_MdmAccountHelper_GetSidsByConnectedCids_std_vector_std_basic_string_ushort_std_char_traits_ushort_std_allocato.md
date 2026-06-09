# MdmAccountHelper::GetSidsByConnectedCids(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180016080`
- end: `0x180016bab`
- name: `?GetSidsByConnectedCids@MdmAccountHelper@@SAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z`
- size: `2859`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003940`

## callees

- `0x180001520`
- `0x1800028e4`
- `0x180002de8`
- `0x180002e54`
- `0x1800065c0`
- `0x180006734`
- `0x1800098f0`
- `0x180014490`
- `0x180016080`
- `0x18001dbfc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1800166aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001673b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001673b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016116`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001653a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001680f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001653a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001680f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b2b`
- `PROPSYS!PropVariantToStringAlloc` at `0x180016553`
- `PROPSYS!PropVariantToStringAlloc` at `0x180016828`
- `PROPSYS!PropVariantToStringAlloc` at `0x180016553`
- `PROPSYS!PropVariantToStringAlloc` at `0x180016828`

## string_xrefs

- `0x180016149`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180016258`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180016347`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800163fb`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800164b9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180016586`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001678e`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001685b`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001677a`: `CHR(spPropStore->GetValue(PKEY_Identity_PrimarySid, &propertyValue))`
- `0x180016135`: `CHR(CoCreateInstance( __uuidof(CoClassConnectedUserStore), nullptr, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLSCTX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(**(spUserStore.GetAddressOf())), IID_PPV_ARGS_Helper(spUserStore.GetAddressOf())))`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall MdmAccountHelper::GetSidsByConnectedCids(__int64 *a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
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
  __int64 v81; // rcx
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
  _BYTE v103[32]; // [rsp+C0h] [rbp-58h] BYREF

  ppv = 0;
  v93 = 0;
  pv = 0;
  v96 = 0;
  v97 = 0;
  v4 = a2[1];
  v5 = *a2;
  if ( *a2 != v4 )
  {
    do
    {
      std::wstring::~wstring(v5);
      v5 += 32;
    }
    while ( v5 != v4 );
    a2[1] = *a2;
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
      std::wstring::~wstring(S2);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v18)[2])(v18);
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
      std::wstring::~wstring(S2);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v26)[2])(v26);
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
      std::wstring::~wstring(S2);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v31)[2])(v31);
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
      std::wstring::~wstring(S2);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v36)[2])(v36);
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
      std::wstring::~wstring(S2);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v42)[2])(v42);
      }
      goto LABEL_151;
    }
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)pv + v43) );
    try
    {
      if ( v43 > v102 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          S2,
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
    catch ( std::bad_alloc )
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
      std::wstring::~wstring(S2);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v77)[2])(v77);
      }
LABEL_142:
      v8 = v91;
      goto LABEL_151;
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
        std::wstring::~wstring(S2);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v60)[2])(v60);
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
        std::wstring::~wstring(S2);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v65)[2])(v65);
        }
        goto LABEL_151;
      }
      try
      {
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
      catch ( std::bad_alloc )
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
        std::wstring::~wstring(S2);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v74)[2])(v74);
        }
        goto LABEL_142;
      }
    }
    std::wstring::~wstring(S2);
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
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v71)[2])(v71);
    }
  }
  v8 = 0;
  std::wstring::~wstring(S2);
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
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v80)[2])(v80);
  }
  if ( a2 != (__int64 *)&v96 )
  {
    v81 = *a2;
    *a2 = v96;
    *(_QWORD *)&v96 = v81;
    v82 = a2[1];
    a2[1] = *((_QWORD *)&v96 + 1);
    *((_QWORD *)&v96 + 1) = v82;
    v83 = a2[2];
    a2[2] = v97;
    v97 = v83;
  }
LABEL_151:
  if ( pv )
    CoTaskMemFree(pv);
  std::vector<std::wstring>::~vector<std::wstring>(&v96);
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
0x180016080  mov     [rsp+arg_0], rbx
0x180016085  mov     [rsp+arg_10], rsi
0x18001608a  push    rdi
0x18001608b  push    r12
0x18001608d  push    r13
0x18001608f  push    r14
0x180016091  push    r15
0x180016093  sub     rsp, 0F0h
0x18001609a  mov     rax, cs:__security_cookie
0x1800160a1  xor     rax, rsp
0x1800160a4  mov     [rsp+118h+var_38], rax
0x1800160ac  mov     r14, rdx
0x1800160af  mov     r12, rcx
0x1800160b2  xor     esi, esi
0x1800160b4  mov     [rsp+118h+var_B0], rsi
0x1800160b9  mov     [rsp+118h+var_C0], rsi
0x1800160be  mov     [rsp+118h+pv], rsi
0x1800160c3  xorps   xmm0, xmm0
0x1800160c6  movdqu  [rsp+118h+var_A8], xmm0
0x1800160cc  mov     [rsp+118h+var_98], rsi
0x1800160d4  mov     rdi, [rdx+8]
0x1800160d8  mov     rbx, [rdx]
0x1800160db  cmp     rbx, rdi
0x1800160de  jz      short loc_1800160F8
0x1800160e0  mov     rcx, rbx
0x1800160e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800160e8  add     rbx, 20h ; ' '
0x1800160ec  cmp     rbx, rdi
0x1800160ef  jnz     short loc_1800160E0
0x1800160f1  mov     rax, [r14]
0x1800160f4  mov     [r14+8], rax
0x1800160f8  lea     rax, [rsp+118h+var_B0]
0x1800160fd  mov     [rsp+118h+ppv], rax; ppv
0x180016102  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x180016109  xor     edx, edx; pUnkOuter
0x18001610b  lea     r8d, [rdx+17h]; dwClsContext
0x18001610f  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x180016116  call    cs:__imp_CoCreateInstance
0x18001611d  nop     dword ptr [rax+rax+00h]
0x180016122  mov     ebx, eax
0x180016124  test    eax, eax
0x180016126  jns     short loc_18001615D
0x180016128  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001612f  jz      loc_180016B21
0x180016135  lea     rax, aChrCocreateins_1; "CHR(CoCreateInstance( __uuidof(CoClassC"...
0x18001613c  mov     [rsp+118h+var_F0], rax
0x180016141  mov     dword ptr [rsp+118h+ppv], 17Fh
0x180016149  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180016150  mov     r8d, ebx
0x180016153  call    McTemplateU0dsqs_EventWriteTransfer
0x180016158  jmp     loc_180016B21
0x18001615d  mov     rbx, [rsp+118h+var_B0]
0x180016162  mov     rax, [rbx]
0x180016165  mov     rdi, [rax+18h]
0x180016169  mov     rcx, [rsp+118h+var_C0]
0x18001616e  test    rcx, rcx
0x180016171  jz      short loc_180016185
0x180016173  mov     [rsp+118h+var_C0], rsi
0x180016178  mov     rdx, [rcx]
0x18001617b  mov     rax, [rdx+10h]
0x18001617f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016184  nop
0x180016185  lea     r9, [rsp+118h+var_C0]
0x18001618a  xor     r8d, r8d
0x18001618d  xor     edx, edx
0x18001618f  mov     rcx, rbx
0x180016192  mov     rax, rdi
0x180016195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001619a  mov     ebx, eax
0x18001619c  test    eax, eax
0x18001619e  jns     short loc_1800161C3
0x1800161a0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800161a7  jz      loc_180016B21
0x1800161ad  lea     rax, aChrSpuserstore_0; "CHR(spUserStore->GetConnectedUserEnum( "...
0x1800161b4  mov     [rsp+118h+var_F0], rax
0x1800161b9  mov     dword ptr [rsp+118h+ppv], 184h
0x1800161c1  jmp     short loc_180016149
0x1800161c3  mov     r13d, 7
0x1800161c9  mov     [rsp+118h+var_D8], rsi
0x1800161ce  mov     [rsp+118h+var_E8], rsi
0x1800161d3  mov     [rsp+118h+var_E0], rsi
0x1800161d8  mov     [rsp+118h+var_B8], esi
0x1800161dc  xorps   xmm0, xmm0
0x1800161df  xor     eax, eax
0x1800161e1  movups  xmmword ptr [rsp+118h+propvar], xmm0
0x1800161e9  mov     [rsp+118h+var_80], rax
0x1800161f1  movups  xmmword ptr [rsp+118h+S2], xmm0
0x1800161f9  mov     [rsp+118h+var_68], rsi
0x180016201  mov     [rsp+118h+var_60], r13
0x180016209  mov     word ptr [rsp+118h+S2], si
0x180016211  mov     rcx, [rsp+118h+var_C0]
0x180016216  mov     rax, [rcx]
0x180016219  lea     r9, [rsp+118h+var_B8]
0x18001621e  lea     r8, [rsp+118h+var_D8]
0x180016223  mov     edx, 1
0x180016228  mov     rax, [rax+18h]
0x18001622c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016231  mov     ebx, eax
0x180016233  test    eax, eax
0x180016235  jns     loc_1800162CF
0x18001623b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016242  jz      short loc_180016268
0x180016244  lea     rax, aChrSpuserenumN; "CHR(spUserEnum->Next(1, spUnknown.GetAd"...
0x18001624b  mov     [rsp+118h+var_F0], rax
0x180016250  mov     dword ptr [rsp+118h+ppv], 18Fh
0x180016258  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001625f  mov     r8d, ebx
0x180016262  call    McTemplateU0dsqs_EventWriteTransfer
0x180016267  nop
0x180016268  lea     rcx, [rsp+118h+S2]
0x180016270  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016275  nop
0x180016276  mov     rcx, [rsp+118h+var_E0]
0x18001627b  test    rcx, rcx
0x18001627e  jz      short loc_180016292
0x180016280  mov     [rsp+118h+var_E0], rsi
0x180016285  mov     rax, [rcx]
0x180016288  mov     rax, [rax+10h]
0x18001628c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016291  nop
0x180016292  mov     rcx, [rsp+118h+var_E8]
0x180016297  test    rcx, rcx
0x18001629a  jz      short loc_1800162AE
0x18001629c  mov     [rsp+118h+var_E8], rsi
0x1800162a1  mov     rax, [rcx]
0x1800162a4  mov     rax, [rax+10h]
0x1800162a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162ad  nop
0x1800162ae  mov     rcx, [rsp+118h+var_D8]
0x1800162b3  test    rcx, rcx
0x1800162b6  jz      short loc_1800162CA
0x1800162b8  mov     [rsp+118h+var_D8], rsi
0x1800162bd  mov     rax, [rcx]
0x1800162c0  mov     rax, [rax+10h]
0x1800162c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162c9  nop
0x1800162ca  jmp     loc_180016B21
0x1800162cf  cmp     ebx, 1
0x1800162d2  jz      loc_180016A79
0x1800162d8  cmp     [rsp+118h+var_B8], esi
0x1800162dc  jz      loc_180016A79
0x1800162e2  mov     rbx, [rsp+118h+var_D8]
0x1800162e7  mov     rax, [rbx]
0x1800162ea  mov     rdi, [rax]
0x1800162ed  mov     rcx, [rsp+118h+var_E8]
0x1800162f2  test    rcx, rcx
0x1800162f5  jz      short loc_180016309
0x1800162f7  mov     [rsp+118h+var_E8], rsi
0x1800162fc  mov     rdx, [rcx]
0x1800162ff  mov     rax, [rdx+10h]
0x180016303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016308  nop
0x180016309  lea     r8, [rsp+118h+var_E8]
0x18001630e  lea     rdx, _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d
0x180016315  mov     rcx, rbx
0x180016318  mov     rax, rdi
0x18001631b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016320  mov     ebx, eax
0x180016322  test    eax, eax
0x180016324  jns     loc_1800163BE
0x18001632a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016331  jz      short loc_180016357
0x180016333  lea     rax, aChrSpunknownAs; "CHR(spUnknown.As(&spUser))"
0x18001633a  mov     [rsp+118h+var_F0], rax
0x18001633f  mov     dword ptr [rsp+118h+ppv], 196h
0x180016347  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001634e  mov     r8d, ebx
0x180016351  call    McTemplateU0dsqs_EventWriteTransfer
0x180016356  nop
0x180016357  lea     rcx, [rsp+118h+S2]
0x18001635f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016364  nop
0x180016365  mov     rcx, [rsp+118h+var_E0]
0x18001636a  test    rcx, rcx
0x18001636d  jz      short loc_180016381
0x18001636f  mov     [rsp+118h+var_E0], rsi
0x180016374  mov     rax, [rcx]
0x180016377  mov     rax, [rax+10h]
0x18001637b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016380  nop
0x180016381  mov     rcx, [rsp+118h+var_E8]
0x180016386  test    rcx, rcx
0x180016389  jz      short loc_18001639D
0x18001638b  mov     [rsp+118h+var_E8], rsi
0x180016390  mov     rax, [rcx]
0x180016393  mov     rax, [rax+10h]
0x180016397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001639c  nop
0x18001639d  mov     rcx, [rsp+118h+var_D8]
0x1800163a2  test    rcx, rcx
0x1800163a5  jz      short loc_1800163B9
0x1800163a7  mov     [rsp+118h+var_D8], rsi
0x1800163ac  mov     rax, [rcx]
0x1800163af  mov     rax, [rax+10h]
0x1800163b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163b8  nop
0x1800163b9  jmp     loc_180016B21
0x1800163be  mov     rcx, [rsp+118h+var_E8]
0x1800163c3  mov     rax, [rcx]
0x1800163c6  lea     rdx, [rsp+118h+var_E0]
0x1800163cb  mov     rax, [rax+18h]
0x1800163cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163d4  mov     ebx, eax
0x1800163d6  test    eax, eax
0x1800163d8  jns     loc_180016472
0x1800163de  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800163e5  jz      short loc_18001640B
0x1800163e7  lea     rax, aChrSpuserGetco; "CHR(spUser->GetConnectedUserInfo(spProp"...
0x1800163ee  mov     [rsp+118h+var_F0], rax
0x1800163f3  mov     dword ptr [rsp+118h+ppv], 197h
0x1800163fb  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180016402  mov     r8d, ebx
0x180016405  call    McTemplateU0dsqs_EventWriteTransfer
0x18001640a  nop
0x18001640b  lea     rcx, [rsp+118h+S2]
0x180016413  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016418  nop
0x180016419  mov     rcx, [rsp+118h+var_E0]
0x18001641e  test    rcx, rcx
0x180016421  jz      short loc_180016435
0x180016423  mov     [rsp+118h+var_E0], rsi
0x180016428  mov     rax, [rcx]
0x18001642b  mov     rax, [rax+10h]
0x18001642f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016434  nop
0x180016435  mov     rcx, [rsp+118h+var_E8]
0x18001643a  test    rcx, rcx
0x18001643d  jz      short loc_180016451
0x18001643f  mov     [rsp+118h+var_E8], rsi
0x180016444  mov     rax, [rcx]
0x180016447  mov     rax, [rax+10h]
0x18001644b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016450  nop
0x180016451  mov     rcx, [rsp+118h+var_D8]
0x180016456  test    rcx, rcx
0x180016459  jz      short loc_18001646D
0x18001645b  mov     [rsp+118h+var_D8], rsi
0x180016460  mov     rax, [rcx]
0x180016463  mov     rax, [rax+10h]
0x180016467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001646c  nop
0x18001646d  jmp     loc_180016B21
0x180016472  mov     rcx, [rsp+118h+var_E0]
0x180016477  mov     rax, [rcx]
0x18001647a  lea     r8, [rsp+118h+propvar]
0x180016482  lea     rdx, PKEY_Identity_UniqueID
0x180016489  mov     rax, [rax+28h]
0x18001648d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016492  mov     ebx, eax
0x180016494  test    eax, eax
0x180016496  jns     loc_180016530
0x18001649c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800164a3  jz      short loc_1800164C9
0x1800164a5  lea     rax, aChrSppropstore_1; "CHR(spPropStore->GetValue(PKEY_Identity"...
0x1800164ac  mov     [rsp+118h+var_F0], rax
0x1800164b1  mov     dword ptr [rsp+118h+ppv], 19Ah
0x1800164b9  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800164c0  mov     r8d, ebx
0x1800164c3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800164c8  nop
0x1800164c9  lea     rcx, [rsp+118h+S2]
0x1800164d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800164d6  nop
0x1800164d7  mov     rcx, [rsp+118h+var_E0]
0x1800164dc  test    rcx, rcx
0x1800164df  jz      short loc_1800164F3
0x1800164e1  mov     [rsp+118h+var_E0], rsi
0x1800164e6  mov     rax, [rcx]
0x1800164e9  mov     rax, [rax+10h]
0x1800164ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164f2  nop
0x1800164f3  mov     rcx, [rsp+118h+var_E8]
0x1800164f8  test    rcx, rcx
0x1800164fb  jz      short loc_18001650F
0x1800164fd  mov     [rsp+118h+var_E8], rsi
0x180016502  mov     rax, [rcx]
0x180016505  mov     rax, [rax+10h]
0x180016509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001650e  nop
0x18001650f  mov     rcx, [rsp+118h+var_D8]
0x180016514  test    rcx, rcx
0x180016517  jz      short loc_18001652B
0x180016519  mov     [rsp+118h+var_D8], rsi
0x18001651e  mov     rax, [rcx]
0x180016521  mov     rax, [rax+10h]
0x180016525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001652a  nop
0x18001652b  jmp     loc_180016B21
0x180016530  mov     rcx, [rsp+118h+pv]; pv
0x180016535  test    rcx, rcx
0x180016538  jz      short loc_180016546
0x18001653a  call    cs:__imp_CoTaskMemFree
0x180016541  nop     dword ptr [rax+rax+00h]
0x180016546  lea     rdx, [rsp+118h+pv]; ppszOut
0x18001654b  lea     rcx, [rsp+118h+propvar]; propvar
0x180016553  call    cs:__imp_PropVariantToStringAlloc
0x18001655a  nop     dword ptr [rax+rax+00h]
0x18001655f  mov     ebx, eax
0x180016561  test    eax, eax
0x180016563  jns     loc_1800165FD
  ... truncated ...
```
