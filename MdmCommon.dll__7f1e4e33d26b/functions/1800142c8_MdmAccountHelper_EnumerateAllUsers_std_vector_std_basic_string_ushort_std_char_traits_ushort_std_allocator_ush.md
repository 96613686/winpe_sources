# MdmAccountHelper::EnumerateAllUsers(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x1800142c8`
- end: `0x180014e26`
- name: `?EnumerateAllUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z`
- size: `2910`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800034b0`
- `0x180005cb0`

## callees

- `0x180001520`
- `0x18000269c`
- `0x1800028e4`
- `0x180002bb8`
- `0x180002de4`
- `0x180006548`
- `0x1800142c8`
- `0x1800166f8`
- `0x180016994`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001479e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001488c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014dbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001488c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014dbe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800147bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800147bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001433d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001433d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001465b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014dae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001465b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014dae`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001466b`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001466b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800148ac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800148ac`

## string_xrefs

- `0x18001435c`: `CHR(CoCreateInstance( __uuidof(CoClassIdentityStore), nullptr, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLSCTX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(**(spUserStore.GetAddressOf())), IID_PPV_ARGS_Helper(spUserStore.GetAddressOf())))`
- `0x180014370`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001448c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001455b`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800145f6`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014694`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014802`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014985`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014ba9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014c36`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014cb3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014c22`: `CBR(ConvertStringSidToSidW(propertyValue.calpwstr.pElems[i], &pSid))`
- `0x180014b95`: `CHR(IsAdminBySid(pSid, &fFoundMatch, &fIsAdmin))`
- `0x180014971`: `CHR(IsDeviceOwnerBySid(pSid, &fIsDeviceOwner))`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateAllUsers(__int64 *a1, __int64 *a2, __int64 *a3)
{
  int v5; // edx
  int v6; // ecx
  int IsAdminBySid; // ebx
  int v8; // edx
  int v9; // ecx
  int v10; // edx
  int v11; // ecx
  _QWORD *v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v15)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v16; // rcx
  int v17; // edx
  int v18; // ecx
  _QWORD *v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rcx
  int v21; // edx
  int v22; // ecx
  _QWORD *v23; // rcx
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rcx
  int v25; // edx
  int v26; // ecx
  __int64 v27; // r8
  _QWORD *v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rcx
  unsigned __int64 v30; // rdx
  void **v31; // rdi
  __int64 v32; // rbx
  int v33; // ecx
  void **v34; // rdi
  void **v35; // rdx
  void **v36; // r15
  void **v37; // rbx
  int v38; // edx
  int v39; // ecx
  _QWORD *v40; // rcx
  __int64 (__fastcall ***v41)(_QWORD, _QWORD, _QWORD); // rcx
  unsigned __int16 v42; // r15
  int v43; // edx
  __int64 v44; // rcx
  int v45; // edi
  int v46; // edx
  int v47; // edx
  int v48; // ecx
  __int64 v49; // rdx
  int v50; // ecx
  _QWORD *v51; // rcx
  __int64 (__fastcall ***v52)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v53; // rcx
  __int64 (__fastcall ***v54)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 *v55; // rbx
  __int64 v56; // rdx
  int v57; // ecx
  _QWORD *v58; // rcx
  __int64 (__fastcall ***v59)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v60; // rdx
  int v61; // ecx
  _QWORD *v62; // rcx
  __int64 (__fastcall ***v63)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v64; // rcx
  __int64 (__fastcall ***v65)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v66; // rcx
  __int64 (__fastcall ***v67)(_QWORD, _QWORD, _QWORD); // rcx
  signed int LastError; // eax
  int v69; // edx
  int v70; // ecx
  _QWORD *v71; // rcx
  __int64 (__fastcall ***v72)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v73; // rcx
  __int64 (__fastcall ***v74)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v75; // rcx
  __int64 (__fastcall ***v76)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v77; // rcx
  __int64 (__fastcall ***v78)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v79; // rcx
  LPVOID v80; // rcx
  _BYTE v82[32]; // [rsp+0h] [rbp-F8h] BYREF
  _QWORD *v83; // [rsp+30h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v84)(_QWORD, GUID *, _QWORD **); // [rsp+38h] [rbp-C0h] BYREF
  int v85; // [rsp+40h] [rbp-B8h] BYREF
  int v86; // [rsp+44h] [rbp-B4h] BYREF
  int v87; // [rsp+48h] [rbp-B0h]
  HLOCAL hMem; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v89; // [rsp+58h] [rbp-A0h] BYREF
  int v90; // [rsp+60h] [rbp-98h] BYREF
  int v91; // [rsp+64h] [rbp-94h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-90h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-88h] BYREF
  PROPVARIANT propvar[2]; // [rsp+78h] [rbp-80h] BYREF
  __int64 v95; // [rsp+88h] [rbp-70h]
  __int64 *v96; // [rsp+90h] [rbp-68h]
  void *v97[2]; // [rsp+98h] [rbp-60h] BYREF
  unsigned __int64 v98; // [rsp+A8h] [rbp-50h]
  unsigned __int64 v99; // [rsp+B0h] [rbp-48h]

  v96 = a2;
  ppv = 0;
  v89 = 0;
  pv = 0;
  hMem = 0;
  if ( !a1 && !a3 )
    goto LABEL_159;
  IsAdminBySid = CoCreateInstance(
                   &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
                   0,
                   0x17u,
                   &GUID_df586fa5_6f35_44f1_b209_b38e169772eb,
                   &ppv);
  if ( IsAdminBySid < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        IsAdminBySid,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
        49,
        "CHR(CoCreateInstance( __uuidof(CoClassIdentityStore), nullptr, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLS"
        "CTX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(**(spUserStore.GetAddressOf())), IID_PPV_ARGS_Helper(spUserSto"
        "re.GetAddressOf())))");
    goto LABEL_160;
  }
  IsAdminBySid = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 56LL))(
                   ppv,
                   0,
                   0,
                   0,
                   &v89);
  if ( IsAdminBySid < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        IsAdminBySid,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
        55,
        "CHR(spUserStore->EnumerateIdentities( IDENTITIES_ALL, nullptr, nullptr, &spUserEnum))");
    goto LABEL_160;
  }
LABEL_9:
  v84 = 0;
  v83 = 0;
  v90 = 0;
  *(_OWORD *)propvar = 0;
  v95 = 0;
  v91 = 0;
  v86 = 0;
  v85 = 0;
  *(_OWORD *)v97 = 0;
  v98 = 0;
  v99 = 7;
  LOWORD(v97[0]) = 0;
  IsAdminBySid = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **), int *))(*(_QWORD *)v89 + 24LL))(
                   v89,
                   1,
                   &v84,
                   &v90);
  if ( IsAdminBySid < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        IsAdminBySid,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
        70,
        "CHR(spUserEnum->Next(1, spUnknown.GetAddressOf(), &cFetch))");
    std::wstring::~wstring((char **)v97);
    v12 = v83;
    if ( v83 )
    {
      v83 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
    }
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
    if ( v84 )
    {
      v84 = 0;
      ((void (__fastcall *)(_QWORD))(*v13)[2])(v13);
    }
    goto LABEL_160;
  }
  if ( IsAdminBySid != 1 && v90 )
  {
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
    v15 = **v84;
    v16 = v83;
    if ( v83 )
    {
      v83 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v16 + 16LL))(v16, *v16);
    }
    IsAdminBySid = v15(v14, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v83);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v18,
          v17,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          77,
          "CHR(spUnknown.As(&spPropStore))");
      std::wstring::~wstring((char **)v97);
      v19 = v83;
      if ( v83 )
      {
        v83 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      }
      v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
      if ( v84 )
      {
        v84 = 0;
        ((void (__fastcall *)(_QWORD))(*v20)[2])(v20);
      }
      goto LABEL_160;
    }
    IsAdminBySid = (*(__int64 (__fastcall **)(_QWORD *, const PROPERTYKEY *, PROPVARIANT *))(*v83 + 40LL))(
                     v83,
                     &PKEY_Identity_UniqueID,
                     propvar);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v22,
          v21,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          80,
          "CHR(spPropStore->GetValue(PKEY_Identity_UniqueID, &propertyValue))");
      std::wstring::~wstring((char **)v97);
      v23 = v83;
      if ( v83 )
      {
        v83 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
      }
      v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
      if ( v84 )
      {
        v84 = 0;
        ((void (__fastcall *)(_QWORD))(*v24)[2])(v24);
      }
      goto LABEL_160;
    }
    if ( pv )
      CoTaskMemFree(pv);
    IsAdminBySid = PropVariantToStringAlloc(propvar, (PWSTR *)&pv);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v26,
          v25,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          87,
          "CHR(PropVariantToStringAlloc(propertyValue, &pwszCid))");
      std::wstring::~wstring((char **)v97);
      v28 = v83;
      if ( v83 )
      {
        v83 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
      }
      v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
      if ( v84 )
      {
        v84 = 0;
        ((void (__fastcall *)(_QWORD))(*v29)[2])(v29);
      }
      goto LABEL_160;
    }
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)pv + v30) );
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( v30 > v99 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)v97,
          v30,
          v27,
          pv);
      }
      else
      {
        v31 = v97;
        if ( v99 > 7 )
          v31 = (void **)v97[0];
        v98 = v30;
        v32 = 2 * v30;
        memmove_0(v31, pv, 2 * v30);
        *(_WORD *)((char *)v31 + v32) = 0;
      }
      v33 = (int)v97[0];
      if ( v99 <= 7 )
      {
        v34 = v97;
        v35 = v97;
      }
      else
      {
        v34 = (void **)v97[0];
        v35 = (void **)v97[0];
      }
      v36 = (void **)((char *)v35 + 2 * v98);
      v37 = v97;
      if ( v99 > 7 )
        v37 = (void **)v97[0];
      while ( v37 != v36 )
      {
        *(_WORD *)v34 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v37);
        v37 = (void **)((char *)v37 + 2);
        v34 = (void **)((char *)v34 + 2);
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v85 = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v33,
            (unsigned int)v82,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
            96,
            "CHR(((HRESULT)0x8007000EL))");
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180014D0E);
        std::wstring::~wstring((char **)v97);
        v75 = v83;
        if ( v83 )
        {
          v83 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v75 + 16LL))(v75);
        }
        v76 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
        if ( v84 )
        {
          v84 = 0;
          ((void (__fastcall *)(_QWORD))(*v76)[2])(v76);
        }
LABEL_154:
        IsAdminBySid = v85;
        goto LABEL_160;
      }
    }
    PropVariantClear(propvar);
    IsAdminBySid = (*(__int64 (__fastcall **)(_QWORD *, const PROPERTYKEY *, PROPVARIANT *))(*v83 + 40LL))(
                     v83,
                     &PKEY_Identity_ProviderData,
                     propvar);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v39,
          v38,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          101,
          "CHR(spPropStore->GetValue(PKEY_Identity_ProviderData, &propertyValue))");
      std::wstring::~wstring((char **)v97);
      v40 = v83;
      if ( v83 )
      {
        v83 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
      }
      v41 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
      if ( v84 )
      {
        v84 = 0;
        ((void (__fastcall *)(_QWORD))(*v41)[2])(v41);
      }
      goto LABEL_160;
    }
    if ( LOWORD(propvar[0]) != 4127 )
    {
      IsAdminBySid = -2147467259;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v39,
          v38,
          -2147467259,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          102,
          "CBR(propertyValue.vt == (VT_VECTOR | VT_LPWSTR))");
      std::wstring::~wstring((char **)v97);
      v73 = v83;
      if ( v83 )
      {
        v83 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v73 + 16LL))(v73);
      }
      v74 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
      if ( v84 )
      {
        v84 = 0;
        ((void (__fastcall *)(_QWORD))(*v74)[2])(v74);
      }
      goto LABEL_160;
    }
    v87 = 0;
    v42 = 0;
    if ( !LODWORD(propvar[1]) )
      goto LABEL_117;
    while ( 1 )
    {
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      if ( !ConvertStringSidToSidW(*(LPCWSTR *)(v95 + 8LL * v42), &hMem) )
      {
        LastError = GetLastError();
        IsAdminBySid = LastError;
        if ( LastError > 0 )
          IsAdminBySid = (unsigned __int16)LastError | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v70,
            v69,
            IsAdminBySid,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
            113,
            "CBR(ConvertStringSidToSidW(propertyValue.calpwstr.pElems[i], &pSid))");
        std::wstring::~wstring((char **)v97);
        v71 = v83;
        if ( v83 )
        {
          v83 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v71 + 16LL))(v71);
        }
        v72 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
        if ( v84 )
        {
          v84 = 0;
          ((void (__fastcall *)(_QWORD))(*v72)[2])(v72);
        }
        goto LABEL_160;
      }
      IsAdminBySid = MdmAccountHelper::IsAdminBySid(hMem, &v91, &v86);
      if ( IsAdminBySid < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v44,
            v43,
            IsAdminBySid,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
            114,
            "CHR(IsAdminBySid(pSid, &fFoundMatch, &fIsAdmin))");
        std::wstring::~wstring((char **)v97);
        v66 = v83;
        if ( v83 )
        {
          v83 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v66 + 16LL))(v66);
        }
        v67 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
        if ( v84 )
        {
          v84 = 0;
          ((void (__fastcall *)(_QWORD))(*v67)[2])(v67);
        }
        goto LABEL_160;
      }
      v45 = v86;
      if ( v91 )
      {
        if ( v86 )
          goto LABEL_84;
        v46 = 1;
        v87 = 1;
        v44 = (unsigned int)v85;
        if ( v85 )
          goto LABEL_81;
        IsAdminBySid = MdmAccountHelper::IsDeviceOwnerBySid(hMem, &v85);
        if ( IsAdminBySid < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v48,
              v47,
              IsAdminBySid,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
              132,
              "CHR(IsDeviceOwnerBySid(pSid, &fIsDeviceOwner))");
          std::wstring::~wstring((char **)v97);
          v51 = v83;
          if ( v83 )
          {
            v83 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
          }
          v52 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
          if ( v84 )
          {
            v84 = 0;
            ((void (__fastcall *)(_QWORD))(*v52)[2])(v52);
          }
          goto LABEL_160;
        }
      }
      v44 = (unsigned int)v85;
      v46 = v87;
LABEL_81:
      if ( (unsigned int)++v42 >= LODWORD(propvar[1]) )
      {
        if ( !v46 )
          goto LABEL_117;
        if ( v45 )
        {
LABEL_84:
          if ( !a1 )
            goto LABEL_117;
          if ( __eh34_try(-1, 2) )
          {
            __eh34_scope_strut(2);
            v49 = a1[1];
            if ( v49 == a1[2] )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v49, (__int64)v97);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                v44,
                v49,
                (__int64)v97);
              a1[1] += 32;
            }
          }
          if ( __eh34_catch(2) )
          {
            if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              v85 = -2147024882;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v50,
                  (unsigned int)v82,
                  -2147024882,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
                  149,
                  "CHR(((HRESULT)0x8007000EL))");
              __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_1800149ED);
              std::wstring::~wstring((char **)v97);
              v53 = v83;
              if ( v83 )
              {
                v83 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v53 + 16LL))(v53);
              }
              v54 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
              if ( v84 )
              {
                v84 = 0;
                ((void (__fastcall *)(_QWORD))(*v54)[2])(v54);
              }
              goto LABEL_154;
            }
          }
        }
        else if ( (_DWORD)v44 )
        {
          v55 = v96;
          if ( !v96 )
            goto LABEL_117;
          if ( __eh34_try(-1, 4) )
          {
            __eh34_scope_strut(4);
            v56 = v96[1];
            if ( v56 == v96[2] )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v96, v56, (__int64)v97);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                v44,
                v56,
                (__int64)v97);
              v55[1] += 32;
            }
          }
          if ( __eh34_catch(4) )
          {
            if ( __eh34_catch_type(4, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              v85 = -2147024882;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v57,
                  (unsigned int)v82,
                  -2147024882,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
                  163,
                  "CHR(((HRESULT)0x8007000EL))");
              __eh34_try_continuation(4, &std::bad_alloc `RTTI Type Descriptor', &loc_180014A7B);
              std::wstring::~wstring((char **)v97);
              v58 = v83;
              if ( v83 )
              {
                v83 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v58 + 16LL))(v58);
              }
              v59 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
              if ( v84 )
              {
                v84 = 0;
                ((void (__fastcall *)(_QWORD))(*v59)[2])(v59);
              }
              goto LABEL_154;
            }
          }
        }
        else
        {
          if ( !a3 )
            goto LABEL_117;
          if ( __eh34_try(-1, 6) )
          {
            __eh34_scope_strut(6);
            v60 = a3[1];
            if ( v60 == a3[2] )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a3, v60, (__int64)v97);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                v44,
                v60,
                (__int64)v97);
              a3[1] += 32;
            }
          }
          if ( __eh34_catch(6) )
          {
            if ( __eh34_catch_type(6, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              v85 = -2147024882;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v61,
                  (unsigned int)v82,
                  -2147024882,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
                  177,
                  "CHR(((HRESULT)0x8007000EL))");
              __eh34_try_continuation(6, &std::bad_alloc `RTTI Type Descriptor', &loc_180014B3F);
              std::wstring::~wstring((char **)v97);
              v64 = v83;
              if ( v83 )
              {
                v83 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
              }
              v65 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
              if ( v84 )
              {
                v84 = 0;
                ((void (__fastcall *)(_QWORD))(*v65)[2])(v65);
              }
              goto LABEL_154;
            }
          }
        }
LABEL_117:
        std::wstring::~wstring((char **)v97);
        v62 = v83;
        if ( v83 )
        {
          v83 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
        }
        v63 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
        if ( v84 )
        {
          v84 = 0;
          ((void (__fastcall *)(_QWORD))(*v63)[2])(v63);
        }
        goto LABEL_9;
      }
    }
  }
  std::wstring::~wstring((char **)v97);
  v77 = v83;
  if ( v83 )
  {
    v83 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v77 + 16LL))(v77);
  }
  v78 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
  if ( v84 )
  {
    v84 = 0;
    ((void (__fastcall *)(_QWORD))(*v78)[2])(v78);
  }
LABEL_159:
  IsAdminBySid = 0;
LABEL_160:
  if ( pv )
    CoTaskMemFree(pv);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  v79 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  }
  v80 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
  }
  return (unsigned int)IsAdminBySid;
}

```

## disassembly

```asm
0x1800142c8  push    rbx
0x1800142ca  push    rsi
0x1800142cb  push    rdi
0x1800142cc  push    r12
0x1800142ce  push    r13
0x1800142d0  push    r14
0x1800142d2  push    r15
0x1800142d4  sub     rsp, 0C0h
0x1800142db  mov     rax, cs:__security_cookie
0x1800142e2  xor     rax, rsp
0x1800142e5  mov     [rsp+0F8h+var_40], rax
0x1800142ed  mov     r13, r8
0x1800142f0  mov     [rsp+0F8h+var_68], rdx
0x1800142f8  mov     r12, rcx
0x1800142fb  xor     esi, esi
0x1800142fd  mov     [rsp+0F8h+var_88], rsi
0x180014302  mov     [rsp+0F8h+var_A0], rsi
0x180014307  mov     [rsp+0F8h+pv], rsi
0x18001430c  mov     [rsp+0F8h+hMem], rsi
0x180014311  test    rcx, rcx
0x180014314  jnz     short loc_18001431F
0x180014316  test    r8, r8
0x180014319  jz      loc_180014DA2
0x18001431f  lea     rax, [rsp+0F8h+var_88]
0x180014324  mov     [rsp+0F8h+ppv], rax; ppv
0x180014329  lea     r9, _GUID_df586fa5_6f35_44f1_b209_b38e169772eb; riid
0x180014330  xor     edx, edx; pUnkOuter
0x180014332  lea     r8d, [rdx+17h]; dwClsContext
0x180014336  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x18001433d  call    cs:__imp_CoCreateInstance
0x180014343  mov     ebx, eax
0x180014345  test    eax, eax
0x180014347  jns     short loc_180014384
0x180014349  mov     r14d, 1
0x18001434f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x180014356  jz      loc_180014DA4
0x18001435c  lea     rax, aChrCocreateins_0; "CHR(CoCreateInstance( __uuidof(CoClassI"...
0x180014363  mov     [rsp+0F8h+var_D0], rax
0x180014368  mov     dword ptr [rsp+0F8h+ppv], 31h ; '1'
0x180014370  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014377  mov     r8d, ebx
0x18001437a  call    McTemplateU0dsqs_EventWriteTransfer
0x18001437f  jmp     loc_180014DA4
0x180014384  mov     rbx, [rsp+0F8h+var_88]
0x180014389  mov     rax, [rbx]
0x18001438c  mov     rdi, [rax+38h]
0x180014390  mov     rcx, [rsp+0F8h+var_A0]
0x180014395  test    rcx, rcx
0x180014398  jz      short loc_1800143AC
0x18001439a  mov     [rsp+0F8h+var_A0], rsi
0x18001439f  mov     rax, [rcx]
0x1800143a2  mov     rax, [rax+10h]
0x1800143a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143ab  nop
0x1800143ac  lea     rax, [rsp+0F8h+var_A0]
0x1800143b1  mov     [rsp+0F8h+ppv], rax
0x1800143b6  xor     r9d, r9d
0x1800143b9  xor     r8d, r8d
0x1800143bc  xor     edx, edx
0x1800143be  mov     rcx, rbx
0x1800143c1  mov     rax, rdi
0x1800143c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143c9  mov     ebx, eax
0x1800143cb  mov     r14d, 1
0x1800143d1  test    eax, eax
0x1800143d3  jns     short loc_1800143FB
0x1800143d5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x1800143dc  jz      loc_180014DA4
0x1800143e2  lea     rax, aChrSpuserstore; "CHR(spUserStore->EnumerateIdentities( I"...
0x1800143e9  mov     [rsp+0F8h+var_D0], rax
0x1800143ee  mov     dword ptr [rsp+0F8h+ppv], 37h ; '7'
0x1800143f6  jmp     loc_180014370
0x1800143fb  mov     [rsp+0F8h+var_C0], rsi
0x180014400  mov     [rsp+0F8h+var_C8], rsi
0x180014405  mov     [rsp+0F8h+var_98], esi
0x180014409  xorps   xmm0, xmm0
0x18001440c  xor     eax, eax
0x18001440e  movups  xmmword ptr [rsp+0F8h+propvar], xmm0
0x180014413  mov     [rsp+0F8h+var_70], rax
0x18001441b  mov     [rsp+0F8h+var_94], esi
0x18001441f  mov     [rsp+0F8h+var_B4], esi
0x180014423  mov     [rsp+0F8h+var_B8], esi
0x180014427  movups  xmmword ptr [rsp+0F8h+var_60], xmm0
0x18001442f  mov     [rsp+0F8h+var_50], rsi
0x180014437  mov     [rsp+0F8h+var_48], 7
0x180014443  mov     word ptr [rsp+0F8h+var_60], si
0x18001444b  mov     rcx, [rsp+0F8h+var_A0]
0x180014450  mov     rax, [rcx]
0x180014453  lea     r9, [rsp+0F8h+var_98]
0x180014458  lea     r8, [rsp+0F8h+var_C0]
0x18001445d  mov     edx, r14d
0x180014460  mov     rax, [rax+18h]
0x180014464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014469  mov     ebx, eax
0x18001446b  test    eax, eax
0x18001446d  jns     short loc_1800144E7
0x18001446f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x180014476  jz      short loc_18001449C
0x180014478  lea     rax, aChrSpuserenumN; "CHR(spUserEnum->Next(1, spUnknown.GetAd"...
0x18001447f  mov     [rsp+0F8h+var_D0], rax
0x180014484  mov     dword ptr [rsp+0F8h+ppv], 46h ; 'F'
0x18001448c  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014493  mov     r8d, ebx
0x180014496  call    McTemplateU0dsqs_EventWriteTransfer
0x18001449b  nop
0x18001449c  lea     rcx, [rsp+0F8h+var_60]
0x1800144a4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800144a9  nop
0x1800144aa  mov     rcx, [rsp+0F8h+var_C8]
0x1800144af  test    rcx, rcx
0x1800144b2  jz      short loc_1800144C6
0x1800144b4  mov     [rsp+0F8h+var_C8], rsi
0x1800144b9  mov     rax, [rcx]
0x1800144bc  mov     rax, [rax+10h]
0x1800144c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144c5  nop
0x1800144c6  mov     rcx, [rsp+0F8h+var_C0]
0x1800144cb  test    rcx, rcx
0x1800144ce  jz      short loc_1800144E2
0x1800144d0  mov     [rsp+0F8h+var_C0], rsi
0x1800144d5  mov     rax, [rcx]
0x1800144d8  mov     rax, [rax+10h]
0x1800144dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144e1  nop
0x1800144e2  jmp     loc_180014DA4
0x1800144e7  cmp     ebx, r14d
0x1800144ea  jz      loc_180014D5C
0x1800144f0  cmp     [rsp+0F8h+var_98], esi
0x1800144f4  jz      loc_180014D5C
0x1800144fa  mov     rbx, [rsp+0F8h+var_C0]
0x1800144ff  mov     rax, [rbx]
0x180014502  mov     rdi, [rax]
0x180014505  mov     rcx, [rsp+0F8h+var_C8]
0x18001450a  test    rcx, rcx
0x18001450d  jz      short loc_180014521
0x18001450f  mov     [rsp+0F8h+var_C8], rsi
0x180014514  mov     rdx, [rcx]
0x180014517  mov     rax, [rdx+10h]
0x18001451b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014520  nop
0x180014521  lea     r8, [rsp+0F8h+var_C8]
0x180014526  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18001452d  mov     rcx, rbx
0x180014530  mov     rax, rdi
0x180014533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014538  mov     ebx, eax
0x18001453a  test    eax, eax
0x18001453c  jns     short loc_1800145B6
0x18001453e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x180014545  jz      short loc_18001456B
0x180014547  lea     rax, aChrSpunknownAs_0; "CHR(spUnknown.As(&spPropStore))"
0x18001454e  mov     [rsp+0F8h+var_D0], rax
0x180014553  mov     dword ptr [rsp+0F8h+ppv], 4Dh ; 'M'
0x18001455b  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014562  mov     r8d, ebx
0x180014565  call    McTemplateU0dsqs_EventWriteTransfer
0x18001456a  nop
0x18001456b  lea     rcx, [rsp+0F8h+var_60]
0x180014573  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014578  nop
0x180014579  mov     rcx, [rsp+0F8h+var_C8]
0x18001457e  test    rcx, rcx
0x180014581  jz      short loc_180014595
0x180014583  mov     [rsp+0F8h+var_C8], rsi
0x180014588  mov     rax, [rcx]
0x18001458b  mov     rax, [rax+10h]
0x18001458f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014594  nop
0x180014595  mov     rcx, [rsp+0F8h+var_C0]
0x18001459a  test    rcx, rcx
0x18001459d  jz      short loc_1800145B1
0x18001459f  mov     [rsp+0F8h+var_C0], rsi
0x1800145a4  mov     rax, [rcx]
0x1800145a7  mov     rax, [rax+10h]
0x1800145ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145b0  nop
0x1800145b1  jmp     loc_180014DA4
0x1800145b6  mov     rcx, [rsp+0F8h+var_C8]
0x1800145bb  mov     rax, [rcx]
0x1800145be  lea     r8, [rsp+0F8h+propvar]
0x1800145c3  lea     rdx, PKEY_Identity_UniqueID
0x1800145ca  mov     rax, [rax+28h]
0x1800145ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145d3  mov     ebx, eax
0x1800145d5  test    eax, eax
0x1800145d7  jns     short loc_180014651
0x1800145d9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x1800145e0  jz      short loc_180014606
0x1800145e2  lea     rax, aChrSppropstore_1; "CHR(spPropStore->GetValue(PKEY_Identity"...
0x1800145e9  mov     [rsp+0F8h+var_D0], rax
0x1800145ee  mov     dword ptr [rsp+0F8h+ppv], 50h ; 'P'
0x1800145f6  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800145fd  mov     r8d, ebx
0x180014600  call    McTemplateU0dsqs_EventWriteTransfer
0x180014605  nop
0x180014606  lea     rcx, [rsp+0F8h+var_60]
0x18001460e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014613  nop
0x180014614  mov     rcx, [rsp+0F8h+var_C8]
0x180014619  test    rcx, rcx
0x18001461c  jz      short loc_180014630
0x18001461e  mov     [rsp+0F8h+var_C8], rsi
0x180014623  mov     rax, [rcx]
0x180014626  mov     rax, [rax+10h]
0x18001462a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001462f  nop
0x180014630  mov     rcx, [rsp+0F8h+var_C0]
0x180014635  test    rcx, rcx
0x180014638  jz      short loc_18001464C
0x18001463a  mov     [rsp+0F8h+var_C0], rsi
0x18001463f  mov     rax, [rcx]
0x180014642  mov     rax, [rax+10h]
0x180014646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001464b  nop
0x18001464c  jmp     loc_180014DA4
0x180014651  mov     rcx, [rsp+0F8h+pv]; pv
0x180014656  test    rcx, rcx
0x180014659  jz      short loc_180014661
0x18001465b  call    cs:__imp_CoTaskMemFree
0x180014661  lea     rdx, [rsp+0F8h+pv]; ppszOut
0x180014666  lea     rcx, [rsp+0F8h+propvar]; propvar
0x18001466b  call    cs:__imp_PropVariantToStringAlloc
0x180014671  mov     ebx, eax
0x180014673  test    eax, eax
0x180014675  jns     short loc_1800146EF
0x180014677  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18001467e  jz      short loc_1800146A4
0x180014680  lea     rax, aChrPropvariant_0; "CHR(PropVariantToStringAlloc(propertyVa"...
0x180014687  mov     [rsp+0F8h+var_D0], rax
0x18001468c  mov     dword ptr [rsp+0F8h+ppv], 57h ; 'W'
0x180014694  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001469b  mov     r8d, ebx
0x18001469e  call    McTemplateU0dsqs_EventWriteTransfer
0x1800146a3  nop
0x1800146a4  lea     rcx, [rsp+0F8h+var_60]
0x1800146ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800146b1  nop
0x1800146b2  mov     rcx, [rsp+0F8h+var_C8]
0x1800146b7  test    rcx, rcx
0x1800146ba  jz      short loc_1800146CE
0x1800146bc  mov     [rsp+0F8h+var_C8], rsi
0x1800146c1  mov     rax, [rcx]
0x1800146c4  mov     rax, [rax+10h]
0x1800146c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146cd  nop
0x1800146ce  mov     rcx, [rsp+0F8h+var_C0]
0x1800146d3  test    rcx, rcx
0x1800146d6  jz      short loc_1800146EA
0x1800146d8  mov     [rsp+0F8h+var_C0], rsi
0x1800146dd  mov     rax, [rcx]
0x1800146e0  mov     rax, [rax+10h]
0x1800146e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146e9  nop
0x1800146ea  jmp     loc_180014DA4
0x1800146ef  mov     r9, [rsp+0F8h+pv]
0x1800146f4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800146f8  inc     rdx
0x1800146fb  cmp     [r9+rdx*2], si
0x180014700  jnz     short loc_1800146F8
0x180014702  cmp     rdx, [rsp+0F8h+var_48]
0x18001470a  ja      short loc_180014746
0x18001470c  lea     rdi, [rsp+0F8h+var_60]
0x180014714  cmp     [rsp+0F8h+var_48], 7
0x18001471d  cmova   rdi, [rsp+0F8h+var_60]
0x180014726  mov     [rsp+0F8h+var_50], rdx
0x18001472e  lea     rbx, [rdx+rdx]
0x180014732  mov     r8, rbx; Size
0x180014735  mov     rdx, r9; Src
0x180014738  mov     rcx, rdi; void *
0x18001473b  call    memmove_0
0x180014740  mov     [rbx+rdi], si
0x180014744  jmp     short loc_180014753
0x180014746  lea     rcx, [rsp+0F8h+var_60]
0x18001474e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180014753  mov     rcx, [rsp+0F8h+var_60]
0x18001475b  cmp     [rsp+0F8h+var_48], 7
0x180014764  jbe     short loc_18001476E
0x180014766  mov     rdi, rcx
0x180014769  mov     rdx, rcx
0x18001476c  jmp     short loc_18001477E
0x18001476e  lea     rdi, [rsp+0F8h+var_60]
0x180014776  lea     rdx, [rsp+0F8h+var_60]
0x18001477e  mov     rax, [rsp+0F8h+var_50]
0x180014786  lea     r15, [rdx+rax*2]
0x18001478a  lea     rbx, [rsp+0F8h+var_60]
0x180014792  cmova   rbx, rcx
0x180014796  cmp     rbx, r15
0x180014799  jz      short loc_1800147B7
0x18001479b  movzx   ecx, word ptr [rbx]
0x18001479e  mov     rax, cs:__imp_towupper
0x1800147a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147aa  mov     [rdi], ax
0x1800147ad  add     rbx, 2
0x1800147b1  add     rdi, 2
0x1800147b5  jmp     short loc_180014796
0x1800147b7  lea     rcx, [rsp+0F8h+propvar]; pvar
0x1800147bc  call    cs:__imp_PropVariantClear
0x1800147c2  mov     rcx, [rsp+0F8h+var_C8]
0x1800147c7  mov     rax, [rcx]
0x1800147ca  lea     r8, [rsp+0F8h+propvar]
  ... truncated ...
```
