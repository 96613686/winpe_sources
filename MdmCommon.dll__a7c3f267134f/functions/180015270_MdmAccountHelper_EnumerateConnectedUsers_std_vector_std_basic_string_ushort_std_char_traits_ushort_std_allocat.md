# MdmAccountHelper::EnumerateConnectedUsers(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x180015270`
- end: `0x180016077`
- name: `?EnumerateConnectedUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z`
- size: `3591`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800034c0`

## callees

- `0x180001520`
- `0x18000269c`
- `0x1800028e4`
- `0x180002bb8`
- `0x180002de8`
- `0x1800065c0`
- `0x180015270`
- `0x180016bb4`
- `0x180016e78`
- `0x18001dbfc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180015894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ffd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ffd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800158bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800158bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800152e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800152e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001571a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001571a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015fe7`
- `PROPSYS!PropVariantToStringAlloc` at `0x180015733`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800159aa`
- `PROPSYS!PropVariantToStringAlloc` at `0x180015733`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800159aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180015a79`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180015a79`

## string_xrefs

- `0x18001531c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015438`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015527`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800155db`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015699`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015766`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015910`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800159dd`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015ac5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015b77`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015c38`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015b63`: `CHR(IsAdminBySid(pSid, &fFoundMatch, &fIsAdmin))`
- `0x180015c24`: `CHR(IsDeviceOwnerBySid(pSid, &fIsDeviceOwner))`
- `0x180015308`: `CHR(CoCreateInstance( __uuidof(CoClassConnectedUserStore), 0, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLSCTX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(**(spUserStore.GetAddressOf())), IID_PPV_ARGS_Helper(spUserStore.GetAddressOf())))`
- `0x1800158fc`: `CHR(spPropStore->GetValue(PKEY_Identity_PrimarySid, &propertyValue))`
- `0x1800159c9`: `CHR(PropVariantToStringAlloc(propertyValue, &pwszSid))`
- `0x180015ab1`: `CBR(ConvertStringSidToSidW(pwszSid, &pSid))`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall MdmAccountHelper::EnumerateConnectedUsers(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // edx
  int v7; // ecx
  int IsAdminBySid; // ebx
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v18; // rcx
  int v19; // edx
  int v20; // ecx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  int v24; // edx
  int v25; // ecx
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rcx
  int v29; // edx
  int v30; // ecx
  __int64 v31; // rcx
  _QWORD *v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rcx
  int v34; // edx
  int v35; // ecx
  __int64 v36; // r8
  __int64 v37; // rcx
  _QWORD *v38; // rcx
  __int64 (__fastcall ***v39)(_QWORD, _QWORD, _QWORD); // rcx
  unsigned __int64 v40; // rdx
  void **v41; // rdi
  __int64 v42; // rbx
  int v43; // ecx
  void **v44; // rdi
  void **v45; // rdx
  void **v46; // rax
  void **v47; // rbx
  int v48; // edx
  int v49; // ecx
  __int64 v50; // rcx
  _QWORD *v51; // rcx
  __int64 (__fastcall ***v52)(_QWORD, _QWORD, _QWORD); // rcx
  int v53; // edx
  int v54; // ecx
  __int64 v55; // rcx
  _QWORD *v56; // rcx
  __int64 (__fastcall ***v57)(_QWORD, _QWORD, _QWORD); // rcx
  signed int LastError; // eax
  int v59; // edx
  int v60; // ecx
  __int64 v61; // rcx
  _QWORD *v62; // rcx
  __int64 (__fastcall ***v63)(_QWORD, _QWORD, _QWORD); // rcx
  int v64; // edx
  __int64 v65; // rcx
  __int64 v66; // rcx
  _QWORD *v67; // rcx
  __int64 (__fastcall ***v68)(_QWORD, _QWORD, _QWORD); // rcx
  int v69; // edx
  __int64 v70; // rcx
  _QWORD *v71; // rcx
  __int64 (__fastcall ***v72)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v73; // rdx
  int v74; // ecx
  __int64 v75; // rcx
  _QWORD *v76; // rcx
  __int64 (__fastcall ***v77)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v78; // rdx
  int v79; // ecx
  __int64 v80; // rcx
  _QWORD *v81; // rcx
  __int64 (__fastcall ***v82)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v83; // rdx
  int v84; // ecx
  __int64 v85; // rcx
  _QWORD *v86; // rcx
  __int64 (__fastcall ***v87)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v88; // rcx
  _QWORD *v89; // rcx
  __int64 (__fastcall ***v90)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v91; // rcx
  _QWORD *v92; // rcx
  __int64 (__fastcall ***v93)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v94; // rcx
  _QWORD *v95; // rcx
  __int64 (__fastcall ***v96)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v97; // rcx
  LPVOID v98; // rcx
  _BYTE v100[32]; // [rsp+0h] [rbp-F8h] BYREF
  _QWORD *v101; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v102; // [rsp+38h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v103)(_QWORD, GUID *, _QWORD **); // [rsp+40h] [rbp-B8h] BYREF
  int v104; // [rsp+48h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v106; // [rsp+58h] [rbp-A0h] BYREF
  int v107; // [rsp+60h] [rbp-98h] BYREF
  int v108; // [rsp+64h] [rbp-94h] BYREF
  int v109; // [rsp+68h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-88h] BYREF
  PWSTR ppszOut; // [rsp+78h] [rbp-80h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-78h] BYREF
  PROPVARIANT propvar[2]; // [rsp+88h] [rbp-70h] BYREF
  __int64 v114; // [rsp+98h] [rbp-60h]
  void **v115; // [rsp+A0h] [rbp-58h]
  void *v116[2]; // [rsp+A8h] [rbp-50h] BYREF
  unsigned __int64 v117; // [rsp+B8h] [rbp-40h]
  unsigned __int64 v118; // [rsp+C0h] [rbp-38h]

  ppv = 0;
  v106 = 0;
  pv = 0;
  ppszOut = 0;
  hMem = 0;
  if ( !a1 && !a3 )
  {
LABEL_196:
    IsAdminBySid = 0;
    goto LABEL_197;
  }
  IsAdminBySid = CoCreateInstance(
                   &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
                   0,
                   0x17u,
                   &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
                   &ppv);
  if ( IsAdminBySid < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        IsAdminBySid,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
        222,
        "CHR(CoCreateInstance( __uuidof(CoClassConnectedUserStore), 0, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLSC"
        "TX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(**(spUserStore.GetAddressOf())), IID_PPV_ARGS_Helper(spUserStor"
        "e.GetAddressOf())))");
    goto LABEL_197;
  }
  IsAdminBySid = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   0,
                   0,
                   &v106);
  if ( IsAdminBySid < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        v9,
        IsAdminBySid,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
        227,
        "CHR(spUserStore->GetConnectedUserEnum( 0, 0, &spUserEnum))");
    goto LABEL_197;
  }
  while ( 1 )
  {
    v103 = 0;
    v101 = 0;
    v102 = 0;
    v107 = 0;
    *(_OWORD *)propvar = 0;
    v114 = 0;
    v108 = 0;
    v104 = 0;
    v109 = 0;
    *(_OWORD *)v116 = 0;
    v117 = 0;
    v118 = 7;
    LOWORD(v116[0]) = 0;
    IsAdminBySid = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **), int *))(*(_QWORD *)v106 + 24LL))(
                     v106,
                     1,
                     &v103,
                     &v107);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          241,
          "CHR(spUserEnum->Next(1, spUnknown.GetAddressOf(), &cFetch))");
      std::wstring::~wstring(v116);
      v13 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      v14 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
      }
      v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
      }
      goto LABEL_197;
    }
    if ( IsAdminBySid == 1 || !v107 )
    {
      std::wstring::~wstring(v116);
      v94 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      }
      v95 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v95 + 16LL))(v95);
      }
      v96 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v96)[2])(v96);
      }
      goto LABEL_196;
    }
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
    v17 = **v103;
    v18 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v18 + 16LL))(v18, *v18);
    }
    IsAdminBySid = v17(v16, &GUID_9d5f2149_de8c_45f2_b313_6587a04f771d, &v101);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v20,
          v19,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          248,
          "CHR(spUnknown.As(&spUser))");
      std::wstring::~wstring(v116);
      v21 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
      }
      v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
      }
      goto LABEL_197;
    }
    IsAdminBySid = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v101 + 24LL))(v101, &v102);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v25,
          v24,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          249,
          "CHR(spUser->GetConnectedUserInfo(spPropStore.GetAddressOf()))");
      std::wstring::~wstring(v116);
      v26 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v27 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
      }
      v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v28)[2])(v28);
      }
      goto LABEL_197;
    }
    IsAdminBySid = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v102 + 40LL))(
                     v102,
                     &PKEY_Identity_UniqueID,
                     propvar);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v30,
          v29,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          252,
          "CHR(spPropStore->GetValue(PKEY_Identity_UniqueID, &propertyValue))");
      std::wstring::~wstring(v116);
      v31 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v32 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
      }
      v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v33)[2])(v33);
      }
      goto LABEL_197;
    }
    if ( pv )
      CoTaskMemFree(pv);
    IsAdminBySid = PropVariantToStringAlloc(propvar, (PWSTR *)&pv);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v35,
          v34,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          3,
          "CHR(PropVariantToStringAlloc(propertyValue, &pwszCid))");
      std::wstring::~wstring(v116);
      v37 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v38 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v38 + 16LL))(v38);
      }
      v39 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v39)[2])(v39);
      }
      goto LABEL_197;
    }
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)pv + v40) );
    try
    {
      if ( v40 > v118 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v116,
          v40,
          v36,
          pv);
      }
      else
      {
        v41 = v116;
        if ( v118 > 7 )
          v41 = (void **)v116[0];
        v117 = v40;
        v42 = 2 * v40;
        memmove_0(v41, pv, 2 * v40);
        *(_WORD *)((char *)v41 + v42) = 0;
      }
      v43 = (int)v116[0];
      if ( v118 <= 7 )
      {
        v44 = v116;
        v45 = v116;
      }
      else
      {
        v44 = (void **)v116[0];
        v45 = (void **)v116[0];
      }
      v46 = (void **)((char *)v45 + 2 * v117);
      v115 = v46;
      v47 = v116;
      if ( v118 > 7 )
        v47 = (void **)v116[0];
      while ( v47 != v46 )
      {
        *(_WORD *)v44 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v47);
        v47 = (void **)((char *)v47 + 2);
        v44 = (void **)((char *)v44 + 2);
        v46 = v115;
      }
    }
    catch ( std::bad_alloc )
    {
      v104 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v43,
          (unsigned int)v100,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          12,
          "CHR(((HRESULT)0x8007000EL))");
      std::wstring::~wstring(v116);
      v91 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      }
      v92 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v92 + 16LL))(v92);
      }
      v93 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v93)[2])(v93);
      }
LABEL_189:
      IsAdminBySid = v104;
      goto LABEL_197;
    }
    PropVariantClear(propvar);
    IsAdminBySid = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v102 + 40LL))(
                     v102,
                     &PKEY_Identity_PrimarySid,
                     propvar);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v49,
          v48,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          17,
          "CHR(spPropStore->GetValue(PKEY_Identity_PrimarySid, &propertyValue))");
      std::wstring::~wstring(v116);
      v50 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      }
      v51 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
      }
      v52 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v52)[2])(v52);
      }
      goto LABEL_197;
    }
    if ( ppszOut )
      CoTaskMemFree(ppszOut);
    IsAdminBySid = PropVariantToStringAlloc(propvar, &ppszOut);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v54,
          v53,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          24,
          "CHR(PropVariantToStringAlloc(propertyValue, &pwszSid))");
      std::wstring::~wstring(v116);
      v55 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      v56 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v56 + 16LL))(v56);
      }
      v57 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v57)[2])(v57);
      }
      goto LABEL_197;
    }
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( !ConvertStringSidToSidW(ppszOut, &hMem) )
    {
      LastError = GetLastError();
      IsAdminBySid = LastError;
      if ( LastError > 0 )
        IsAdminBySid = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v60,
          v59,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          32,
          "CBR(ConvertStringSidToSidW(pwszSid, &pSid))");
      std::wstring::~wstring(v116);
      v61 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      }
      v62 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
      }
      v63 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v63)[2])(v63);
      }
      goto LABEL_197;
    }
    IsAdminBySid = MdmAccountHelper::IsAdminBySid(hMem, &v108, &v104);
    if ( IsAdminBySid < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v65,
          v64,
          IsAdminBySid,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          34,
          "CHR(IsAdminBySid(pSid, &fFoundMatch, &fIsAdmin))");
      std::wstring::~wstring(v116);
      v66 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
      }
      v67 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v67 + 16LL))(v67);
      }
      v68 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v68)[2])(v68);
      }
      goto LABEL_197;
    }
    if ( v108 )
      break;
LABEL_169:
    std::wstring::~wstring(v116);
    v85 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
    v86 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v86 + 16LL))(v86);
    }
    v87 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
    if ( v103 )
    {
      v103 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v87)[2])(v87);
    }
  }
  if ( v104 )
  {
LABEL_139:
    if ( a1 )
    {
      try
      {
        v73 = *(_QWORD *)(a1 + 8);
        if ( v73 == *(_QWORD *)(a1 + 16) )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v73, v116);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
            v65,
            v73,
            v116);
          *(_QWORD *)(a1 + 8) += 32LL;
        }
      }
      catch ( std::bad_alloc )
      {
        v104 = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v74,
            (unsigned int)v100,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
            55,
            "CHR(((HRESULT)0x8007000EL))");
        std::wstring::~wstring(v116);
        v75 = v102;
        if ( v102 )
        {
          v102 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
        }
        v76 = v101;
        if ( v101 )
        {
          v101 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v76 + 16LL))(v76);
        }
        v77 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
        if ( v103 )
        {
          v103 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v77)[2])(v77);
        }
        goto LABEL_189;
      }
    }
    goto LABEL_169;
  }
  IsAdminBySid = MdmAccountHelper::IsDeviceOwnerBySid(hMem, &v109);
  if ( IsAdminBySid >= 0 )
  {
    if ( !v104 )
    {
      if ( v109 )
      {
        if ( a2 )
        {
          try
          {
            v78 = *(_QWORD *)(a2 + 8);
            if ( v78 == *(_QWORD *)(a2 + 16) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a2, v78, v116);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                v65,
                v78,
                v116);
              *(_QWORD *)(a2 + 8) += 32LL;
            }
          }
          catch ( std::bad_alloc )
          {
            v104 = -2147024882;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v79,
                (unsigned int)v100,
                -2147024882,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
                69,
                "CHR(((HRESULT)0x8007000EL))");
            std::wstring::~wstring(v116);
            v80 = v102;
            if ( v102 )
            {
              v102 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
            }
            v81 = v101;
            if ( v101 )
            {
              v101 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v81 + 16LL))(v81);
            }
            v82 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
            if ( v103 )
            {
              v103 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v82)[2])(v82);
            }
            goto LABEL_189;
          }
        }
      }
      else if ( a3 )
      {
        try
        {
          v83 = *(_QWORD *)(a3 + 8);
          if ( v83 == *(_QWORD *)(a3 + 16) )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a3, v83, v116);
          }
          else
          {
            std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
              v65,
              v83,
              v116);
            *(_QWORD *)(a3 + 8) += 32LL;
          }
        }
        catch ( std::bad_alloc )
        {
          v104 = -2147024882;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v84,
              (unsigned int)v100,
              -2147024882,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
              83,
              "CHR(((HRESULT)0x8007000EL))");
          std::wstring::~wstring(v116);
          v88 = v102;
          if ( v102 )
          {
            v102 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
          }
          v89 = v101;
          if ( v101 )
          {
            v101 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v89 + 16LL))(v89);
          }
          v90 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
          if ( v103 )
          {
            v103 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v90)[2])(v90);
          }
          goto LABEL_189;
        }
      }
      goto LABEL_169;
    }
    goto LABEL_139;
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v65,
      v69,
      IsAdminBySid,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      39,
      "CHR(IsDeviceOwnerBySid(pSid, &fIsDeviceOwner))");
  std::wstring::~wstring(v116);
  v70 = v102;
  if ( v102 )
  {
    v102 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
  }
  v71 = v101;
  if ( v101 )
  {
    v101 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v71 + 16LL))(v71);
  }
  v72 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v103;
  if ( v103 )
  {
    v103 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v72)[2])(v72);
  }
LABEL_197:
  if ( pv )
    CoTaskMemFree(pv);
  if ( ppszOut )
    CoTaskMemFree(ppszOut);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  v97 = v106;
  if ( v106 )
  {
    v106 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  }
  v98 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v98 + 16LL))(v98);
  }
  return (unsigned int)IsAdminBySid;
}

```

## disassembly

```asm
0x180015270  mov     r11, rsp
0x180015273  mov     [r11+20h], rbx
0x180015277  push    rsi
0x180015278  push    rdi
0x180015279  push    r12
0x18001527b  push    r13
0x18001527d  push    r15
0x18001527f  sub     rsp, 0D0h
0x180015286  mov     rax, cs:__security_cookie
0x18001528d  xor     rax, rsp
0x180015290  mov     [rsp+0F8h+var_30], rax
0x180015298  mov     r15, r8
0x18001529b  mov     r12, rdx
0x18001529e  mov     r13, rcx
0x1800152a1  xor     esi, esi
0x1800152a3  mov     [r11-78h], rsi
0x1800152a7  mov     [rsp+0F8h+var_A0], rsi
0x1800152ac  mov     [rsp+0F8h+pv], rsi
0x1800152b1  mov     [r11-80h], rsi
0x1800152b5  mov     [rsp+0F8h+hMem], rsi
0x1800152ba  test    rcx, rcx
0x1800152bd  jnz     short loc_1800152C8
0x1800152bf  test    r8, r8
0x1800152c2  jz      loc_180015FC5
0x1800152c8  lea     rax, [rsp+0F8h+var_78]
0x1800152d0  mov     [rsp+0F8h+ppv], rax; ppv
0x1800152d5  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x1800152dc  xor     edx, edx; pUnkOuter
0x1800152de  lea     r8d, [rdx+17h]; dwClsContext
0x1800152e2  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x1800152e9  call    cs:__imp_CoCreateInstance
0x1800152f0  nop     dword ptr [rax+rax+00h]
0x1800152f5  mov     ebx, eax
0x1800152f7  test    eax, eax
0x1800152f9  jns     short loc_180015330
0x1800152fb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015302  jz      loc_180015FC7
0x180015308  lea     rax, aChrCocreateins; "CHR(CoCreateInstance( __uuidof(CoClassC"...
0x18001530f  mov     [rsp+0F8h+var_D0], rax
0x180015314  mov     dword ptr [rsp+0F8h+ppv], 0DEh
0x18001531c  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180015323  mov     r8d, ebx
0x180015326  call    McTemplateU0dsqs_EventWriteTransfer
0x18001532b  jmp     loc_180015FC7
0x180015330  mov     rbx, [rsp+0F8h+var_78]
0x180015338  mov     rax, [rbx]
0x18001533b  mov     rdi, [rax+18h]
0x18001533f  mov     rcx, [rsp+0F8h+var_A0]
0x180015344  test    rcx, rcx
0x180015347  jz      short loc_18001535B
0x180015349  mov     [rsp+0F8h+var_A0], rsi
0x18001534e  mov     rdx, [rcx]
0x180015351  mov     rax, [rdx+10h]
0x180015355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001535a  nop
0x18001535b  lea     r9, [rsp+0F8h+var_A0]
0x180015360  xor     r8d, r8d
0x180015363  xor     edx, edx
0x180015365  mov     rcx, rbx
0x180015368  mov     rax, rdi
0x18001536b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015370  mov     ebx, eax
0x180015372  test    eax, eax
0x180015374  jns     short loc_180015399
0x180015376  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001537d  jz      loc_180015FC7
0x180015383  lea     rax, aChrSpuserstore_1; "CHR(spUserStore->GetConnectedUserEnum( "...
0x18001538a  mov     [rsp+0F8h+var_D0], rax
0x18001538f  mov     dword ptr [rsp+0F8h+ppv], 0E3h
0x180015397  jmp     short loc_18001531C
0x180015399  mov     [rsp+0F8h+var_B8], rsi
0x18001539e  mov     [rsp+0F8h+var_C8], rsi
0x1800153a3  mov     [rsp+0F8h+var_C0], rsi
0x1800153a8  mov     [rsp+0F8h+var_98], esi
0x1800153ac  xorps   xmm0, xmm0
0x1800153af  xor     eax, eax
0x1800153b1  movups  xmmword ptr [rsp+0F8h+propvar], xmm0
0x1800153b9  mov     [rsp+0F8h+var_60], rax
0x1800153c1  mov     [rsp+0F8h+var_94], esi
0x1800153c5  mov     [rsp+0F8h+var_B0], esi
0x1800153c9  mov     [rsp+0F8h+var_90], esi
0x1800153cd  movups  xmmword ptr [rsp+0F8h+var_50], xmm0
0x1800153d5  mov     [rsp+0F8h+var_40], rsi
0x1800153dd  mov     [rsp+0F8h+var_38], 7
0x1800153e9  mov     word ptr [rsp+0F8h+var_50], si
0x1800153f1  mov     rcx, [rsp+0F8h+var_A0]
0x1800153f6  mov     rax, [rcx]
0x1800153f9  lea     r9, [rsp+0F8h+var_98]
0x1800153fe  lea     r8, [rsp+0F8h+var_B8]
0x180015403  mov     edx, 1
0x180015408  mov     rax, [rax+18h]
0x18001540c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015411  mov     ebx, eax
0x180015413  test    eax, eax
0x180015415  jns     loc_1800154AF
0x18001541b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015422  jz      short loc_180015448
0x180015424  lea     rax, aChrSpuserenumN; "CHR(spUserEnum->Next(1, spUnknown.GetAd"...
0x18001542b  mov     [rsp+0F8h+var_D0], rax
0x180015430  mov     dword ptr [rsp+0F8h+ppv], 0F1h
0x180015438  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001543f  mov     r8d, ebx
0x180015442  call    McTemplateU0dsqs_EventWriteTransfer
0x180015447  nop
0x180015448  lea     rcx, [rsp+0F8h+var_50]
0x180015450  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015455  nop
0x180015456  mov     rcx, [rsp+0F8h+var_C0]
0x18001545b  test    rcx, rcx
0x18001545e  jz      short loc_180015472
0x180015460  mov     [rsp+0F8h+var_C0], rsi
0x180015465  mov     rax, [rcx]
0x180015468  mov     rax, [rax+10h]
0x18001546c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015471  nop
0x180015472  mov     rcx, [rsp+0F8h+var_C8]
0x180015477  test    rcx, rcx
0x18001547a  jz      short loc_18001548E
0x18001547c  mov     [rsp+0F8h+var_C8], rsi
0x180015481  mov     rax, [rcx]
0x180015484  mov     rax, [rax+10h]
0x180015488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001548d  nop
0x18001548e  mov     rcx, [rsp+0F8h+var_B8]
0x180015493  test    rcx, rcx
0x180015496  jz      short loc_1800154AA
0x180015498  mov     [rsp+0F8h+var_B8], rsi
0x18001549d  mov     rax, [rcx]
0x1800154a0  mov     rax, [rax+10h]
0x1800154a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154a9  nop
0x1800154aa  jmp     loc_180015FC7
0x1800154af  cmp     ebx, 1
0x1800154b2  jz      loc_180015F63
0x1800154b8  cmp     [rsp+0F8h+var_98], esi
0x1800154bc  jz      loc_180015F63
0x1800154c2  mov     rbx, [rsp+0F8h+var_B8]
0x1800154c7  mov     rax, [rbx]
0x1800154ca  mov     rdi, [rax]
0x1800154cd  mov     rcx, [rsp+0F8h+var_C8]
0x1800154d2  test    rcx, rcx
0x1800154d5  jz      short loc_1800154E9
0x1800154d7  mov     [rsp+0F8h+var_C8], rsi
0x1800154dc  mov     rdx, [rcx]
0x1800154df  mov     rax, [rdx+10h]
0x1800154e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154e8  nop
0x1800154e9  lea     r8, [rsp+0F8h+var_C8]
0x1800154ee  lea     rdx, _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d
0x1800154f5  mov     rcx, rbx
0x1800154f8  mov     rax, rdi
0x1800154fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015500  mov     ebx, eax
0x180015502  test    eax, eax
0x180015504  jns     loc_18001559E
0x18001550a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015511  jz      short loc_180015537
0x180015513  lea     rax, aChrSpunknownAs; "CHR(spUnknown.As(&spUser))"
0x18001551a  mov     [rsp+0F8h+var_D0], rax
0x18001551f  mov     dword ptr [rsp+0F8h+ppv], 0F8h
0x180015527  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001552e  mov     r8d, ebx
0x180015531  call    McTemplateU0dsqs_EventWriteTransfer
0x180015536  nop
0x180015537  lea     rcx, [rsp+0F8h+var_50]
0x18001553f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015544  nop
0x180015545  mov     rcx, [rsp+0F8h+var_C0]
0x18001554a  test    rcx, rcx
0x18001554d  jz      short loc_180015561
0x18001554f  mov     [rsp+0F8h+var_C0], rsi
0x180015554  mov     rax, [rcx]
0x180015557  mov     rax, [rax+10h]
0x18001555b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015560  nop
0x180015561  mov     rcx, [rsp+0F8h+var_C8]
0x180015566  test    rcx, rcx
0x180015569  jz      short loc_18001557D
0x18001556b  mov     [rsp+0F8h+var_C8], rsi
0x180015570  mov     rax, [rcx]
0x180015573  mov     rax, [rax+10h]
0x180015577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001557c  nop
0x18001557d  mov     rcx, [rsp+0F8h+var_B8]
0x180015582  test    rcx, rcx
0x180015585  jz      short loc_180015599
0x180015587  mov     [rsp+0F8h+var_B8], rsi
0x18001558c  mov     rax, [rcx]
0x18001558f  mov     rax, [rax+10h]
0x180015593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015598  nop
0x180015599  jmp     loc_180015FC7
0x18001559e  mov     rcx, [rsp+0F8h+var_C8]
0x1800155a3  mov     rax, [rcx]
0x1800155a6  lea     rdx, [rsp+0F8h+var_C0]
0x1800155ab  mov     rax, [rax+18h]
0x1800155af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155b4  mov     ebx, eax
0x1800155b6  test    eax, eax
0x1800155b8  jns     loc_180015652
0x1800155be  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800155c5  jz      short loc_1800155EB
0x1800155c7  lea     rax, aChrSpuserGetco; "CHR(spUser->GetConnectedUserInfo(spProp"...
0x1800155ce  mov     [rsp+0F8h+var_D0], rax
0x1800155d3  mov     dword ptr [rsp+0F8h+ppv], 0F9h
0x1800155db  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800155e2  mov     r8d, ebx
0x1800155e5  call    McTemplateU0dsqs_EventWriteTransfer
0x1800155ea  nop
0x1800155eb  lea     rcx, [rsp+0F8h+var_50]
0x1800155f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800155f8  nop
0x1800155f9  mov     rcx, [rsp+0F8h+var_C0]
0x1800155fe  test    rcx, rcx
0x180015601  jz      short loc_180015615
0x180015603  mov     [rsp+0F8h+var_C0], rsi
0x180015608  mov     rax, [rcx]
0x18001560b  mov     rax, [rax+10h]
0x18001560f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015614  nop
0x180015615  mov     rcx, [rsp+0F8h+var_C8]
0x18001561a  test    rcx, rcx
0x18001561d  jz      short loc_180015631
0x18001561f  mov     [rsp+0F8h+var_C8], rsi
0x180015624  mov     rax, [rcx]
0x180015627  mov     rax, [rax+10h]
0x18001562b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015630  nop
0x180015631  mov     rcx, [rsp+0F8h+var_B8]
0x180015636  test    rcx, rcx
0x180015639  jz      short loc_18001564D
0x18001563b  mov     [rsp+0F8h+var_B8], rsi
0x180015640  mov     rax, [rcx]
0x180015643  mov     rax, [rax+10h]
0x180015647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001564c  nop
0x18001564d  jmp     loc_180015FC7
0x180015652  mov     rcx, [rsp+0F8h+var_C0]
0x180015657  mov     rax, [rcx]
0x18001565a  lea     r8, [rsp+0F8h+propvar]
0x180015662  lea     rdx, PKEY_Identity_UniqueID
0x180015669  mov     rax, [rax+28h]
0x18001566d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015672  mov     ebx, eax
0x180015674  test    eax, eax
0x180015676  jns     loc_180015710
0x18001567c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015683  jz      short loc_1800156A9
0x180015685  lea     rax, aChrSppropstore_1; "CHR(spPropStore->GetValue(PKEY_Identity"...
0x18001568c  mov     [rsp+0F8h+var_D0], rax
0x180015691  mov     dword ptr [rsp+0F8h+ppv], 0FCh
0x180015699  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800156a0  mov     r8d, ebx
0x1800156a3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800156a8  nop
0x1800156a9  lea     rcx, [rsp+0F8h+var_50]
0x1800156b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800156b6  nop
0x1800156b7  mov     rcx, [rsp+0F8h+var_C0]
0x1800156bc  test    rcx, rcx
0x1800156bf  jz      short loc_1800156D3
0x1800156c1  mov     [rsp+0F8h+var_C0], rsi
0x1800156c6  mov     rax, [rcx]
0x1800156c9  mov     rax, [rax+10h]
0x1800156cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156d2  nop
0x1800156d3  mov     rcx, [rsp+0F8h+var_C8]
0x1800156d8  test    rcx, rcx
0x1800156db  jz      short loc_1800156EF
0x1800156dd  mov     [rsp+0F8h+var_C8], rsi
0x1800156e2  mov     rax, [rcx]
0x1800156e5  mov     rax, [rax+10h]
0x1800156e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156ee  nop
0x1800156ef  mov     rcx, [rsp+0F8h+var_B8]
0x1800156f4  test    rcx, rcx
0x1800156f7  jz      short loc_18001570B
0x1800156f9  mov     [rsp+0F8h+var_B8], rsi
0x1800156fe  mov     rax, [rcx]
0x180015701  mov     rax, [rax+10h]
0x180015705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001570a  nop
0x18001570b  jmp     loc_180015FC7
0x180015710  mov     rcx, [rsp+0F8h+pv]; pv
0x180015715  test    rcx, rcx
0x180015718  jz      short loc_180015726
0x18001571a  call    cs:__imp_CoTaskMemFree
0x180015721  nop     dword ptr [rax+rax+00h]
0x180015726  lea     rdx, [rsp+0F8h+pv]; ppszOut
0x18001572b  lea     rcx, [rsp+0F8h+propvar]; propvar
0x180015733  call    cs:__imp_PropVariantToStringAlloc
0x18001573a  nop     dword ptr [rax+rax+00h]
0x18001573f  mov     ebx, eax
0x180015741  test    eax, eax
0x180015743  jns     loc_1800157DD
0x180015749  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015750  jz      short loc_180015776
0x180015752  lea     rax, aChrPropvariant_0; "CHR(PropVariantToStringAlloc(propertyVa"...
0x180015759  mov     [rsp+0F8h+var_D0], rax
0x18001575e  mov     dword ptr [rsp+0F8h+ppv], 103h
  ... truncated ...
```
