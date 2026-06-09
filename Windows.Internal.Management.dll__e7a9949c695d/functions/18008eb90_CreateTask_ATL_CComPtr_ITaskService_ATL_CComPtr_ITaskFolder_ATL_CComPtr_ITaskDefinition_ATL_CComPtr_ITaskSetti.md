# CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x18008eb90`
- end: `0x18008fd53`
- name: `?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `4547`
- prototype: ``
- caller_count: `6`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180090484`
- `0x180090a94`
- `0x180090edc`
- `0x180091418`
- `0x180091734`
- `0x180091d78`

## callees

- `0x1800051fc`
- `0x180022318`
- `0x18003a478`
- `0x18004b204`
- `0x18008e3fc`
- `0x18008e454`
- `0x18008e4c4`
- `0x18008e510`
- `0x18008e584`
- `0x18008e5b8`
- `0x18008e6ec`
- `0x18008e71c`
- `0x18008eb90`
- `0x1800927dc`
- `0x180092804`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ec9f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ecbb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ec9f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ecbb`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f132`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f325`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f132`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f325`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f010`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f0cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f1db`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f2b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f3cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f4f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f60e`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f6ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f766`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f912`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fb67`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fbfa`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f010`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f0cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f1db`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f2b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f3cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f4f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f60e`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f6ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f766`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f912`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fb67`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fbfa`
- `OLEAUT32!__imp_VariantInit` at `0x18008eeb5`
- `OLEAUT32!__imp_VariantInit` at `0x18008eed0`
- `OLEAUT32!__imp_VariantInit` at `0x18008eee8`
- `OLEAUT32!__imp_VariantInit` at `0x18008eefc`
- `OLEAUT32!__imp_VariantInit` at `0x18008eeb5`
- `OLEAUT32!__imp_VariantInit` at `0x18008eed0`
- `OLEAUT32!__imp_VariantInit` at `0x18008eee8`
- `OLEAUT32!__imp_VariantInit` at `0x18008eefc`
- `OLEAUT32!__imp_VariantClear` at `0x18008f11f`
- `OLEAUT32!__imp_VariantClear` at `0x18008f20d`
- `OLEAUT32!__imp_VariantClear` at `0x18008f312`
- `OLEAUT32!__imp_VariantClear` at `0x18008f401`
- `OLEAUT32!__imp_VariantClear` at `0x18008f11f`
- `OLEAUT32!__imp_VariantClear` at `0x18008f20d`
- `OLEAUT32!__imp_VariantClear` at `0x18008f312`
- `OLEAUT32!__imp_VariantClear` at `0x18008f401`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008ee89`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008ee89`

## string_xrefs

- `0x18008ee5d`: `22CoCreateTaskScheduler2`
- `0x18008ee41`: `CreateTask`

## pseudocode

```c
__int64 CreateTask(
        LPVOID *a1,
        struct IUnknown **a2,
        _QWORD *a3,
        _QWORD *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned int a9,
        int a10,
        int a11,
        int a12,
        ...)
{
  LPVOID *v12; // r15
  unsigned int v14; // r13d
  char *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  const WCHAR *v19; // r8
  unsigned int v20; // ebx
  LPVOID v21; // rdi
  __int64 (__fastcall *v22)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v23; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v25; // xmm8
  IRecordInfo *v26; // xmm9_8
  __int128 v27; // xmm6
  IRecordInfo *v28; // xmm7_8
  LPVOID v29; // rbx
  __int64 (__fastcall *v30)(LPVOID, __int64, __int64 **); // rdi
  _bstr_t *v31; // rax
  __int64 v32; // rdx
  int v33; // eax
  BSTR *v34; // rbx
  int v35; // edi
  BSTR v36; // rcx
  __int64 *v37; // rbx
  __int64 (__fastcall *v38)(__int64 *, __int64, VARIANTARG *); // rdi
  _bstr_t *v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  BSTR *v42; // rbx
  BSTR v43; // rcx
  __int64 *v44; // rdi
  OLECHAR *v45; // rbx
  __int64 v46; // r14
  __int128 v47; // xmm6
  __int64 v48; // xmm7_8
  _QWORD *v49; // rdx
  __int64 (__fastcall *v50)(__int64 *, _QWORD *, __int128 *, VARIANTARG *); // rax
  int v51; // eax
  BSTR *v52; // rbx
  BSTR v53; // rcx
  __int64 v54; // rbx
  __int64 (__fastcall *v55)(__int64, _QWORD *, struct IUnknown **); // r14
  _QWORD *v56; // rdx
  int v57; // eax
  BSTR *v58; // rbx
  BSTR v59; // rcx
  __int64 v60; // r14
  OLECHAR *v61; // rbx
  __int64 v62; // r15
  __int128 v63; // xmm6
  __int64 v64; // xmm7_8
  _bstr_t *v65; // rax
  __int64 v66; // rdx
  __int64 (__fastcall *v67)(__int64, __int64, __int128 *, struct IUnknown **); // rax
  int v68; // eax
  BSTR *v69; // rbx
  BSTR v70; // rcx
  __int64 v71; // rbx
  __int64 (__fastcall *v72)(__int64, __int64); // rdi
  _bstr_t *v73; // rax
  __int64 v74; // rdx
  int v75; // eax
  BSTR *v76; // rbx
  BSTR v77; // rcx
  __int64 v78; // rdi
  __int64 (__fastcall *v79)(__int64, __int128 *); // rbx
  _variant_t *v80; // rax
  __int64 v81; // xmm1_8
  const char *v82; // rdx
  __int64 *v83; // rbx
  __int64 v84; // rax
  __int64 (__fastcall *v85)(__int64 *, __int64); // rdi
  _bstr_t *v86; // rax
  __int64 v87; // rdx
  int v88; // eax
  BSTR *v89; // rbx
  BSTR v90; // rcx
  __int64 (__fastcall *v91)(__int64 *, __int64); // rdi
  _bstr_t *v92; // rax
  __int64 v93; // rdx
  int v94; // eax
  BSTR *v95; // rbx
  BSTR v96; // rcx
  __int64 (__fastcall *v97)(__int64 *, __int64); // rdi
  _bstr_t *v98; // rax
  __int64 v99; // rdx
  int v100; // eax
  BSTR *v101; // rbx
  BSTR v102; // rcx
  __int64 v103; // rbx
  __int64 (__fastcall *v104)(__int64, __int64); // rdi
  _bstr_t *v105; // rax
  __int64 v106; // rdx
  int v107; // eax
  BSTR *v108; // rbx
  BSTR v109; // rcx
  __int64 v110; // rbx
  __int64 (__fastcall *v111)(__int64, __int64); // rdi
  _bstr_t *v112; // rax
  __int64 v113; // rdx
  int v114; // eax
  BSTR *v115; // rbx
  BSTR v116; // rcx
  __int64 v117; // rbx
  __int64 (__fastcall *v118)(__int64, __int64); // rdi
  _bstr_t *v119; // rax
  __int64 v120; // rdx
  unsigned int v121; // eax
  BSTR *v122; // rbx
  unsigned int v123; // edi
  BSTR v124; // rcx
  void *Block[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v127[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v128; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v129; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v130; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v131; // [rsp+80h] [rbp-88h]
  __int64 v132; // [rsp+88h] [rbp-80h] BYREF
  int v133; // [rsp+90h] [rbp-78h]
  int v134; // [rsp+94h] [rbp-74h]
  __int64 v135; // [rsp+98h] [rbp-70h] BYREF
  __int64 v136; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v137; // [rsp+A8h] [rbp-60h] BYREF
  __int64 (__fastcall ***v138)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-58h] BYREF
  __int64 v139; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v140; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v141; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v142; // [rsp+E8h] [rbp-20h]
  OLECHAR *psz; // [rsp+F8h] [rbp-10h] BYREF
  OLECHAR *v144; // [rsp+100h] [rbp-8h]
  unsigned __int16 *v145; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 *v146; // [rsp+120h] [rbp+18h]
  unsigned __int16 *v147[4]; // [rsp+138h] [rbp+30h] BYREF
  __int128 v148; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v149; // [rsp+168h] [rbp+60h]
  VARIANTARG v150; // [rsp+178h] [rbp+70h] BYREF
  VARIANTARG pvarg; // [rsp+190h] [rbp+88h] BYREF
  __int128 v152; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v153; // [rsp+1B8h] [rbp+B0h]
  __int128 v154; // [rsp+1C8h] [rbp+C0h] BYREF
  IRecordInfo *v155; // [rsp+1D8h] [rbp+D0h]
  __int64 Data; // [rsp+2E8h] [rbp+1E0h] BYREF
  va_list Dataa; // [rsp+2E8h] [rbp+1E0h]
  va_list va1; // [rsp+2F0h] [rbp+1E8h] BYREF

  va_start(va1, a12);
  va_start(Dataa, a12);
  Data = va_arg(va1, _QWORD);
  v12 = a1;
  v137 = 0;
  *(_QWORD *)&v130.vt = 0;
  v128 = 0;
  v136 = 0;
  v129 = 0;
  v132 = 0;
  v139 = 0;
  v138 = 0;
  v135 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v145);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v147);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&psz);
  v14 = 0;
  if ( (_DWORD)Data != 1 )
  {
    LOBYTE(v14) = a10 != 1;
    ++v14;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v145,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;",
                           50)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;",
                           63) )
  {
    goto LABEL_220;
  }
  v134 = 0;
  if ( a8 && (unsigned int)_o__wcsicmp(a8, L"S-1-5-18") )
  {
    v133 = 0;
    if ( !(unsigned int)_o__wcsicmp(a8, L"S-1-5-32-545") )
    {
      v146 = v145;
      *v145 = 0;
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              &v145,
                              L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                              41) )
      {
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v147,
                                L"\\Microsoft\\Windows\\EnterpriseMgmt",
                                33) )
        {
          v144 = psz;
          *psz = 0;
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  &psz,
                                  L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
                                  34) )
          {
            v134 = 1;
            goto LABEL_22;
          }
        }
      }
LABEL_220:
      v20 = -2147024882;
      goto LABEL_221;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v145,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v145,
                             L")",
                             1)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v147,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v147,
                             L"\\EnterpriseMgmt",
                             15)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &psz,
                             a8) )
    {
      goto LABEL_220;
    }
    v17 = 1;
    v18 = L")";
  }
  else
  {
    v146 = v145;
    *v145 = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v145,
                             L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                             41)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v147,
                             L"\\Microsoft\\Windows\\EnterpriseMgmt",
                             33) )
    {
      goto LABEL_220;
    }
    v18 = L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)";
    v144 = psz;
    v17 = 34;
    v133 = 1;
    *psz = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           v18,
                           v17) )
    goto LABEL_220;
LABEL_22:
  LODWORD(Data) = CoCreateTaskScheduler(v16, v15, v12);
  v127[0] = "CreateTask";
  va_copy((va_list)&v127[1], Dataa);
  if ( (int)Data < 0 )
  {
    v19 = L"22CoCreateTaskScheduler2";
LABEL_24:
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, v19, 4u, Dataa, 4u);
    v20 = Data;
LABEL_25:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v127);
LABEL_221:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&psz);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v147);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v145);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v135);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v138);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v139);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v132);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v129);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v136);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v128);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v130);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v137);
    return v20;
  }
  v21 = *v12;
  v22 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*v12 + 80LL);
  VariantInit(&pvarg);
  v23 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v150);
  v25 = *(_OWORD *)&v150.vt;
  v26 = v150.pRecInfo;
  VariantInit(&v140);
  v27 = *(_OWORD *)&v140.vt;
  v28 = v140.pRecInfo;
  VariantInit((VARIANTARG *)&v130.decVal.8);
  v141 = *(_OWORD *)&v130.decVal.Lo32;
  v152 = v23;
  v153 = pRecInfo;
  v154 = v25;
  v155 = v26;
  v148 = v27;
  v149 = v28;
  v142 = v131;
  LODWORD(Data) = v22(v21, &v141, &v148, &v154, &v152);
  _variant_t::~_variant_t((_variant_t *)&v130.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v140);
  _variant_t::~_variant_t((_variant_t *)&v150);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( (int)Data < 0 )
  {
    v19 = L"23Connect";
    goto LABEL_24;
  }
  v29 = *v12;
  v30 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(*(_QWORD *)*v12 + 56LL);
  v31 = _bstr_t::_bstr_t((_bstr_t *)Block, L"\\");
  if ( *(_QWORD *)v31 )
    v32 = **(_QWORD **)v31;
  else
    v32 = 0;
  v33 = v30(v29, v32, &v137);
  v34 = (BSTR *)Block[0];
  v35 = v33;
  LODWORD(Data) = v33;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v34 )
    {
      if ( *v34 )
      {
        SysFreeString(*v34);
        *v34 = 0;
      }
      v36 = v34[1];
      if ( v36 )
      {
        operator delete(v36);
        v34[1] = 0;
      }
      operator delete(v34);
    }
    v35 = Data;
  }
  if ( v35 < 0 )
    goto LABEL_41;
  v37 = v137;
  *(_QWORD *)&v140.vt = "spRootFolder->GetFolder()";
  va_copy(v140.pcVal, Dataa);
  v38 = *(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(*v137 + 72);
  v39 = _bstr_t::_bstr_t((_bstr_t *)Block, v147[0]);
  if ( *(_QWORD *)v39 )
    v40 = **(_QWORD **)v39;
  else
    v40 = 0;
  v41 = v38(v37, v40, &v130);
  v42 = (BSTR *)Block[0];
  LODWORD(Data) = v41;
  if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v42 )
  {
    if ( *v42 )
    {
      SysFreeString(*v42);
      *v42 = 0;
    }
    v43 = v42[1];
    if ( v43 )
    {
      operator delete(v43);
      v42[1] = 0;
    }
    operator delete(v42);
  }
  if ( (unsigned int)(Data + 2147024894) <= 1 )
  {
    v44 = v137;
    v45 = psz;
    v46 = *v137;
    v130.iVal = 0;
    VariantClear((VARIANTARG *)&v130.decVal.8);
    v130.iVal = 8;
    v130.pRecInfo = (IRecordInfo *)SysAllocString(v45);
    if ( !v130.pRecInfo && v45 )
    {
      v130.iVal = 10;
      *((_DWORD *)&v130.decVal + 4) = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v47 = *(_OWORD *)&v130.decVal.Lo32;
    v48 = v131;
    v49 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)Block, v147[0]);
    if ( v49 )
      v49 = (_QWORD *)*v49;
    v50 = *(__int64 (__fastcall **)(__int64 *, _QWORD *, __int128 *, VARIANTARG *))(v46 + 88);
    v141 = v47;
    v142 = v48;
    v51 = v50(v44, v49, &v141, &v130);
    v52 = (BSTR *)Block[0];
    LODWORD(Data) = v51;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v52 )
      {
        if ( *v52 )
        {
          SysFreeString(*v52);
          *v52 = 0;
        }
        v53 = v52[1];
        if ( v53 )
        {
          operator delete(v53);
          v52[1] = 0;
        }
        operator delete(v52);
      }
      Block[0] = 0;
    }
    VariantClear((VARIANTARG *)&v130.decVal.8);
    v20 = Data;
    if ( (int)Data < 0 )
    {
LABEL_69:
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v140);
      goto LABEL_25;
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v140);
  if ( a5 )
  {
    v54 = *(_QWORD *)&v130.vt;
    *(_QWORD *)&v140.vt = "spEnterpriseMgmtFolder->GetFolder()";
    va_copy(v140.pcVal, Dataa);
    v55 = *(__int64 (__fastcall **)(__int64, _QWORD *, struct IUnknown **))(**(_QWORD **)&v130.vt + 72LL);
    v56 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)Block, a5);
    if ( v56 )
      v56 = (_QWORD *)*v56;
    v57 = v55(v54, v56, a2);
    v58 = (BSTR *)Block[0];
    LODWORD(Data) = v57;
    if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v58 )
    {
      if ( *v58 )
      {
        SysFreeString(*v58);
        *v58 = 0;
      }
      v59 = v58[1];
      if ( v59 )
      {
        operator delete(v59);
        v58[1] = 0;
      }
      operator delete(v58);
    }
    if ( (unsigned int)(Data + 2147024894) <= 1 )
    {
      v60 = *(_QWORD *)&v130.vt;
      v61 = psz;
      v62 = **(_QWORD **)&v130.vt;
      v130.iVal = 0;
      VariantClear((VARIANTARG *)&v130.decVal.8);
      v130.iVal = 8;
      v130.pRecInfo = (IRecordInfo *)SysAllocString(v61);
      if ( !v130.pRecInfo && v61 )
      {
        v130.iVal = 10;
        *((_DWORD *)&v130.decVal + 4) = -2147024882;
        ATL::AtlThrowImpl(-2147024882);
      }
      v63 = *(_OWORD *)&v130.decVal.Lo32;
      v64 = v131;
      v65 = _bstr_t::_bstr_t((_bstr_t *)Block, a5);
      if ( *(_QWORD *)v65 )
        v66 = **(_QWORD **)v65;
      else
        v66 = 0;
      v67 = *(__int64 (__fastcall **)(__int64, __int64, __int128 *, struct IUnknown **))(v62 + 88);
      v141 = v63;
      v142 = v64;
      v68 = v67(v60, v66, &v141, a2);
      v69 = (BSTR *)Block[0];
      LODWORD(Data) = v68;
      if ( Block[0] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v69 )
        {
          if ( *v69 )
          {
            SysFreeString(*v69);
            *v69 = 0;
          }
          v70 = v69[1];
          if ( v70 )
          {
            operator delete(v70);
            v69[1] = 0;
          }
          operator delete(v69);
        }
        Block[0] = 0;
      }
      VariantClear((VARIANTARG *)&v130.decVal.8);
      v20 = Data;
      if ( (int)Data < 0 )
        goto LABEL_69;
      v12 = a1;
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v140);
  }
  else if ( *a2 != *(struct IUnknown **)&v130.vt )
  {
    ATL::AtlComPtrAssign(a2, *(struct IUnknown **)&v130.vt);
  }
  LODWORD(Data) = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD *))(*(_QWORD *)*v12 + 72LL))(*v12, 0, a3);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 56LL))(*a3, &v136);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v71 = v136;
  v72 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v136 + 80LL);
  v73 = _bstr_t::_bstr_t((_bstr_t *)Block, L"Microsoft Corporation");
  if ( *(_QWORD *)v73 )
    v74 = **(_QWORD **)v73;
  else
    v74 = 0;
  v75 = v72(v71, v74);
  v76 = (BSTR *)Block[0];
  LODWORD(Data) = v75;
  v35 = v75;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v76 )
    {
      if ( *v76 )
      {
        SysFreeString(*v76);
        *v76 = 0;
      }
      v77 = v76[1];
      if ( v77 )
      {
        operator delete(v77);
        v76[1] = 0;
      }
      operator delete(v76);
    }
    v35 = Data;
  }
  if ( v35 < 0 )
    goto LABEL_41;
  v78 = v136;
  v79 = *(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v136 + 176LL);
  v80 = _variant_t::_variant_t((_variant_t *)&v148, v145);
  v81 = *((_QWORD *)v80 + 2);
  v141 = *(_OWORD *)v80;
  v142 = v81;
  LODWORD(Data) = v79(v78, &v141);
  _variant_t::~_variant_t((_variant_t *)&v148);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 120LL))(*a3, &v129);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v83 = v129;
  v84 = *v129;
  if ( v133 )
  {
    v85 = *(__int64 (__fastcall **)(__int64 *, __int64))(v84 + 128);
    v86 = _bstr_t::_bstr_t((_bstr_t *)Block, v82);
    if ( *(_QWORD *)v86 )
      v87 = **(_QWORD **)v86;
    else
      v87 = 0;
    v88 = v85(v83, v87);
    v89 = (BSTR *)Block[0];
    v35 = v88;
    LODWORD(Data) = v88;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v89 )
      {
        if ( *v89 )
        {
          SysFreeString(*v89);
          *v89 = 0;
        }
        v90 = v89[1];
        if ( v90 )
        {
          operator delete(v90);
          v89[1] = 0;
        }
        operator delete(v89);
      }
      v35 = Data;
    }
    if ( v35 < 0 )
      goto LABEL_41;
  }
  else if ( v134 )
  {
    v91 = *(__int64 (__fastcall **)(__int64 *, __int64))(v84 + 128);
    v92 = _bstr_t::_bstr_t((_bstr_t *)Block, L"S-1-5-32-545");
    if ( *(_QWORD *)v92 )
      v93 = **(_QWORD **)v92;
    else
      v93 = 0;
    v94 = v91(v83, v93);
    v95 = (BSTR *)Block[0];
    v35 = v94;
    LODWORD(Data) = v94;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v95 )
      {
        if ( *v95 )
        {
          SysFreeString(*v95);
          *v95 = 0;
        }
        v96 = v95[1];
        if ( v96 )
        {
          operator delete(v96);
          v95[1] = 0;
        }
        operator delete(v95);
      }
      v35 = Data;
    }
    if ( v35 < 0 )
      goto LABEL_41;
    LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v129 + 144))(v129, 1);
    v20 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
  }
  else
  {
    v97 = *(__int64 (__fastcall **)(__int64 *, __int64))(v84 + 96);
    v98 = _bstr_t::_bstr_t((_bstr_t *)Block, a8);
    if ( *(_QWORD *)v98 )
      v99 = **(_QWORD **)v98;
    else
      v99 = 0;
    v100 = v97(v83, v99);
    v101 = (BSTR *)Block[0];
    v35 = v100;
    LODWORD(Data) = v100;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v101 )
      {
        if ( *v101 )
        {
          SysFreeString(*v101);
          *v101 = 0;
        }
        v102 = v101[1];
        if ( v102 )
        {
          operator delete(v102);
          v101[1] = 0;
        }
        operator delete(v101);
      }
      v35 = Data;
    }
    if ( v35 < 0 )
      goto LABEL_41;
    LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v129 + 112))(v129, 3);
    v20 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
    LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v129 + 144))(v129, a9);
    v20 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
  }
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 88LL))(*a3, &v128);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 128LL))(v128, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 144LL))(v128, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 112LL))(v128, v14);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 352LL))(v128, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v103 = v128;
  v104 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v128 + 224LL);
  v105 = _bstr_t::_bstr_t((_bstr_t *)Block, L"PT1H");
  if ( *(_QWORD *)v105 )
    v106 = **(_QWORD **)v105;
  else
    v106 = 0;
  v107 = v104(v103, v106);
  v108 = (BSTR *)Block[0];
  v35 = v107;
  LODWORD(Data) = v107;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v108 )
    {
      if ( *v108 )
      {
        SysFreeString(*v108);
        *v108 = 0;
      }
      v109 = v108[1];
      if ( v109 )
      {
        operator delete(v109);
        v108[1] = 0;
      }
      operator delete(v108);
    }
    v35 = Data;
  }
  if ( v35 < 0 )
    goto LABEL_41;
  LODWORD(Data) = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v128)(
                    v128,
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    a4);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 176LL))(
                    *a4,
                    (unsigned __int16)((a11 != 1) - 1));
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 208LL))(
                    *a4,
                    (unsigned __int16)((a12 != 1) - 1));
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 400LL))(*a4, 0xFFFFFFFFLL);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v128 + 312LL))(v128, &v132);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v132 + 96LL))(v132, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v132 + 64LL))(v132, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v132 + 80LL))(v132, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 136LL))(*a3, &v139);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v139 + 96LL))(v139, 0, &v138);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (**v138)(v138, &IID_IExecAction, &v135);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v110 = v135;
  v111 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v135 + 88LL);
  v112 = _bstr_t::_bstr_t((_bstr_t *)Block, a6);
  if ( *(_QWORD *)v112 )
    v113 = **(_QWORD **)v112;
  else
    v113 = 0;
  v114 = v111(v110, v113);
  v115 = (BSTR *)Block[0];
  v35 = v114;
  LODWORD(Data) = v114;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v115 )
    {
      if ( *v115 )
      {
        SysFreeString(*v115);
        *v115 = 0;
      }
      v116 = v115[1];
      if ( v116 )
      {
        operator delete(v116);
        v115[1] = 0;
      }
      operator delete(v115);
    }
    v35 = Data;
  }
  if ( v35 < 0 )
  {
LABEL_41:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v127);
    v20 = v35;
    goto LABEL_221;
  }
  v117 = v135;
  v118 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v135 + 104LL);
  v119 = _bstr_t::_bstr_t((_bstr_t *)Block, a7);
  if ( *(_QWORD *)v119 )
    v120 = **(_QWORD **)v119;
  else
    v120 = 0;
  v121 = v118(v117, v120);
  v122 = (BSTR *)Block[0];
  v123 = v121;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v122 )
    {
      if ( *v122 )
      {
        SysFreeString(*v122);
        *v122 = 0;
      }
      v124 = v122[1];
      if ( v124 )
      {
        operator delete(v124);
        v122[1] = 0;
      }
      operator delete(v122);
    }
    Block[0] = 0;
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v127);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&psz);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v147);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v145);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v135);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v138);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v139);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v132);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v129);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v136);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v128);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v130);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v137);
  return v123;
}

```

## disassembly

```asm
0x18008eb90  mov     rax, rsp
0x18008eb93  mov     [rax+10h], rbx
0x18008eb97  mov     [rax+20h], r9
0x18008eb9b  mov     [rax+18h], r8
0x18008eb9f  mov     [rax+8], rcx
0x18008eba3  push    rbp
0x18008eba4  push    rsi
0x18008eba5  push    rdi
0x18008eba6  push    r12
0x18008eba8  push    r13
0x18008ebaa  push    r14
0x18008ebac  push    r15
0x18008ebae  lea     rbp, [rax-178h]
0x18008ebb5  sub     rsp, 240h
0x18008ebbc  xor     r14d, r14d
0x18008ebbf  movaps  xmmword ptr [rax-48h], xmm6
0x18008ebc3  movaps  xmmword ptr [rax-58h], xmm7
0x18008ebc7  mov     r15, rcx
0x18008ebca  movaps  xmmword ptr [rax-68h], xmm8
0x18008ebcf  lea     rcx, [rbp+170h+var_160]
0x18008ebd3  movaps  xmmword ptr [rax-78h], xmm9
0x18008ebd8  mov     r12, rdx
0x18008ebdb  movaps  xmmword ptr [rax-88h], xmm10
0x18008ebe3  movaps  xmmword ptr [rax-98h], xmm11
0x18008ebeb  mov     [rbp+170h+var_1D0], r14
0x18008ebef  mov     qword ptr [rsp+270h+var_210], r14
0x18008ebf4  mov     [rsp+270h+var_220], r14
0x18008ebf9  mov     [rbp+170h+var_1D8], r14
0x18008ebfd  mov     [rsp+270h+var_218], r14
0x18008ec02  mov     [rbp+170h+var_1F0], r14
0x18008ec06  mov     [rbp+170h+var_1C0], r14
0x18008ec0a  mov     [rbp+170h+var_1C8], r14
0x18008ec0e  mov     [rbp+170h+var_1E0], r14
0x18008ec12  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18008ec17  lea     rcx, [rbp+170h+var_140]
0x18008ec1b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18008ec20  lea     rcx, [rbp+170h+psz]
0x18008ec24  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18008ec29  lea     ebx, [r14+1]
0x18008ec2d  mov     r13d, r14d
0x18008ec30  cmp     dword ptr [rbp+170h+Data], ebx
0x18008ec36  jz      short loc_18008EC45
0x18008ec38  cmp     [rbp+170h+arg_48], ebx
0x18008ec3e  setnz   r13b
0x18008ec42  add     r13d, ebx
0x18008ec45  mov     r8d, 32h ; '2'
0x18008ec4b  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x18008ec52  lea     rcx, [rbp+170h+var_160]
0x18008ec56  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008ec5b  test    al, al
0x18008ec5d  jz      loc_18008FCA4
0x18008ec63  mov     r8d, 3Fh ; '?'
0x18008ec69  lea     rdx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x18008ec70  lea     rcx, [rbp+170h+psz]
0x18008ec74  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008ec79  test    al, al
0x18008ec7b  jz      loc_18008FCA4
0x18008ec81  mov     rsi, [rbp+170h+arg_38]
0x18008ec88  mov     [rbp+170h+var_1E4], r14d
0x18008ec8c  test    rsi, rsi
0x18008ec8f  jz      loc_18008EDBE
0x18008ec95  lea     rdx, aS1518; "S-1-5-18"
0x18008ec9c  mov     rcx, rsi
0x18008ec9f  call    cs:__imp__o__wcsicmp
0x18008eca5  test    eax, eax
0x18008eca7  jz      loc_18008EDBE
0x18008ecad  lea     rdx, aS1532545; "S-1-5-32-545"
0x18008ecb4  mov     [rbp+170h+var_1E8], r14d
0x18008ecb8  mov     rcx, rsi
0x18008ecbb  call    cs:__imp__o__wcsicmp
0x18008ecc1  test    eax, eax
0x18008ecc3  jnz     short loc_18008ED3D
0x18008ecc5  mov     rcx, [rbp+170h+var_160]
0x18008ecc9  lea     r8d, [rax+29h]
0x18008eccd  mov     [rbp+170h+var_158], rcx
0x18008ecd1  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x18008ecd8  mov     [rcx], r14w
0x18008ecdc  lea     rcx, [rbp+170h+var_160]
0x18008ece0  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008ece5  test    al, al
0x18008ece7  jz      loc_18008FCA4
0x18008eced  mov     r8d, 21h ; '!'
0x18008ecf3  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18008ecfa  lea     rcx, [rbp+170h+var_140]
0x18008ecfe  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008ed03  test    al, al
0x18008ed05  jz      loc_18008FCA4
0x18008ed0b  mov     rcx, [rbp+170h+psz]
0x18008ed0f  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x18008ed16  mov     [rbp+170h+var_178], rcx
0x18008ed1a  mov     r8d, 22h ; '"'
0x18008ed20  mov     [rcx], r14w
0x18008ed24  lea     rcx, [rbp+170h+psz]
0x18008ed28  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008ed2d  test    al, al
0x18008ed2f  jz      loc_18008FCA4
0x18008ed35  mov     [rbp+170h+var_1E4], ebx
0x18008ed38  jmp     loc_18008EE33
0x18008ed3d  mov     rdx, rsi
0x18008ed40  lea     rcx, [rbp+170h+var_160]
0x18008ed44  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18008ed49  test    al, al
0x18008ed4b  jz      loc_18008FCA4
0x18008ed51  mov     r8, rbx
0x18008ed54  lea     rdx, asc_1800DF1A4; ")"
0x18008ed5b  lea     rcx, [rbp+170h+var_160]
0x18008ed5f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008ed64  test    al, al
0x18008ed66  jz      loc_18008FCA4
0x18008ed6c  mov     rdx, rsi
0x18008ed6f  lea     rcx, [rbp+170h+var_140]
0x18008ed73  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18008ed78  test    al, al
0x18008ed7a  jz      loc_18008FCA4
0x18008ed80  mov     r8d, 0Fh
0x18008ed86  lea     rdx, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x18008ed8d  lea     rcx, [rbp+170h+var_140]
0x18008ed91  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008ed96  test    al, al
0x18008ed98  jz      loc_18008FCA4
0x18008ed9e  mov     rdx, rsi
0x18008eda1  lea     rcx, [rbp+170h+psz]
0x18008eda5  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18008edaa  test    al, al
0x18008edac  jz      loc_18008FCA4
0x18008edb2  mov     r8, rbx
0x18008edb5  lea     rdx, asc_1800DF1A4; ")"
0x18008edbc  jmp     short loc_18008EE22
0x18008edbe  mov     rcx, [rbp+170h+var_160]
0x18008edc2  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x18008edc9  mov     [rbp+170h+var_158], rcx
0x18008edcd  mov     r8d, 29h ; ')'
0x18008edd3  mov     [rcx], r14w
0x18008edd7  lea     rcx, [rbp+170h+var_160]
0x18008eddb  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008ede0  test    al, al
0x18008ede2  jz      loc_18008FCA4
0x18008ede8  mov     r8d, 21h ; '!'
0x18008edee  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18008edf5  lea     rcx, [rbp+170h+var_140]
0x18008edf9  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008edfe  test    al, al
0x18008ee00  jz      loc_18008FCA4
0x18008ee06  mov     rcx, [rbp+170h+psz]
0x18008ee0a  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x18008ee11  mov     [rbp+170h+var_178], rcx
0x18008ee15  mov     r8d, 22h ; '"'
0x18008ee1b  mov     [rbp+170h+var_1E8], ebx
0x18008ee1e  mov     [rcx], r14w
0x18008ee22  lea     rcx, [rbp+170h+psz]
0x18008ee26  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008ee2b  test    al, al
0x18008ee2d  jz      loc_18008FCA4
0x18008ee33  mov     r8, r15
0x18008ee36  call    CoCreateTaskScheduler
0x18008ee3b  mov     dword ptr [rbp+170h+Data], eax
0x18008ee41  lea     rcx, aCreatetask; "CreateTask"
0x18008ee48  mov     [rsp+270h+var_230], rcx
0x18008ee4d  lea     rcx, [rbp+170h+Data]
0x18008ee54  mov     [rsp+270h+var_228], rcx
0x18008ee59  test    eax, eax
0x18008ee5b  jns     short loc_18008EEA4
0x18008ee5d  lea     r8, a22cocreatetask; "22CoCreateTaskScheduler2"
0x18008ee64  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18008ee6b  lea     rax, [rbp+170h+Data]
0x18008ee72  mov     r9d, 4; dwType
0x18008ee78  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008ee7f  mov     [rsp+270h+cbData], r9d; cbData
0x18008ee84  mov     [rsp+270h+lpData], rax; lpData
0x18008ee89  call    cs:__imp_RegSetKeyValueW
0x18008ee8f  mov     ebx, dword ptr [rbp+170h+Data]
0x18008ee95  lea     rcx, [rsp+270h+var_230]; this
0x18008ee9a  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18008ee9f  jmp     loc_18008FCA9
0x18008eea4  mov     rdi, [r15]
0x18008eea7  lea     rcx, [rbp+170h+pvarg]; pvarg
0x18008eeae  mov     rax, [rdi]
0x18008eeb1  mov     rbx, [rax+50h]
0x18008eeb5  call    cs:__imp_VariantInit
0x18008eebb  movups  xmm10, xmmword ptr [rbp+170h+pvarg]
0x18008eec3  lea     rcx, [rbp+170h+var_100]; pvarg
0x18008eec7  movsd   xmm11, qword ptr [rbp+170h+pvarg+10h]
0x18008eed0  call    cs:__imp_VariantInit
0x18008eed6  movups  xmm8, xmmword ptr [rbp+170h+var_100]
0x18008eedb  lea     rcx, [rbp+170h+var_1B8]; pvarg
0x18008eedf  movsd   xmm9, qword ptr [rbp+170h+var_100+10h]
0x18008eee8  call    cs:__imp_VariantInit
0x18008eeee  movups  xmm6, xmmword ptr [rbp+170h+var_1B8]
0x18008eef2  lea     rcx, [rsp+270h+var_210+8]; pvarg
0x18008eef7  movsd   xmm7, qword ptr [rbp+170h+var_1B8+10h]
0x18008eefc  call    cs:__imp_VariantInit
0x18008ef02  movups  xmm0, xmmword ptr [rsp+270h+var_210+8]
0x18008ef07  lea     rax, [rbp+170h+var_D0]
0x18008ef0e  mov     rcx, rdi
0x18008ef11  movsd   xmm1, [rsp+270h+var_1F8]
0x18008ef17  lea     r9, [rbp+170h+var_B0]
0x18008ef1e  mov     [rsp+270h+lpData], rax
0x18008ef23  lea     r8, [rbp+170h+var_120]
0x18008ef27  mov     rax, rbx
0x18008ef2a  movaps  [rbp+170h+var_1A0], xmm0
0x18008ef2e  lea     rdx, [rbp+170h+var_1A0]
0x18008ef32  movaps  [rbp+170h+var_D0], xmm10
0x18008ef3a  movsd   [rbp+170h+var_C0], xmm11
0x18008ef43  movaps  [rbp+170h+var_B0], xmm8
0x18008ef4b  movsd   [rbp+170h+var_A0], xmm9
0x18008ef54  movaps  [rbp+170h+var_120], xmm6
0x18008ef58  movsd   [rbp+170h+var_110], xmm7
0x18008ef5d  movsd   [rbp+170h+var_190], xmm1
0x18008ef62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef67  lea     rcx, [rsp+270h+var_210+8]; this
0x18008ef6c  mov     dword ptr [rbp+170h+Data], eax
0x18008ef72  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18008ef77  lea     rcx, [rbp+170h+var_1B8]; this
0x18008ef7b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18008ef80  lea     rcx, [rbp+170h+var_100]; this
0x18008ef84  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18008ef89  lea     rcx, [rbp+170h+pvarg]; this
0x18008ef90  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18008ef95  cmp     dword ptr [rbp+170h+Data], r14d
0x18008ef9c  jge     short loc_18008EFAA
0x18008ef9e  lea     r8, a23connect; "23Connect"
0x18008efa5  jmp     loc_18008EE64
0x18008efaa  mov     rbx, [r15]
0x18008efad  lea     rdx, asc_1800D9938; "\\"
0x18008efb4  lea     rcx, [rsp+270h+Block]; this
0x18008efb9  mov     rax, [rbx]
0x18008efbc  mov     rdi, [rax+38h]
0x18008efc0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18008efc5  mov     rcx, [rax]
0x18008efc8  test    rcx, rcx
0x18008efcb  jz      short loc_18008EFD2
0x18008efcd  mov     rdx, [rcx]
0x18008efd0  jmp     short loc_18008EFD5
0x18008efd2  mov     rdx, r14
0x18008efd5  lea     r8, [rbp+170h+var_1D0]
0x18008efd9  mov     rcx, rbx
0x18008efdc  mov     rax, rdi
0x18008efdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008efe4  mov     rbx, [rsp+270h+Block]
0x18008efe9  mov     edi, eax
0x18008efeb  mov     dword ptr [rbp+170h+Data], eax
0x18008eff1  test    rbx, rbx
0x18008eff4  jz      short loc_18008F03E
0x18008eff6  or      eax, 0FFFFFFFFh
0x18008eff9  lock xadd [rbx+10h], eax
0x18008effe  cmp     eax, 1
0x18008f001  jnz     short loc_18008F038
0x18008f003  test    rbx, rbx
0x18008f006  jz      short loc_18008F038
0x18008f008  mov     rcx, [rbx]; bstrString
0x18008f00b  test    rcx, rcx
0x18008f00e  jz      short loc_18008F019
0x18008f010  call    cs:__imp_SysFreeString
0x18008f016  mov     [rbx], r14
0x18008f019  mov     rcx, [rbx+8]; Block
0x18008f01d  test    rcx, rcx
0x18008f020  jz      short loc_18008F02B
0x18008f022  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008f027  mov     [rbx+8], r14
0x18008f02b  mov     edx, 18h
0x18008f030  mov     rcx, rbx; Block
0x18008f033  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008f038  mov     edi, dword ptr [rbp+170h+Data]
0x18008f03e  test    edi, edi
0x18008f040  jns     short loc_18008F053
0x18008f042  lea     rcx, [rsp+270h+var_230]; this
0x18008f047  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18008f04c  mov     ebx, edi
0x18008f04e  jmp     loc_18008FCA9
0x18008f053  mov     rbx, [rbp+170h+var_1D0]
0x18008f057  lea     rax, aSprootfolderGe; "spRootFolder->GetFolder()"
0x18008f05e  mov     rdx, [rbp+170h+var_140]; unsigned __int16 *
0x18008f062  lea     rcx, [rsp+270h+Block]; this
0x18008f067  mov     qword ptr [rbp+170h+var_1B8], rax
0x18008f06b  lea     rax, [rbp+170h+Data]
0x18008f072  mov     qword ptr [rbp+170h+var_1B8+8], rax
0x18008f076  mov     rax, [rbx]
0x18008f079  mov     rdi, [rax+48h]
0x18008f07d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18008f082  mov     rdx, [rax]
0x18008f085  test    rdx, rdx
0x18008f088  jz      short loc_18008F08F
0x18008f08a  mov     rdx, [rdx]
0x18008f08d  jmp     short loc_18008F092
0x18008f08f  mov     rdx, r14
0x18008f092  lea     r8, [rsp+270h+var_210]
0x18008f097  mov     rcx, rbx
0x18008f09a  mov     rax, rdi
0x18008f09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f0a2  mov     rbx, [rsp+270h+Block]
0x18008f0a7  mov     dword ptr [rbp+170h+Data], eax
0x18008f0ad  test    rbx, rbx
0x18008f0b0  jz      short loc_18008F0F4
0x18008f0b2  or      eax, 0FFFFFFFFh
0x18008f0b5  lock xadd [rbx+10h], eax
0x18008f0ba  cmp     eax, 1
0x18008f0bd  jnz     short loc_18008F0F4
0x18008f0bf  test    rbx, rbx
0x18008f0c2  jz      short loc_18008F0F4
0x18008f0c4  mov     rcx, [rbx]; bstrString
  ... truncated ...
```
