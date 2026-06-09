# MdmAccountHelper::EnumerateConnectedUsers(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x180014e2c`
- end: `0x180015bea`
- name: `?EnumerateConnectedUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z`
- size: `3518`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800034b0`

## callees

- `0x180001520`
- `0x18000269c`
- `0x1800028e4`
- `0x180002bb8`
- `0x180002de4`
- `0x180006548`
- `0x180014e2c`
- `0x1800166f8`
- `0x180016994`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001543e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015619`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800155f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800155f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b77`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015467`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015467`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014ea5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015535`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015535`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b67`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800152e3`
- `PROPSYS!PropVariantToStringAlloc` at `0x180015548`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800152e3`
- `PROPSYS!PropVariantToStringAlloc` at `0x180015548`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001560b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001560b`

## string_xrefs

- `0x180014ed2`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180014fee`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800150dd`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015191`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001524f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015310`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800154b4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180015575`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x18001564b`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800156fd`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800157be`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800156e9`: `CHR(IsAdminBySid(pSid, &fFoundMatch, &fIsAdmin))`
- `0x1800157aa`: `CHR(IsDeviceOwnerBySid(pSid, &fIsDeviceOwner))`
- `0x180014ebe`: `CHR(CoCreateInstance( __uuidof(CoClassConnectedUserStore), 0, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLSCTX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(**(spUserStore.GetAddressOf())), IID_PPV_ARGS_Helper(spUserStore.GetAddressOf())))`
- `0x1800154a0`: `CHR(spPropStore->GetValue(PKEY_Identity_PrimarySid, &propertyValue))`
- `0x180015561`: `CHR(PropVariantToStringAlloc(propertyValue, &pwszSid))`
- `0x180015637`: `CBR(ConvertStringSidToSidW(pwszSid, &pSid))`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateConnectedUsers(__int64 *a1, __int64 *a2, __int64 *a3)
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
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v15)[2])(v15);
      }
      goto LABEL_197;
    }
    if ( IsAdminBySid == 1 || !v107 )
    {
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v96)[2])(v96);
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
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v23)[2])(v23);
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
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v28)[2])(v28);
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
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v33)[2])(v33);
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
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v39)[2])(v39);
      }
      goto LABEL_197;
    }
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)pv + v40) );
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( v40 > v118 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)v116,
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
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
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
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180015A7F);
        std::wstring::~wstring((char **)v116);
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
          ((void (__fastcall *)(_QWORD))(*v93)[2])(v93);
        }
LABEL_189:
        IsAdminBySid = v104;
        goto LABEL_197;
      }
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
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v52)[2])(v52);
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
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v57)[2])(v57);
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
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v63)[2])(v63);
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
      std::wstring::~wstring((char **)v116);
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
        ((void (__fastcall *)(_QWORD))(*v68)[2])(v68);
      }
      goto LABEL_197;
    }
    if ( v108 )
      break;
LABEL_169:
    std::wstring::~wstring((char **)v116);
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
      ((void (__fastcall *)(_QWORD))(*v87)[2])(v87);
    }
  }
  if ( v104 )
  {
LABEL_139:
    if ( a1 )
    {
      if ( __eh34_try(-1, 2) )
      {
        __eh34_scope_strut(2);
        v73 = a1[1];
        if ( v73 == a1[2] )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v73, (__int64)v116);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
            v65,
            v73,
            (__int64)v116);
          a1[1] += 32;
        }
      }
      if ( __eh34_catch(2) )
      {
        if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
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
          __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_180015873);
          std::wstring::~wstring((char **)v116);
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
            ((void (__fastcall *)(_QWORD))(*v77)[2])(v77);
          }
          goto LABEL_189;
        }
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
          if ( __eh34_try(-1, 4) )
          {
            __eh34_scope_strut(4);
            v78 = a2[1];
            if ( v78 == a2[2] )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a2, v78, (__int64)v116);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                v65,
                v78,
                (__int64)v116);
              a2[1] += 32;
            }
          }
          if ( __eh34_catch(4) )
          {
            if ( __eh34_catch_type(4, &std::bad_alloc `RTTI Type Descriptor', 0) )
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
              __eh34_try_continuation(4, &std::bad_alloc `RTTI Type Descriptor', &loc_18001591D);
              std::wstring::~wstring((char **)v116);
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
                ((void (__fastcall *)(_QWORD))(*v82)[2])(v82);
              }
              goto LABEL_189;
            }
          }
        }
      }
      else if ( a3 )
      {
        if ( __eh34_try(-1, 6) )
        {
          __eh34_scope_strut(6);
          v83 = a3[1];
          if ( v83 == a3[2] )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a3, v83, (__int64)v116);
          }
          else
          {
            std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
              v65,
              v83,
              (__int64)v116);
            a3[1] += 32;
          }
        }
        if ( __eh34_catch(6) )
        {
          if ( __eh34_catch_type(6, &std::bad_alloc `RTTI Type Descriptor', 0) )
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
            __eh34_try_continuation(6, &std::bad_alloc `RTTI Type Descriptor', &loc_180015A19);
            std::wstring::~wstring((char **)v116);
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
              ((void (__fastcall *)(_QWORD))(*v90)[2])(v90);
            }
            goto LABEL_189;
          }
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
  std::wstring::~wstring((char **)v116);
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
    ((void (__fastcall *)(_QWORD))(*v72)[2])(v72);
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
0x180014e2c  mov     r11, rsp
0x180014e2f  mov     [r11+20h], rbx
0x180014e33  push    rsi
0x180014e34  push    rdi
0x180014e35  push    r12
0x180014e37  push    r13
0x180014e39  push    r15
0x180014e3b  sub     rsp, 0D0h
0x180014e42  mov     rax, cs:__security_cookie
0x180014e49  xor     rax, rsp
0x180014e4c  mov     [rsp+0F8h+var_30], rax
0x180014e54  mov     r15, r8
0x180014e57  mov     r12, rdx
0x180014e5a  mov     r13, rcx
0x180014e5d  xor     esi, esi
0x180014e5f  mov     [r11-78h], rsi
0x180014e63  mov     [rsp+0F8h+var_A0], rsi
0x180014e68  mov     [rsp+0F8h+pv], rsi
0x180014e6d  mov     [r11-80h], rsi
0x180014e71  mov     [rsp+0F8h+hMem], rsi
0x180014e76  test    rcx, rcx
0x180014e79  jnz     short loc_180014E84
0x180014e7b  test    r8, r8
0x180014e7e  jz      loc_180015B4B
0x180014e84  lea     rax, [rsp+0F8h+var_78]
0x180014e8c  mov     [rsp+0F8h+ppv], rax; ppv
0x180014e91  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x180014e98  xor     edx, edx; pUnkOuter
0x180014e9a  lea     r8d, [rdx+17h]; dwClsContext
0x180014e9e  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x180014ea5  call    cs:__imp_CoCreateInstance
0x180014eab  mov     ebx, eax
0x180014ead  test    eax, eax
0x180014eaf  jns     short loc_180014EE6
0x180014eb1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014eb8  jz      loc_180015B4D
0x180014ebe  lea     rax, aChrCocreateins; "CHR(CoCreateInstance( __uuidof(CoClassC"...
0x180014ec5  mov     [rsp+0F8h+var_D0], rax
0x180014eca  mov     dword ptr [rsp+0F8h+ppv], 0DEh
0x180014ed2  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014ed9  mov     r8d, ebx
0x180014edc  call    McTemplateU0dsqs_EventWriteTransfer
0x180014ee1  jmp     loc_180015B4D
0x180014ee6  mov     rbx, [rsp+0F8h+var_78]
0x180014eee  mov     rax, [rbx]
0x180014ef1  mov     rdi, [rax+18h]
0x180014ef5  mov     rcx, [rsp+0F8h+var_A0]
0x180014efa  test    rcx, rcx
0x180014efd  jz      short loc_180014F11
0x180014eff  mov     [rsp+0F8h+var_A0], rsi
0x180014f04  mov     rdx, [rcx]
0x180014f07  mov     rax, [rdx+10h]
0x180014f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f10  nop
0x180014f11  lea     r9, [rsp+0F8h+var_A0]
0x180014f16  xor     r8d, r8d
0x180014f19  xor     edx, edx
0x180014f1b  mov     rcx, rbx
0x180014f1e  mov     rax, rdi
0x180014f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f26  mov     ebx, eax
0x180014f28  test    eax, eax
0x180014f2a  jns     short loc_180014F4F
0x180014f2c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014f33  jz      loc_180015B4D
0x180014f39  lea     rax, aChrSpuserstore_1; "CHR(spUserStore->GetConnectedUserEnum( "...
0x180014f40  mov     [rsp+0F8h+var_D0], rax
0x180014f45  mov     dword ptr [rsp+0F8h+ppv], 0E3h
0x180014f4d  jmp     short loc_180014ED2
0x180014f4f  mov     [rsp+0F8h+var_B8], rsi
0x180014f54  mov     [rsp+0F8h+var_C8], rsi
0x180014f59  mov     [rsp+0F8h+var_C0], rsi
0x180014f5e  mov     [rsp+0F8h+var_98], esi
0x180014f62  xorps   xmm0, xmm0
0x180014f65  xor     eax, eax
0x180014f67  movups  xmmword ptr [rsp+0F8h+propvar], xmm0
0x180014f6f  mov     [rsp+0F8h+var_60], rax
0x180014f77  mov     [rsp+0F8h+var_94], esi
0x180014f7b  mov     [rsp+0F8h+var_B0], esi
0x180014f7f  mov     [rsp+0F8h+var_90], esi
0x180014f83  movups  xmmword ptr [rsp+0F8h+var_50], xmm0
0x180014f8b  mov     [rsp+0F8h+var_40], rsi
0x180014f93  mov     [rsp+0F8h+var_38], 7
0x180014f9f  mov     word ptr [rsp+0F8h+var_50], si
0x180014fa7  mov     rcx, [rsp+0F8h+var_A0]
0x180014fac  mov     rax, [rcx]
0x180014faf  lea     r9, [rsp+0F8h+var_98]
0x180014fb4  lea     r8, [rsp+0F8h+var_B8]
0x180014fb9  mov     edx, 1
0x180014fbe  mov     rax, [rax+18h]
0x180014fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fc7  mov     ebx, eax
0x180014fc9  test    eax, eax
0x180014fcb  jns     loc_180015065
0x180014fd1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014fd8  jz      short loc_180014FFE
0x180014fda  lea     rax, aChrSpuserenumN; "CHR(spUserEnum->Next(1, spUnknown.GetAd"...
0x180014fe1  mov     [rsp+0F8h+var_D0], rax
0x180014fe6  mov     dword ptr [rsp+0F8h+ppv], 0F1h
0x180014fee  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014ff5  mov     r8d, ebx
0x180014ff8  call    McTemplateU0dsqs_EventWriteTransfer
0x180014ffd  nop
0x180014ffe  lea     rcx, [rsp+0F8h+var_50]
0x180015006  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001500b  nop
0x18001500c  mov     rcx, [rsp+0F8h+var_C0]
0x180015011  test    rcx, rcx
0x180015014  jz      short loc_180015028
0x180015016  mov     [rsp+0F8h+var_C0], rsi
0x18001501b  mov     rax, [rcx]
0x18001501e  mov     rax, [rax+10h]
0x180015022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015027  nop
0x180015028  mov     rcx, [rsp+0F8h+var_C8]
0x18001502d  test    rcx, rcx
0x180015030  jz      short loc_180015044
0x180015032  mov     [rsp+0F8h+var_C8], rsi
0x180015037  mov     rax, [rcx]
0x18001503a  mov     rax, [rax+10h]
0x18001503e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015043  nop
0x180015044  mov     rcx, [rsp+0F8h+var_B8]
0x180015049  test    rcx, rcx
0x18001504c  jz      short loc_180015060
0x18001504e  mov     [rsp+0F8h+var_B8], rsi
0x180015053  mov     rax, [rcx]
0x180015056  mov     rax, [rax+10h]
0x18001505a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001505f  nop
0x180015060  jmp     loc_180015B4D
0x180015065  cmp     ebx, 1
0x180015068  jz      loc_180015AE9
0x18001506e  cmp     [rsp+0F8h+var_98], esi
0x180015072  jz      loc_180015AE9
0x180015078  mov     rbx, [rsp+0F8h+var_B8]
0x18001507d  mov     rax, [rbx]
0x180015080  mov     rdi, [rax]
0x180015083  mov     rcx, [rsp+0F8h+var_C8]
0x180015088  test    rcx, rcx
0x18001508b  jz      short loc_18001509F
0x18001508d  mov     [rsp+0F8h+var_C8], rsi
0x180015092  mov     rdx, [rcx]
0x180015095  mov     rax, [rdx+10h]
0x180015099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001509e  nop
0x18001509f  lea     r8, [rsp+0F8h+var_C8]
0x1800150a4  lea     rdx, _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d
0x1800150ab  mov     rcx, rbx
0x1800150ae  mov     rax, rdi
0x1800150b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150b6  mov     ebx, eax
0x1800150b8  test    eax, eax
0x1800150ba  jns     loc_180015154
0x1800150c0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800150c7  jz      short loc_1800150ED
0x1800150c9  lea     rax, aChrSpunknownAs; "CHR(spUnknown.As(&spUser))"
0x1800150d0  mov     [rsp+0F8h+var_D0], rax
0x1800150d5  mov     dword ptr [rsp+0F8h+ppv], 0F8h
0x1800150dd  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800150e4  mov     r8d, ebx
0x1800150e7  call    McTemplateU0dsqs_EventWriteTransfer
0x1800150ec  nop
0x1800150ed  lea     rcx, [rsp+0F8h+var_50]
0x1800150f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800150fa  nop
0x1800150fb  mov     rcx, [rsp+0F8h+var_C0]
0x180015100  test    rcx, rcx
0x180015103  jz      short loc_180015117
0x180015105  mov     [rsp+0F8h+var_C0], rsi
0x18001510a  mov     rax, [rcx]
0x18001510d  mov     rax, [rax+10h]
0x180015111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015116  nop
0x180015117  mov     rcx, [rsp+0F8h+var_C8]
0x18001511c  test    rcx, rcx
0x18001511f  jz      short loc_180015133
0x180015121  mov     [rsp+0F8h+var_C8], rsi
0x180015126  mov     rax, [rcx]
0x180015129  mov     rax, [rax+10h]
0x18001512d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015132  nop
0x180015133  mov     rcx, [rsp+0F8h+var_B8]
0x180015138  test    rcx, rcx
0x18001513b  jz      short loc_18001514F
0x18001513d  mov     [rsp+0F8h+var_B8], rsi
0x180015142  mov     rax, [rcx]
0x180015145  mov     rax, [rax+10h]
0x180015149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001514e  nop
0x18001514f  jmp     loc_180015B4D
0x180015154  mov     rcx, [rsp+0F8h+var_C8]
0x180015159  mov     rax, [rcx]
0x18001515c  lea     rdx, [rsp+0F8h+var_C0]
0x180015161  mov     rax, [rax+18h]
0x180015165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001516a  mov     ebx, eax
0x18001516c  test    eax, eax
0x18001516e  jns     loc_180015208
0x180015174  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001517b  jz      short loc_1800151A1
0x18001517d  lea     rax, aChrSpuserGetco; "CHR(spUser->GetConnectedUserInfo(spProp"...
0x180015184  mov     [rsp+0F8h+var_D0], rax
0x180015189  mov     dword ptr [rsp+0F8h+ppv], 0F9h
0x180015191  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180015198  mov     r8d, ebx
0x18001519b  call    McTemplateU0dsqs_EventWriteTransfer
0x1800151a0  nop
0x1800151a1  lea     rcx, [rsp+0F8h+var_50]
0x1800151a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800151ae  nop
0x1800151af  mov     rcx, [rsp+0F8h+var_C0]
0x1800151b4  test    rcx, rcx
0x1800151b7  jz      short loc_1800151CB
0x1800151b9  mov     [rsp+0F8h+var_C0], rsi
0x1800151be  mov     rax, [rcx]
0x1800151c1  mov     rax, [rax+10h]
0x1800151c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151ca  nop
0x1800151cb  mov     rcx, [rsp+0F8h+var_C8]
0x1800151d0  test    rcx, rcx
0x1800151d3  jz      short loc_1800151E7
0x1800151d5  mov     [rsp+0F8h+var_C8], rsi
0x1800151da  mov     rax, [rcx]
0x1800151dd  mov     rax, [rax+10h]
0x1800151e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151e6  nop
0x1800151e7  mov     rcx, [rsp+0F8h+var_B8]
0x1800151ec  test    rcx, rcx
0x1800151ef  jz      short loc_180015203
0x1800151f1  mov     [rsp+0F8h+var_B8], rsi
0x1800151f6  mov     rax, [rcx]
0x1800151f9  mov     rax, [rax+10h]
0x1800151fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015202  nop
0x180015203  jmp     loc_180015B4D
0x180015208  mov     rcx, [rsp+0F8h+var_C0]
0x18001520d  mov     rax, [rcx]
0x180015210  lea     r8, [rsp+0F8h+propvar]
0x180015218  lea     rdx, PKEY_Identity_UniqueID
0x18001521f  mov     rax, [rax+28h]
0x180015223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015228  mov     ebx, eax
0x18001522a  test    eax, eax
0x18001522c  jns     loc_1800152C6
0x180015232  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180015239  jz      short loc_18001525F
0x18001523b  lea     rax, aChrSppropstore_1; "CHR(spPropStore->GetValue(PKEY_Identity"...
0x180015242  mov     [rsp+0F8h+var_D0], rax
0x180015247  mov     dword ptr [rsp+0F8h+ppv], 0FCh
0x18001524f  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180015256  mov     r8d, ebx
0x180015259  call    McTemplateU0dsqs_EventWriteTransfer
0x18001525e  nop
0x18001525f  lea     rcx, [rsp+0F8h+var_50]
0x180015267  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001526c  nop
0x18001526d  mov     rcx, [rsp+0F8h+var_C0]
0x180015272  test    rcx, rcx
0x180015275  jz      short loc_180015289
0x180015277  mov     [rsp+0F8h+var_C0], rsi
0x18001527c  mov     rax, [rcx]
0x18001527f  mov     rax, [rax+10h]
0x180015283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015288  nop
0x180015289  mov     rcx, [rsp+0F8h+var_C8]
0x18001528e  test    rcx, rcx
0x180015291  jz      short loc_1800152A5
0x180015293  mov     [rsp+0F8h+var_C8], rsi
0x180015298  mov     rax, [rcx]
0x18001529b  mov     rax, [rax+10h]
0x18001529f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152a4  nop
0x1800152a5  mov     rcx, [rsp+0F8h+var_B8]
0x1800152aa  test    rcx, rcx
0x1800152ad  jz      short loc_1800152C1
0x1800152af  mov     [rsp+0F8h+var_B8], rsi
0x1800152b4  mov     rax, [rcx]
0x1800152b7  mov     rax, [rax+10h]
0x1800152bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152c0  nop
0x1800152c1  jmp     loc_180015B4D
0x1800152c6  mov     rcx, [rsp+0F8h+pv]; pv
0x1800152cb  test    rcx, rcx
0x1800152ce  jz      short loc_1800152D6
0x1800152d0  call    cs:__imp_CoTaskMemFree
0x1800152d6  lea     rdx, [rsp+0F8h+pv]; ppszOut
0x1800152db  lea     rcx, [rsp+0F8h+propvar]; propvar
0x1800152e3  call    cs:__imp_PropVariantToStringAlloc
0x1800152e9  mov     ebx, eax
0x1800152eb  test    eax, eax
0x1800152ed  jns     loc_180015387
0x1800152f3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800152fa  jz      short loc_180015320
0x1800152fc  lea     rax, aChrPropvariant_0; "CHR(PropVariantToStringAlloc(propertyVa"...
0x180015303  mov     [rsp+0F8h+var_D0], rax
0x180015308  mov     dword ptr [rsp+0F8h+ppv], 103h
0x180015310  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180015317  mov     r8d, ebx
0x18001531a  call    McTemplateU0dsqs_EventWriteTransfer
  ... truncated ...
```
