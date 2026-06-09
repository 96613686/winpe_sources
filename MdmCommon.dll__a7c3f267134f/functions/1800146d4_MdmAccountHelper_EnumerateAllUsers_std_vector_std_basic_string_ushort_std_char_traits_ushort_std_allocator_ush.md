# MdmAccountHelper::EnumerateAllUsers(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x1800146d4`
- end: `0x180015269`
- name: `?EnumerateAllUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z`
- size: `2965`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800034c0`
- `0x180005d00`

## callees

- `0x180001520`
- `0x18000269c`
- `0x1800028e4`
- `0x180002bb8`
- `0x180002de8`
- `0x1800065c0`
- `0x1800146d4`
- `0x180016bb4`
- `0x180016e78`
- `0x18001dbfc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180014bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015034`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800151fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800151fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014bda`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014bda`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014749`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151e4`
- `PROPSYS!PropVariantToStringAlloc` at `0x180014a83`
- `PROPSYS!PropVariantToStringAlloc` at `0x180014a83`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180014cd6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180014cd6`

## string_xrefs

- `0x18001476e`: `CHR(CoCreateInstance( __uuidof(CoClassIdentityStore), nullptr, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLSCTX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(**(spUserStore.GetAddressOf())), IID_PPV_ARGS_Helper(spUserStore.GetAddressOf())))`
- `0x180014782`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001489e`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001496d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014a08`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014ab2`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014c26`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014db5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014fd9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001506c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800150e9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015058`: `CBR(ConvertStringSidToSidW(propertyValue.calpwstr.pElems[i], &pSid))`
- `0x180014fc5`: `CHR(IsAdminBySid(pSid, &fFoundMatch, &fIsAdmin))`
- `0x180014da1`: `CHR(IsDeviceOwnerBySid(pSid, &fIsDeviceOwner))`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall MdmAccountHelper::EnumerateAllUsers(__int64 a1, __int64 a2, __int64 a3)
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
  __int64 v55; // rbx
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
  __int64 v96; // [rsp+90h] [rbp-68h]
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
    std::wstring::~wstring(v97);
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
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
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
      std::wstring::~wstring(v97);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v20)[2])(v20);
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
      std::wstring::~wstring(v97);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v24)[2])(v24);
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
      std::wstring::~wstring(v97);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v29)[2])(v29);
      }
      goto LABEL_160;
    }
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)pv + v30) );
    try
    {
      if ( v30 > v99 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v97,
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
    catch ( std::bad_alloc )
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
      std::wstring::~wstring(v97);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v76)[2])(v76);
      }
LABEL_154:
      IsAdminBySid = v85;
      goto LABEL_160;
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
      std::wstring::~wstring(v97);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v41)[2])(v41);
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
      std::wstring::~wstring(v97);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v74)[2])(v74);
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
        std::wstring::~wstring(v97);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v72)[2])(v72);
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
        std::wstring::~wstring(v97);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v67)[2])(v67);
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
          std::wstring::~wstring(v97);
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
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v52)[2])(v52);
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
          try
          {
            v49 = *(_QWORD *)(a1 + 8);
            if ( v49 == *(_QWORD *)(a1 + 16) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v49, v97);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                v44,
                v49,
                v97);
              *(_QWORD *)(a1 + 8) += 32LL;
            }
          }
          catch ( std::bad_alloc )
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
            std::wstring::~wstring(v97);
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
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v54)[2])(v54);
            }
            goto LABEL_154;
          }
        }
        else if ( (_DWORD)v44 )
        {
          v55 = v96;
          if ( !v96 )
            goto LABEL_117;
          try
          {
            v56 = *(_QWORD *)(v96 + 8);
            if ( v56 == *(_QWORD *)(v96 + 16) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v96, v56, v97);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                v44,
                v56,
                v97);
              *(_QWORD *)(v55 + 8) += 32LL;
            }
          }
          catch ( std::bad_alloc )
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
            std::wstring::~wstring(v97);
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
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v59)[2])(v59);
            }
            goto LABEL_154;
          }
        }
        else
        {
          if ( !a3 )
            goto LABEL_117;
          try
          {
            v60 = *(_QWORD *)(a3 + 8);
            if ( v60 == *(_QWORD *)(a3 + 16) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a3, v60, v97);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                v44,
                v60,
                v97);
              *(_QWORD *)(a3 + 8) += 32LL;
            }
          }
          catch ( std::bad_alloc )
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
            std::wstring::~wstring(v97);
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
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v65)[2])(v65);
            }
            goto LABEL_154;
          }
        }
LABEL_117:
        std::wstring::~wstring(v97);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v63)[2])(v63);
        }
        goto LABEL_9;
      }
    }
  }
  std::wstring::~wstring(v97);
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
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v78)[2])(v78);
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
0x1800146d4  push    rbx
0x1800146d6  push    rsi
0x1800146d7  push    rdi
0x1800146d8  push    r12
0x1800146da  push    r13
0x1800146dc  push    r14
0x1800146de  push    r15
0x1800146e0  sub     rsp, 0C0h
0x1800146e7  mov     rax, cs:__security_cookie
0x1800146ee  xor     rax, rsp
0x1800146f1  mov     [rsp+0F8h+var_40], rax
0x1800146f9  mov     r13, r8
0x1800146fc  mov     [rsp+0F8h+var_68], rdx
0x180014704  mov     r12, rcx
0x180014707  xor     esi, esi
0x180014709  mov     [rsp+0F8h+var_88], rsi
0x18001470e  mov     [rsp+0F8h+var_A0], rsi
0x180014713  mov     [rsp+0F8h+pv], rsi
0x180014718  mov     [rsp+0F8h+hMem], rsi
0x18001471d  test    rcx, rcx
0x180014720  jnz     short loc_18001472B
0x180014722  test    r8, r8
0x180014725  jz      loc_1800151D8
0x18001472b  lea     rax, [rsp+0F8h+var_88]
0x180014730  mov     [rsp+0F8h+ppv], rax; ppv
0x180014735  lea     r9, _GUID_df586fa5_6f35_44f1_b209_b38e169772eb; riid
0x18001473c  xor     edx, edx; pUnkOuter
0x18001473e  lea     r8d, [rdx+17h]; dwClsContext
0x180014742  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x180014749  call    cs:__imp_CoCreateInstance
0x180014750  nop     dword ptr [rax+rax+00h]
0x180014755  mov     ebx, eax
0x180014757  test    eax, eax
0x180014759  jns     short loc_180014796
0x18001475b  mov     r14d, 1
0x180014761  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x180014768  jz      loc_1800151DA
0x18001476e  lea     rax, aChrCocreateins_0; "CHR(CoCreateInstance( __uuidof(CoClassI"...
0x180014775  mov     [rsp+0F8h+var_D0], rax
0x18001477a  mov     dword ptr [rsp+0F8h+ppv], 31h ; '1'
0x180014782  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014789  mov     r8d, ebx
0x18001478c  call    McTemplateU0dsqs_EventWriteTransfer
0x180014791  jmp     loc_1800151DA
0x180014796  mov     rbx, [rsp+0F8h+var_88]
0x18001479b  mov     rax, [rbx]
0x18001479e  mov     rdi, [rax+38h]
0x1800147a2  mov     rcx, [rsp+0F8h+var_A0]
0x1800147a7  test    rcx, rcx
0x1800147aa  jz      short loc_1800147BE
0x1800147ac  mov     [rsp+0F8h+var_A0], rsi
0x1800147b1  mov     rax, [rcx]
0x1800147b4  mov     rax, [rax+10h]
0x1800147b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147bd  nop
0x1800147be  lea     rax, [rsp+0F8h+var_A0]
0x1800147c3  mov     [rsp+0F8h+ppv], rax
0x1800147c8  xor     r9d, r9d
0x1800147cb  xor     r8d, r8d
0x1800147ce  xor     edx, edx
0x1800147d0  mov     rcx, rbx
0x1800147d3  mov     rax, rdi
0x1800147d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147db  mov     ebx, eax
0x1800147dd  mov     r14d, 1
0x1800147e3  test    eax, eax
0x1800147e5  jns     short loc_18001480D
0x1800147e7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x1800147ee  jz      loc_1800151DA
0x1800147f4  lea     rax, aChrSpuserstore; "CHR(spUserStore->EnumerateIdentities( I"...
0x1800147fb  mov     [rsp+0F8h+var_D0], rax
0x180014800  mov     dword ptr [rsp+0F8h+ppv], 37h ; '7'
0x180014808  jmp     loc_180014782
0x18001480d  mov     [rsp+0F8h+var_C0], rsi
0x180014812  mov     [rsp+0F8h+var_C8], rsi
0x180014817  mov     [rsp+0F8h+var_98], esi
0x18001481b  xorps   xmm0, xmm0
0x18001481e  xor     eax, eax
0x180014820  movups  xmmword ptr [rsp+0F8h+propvar], xmm0
0x180014825  mov     [rsp+0F8h+var_70], rax
0x18001482d  mov     [rsp+0F8h+var_94], esi
0x180014831  mov     [rsp+0F8h+var_B4], esi
0x180014835  mov     [rsp+0F8h+var_B8], esi
0x180014839  movups  xmmword ptr [rsp+0F8h+var_60], xmm0
0x180014841  mov     [rsp+0F8h+var_50], rsi
0x180014849  mov     [rsp+0F8h+var_48], 7
0x180014855  mov     word ptr [rsp+0F8h+var_60], si
0x18001485d  mov     rcx, [rsp+0F8h+var_A0]
0x180014862  mov     rax, [rcx]
0x180014865  lea     r9, [rsp+0F8h+var_98]
0x18001486a  lea     r8, [rsp+0F8h+var_C0]
0x18001486f  mov     edx, r14d
0x180014872  mov     rax, [rax+18h]
0x180014876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001487b  mov     ebx, eax
0x18001487d  test    eax, eax
0x18001487f  jns     short loc_1800148F9
0x180014881  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x180014888  jz      short loc_1800148AE
0x18001488a  lea     rax, aChrSpuserenumN; "CHR(spUserEnum->Next(1, spUnknown.GetAd"...
0x180014891  mov     [rsp+0F8h+var_D0], rax
0x180014896  mov     dword ptr [rsp+0F8h+ppv], 46h ; 'F'
0x18001489e  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800148a5  mov     r8d, ebx
0x1800148a8  call    McTemplateU0dsqs_EventWriteTransfer
0x1800148ad  nop
0x1800148ae  lea     rcx, [rsp+0F8h+var_60]
0x1800148b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800148bb  nop
0x1800148bc  mov     rcx, [rsp+0F8h+var_C8]
0x1800148c1  test    rcx, rcx
0x1800148c4  jz      short loc_1800148D8
0x1800148c6  mov     [rsp+0F8h+var_C8], rsi
0x1800148cb  mov     rax, [rcx]
0x1800148ce  mov     rax, [rax+10h]
0x1800148d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148d7  nop
0x1800148d8  mov     rcx, [rsp+0F8h+var_C0]
0x1800148dd  test    rcx, rcx
0x1800148e0  jz      short loc_1800148F4
0x1800148e2  mov     [rsp+0F8h+var_C0], rsi
0x1800148e7  mov     rax, [rcx]
0x1800148ea  mov     rax, [rax+10h]
0x1800148ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148f3  nop
0x1800148f4  jmp     loc_1800151DA
0x1800148f9  cmp     ebx, r14d
0x1800148fc  jz      loc_180015192
0x180014902  cmp     [rsp+0F8h+var_98], esi
0x180014906  jz      loc_180015192
0x18001490c  mov     rbx, [rsp+0F8h+var_C0]
0x180014911  mov     rax, [rbx]
0x180014914  mov     rdi, [rax]
0x180014917  mov     rcx, [rsp+0F8h+var_C8]
0x18001491c  test    rcx, rcx
0x18001491f  jz      short loc_180014933
0x180014921  mov     [rsp+0F8h+var_C8], rsi
0x180014926  mov     rdx, [rcx]
0x180014929  mov     rax, [rdx+10h]
0x18001492d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014932  nop
0x180014933  lea     r8, [rsp+0F8h+var_C8]
0x180014938  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18001493f  mov     rcx, rbx
0x180014942  mov     rax, rdi
0x180014945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001494a  mov     ebx, eax
0x18001494c  test    eax, eax
0x18001494e  jns     short loc_1800149C8
0x180014950  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x180014957  jz      short loc_18001497D
0x180014959  lea     rax, aChrSpunknownAs_0; "CHR(spUnknown.As(&spPropStore))"
0x180014960  mov     [rsp+0F8h+var_D0], rax
0x180014965  mov     dword ptr [rsp+0F8h+ppv], 4Dh ; 'M'
0x18001496d  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014974  mov     r8d, ebx
0x180014977  call    McTemplateU0dsqs_EventWriteTransfer
0x18001497c  nop
0x18001497d  lea     rcx, [rsp+0F8h+var_60]
0x180014985  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001498a  nop
0x18001498b  mov     rcx, [rsp+0F8h+var_C8]
0x180014990  test    rcx, rcx
0x180014993  jz      short loc_1800149A7
0x180014995  mov     [rsp+0F8h+var_C8], rsi
0x18001499a  mov     rax, [rcx]
0x18001499d  mov     rax, [rax+10h]
0x1800149a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149a6  nop
0x1800149a7  mov     rcx, [rsp+0F8h+var_C0]
0x1800149ac  test    rcx, rcx
0x1800149af  jz      short loc_1800149C3
0x1800149b1  mov     [rsp+0F8h+var_C0], rsi
0x1800149b6  mov     rax, [rcx]
0x1800149b9  mov     rax, [rax+10h]
0x1800149bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149c2  nop
0x1800149c3  jmp     loc_1800151DA
0x1800149c8  mov     rcx, [rsp+0F8h+var_C8]
0x1800149cd  mov     rax, [rcx]
0x1800149d0  lea     r8, [rsp+0F8h+propvar]
0x1800149d5  lea     rdx, PKEY_Identity_UniqueID
0x1800149dc  mov     rax, [rax+28h]
0x1800149e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e5  mov     ebx, eax
0x1800149e7  test    eax, eax
0x1800149e9  jns     short loc_180014A63
0x1800149eb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x1800149f2  jz      short loc_180014A18
0x1800149f4  lea     rax, aChrSppropstore_1; "CHR(spPropStore->GetValue(PKEY_Identity"...
0x1800149fb  mov     [rsp+0F8h+var_D0], rax
0x180014a00  mov     dword ptr [rsp+0F8h+ppv], 50h ; 'P'
0x180014a08  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014a0f  mov     r8d, ebx
0x180014a12  call    McTemplateU0dsqs_EventWriteTransfer
0x180014a17  nop
0x180014a18  lea     rcx, [rsp+0F8h+var_60]
0x180014a20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014a25  nop
0x180014a26  mov     rcx, [rsp+0F8h+var_C8]
0x180014a2b  test    rcx, rcx
0x180014a2e  jz      short loc_180014A42
0x180014a30  mov     [rsp+0F8h+var_C8], rsi
0x180014a35  mov     rax, [rcx]
0x180014a38  mov     rax, [rax+10h]
0x180014a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a41  nop
0x180014a42  mov     rcx, [rsp+0F8h+var_C0]
0x180014a47  test    rcx, rcx
0x180014a4a  jz      short loc_180014A5E
0x180014a4c  mov     [rsp+0F8h+var_C0], rsi
0x180014a51  mov     rax, [rcx]
0x180014a54  mov     rax, [rax+10h]
0x180014a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a5d  nop
0x180014a5e  jmp     loc_1800151DA
0x180014a63  mov     rcx, [rsp+0F8h+pv]; pv
0x180014a68  test    rcx, rcx
0x180014a6b  jz      short loc_180014A79
0x180014a6d  call    cs:__imp_CoTaskMemFree
0x180014a74  nop     dword ptr [rax+rax+00h]
0x180014a79  lea     rdx, [rsp+0F8h+pv]; ppszOut
0x180014a7e  lea     rcx, [rsp+0F8h+propvar]; propvar
0x180014a83  call    cs:__imp_PropVariantToStringAlloc
0x180014a8a  nop     dword ptr [rax+rax+00h]
0x180014a8f  mov     ebx, eax
0x180014a91  test    eax, eax
0x180014a93  jns     short loc_180014B0D
0x180014a95  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x180014a9c  jz      short loc_180014AC2
0x180014a9e  lea     rax, aChrPropvariant_0; "CHR(PropVariantToStringAlloc(propertyVa"...
0x180014aa5  mov     [rsp+0F8h+var_D0], rax
0x180014aaa  mov     dword ptr [rsp+0F8h+ppv], 57h ; 'W'
0x180014ab2  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014ab9  mov     r8d, ebx
0x180014abc  call    McTemplateU0dsqs_EventWriteTransfer
0x180014ac1  nop
0x180014ac2  lea     rcx, [rsp+0F8h+var_60]
0x180014aca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014acf  nop
0x180014ad0  mov     rcx, [rsp+0F8h+var_C8]
0x180014ad5  test    rcx, rcx
0x180014ad8  jz      short loc_180014AEC
0x180014ada  mov     [rsp+0F8h+var_C8], rsi
0x180014adf  mov     rax, [rcx]
0x180014ae2  mov     rax, [rax+10h]
0x180014ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aeb  nop
0x180014aec  mov     rcx, [rsp+0F8h+var_C0]
0x180014af1  test    rcx, rcx
0x180014af4  jz      short loc_180014B08
0x180014af6  mov     [rsp+0F8h+var_C0], rsi
0x180014afb  mov     rax, [rcx]
0x180014afe  mov     rax, [rax+10h]
0x180014b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b07  nop
0x180014b08  jmp     loc_1800151DA
0x180014b0d  mov     r9, [rsp+0F8h+pv]
0x180014b12  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180014b16  inc     rdx
0x180014b19  cmp     [r9+rdx*2], si
0x180014b1e  jnz     short loc_180014B16
0x180014b20  cmp     rdx, [rsp+0F8h+var_48]
0x180014b28  ja      short loc_180014B64
0x180014b2a  lea     rdi, [rsp+0F8h+var_60]
0x180014b32  cmp     [rsp+0F8h+var_48], 7
0x180014b3b  cmova   rdi, [rsp+0F8h+var_60]
0x180014b44  mov     [rsp+0F8h+var_50], rdx
0x180014b4c  lea     rbx, [rdx+rdx]
0x180014b50  mov     r8, rbx; Size
0x180014b53  mov     rdx, r9; Src
0x180014b56  mov     rcx, rdi; void *
0x180014b59  call    memmove_0
0x180014b5e  mov     [rbx+rdi], si
0x180014b62  jmp     short loc_180014B71
0x180014b64  lea     rcx, [rsp+0F8h+var_60]
0x180014b6c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180014b71  mov     rcx, [rsp+0F8h+var_60]
0x180014b79  cmp     [rsp+0F8h+var_48], 7
0x180014b82  jbe     short loc_180014B8C
0x180014b84  mov     rdi, rcx
0x180014b87  mov     rdx, rcx
0x180014b8a  jmp     short loc_180014B9C
0x180014b8c  lea     rdi, [rsp+0F8h+var_60]
0x180014b94  lea     rdx, [rsp+0F8h+var_60]
0x180014b9c  mov     rax, [rsp+0F8h+var_50]
0x180014ba4  lea     r15, [rdx+rax*2]
0x180014ba8  lea     rbx, [rsp+0F8h+var_60]
0x180014bb0  cmova   rbx, rcx
0x180014bb4  cmp     rbx, r15
0x180014bb7  jz      short loc_180014BD5
0x180014bb9  movzx   ecx, word ptr [rbx]
0x180014bbc  mov     rax, cs:__imp_towupper
0x180014bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bc8  mov     [rdi], ax
0x180014bcb  add     rbx, 2
0x180014bcf  add     rdi, 2
0x180014bd3  jmp     short loc_180014BB4
0x180014bd5  lea     rcx, [rsp+0F8h+propvar]; pvar
0x180014bda  call    cs:__imp_PropVariantClear
  ... truncated ...
```
