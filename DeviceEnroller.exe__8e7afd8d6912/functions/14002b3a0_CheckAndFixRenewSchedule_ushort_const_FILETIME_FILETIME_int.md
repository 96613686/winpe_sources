# CheckAndFixRenewSchedule(ushort const *,_FILETIME,_FILETIME,int *)

- ea: `0x14002b3a0`
- end: `0x14002c1aa`
- name: `?CheckAndFixRenewSchedule@@YAJPEBGU_FILETIME@@1PEAH@Z`
- size: `3594`
- prototype: `__int64 __fastcall(const unsigned __int16 *, FILETIME, FILETIME, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002c1b0`

## callees

- `0x1400042f0`
- `0x1400045a8`
- `0x140004e28`
- `0x14000715c`
- `0x1400095b4`
- `0x14000a0fc`
- `0x14001ea48`
- `0x14001ef20`
- `0x14001ef94`
- `0x14002b3a0`
- `0x140033088`
- `0x1400331a8`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bc8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bd93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002be6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bc8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bd93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002be6d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002baf4`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bbcf`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bca7`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bdac`
- `OLEAUT32!__imp_SysFreeString` at `0x14002be86`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c0ce`
- `OLEAUT32!__imp_SysFreeString` at `0x14002baf4`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bbcf`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bca7`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bdac`
- `OLEAUT32!__imp_SysFreeString` at `0x14002be86`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c0ce`
- `OLEAUT32!__imp_VariantInit` at `0x14002b470`
- `OLEAUT32!__imp_VariantInit` at `0x14002b485`
- `OLEAUT32!__imp_VariantInit` at `0x14002b49d`
- `OLEAUT32!__imp_VariantInit` at `0x14002b4b9`
- `OLEAUT32!__imp_VariantInit` at `0x14002b470`
- `OLEAUT32!__imp_VariantInit` at `0x14002b485`
- `OLEAUT32!__imp_VariantInit` at `0x14002b49d`
- `OLEAUT32!__imp_VariantInit` at `0x14002b4b9`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x14002bba8`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x14002bba8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14002bc80`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14002bc80`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002bd85`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002be5f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002bd85`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002be5f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14002bd4d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14002bd5f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14002bd4d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14002bd5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002b426`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002b426`

## string_xrefs

- `0x14002b666`: `Schedule created by enrollment client for renewal of certificate warning`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckAndFixRenewSchedule(const unsigned __int16 *a1, FILETIME a2, FILETIME a3, int *a4)
{
  HRESULT v6; // eax
  signed int v7; // ebx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v11; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v13; // xmm8
  IRecordInfo *v14; // xmm9_8
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  LPVOID v17; // rbx
  __int64 (__fastcall *v18)(LPVOID, _QWORD *, __int64 *); // rdi
  _QWORD *v19; // rdx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, _QWORD *, __int64 *); // rdi
  _QWORD *v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  signed int LastError; // eax
  signed int v29; // eax
  signed int v30; // eax
  signed int v31; // eax
  int v32; // esi
  int v33; // r14d
  int v34; // eax
  int v35; // ecx
  int ppv; // [rsp+28h] [rbp-E0h]
  int *ppva; // [rsp+28h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+28h] [rbp-E0h]
  LPVOID *ppvc; // [rsp+28h] [rbp-E0h]
  __int64 v40; // [rsp+30h] [rbp-D8h]
  __int64 v41; // [rsp+30h] [rbp-D8h]
  __int64 v42; // [rsp+38h] [rbp-D0h]
  __int64 v43; // [rsp+38h] [rbp-D0h]
  __int64 v44; // [rsp+40h] [rbp-C8h]
  __int64 v45; // [rsp+40h] [rbp-C8h]
  __int64 v46; // [rsp+48h] [rbp-C0h]
  __int64 v47; // [rsp+48h] [rbp-C0h]
  LPVOID v48; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v50; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-98h] BYREF
  __int64 v52; // [rsp+78h] [rbp-90h] BYREF
  __int64 v53; // [rsp+80h] [rbp-88h] BYREF
  void *Block[2]; // [rsp+88h] [rbp-80h] BYREF
  _WORD v55[8]; // [rsp+98h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp-60h] BYREF
  int v57; // [rsp+B0h] [rbp-58h] BYREF
  struct _FILETIME FileTime; // [rsp+B8h] [rbp-50h] BYREF
  DOUBLE vtime; // [rsp+C0h] [rbp-48h] BYREF
  FILETIME FileTime2; // [rsp+C8h] [rbp-40h] BYREF
  FILETIME v61; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v62; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-18h] BYREF
  int v64[4]; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v65; // [rsp+118h] [rbp+10h]
  __int128 v66; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v67; // [rsp+138h] [rbp+30h]
  __int128 v68; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v69; // [rsp+158h] [rbp+50h]
  VARIANTARG v70; // [rsp+168h] [rbp+60h] BYREF
  VARIANTARG v71; // [rsp+188h] [rbp+80h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1A0h] [rbp+98h] BYREF
  VARIANTARG v73; // [rsp+1B0h] [rbp+A8h] BYREF
  unsigned __int16 v74[264]; // [rsp+1C8h] [rbp+C0h] BYREF
  unsigned __int16 v75[264]; // [rsp+3D8h] [rbp+2D0h] BYREF
  unsigned __int16 v76[264]; // [rsp+5E8h] [rbp+4E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8A0h] [rbp+798h]

  FileTime2 = a2;
  v61 = a3;
  v48 = 0;
  v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v48);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1201,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v48);
    return (unsigned int)v7;
  }
  v9 = v48;
  v10 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v48 + 80LL);
  VariantInit(&pvarg);
  v11 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v62);
  v13 = *(_OWORD *)&v62.vt;
  v14 = v62.pRecInfo;
  VariantInit(&v71);
  v15 = *(_OWORD *)&v71.vt;
  v16 = v71.pRecInfo;
  VariantInit(&v73);
  *(_OWORD *)v64 = v11;
  v65 = pRecInfo;
  v66 = v13;
  v67 = v14;
  v68 = v15;
  v69 = v16;
  v70 = v73;
  ppva = v64;
  v7 = v10(v9, &v70, &v68, &v66);
  _variant_t::~_variant_t(&v73);
  _variant_t::~_variant_t(&v71);
  _variant_t::~_variant_t(&v62);
  _variant_t::~_variant_t(&pvarg);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1202,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v7,
      (int)v64);
    wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v48);
    return (unsigned int)v7;
  }
  v50 = 0;
  Block[0] = v55;
  Block[1] = v55;
  v55[0] = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
    Block,
    L"\\Microsoft\\Windows\\EnterpriseMgmt\\");
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(Block, a1);
  v17 = v48;
  v18 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *))(*(_QWORD *)v48 + 56LL);
  v19 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v71, (const unsigned __int16 *)Block[0]);
  if ( v19 )
    v19 = (_QWORD *)*v19;
  v7 = v18(v17, v19, &v50);
  _bstr_t::~_bstr_t((_bstr_t *)&v71);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1209,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v7,
      (int)v64);
    if ( Block[0] != v55 )
      operator delete(Block[0]);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
LABEL_163:
    wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v48);
    return (unsigned int)v7;
  }
  v49 = 0;
  v20 = v50;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v50 + 104LL);
  v22 = *(_QWORD **)_bstr_t::_bstr_t(
                      (_bstr_t *)&v71,
                      L"Schedule created by enrollment client for renewal of certificate warning");
  if ( v22 )
    v22 = (_QWORD *)*v22;
  v7 = v21(v20, v22, &v49);
  _bstr_t::~_bstr_t((_bstr_t *)&v71);
  v23 = v49;
  if ( v7 >= 0 )
  {
    v51 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 152LL))(v49, &v51);
    v7 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1219,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v24,
        (int)v64);
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      if ( Block[0] != v55 )
        operator delete(Block[0]);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_163;
    }
    v53 = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 72LL))(v51, &v53);
    v7 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1221,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v25,
        (int)v64);
      if ( v53 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      if ( Block[0] != v55 )
        operator delete(Block[0]);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_163;
    }
    v52 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53 + 64LL))(v53, 1, &v52);
    v7 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1226,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v26,
        (int)v64);
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      if ( v53 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      if ( Block[0] != v55 )
        operator delete(Block[0]);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_163;
    }
    v57 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 56LL))(v52, &v57);
    v7 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x122A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v27,
        (int)v64);
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      if ( v53 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      if ( Block[0] != v55 )
        operator delete(Block[0]);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_163;
    }
    bstrString = 0;
    if ( v57 == 1 )
      v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v52 + 112LL))(v52, &bstrString);
    vtime = 0.0;
    (*(void (__fastcall **)(__int64, DOUBLE *))(*(_QWORD *)v49 + 144LL))(v49, &vtime);
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1234,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v7,
        (int)v64);
      SysFreeString(bstrString);
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      if ( v53 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      if ( Block[0] != v55 )
        operator delete(Block[0]);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_163;
    }
    SystemTime = 0;
    if ( !VariantTimeToSystemTime(vtime, &SystemTime) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      SysFreeString(bstrString);
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      if ( v53 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      if ( Block[0] != v55 )
        operator delete(Block[0]);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_163;
    }
    FileTime = 0;
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      v29 = GetLastError();
      v7 = v29;
      if ( v29 > 0 )
        v7 = (unsigned __int16)v29 | 0x80070000;
      SysFreeString(bstrString);
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      if ( v53 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      if ( Block[0] != v55 )
        operator delete(Block[0]);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_163;
    }
    if ( CompareFileTime(&FileTime, &FileTime2) < 0 || CompareFileTime(&FileTime, &v61) > 0 )
    {
      *a4 = 1;
      *(_OWORD *)&v71.vt = 0;
      if ( !FileTimeToSystemTime(&FileTime2, (LPSYSTEMTIME)&v71) )
      {
        v30 = GetLastError();
        v7 = v30;
        if ( v30 > 0 )
          v7 = (unsigned __int16)v30 | 0x80070000;
        SysFreeString(bstrString);
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        if ( v53 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        if ( v49 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        if ( Block[0] != v55 )
          operator delete(Block[0]);
        if ( v50 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        goto LABEL_163;
      }
      *(_OWORD *)&v73.vt = 0;
      if ( !FileTimeToSystemTime(&v61, (LPSYSTEMTIME)&v73) )
      {
        v31 = GetLastError();
        v7 = v31;
        if ( v31 > 0 )
          v7 = (unsigned __int16)v31 | 0x80070000;
        SysFreeString(bstrString);
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        if ( v53 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        if ( v49 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        if ( Block[0] != v55 )
          operator delete(Block[0]);
        if ( v50 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        goto LABEL_163;
      }
      memset_0(v76, 0, 0x208u);
      memset_0(v75, 0, 0x208u);
      memset_0(v74, 0, 0x208u);
      LODWORD(ppva) = SystemTime.wMonth;
      v32 = StringCchPrintfW(
              v76,
              0x104u,
              L"%4d-%02d-%02dT%2d:%02d:%02d",
              SystemTime.wYear,
              ppva,
              SystemTime.wDay,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond);
      LODWORD(v46) = WORD2(v71.decVal.Lo64);
      LODWORD(v44) = WORD1(v71.decVal.Lo64);
      LODWORD(v42) = v71.uiVal;
      LODWORD(v40) = v71.wReserved3;
      LODWORD(ppvb) = v71.wReserved1;
      v33 = StringCchPrintfW(v75, 0x104u, L"%4d-%02d-%02dT%2d:%02d:%02d", v71.vt, ppvb, v40, v42, v44, v46);
      LODWORD(v47) = WORD2(v73.decVal.Lo64);
      LODWORD(v45) = WORD1(v73.decVal.Lo64);
      LODWORD(v43) = v73.uiVal;
      LODWORD(v41) = v73.wReserved3;
      LODWORD(ppvc) = v73.wReserved1;
      v34 = StringCchPrintfW(v74, 0x104u, L"%4d-%02d-%02dT%2d:%02d:%02d", v73.vt, ppvc, v41, v43, v45, v47);
      if ( v32 < 0 || v33 < 0 || v34 < 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          McTemplateU0zzz_EventWriteTransfer(
            v35,
            (unsigned int)EnterpriseDiagnosticsEnrollRenewScheduleIncorrect,
            (unsigned int)&SubKey,
            (unsigned int)&SubKey,
            (__int64)&SubKey);
      }
      else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        McTemplateU0zzz_EventWriteTransfer(
          v35,
          (unsigned int)EnterpriseDiagnosticsEnrollRenewScheduleIncorrect,
          (unsigned int)v76,
          (unsigned int)v75,
          (__int64)v74);
      }
    }
    SysFreeString(bstrString);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    if ( v49 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    if ( Block[0] != v55 )
      operator delete(Block[0]);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  else
  {
    if ( v7 != -2147024894 )
    {
      if ( v49 )
        (*(void (**)(void))(*(_QWORD *)v49 + 16LL))();
      if ( Block[0] != v55 )
        operator delete(Block[0]);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_163;
    }
    *a4 = 1;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( Block[0] != v55 )
      operator delete(Block[0]);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v48);
  return 0;
}

```

## disassembly

```asm
0x14002b3a0  mov     rax, rsp
0x14002b3a3  push    rbp
0x14002b3a4  push    rbx
0x14002b3a5  push    rsi
0x14002b3a6  push    rdi
0x14002b3a7  push    r14
0x14002b3a9  push    r15
0x14002b3ab  lea     rbp, [rax-798h]
0x14002b3b2  sub     rsp, 868h
0x14002b3b9  movaps  xmmword ptr [rax-48h], xmm6
0x14002b3bd  movaps  xmmword ptr [rax-58h], xmm7
0x14002b3c1  movaps  xmmword ptr [rax-68h], xmm8
0x14002b3c6  movaps  xmmword ptr [rax-78h], xmm9
0x14002b3cb  movaps  xmmword ptr [rax-88h], xmm10
0x14002b3d3  movaps  xmmword ptr [rax-98h], xmm11
0x14002b3db  mov     rax, cs:__security_cookie
0x14002b3e2  xor     rax, rsp
0x14002b3e5  mov     [rbp+790h+var_A0], rax
0x14002b3ec  mov     rsi, r9
0x14002b3ef  mov     r14, rcx
0x14002b3f2  mov     qword ptr [rbp+790h+FileTime2.dwLowDateTime], rdx
0x14002b3f6  mov     qword ptr [rbp+790h+var_7C8.dwLowDateTime], r8
0x14002b3fa  mov     [rsp+890h+var_840], 0
0x14002b403  lea     rax, [rsp+890h+var_840]
0x14002b408  mov     [rsp+890h+ppv], rax; int
0x14002b40d  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14002b414  mov     r15d, 1
0x14002b41a  mov     r8d, r15d; dwClsContext
0x14002b41d  xor     edx, edx; pUnkOuter
0x14002b41f  lea     rcx, CLSID_TaskScheduler; rclsid
0x14002b426  call    cs:__imp_CoCreateInstance
0x14002b42c  mov     ebx, eax
0x14002b42e  test    eax, eax
0x14002b430  jns     short loc_14002B460
0x14002b432  mov     rcx, [rbp+798h]; this
0x14002b439  mov     r9d, eax; char *
0x14002b43c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002b443  mov     edx, 1201h; void *
0x14002b448  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002b44d  nop
0x14002b44e  lea     rcx, [rsp+890h+var_840]
0x14002b453  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002b458  nop
0x14002b459  mov     eax, ebx
0x14002b45b  jmp     loc_14002C169
0x14002b460  mov     rdi, [rsp+890h+var_840]
0x14002b465  mov     rax, [rdi]
0x14002b468  mov     rbx, [rax+50h]
0x14002b46c  lea     rcx, [rbp+790h+pvarg]; pvarg
0x14002b470  call    cs:__imp_VariantInit
0x14002b476  movups  xmm10, xmmword ptr [rbp+790h+pvarg]
0x14002b47b  movsd   xmm11, qword ptr [rbp+790h+pvarg+10h]
0x14002b481  lea     rcx, [rbp+790h+var_7C0]; pvarg
0x14002b485  call    cs:__imp_VariantInit
0x14002b48b  movups  xmm8, xmmword ptr [rbp+790h+var_7C0]
0x14002b490  movsd   xmm9, qword ptr [rbp+790h+var_7C0+10h]
0x14002b496  lea     rcx, [rbp+790h+var_710]; pvarg
0x14002b49d  call    cs:__imp_VariantInit
0x14002b4a3  movups  xmm6, xmmword ptr [rbp+790h+var_710]
0x14002b4aa  movsd   xmm7, qword ptr [rbp+790h+var_710+10h]
0x14002b4b2  lea     rcx, [rbp+790h+var_6E8]; pvarg
0x14002b4b9  call    cs:__imp_VariantInit
0x14002b4bf  movups  xmm0, xmmword ptr [rbp+790h+var_6E8]
0x14002b4c6  movsd   xmm1, qword ptr [rbp+790h+var_6E8+10h]
0x14002b4ce  movaps  xmmword ptr [rbp+790h+var_790], xmm10
0x14002b4d3  movsd   [rbp+790h+var_780], xmm11
0x14002b4d9  movaps  [rbp+790h+var_770], xmm8
0x14002b4de  movsd   [rbp+790h+var_760], xmm9
0x14002b4e4  movaps  [rbp+790h+var_750], xmm6
0x14002b4e8  movsd   [rbp+790h+var_740], xmm7
0x14002b4ed  movaps  [rbp+790h+var_730], xmm0
0x14002b4f1  movsd   [rbp+790h+var_720], xmm1
0x14002b4f6  lea     rax, [rbp+790h+var_790]
0x14002b4fa  mov     [rsp+890h+ppv], rax; int
0x14002b4ff  lea     r9, [rbp+790h+var_770]
0x14002b503  lea     r8, [rbp+790h+var_750]
0x14002b507  lea     rdx, [rbp+790h+var_730]
0x14002b50b  mov     rcx, rdi
0x14002b50e  mov     rax, rbx
0x14002b511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b516  mov     ebx, eax
0x14002b518  lea     rcx, [rbp+790h+var_6E8]; this
0x14002b51f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14002b524  lea     rcx, [rbp+790h+var_710]; this
0x14002b52b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14002b530  lea     rcx, [rbp+790h+var_7C0]; this
0x14002b534  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14002b539  lea     rcx, [rbp+790h+pvarg]; this
0x14002b53d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14002b542  test    ebx, ebx
0x14002b544  jns     short loc_14002B572
0x14002b546  mov     rcx, [rbp+798h]; this
0x14002b54d  mov     r9d, ebx; char *
0x14002b550  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002b557  mov     edx, 1202h; void *
0x14002b55c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002b561  nop
0x14002b562  lea     rcx, [rsp+890h+var_840]
0x14002b567  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002b56c  nop
0x14002b56d  jmp     loc_14002B459
0x14002b572  mov     [rsp+890h+var_830], 0
0x14002b57b  lea     rax, [rbp+790h+var_800]
0x14002b57f  mov     [rbp+790h+Block], rax
0x14002b583  lea     rax, [rbp+790h+var_800]
0x14002b587  mov     [rbp+790h+var_808], rax
0x14002b58b  xor     eax, eax
0x14002b58d  mov     [rbp+790h+var_800], ax
0x14002b591  lea     rdx, aMicrosoftWindo_2; "\\Microsoft\\Windows\\EnterpriseMgmt\\"
0x14002b598  lea     rcx, [rbp+790h+Block]
0x14002b59c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002b5a1  mov     rdx, r14
0x14002b5a4  lea     rcx, [rbp+790h+Block]
0x14002b5a8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002b5ad  mov     rbx, [rsp+890h+var_840]
0x14002b5b2  mov     rax, [rbx]
0x14002b5b5  mov     rdi, [rax+38h]
0x14002b5b9  mov     rdx, [rbp+790h+Block]; unsigned __int16 *
0x14002b5bd  lea     rcx, [rbp+790h+var_710]; this
0x14002b5c4  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14002b5c9  mov     rdx, [rax]
0x14002b5cc  test    rdx, rdx
0x14002b5cf  jz      short loc_14002B5D4
0x14002b5d1  mov     rdx, [rdx]
0x14002b5d4  lea     r8, [rsp+890h+var_830]
0x14002b5d9  mov     rcx, rbx
0x14002b5dc  mov     rax, rdi
0x14002b5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b5e4  mov     ebx, eax
0x14002b5e6  lea     rcx, [rbp+790h+var_710]; this
0x14002b5ed  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002b5f2  test    ebx, ebx
0x14002b5f4  jns     short loc_14002B651
0x14002b5f6  mov     rcx, [rbp+798h]; this
0x14002b5fd  mov     r9d, ebx; char *
0x14002b600  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002b607  mov     edx, 1209h; void *
0x14002b60c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002b611  lea     rax, [rbp+790h+var_800]
0x14002b615  mov     rcx, [rbp+790h+Block]; Block
0x14002b619  cmp     rcx, rax
0x14002b61c  jz      short loc_14002B62A
0x14002b61e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14002b625  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002b62a  mov     rcx, [rsp+890h+var_830]
0x14002b62f  test    rcx, rcx
0x14002b632  jz      short loc_14002B641
0x14002b634  mov     rax, [rcx]
0x14002b637  mov     rax, [rax+10h]
0x14002b63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b640  nop
0x14002b641  lea     rcx, [rsp+890h+var_840]
0x14002b646  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002b64b  nop
0x14002b64c  jmp     loc_14002B459
0x14002b651  mov     [rsp+890h+var_838], 0
0x14002b65a  mov     rbx, [rsp+890h+var_830]
0x14002b65f  mov     rax, [rbx]
0x14002b662  mov     rdi, [rax+68h]
0x14002b666  lea     rdx, aScheduleCreate_0; "Schedule created by enrollment client f"...
0x14002b66d  lea     rcx, [rbp+790h+var_710]; this
0x14002b674  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14002b679  mov     rdx, [rax]
0x14002b67c  test    rdx, rdx
0x14002b67f  jz      short loc_14002B684
0x14002b681  mov     rdx, [rdx]
0x14002b684  lea     r8, [rsp+890h+var_838]
0x14002b689  mov     rcx, rbx
0x14002b68c  mov     rax, rdi
0x14002b68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b694  mov     ebx, eax
0x14002b696  lea     rcx, [rbp+790h+var_710]; this
0x14002b69d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002b6a2  mov     rcx, [rsp+890h+var_838]
0x14002b6a7  test    ebx, ebx
0x14002b6a9  jns     loc_14002B75C
0x14002b6af  cmp     ebx, 80070002h
0x14002b6b5  jnz     short loc_14002B70B
0x14002b6b7  mov     [rsi], r15d
0x14002b6ba  test    rcx, rcx
0x14002b6bd  jz      short loc_14002B6CB
0x14002b6bf  mov     rax, [rcx]
0x14002b6c2  mov     rax, [rax+10h]
0x14002b6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b6cb  lea     rax, [rbp+790h+var_800]
0x14002b6cf  mov     rcx, [rbp+790h+Block]; Block
0x14002b6d3  cmp     rcx, rax
0x14002b6d6  jz      short loc_14002B6E4
0x14002b6d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14002b6df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002b6e4  mov     rcx, [rsp+890h+var_830]
0x14002b6e9  test    rcx, rcx
0x14002b6ec  jz      short loc_14002B6FB
0x14002b6ee  mov     rax, [rcx]
0x14002b6f1  mov     rax, [rax+10h]
0x14002b6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b6fa  nop
0x14002b6fb  lea     rcx, [rsp+890h+var_840]
0x14002b700  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002b705  nop
0x14002b706  jmp     loc_14002C167
0x14002b70b  test    rcx, rcx
0x14002b70e  jz      short loc_14002B71C
0x14002b710  mov     rax, [rcx]
0x14002b713  mov     rax, [rax+10h]
0x14002b717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b71c  lea     rax, [rbp+790h+var_800]
0x14002b720  mov     rcx, [rbp+790h+Block]; Block
0x14002b724  cmp     rcx, rax
0x14002b727  jz      short loc_14002B735
0x14002b729  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14002b730  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002b735  mov     rcx, [rsp+890h+var_830]
0x14002b73a  test    rcx, rcx
0x14002b73d  jz      short loc_14002B74C
0x14002b73f  mov     rax, [rcx]
0x14002b742  mov     rax, [rax+10h]
0x14002b746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b74b  nop
0x14002b74c  lea     rcx, [rsp+890h+var_840]
0x14002b751  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002b756  nop
0x14002b757  jmp     loc_14002B459
0x14002b75c  mov     [rsp+890h+var_828], 0
0x14002b765  mov     rax, [rcx]
0x14002b768  lea     rdx, [rsp+890h+var_828]
0x14002b76d  mov     rax, [rax+98h]
0x14002b774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b779  mov     ebx, eax
0x14002b77b  test    eax, eax
0x14002b77d  jns     loc_14002B80A
0x14002b783  mov     rcx, [rbp+798h]; this
0x14002b78a  mov     r9d, eax; char *
0x14002b78d  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002b794  mov     edx, 1219h; void *
0x14002b799  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002b79e  mov     rcx, [rsp+890h+var_828]
0x14002b7a3  test    rcx, rcx
0x14002b7a6  jz      short loc_14002B7B4
0x14002b7a8  mov     rdx, [rcx]
0x14002b7ab  mov     rax, [rdx+10h]
0x14002b7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b7b4  mov     rcx, [rsp+890h+var_838]
0x14002b7b9  test    rcx, rcx
0x14002b7bc  jz      short loc_14002B7CA
0x14002b7be  mov     rax, [rcx]
0x14002b7c1  mov     rax, [rax+10h]
0x14002b7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b7ca  lea     rax, [rbp+790h+var_800]
0x14002b7ce  mov     rcx, [rbp+790h+Block]; Block
0x14002b7d2  cmp     rcx, rax
0x14002b7d5  jz      short loc_14002B7E3
0x14002b7d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14002b7de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002b7e3  mov     rcx, [rsp+890h+var_830]
0x14002b7e8  test    rcx, rcx
0x14002b7eb  jz      short loc_14002B7FA
0x14002b7ed  mov     rax, [rcx]
0x14002b7f0  mov     rax, [rax+10h]
0x14002b7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b7f9  nop
0x14002b7fa  lea     rcx, [rsp+890h+var_840]
0x14002b7ff  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002b804  nop
0x14002b805  jmp     loc_14002B459
0x14002b80a  mov     [rsp+890h+var_818], 0
0x14002b813  mov     rcx, [rsp+890h+var_828]
0x14002b818  mov     rax, [rcx]
0x14002b81b  lea     rdx, [rsp+890h+var_818]
0x14002b820  mov     rax, [rax+48h]
0x14002b824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b829  mov     ebx, eax
0x14002b82b  test    eax, eax
0x14002b82d  jns     loc_14002B8D0
0x14002b833  mov     rcx, [rbp+798h]; this
0x14002b83a  mov     r9d, eax; char *
0x14002b83d  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002b844  mov     edx, 1221h; void *
0x14002b849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002b84e  mov     rcx, [rsp+890h+var_818]
0x14002b853  test    rcx, rcx
0x14002b856  jz      short loc_14002B864
0x14002b858  mov     rdx, [rcx]
0x14002b85b  mov     rax, [rdx+10h]
0x14002b85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b864  mov     rcx, [rsp+890h+var_828]
0x14002b869  test    rcx, rcx
0x14002b86c  jz      short loc_14002B87A
0x14002b86e  mov     rax, [rcx]
0x14002b871  mov     rax, [rax+10h]
0x14002b875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b87a  mov     rcx, [rsp+890h+var_838]
0x14002b87f  test    rcx, rcx
0x14002b882  jz      short loc_14002B890
0x14002b884  mov     rax, [rcx]
0x14002b887  mov     rax, [rax+10h]
0x14002b88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b890  lea     rax, [rbp+790h+var_800]
0x14002b894  mov     rcx, [rbp+790h+Block]; Block
0x14002b898  cmp     rcx, rax
  ... truncated ...
```
