# CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x180091100`
- end: `0x18009235a`
- name: `?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `4698`
- prototype: ``
- caller_count: `6`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180092abc`
- `0x180093114`
- `0x180093578`
- `0x180093ae4`
- `0x180093e18`
- `0x180094494`

## callees

- `0x18000535c`
- `0x180020954`
- `0x180039784`
- `0x18004b414`
- `0x18009090c`
- `0x180090968`
- `0x1800909e0`
- `0x180090a34`
- `0x180090ab0`
- `0x180090ae4`
- `0x180090c2c`
- `0x180090c64`
- `0x180091100`
- `0x180094f3c`
- `0x180094f64`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009120f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180091231`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009120f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180091231`
- `OLEAUT32!__imp_SysAllocString` at `0x1800916de`
- `OLEAUT32!__imp_SysAllocString` at `0x1800918ef`
- `OLEAUT32!__imp_SysAllocString` at `0x1800916de`
- `OLEAUT32!__imp_SysAllocString` at `0x1800918ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800915aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18009166c`
- `OLEAUT32!__imp_SysFreeString` at `0x18009178d`
- `OLEAUT32!__imp_SysFreeString` at `0x180091874`
- `OLEAUT32!__imp_SysFreeString` at `0x18009199f`
- `OLEAUT32!__imp_SysFreeString` at `0x180091ace`
- `OLEAUT32!__imp_SysFreeString` at `0x180091bf0`
- `OLEAUT32!__imp_SysFreeString` at `0x180091c95`
- `OLEAUT32!__imp_SysFreeString` at `0x180091d54`
- `OLEAUT32!__imp_SysFreeString` at `0x180091f06`
- `OLEAUT32!__imp_SysFreeString` at `0x180092161`
- `OLEAUT32!__imp_SysFreeString` at `0x1800921fa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800915aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18009166c`
- `OLEAUT32!__imp_SysFreeString` at `0x18009178d`
- `OLEAUT32!__imp_SysFreeString` at `0x180091874`
- `OLEAUT32!__imp_SysFreeString` at `0x18009199f`
- `OLEAUT32!__imp_SysFreeString` at `0x180091ace`
- `OLEAUT32!__imp_SysFreeString` at `0x180091bf0`
- `OLEAUT32!__imp_SysFreeString` at `0x180091c95`
- `OLEAUT32!__imp_SysFreeString` at `0x180091d54`
- `OLEAUT32!__imp_SysFreeString` at `0x180091f06`
- `OLEAUT32!__imp_SysFreeString` at `0x180092161`
- `OLEAUT32!__imp_SysFreeString` at `0x1800921fa`
- `OLEAUT32!__imp_VariantInit` at `0x180091437`
- `OLEAUT32!__imp_VariantInit` at `0x180091458`
- `OLEAUT32!__imp_VariantInit` at `0x180091476`
- `OLEAUT32!__imp_VariantInit` at `0x180091490`
- `OLEAUT32!__imp_VariantInit` at `0x180091437`
- `OLEAUT32!__imp_VariantInit` at `0x180091458`
- `OLEAUT32!__imp_VariantInit` at `0x180091476`
- `OLEAUT32!__imp_VariantInit` at `0x180091490`
- `OLEAUT32!__imp_VariantClear` at `0x1800916c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800917c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800918d6`
- `OLEAUT32!__imp_VariantClear` at `0x1800919d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800916c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800917c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800918d6`
- `OLEAUT32!__imp_VariantClear` at `0x1800919d7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180091405`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180091405`

## string_xrefs

- `0x1800913d9`: `22CoCreateTaskScheduler2`
- `0x1800913bd`: `CreateTask`

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
      __debugbreak();
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
        __debugbreak();
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
0x180091100  mov     rax, rsp
0x180091103  mov     [rax+10h], rbx
0x180091107  mov     [rax+20h], r9
0x18009110b  mov     [rax+18h], r8
0x18009110f  mov     [rax+8], rcx
0x180091113  push    rbp
0x180091114  push    rsi
0x180091115  push    rdi
0x180091116  push    r12
0x180091118  push    r13
0x18009111a  push    r14
0x18009111c  push    r15
0x18009111e  lea     rbp, [rax-178h]
0x180091125  sub     rsp, 240h
0x18009112c  xor     r14d, r14d
0x18009112f  movaps  xmmword ptr [rax-48h], xmm6
0x180091133  movaps  xmmword ptr [rax-58h], xmm7
0x180091137  mov     r15, rcx
0x18009113a  movaps  xmmword ptr [rax-68h], xmm8
0x18009113f  lea     rcx, [rbp+170h+var_160]
0x180091143  movaps  xmmword ptr [rax-78h], xmm9
0x180091148  mov     r12, rdx
0x18009114b  movaps  xmmword ptr [rax-88h], xmm10
0x180091153  movaps  xmmword ptr [rax-98h], xmm11
0x18009115b  mov     [rbp+170h+var_1D0], r14
0x18009115f  mov     qword ptr [rsp+270h+var_210], r14
0x180091164  mov     [rsp+270h+var_220], r14
0x180091169  mov     [rbp+170h+var_1D8], r14
0x18009116d  mov     [rsp+270h+var_218], r14
0x180091172  mov     [rbp+170h+var_1F0], r14
0x180091176  mov     [rbp+170h+var_1C0], r14
0x18009117a  mov     [rbp+170h+var_1C8], r14
0x18009117e  mov     [rbp+170h+var_1E0], r14
0x180091182  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180091187  lea     rcx, [rbp+170h+var_140]
0x18009118b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180091190  lea     rcx, [rbp+170h+psz]
0x180091194  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180091199  lea     ebx, [r14+1]
0x18009119d  mov     r13d, r14d
0x1800911a0  cmp     dword ptr [rbp+170h+Data], ebx
0x1800911a6  jz      short loc_1800911B5
0x1800911a8  cmp     [rbp+170h+arg_48], ebx
0x1800911ae  setnz   r13b
0x1800911b2  add     r13d, ebx
0x1800911b5  mov     r8d, 32h ; '2'
0x1800911bb  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1800911c2  lea     rcx, [rbp+170h+var_160]
0x1800911c6  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800911cb  test    al, al
0x1800911cd  jz      loc_1800922AA
0x1800911d3  mov     r8d, 3Fh ; '?'
0x1800911d9  lea     rdx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x1800911e0  lea     rcx, [rbp+170h+psz]
0x1800911e4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800911e9  test    al, al
0x1800911eb  jz      loc_1800922AA
0x1800911f1  mov     rsi, [rbp+170h+arg_38]
0x1800911f8  mov     [rbp+170h+var_1E4], r14d
0x1800911fc  test    rsi, rsi
0x1800911ff  jz      loc_18009133A
0x180091205  lea     rdx, aS1518; "S-1-5-18"
0x18009120c  mov     rcx, rsi
0x18009120f  call    cs:__imp__o__wcsicmp
0x180091216  nop     dword ptr [rax+rax+00h]
0x18009121b  test    eax, eax
0x18009121d  jz      loc_18009133A
0x180091223  lea     rdx, aS1532545; "S-1-5-32-545"
0x18009122a  mov     [rbp+170h+var_1E8], r14d
0x18009122e  mov     rcx, rsi
0x180091231  call    cs:__imp__o__wcsicmp
0x180091238  nop     dword ptr [rax+rax+00h]
0x18009123d  test    eax, eax
0x18009123f  jnz     short loc_1800912B9
0x180091241  mov     rcx, [rbp+170h+var_160]
0x180091245  lea     r8d, [rax+29h]
0x180091249  mov     [rbp+170h+var_158], rcx
0x18009124d  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x180091254  mov     [rcx], r14w
0x180091258  lea     rcx, [rbp+170h+var_160]
0x18009125c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180091261  test    al, al
0x180091263  jz      loc_1800922AA
0x180091269  mov     r8d, 21h ; '!'
0x18009126f  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180091276  lea     rcx, [rbp+170h+var_140]
0x18009127a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18009127f  test    al, al
0x180091281  jz      loc_1800922AA
0x180091287  mov     rcx, [rbp+170h+psz]
0x18009128b  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x180091292  mov     [rbp+170h+var_178], rcx
0x180091296  mov     r8d, 22h ; '"'
0x18009129c  mov     [rcx], r14w
0x1800912a0  lea     rcx, [rbp+170h+psz]
0x1800912a4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800912a9  test    al, al
0x1800912ab  jz      loc_1800922AA
0x1800912b1  mov     [rbp+170h+var_1E4], ebx
0x1800912b4  jmp     loc_1800913AF
0x1800912b9  mov     rdx, rsi
0x1800912bc  lea     rcx, [rbp+170h+var_160]
0x1800912c0  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800912c5  test    al, al
0x1800912c7  jz      loc_1800922AA
0x1800912cd  mov     r8, rbx
0x1800912d0  lea     rdx, asc_1800E3124; ")"
0x1800912d7  lea     rcx, [rbp+170h+var_160]
0x1800912db  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800912e0  test    al, al
0x1800912e2  jz      loc_1800922AA
0x1800912e8  mov     rdx, rsi
0x1800912eb  lea     rcx, [rbp+170h+var_140]
0x1800912ef  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800912f4  test    al, al
0x1800912f6  jz      loc_1800922AA
0x1800912fc  mov     r8d, 0Fh
0x180091302  lea     rdx, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x180091309  lea     rcx, [rbp+170h+var_140]
0x18009130d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180091312  test    al, al
0x180091314  jz      loc_1800922AA
0x18009131a  mov     rdx, rsi
0x18009131d  lea     rcx, [rbp+170h+psz]
0x180091321  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180091326  test    al, al
0x180091328  jz      loc_1800922AA
0x18009132e  mov     r8, rbx
0x180091331  lea     rdx, asc_1800E3124; ")"
0x180091338  jmp     short loc_18009139E
0x18009133a  mov     rcx, [rbp+170h+var_160]
0x18009133e  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x180091345  mov     [rbp+170h+var_158], rcx
0x180091349  mov     r8d, 29h ; ')'
0x18009134f  mov     [rcx], r14w
0x180091353  lea     rcx, [rbp+170h+var_160]
0x180091357  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18009135c  test    al, al
0x18009135e  jz      loc_1800922AA
0x180091364  mov     r8d, 21h ; '!'
0x18009136a  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180091371  lea     rcx, [rbp+170h+var_140]
0x180091375  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18009137a  test    al, al
0x18009137c  jz      loc_1800922AA
0x180091382  mov     rcx, [rbp+170h+psz]
0x180091386  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x18009138d  mov     [rbp+170h+var_178], rcx
0x180091391  mov     r8d, 22h ; '"'
0x180091397  mov     [rbp+170h+var_1E8], ebx
0x18009139a  mov     [rcx], r14w
0x18009139e  lea     rcx, [rbp+170h+psz]
0x1800913a2  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800913a7  test    al, al
0x1800913a9  jz      loc_1800922AA
0x1800913af  mov     r8, r15
0x1800913b2  call    CoCreateTaskScheduler
0x1800913b7  mov     dword ptr [rbp+170h+Data], eax
0x1800913bd  lea     rcx, aCreatetask; "CreateTask"
0x1800913c4  mov     [rsp+270h+var_230], rcx
0x1800913c9  lea     rcx, [rbp+170h+Data]
0x1800913d0  mov     [rsp+270h+var_228], rcx
0x1800913d5  test    eax, eax
0x1800913d7  jns     short loc_180091426
0x1800913d9  lea     r8, a22cocreatetask; "22CoCreateTaskScheduler2"
0x1800913e0  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800913e7  lea     rax, [rbp+170h+Data]
0x1800913ee  mov     r9d, 4; dwType
0x1800913f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800913fb  mov     [rsp+270h+cbData], r9d; cbData
0x180091400  mov     [rsp+270h+lpData], rax; lpData
0x180091405  call    cs:__imp_RegSetKeyValueW
0x18009140c  nop     dword ptr [rax+rax+00h]
0x180091411  mov     ebx, dword ptr [rbp+170h+Data]
0x180091417  lea     rcx, [rsp+270h+var_230]; this
0x18009141c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180091421  jmp     loc_1800922AF
0x180091426  mov     rdi, [r15]
0x180091429  lea     rcx, [rbp+170h+pvarg]; pvarg
0x180091430  mov     rax, [rdi]
0x180091433  mov     rbx, [rax+50h]
0x180091437  call    cs:__imp_VariantInit
0x18009143e  nop     dword ptr [rax+rax+00h]
0x180091443  movups  xmm10, xmmword ptr [rbp+170h+pvarg]
0x18009144b  lea     rcx, [rbp+170h+var_100]; pvarg
0x18009144f  movsd   xmm11, qword ptr [rbp+170h+pvarg+10h]
0x180091458  call    cs:__imp_VariantInit
0x18009145f  nop     dword ptr [rax+rax+00h]
0x180091464  movups  xmm8, xmmword ptr [rbp+170h+var_100]
0x180091469  lea     rcx, [rbp+170h+var_1B8]; pvarg
0x18009146d  movsd   xmm9, qword ptr [rbp+170h+var_100+10h]
0x180091476  call    cs:__imp_VariantInit
0x18009147d  nop     dword ptr [rax+rax+00h]
0x180091482  movups  xmm6, xmmword ptr [rbp+170h+var_1B8]
0x180091486  lea     rcx, [rsp+270h+var_210+8]; pvarg
0x18009148b  movsd   xmm7, qword ptr [rbp+170h+var_1B8+10h]
0x180091490  call    cs:__imp_VariantInit
0x180091497  nop     dword ptr [rax+rax+00h]
0x18009149c  movups  xmm0, xmmword ptr [rsp+270h+var_210+8]
0x1800914a1  lea     rax, [rbp+170h+var_D0]
0x1800914a8  mov     rcx, rdi
0x1800914ab  movsd   xmm1, [rsp+270h+var_1F8]
0x1800914b1  lea     r9, [rbp+170h+var_B0]
0x1800914b8  mov     [rsp+270h+lpData], rax
0x1800914bd  lea     r8, [rbp+170h+var_120]
0x1800914c1  mov     rax, rbx
0x1800914c4  movaps  [rbp+170h+var_1A0], xmm0
0x1800914c8  lea     rdx, [rbp+170h+var_1A0]
0x1800914cc  movaps  [rbp+170h+var_D0], xmm10
0x1800914d4  movsd   [rbp+170h+var_C0], xmm11
0x1800914dd  movaps  [rbp+170h+var_B0], xmm8
0x1800914e5  movsd   [rbp+170h+var_A0], xmm9
0x1800914ee  movaps  [rbp+170h+var_120], xmm6
0x1800914f2  movsd   [rbp+170h+var_110], xmm7
0x1800914f7  movsd   [rbp+170h+var_190], xmm1
0x1800914fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091501  lea     rcx, [rsp+270h+var_210+8]; this
0x180091506  mov     dword ptr [rbp+170h+Data], eax
0x18009150c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180091511  lea     rcx, [rbp+170h+var_1B8]; this
0x180091515  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18009151a  lea     rcx, [rbp+170h+var_100]; this
0x18009151e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180091523  lea     rcx, [rbp+170h+pvarg]; this
0x18009152a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18009152f  cmp     dword ptr [rbp+170h+Data], r14d
0x180091536  jge     short loc_180091544
0x180091538  lea     r8, a23connect; "23Connect"
0x18009153f  jmp     loc_1800913E0
0x180091544  mov     rbx, [r15]
0x180091547  lea     rdx, asc_1800DD8B8; "\\"
0x18009154e  lea     rcx, [rsp+270h+Block]; this
0x180091553  mov     rax, [rbx]
0x180091556  mov     rdi, [rax+38h]
0x18009155a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18009155f  mov     rcx, [rax]
0x180091562  test    rcx, rcx
0x180091565  jz      short loc_18009156C
0x180091567  mov     rdx, [rcx]
0x18009156a  jmp     short loc_18009156F
0x18009156c  mov     rdx, r14
0x18009156f  lea     r8, [rbp+170h+var_1D0]
0x180091573  mov     rcx, rbx
0x180091576  mov     rax, rdi
0x180091579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009157e  mov     rbx, [rsp+270h+Block]
0x180091583  mov     edi, eax
0x180091585  mov     dword ptr [rbp+170h+Data], eax
0x18009158b  test    rbx, rbx
0x18009158e  jz      short loc_1800915DE
0x180091590  or      eax, 0FFFFFFFFh
0x180091593  lock xadd [rbx+10h], eax
0x180091598  cmp     eax, 1
0x18009159b  jnz     short loc_1800915D8
0x18009159d  test    rbx, rbx
0x1800915a0  jz      short loc_1800915D8
0x1800915a2  mov     rcx, [rbx]; bstrString
0x1800915a5  test    rcx, rcx
0x1800915a8  jz      short loc_1800915B9
0x1800915aa  call    cs:__imp_SysFreeString
0x1800915b1  nop     dword ptr [rax+rax+00h]
0x1800915b6  mov     [rbx], r14
0x1800915b9  mov     rcx, [rbx+8]; Block
0x1800915bd  test    rcx, rcx
0x1800915c0  jz      short loc_1800915CB
0x1800915c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800915c7  mov     [rbx+8], r14
0x1800915cb  mov     edx, 18h
0x1800915d0  mov     rcx, rbx; Block
0x1800915d3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800915d8  mov     edi, dword ptr [rbp+170h+Data]
0x1800915de  test    edi, edi
0x1800915e0  jns     short loc_1800915F3
0x1800915e2  lea     rcx, [rsp+270h+var_230]; this
0x1800915e7  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800915ec  mov     ebx, edi
0x1800915ee  jmp     loc_1800922AF
0x1800915f3  mov     rbx, [rbp+170h+var_1D0]
0x1800915f7  lea     rax, aSprootfolderGe; "spRootFolder->GetFolder()"
0x1800915fe  mov     rdx, [rbp+170h+var_140]; unsigned __int16 *
0x180091602  lea     rcx, [rsp+270h+Block]; this
0x180091607  mov     qword ptr [rbp+170h+var_1B8], rax
0x18009160b  lea     rax, [rbp+170h+Data]
0x180091612  mov     qword ptr [rbp+170h+var_1B8+8], rax
0x180091616  mov     rax, [rbx]
0x180091619  mov     rdi, [rax+48h]
0x18009161d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180091622  mov     rdx, [rax]
0x180091625  test    rdx, rdx
0x180091628  jz      short loc_18009162F
0x18009162a  mov     rdx, [rdx]
0x18009162d  jmp     short loc_180091632
0x18009162f  mov     rdx, r14
0x180091632  lea     r8, [rsp+270h+var_210]
0x180091637  mov     rcx, rbx
0x18009163a  mov     rax, rdi
0x18009163d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091642  mov     rbx, [rsp+270h+Block]
0x180091647  mov     dword ptr [rbp+170h+Data], eax
0x18009164d  test    rbx, rbx
  ... truncated ...
```
