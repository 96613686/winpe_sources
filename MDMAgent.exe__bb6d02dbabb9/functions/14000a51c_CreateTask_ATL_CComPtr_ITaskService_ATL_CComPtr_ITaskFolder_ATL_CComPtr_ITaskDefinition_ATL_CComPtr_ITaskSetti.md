# CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x14000a51c`
- end: `0x14000b77c`
- name: `?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `4704`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, int, int, int, int Data)`
- caller_count: `8`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000d780`
- `0x14000ddd8`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ee48`
- `0x14000f220`
- `0x14000f69c`
- `0x14000fd3c`

## callees

- `0x1400029e4`
- `0x14000476c`
- `0x140004cd0`
- `0x140008fbc`
- `0x140009170`
- `0x1400091e0`
- `0x140009268`
- `0x1400094e4`
- `0x140009688`
- `0x140009fc4`
- `0x14000a03c`
- `0x14000a51c`
- `0x140011ab4`
- `0x140011b04`
- `0x140011b2c`
- `0x14001a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a62b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a650`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a62b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a650`
- `OLEAUT32!__imp_SysAllocString` at `0x14000ab02`
- `OLEAUT32!__imp_SysAllocString` at `0x14000ad13`
- `OLEAUT32!__imp_SysAllocString` at `0x14000ab02`
- `OLEAUT32!__imp_SysAllocString` at `0x14000ad13`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a9ce`
- `OLEAUT32!__imp_SysFreeString` at `0x14000aa90`
- `OLEAUT32!__imp_SysFreeString` at `0x14000abb1`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ac98`
- `OLEAUT32!__imp_SysFreeString` at `0x14000adc7`
- `OLEAUT32!__imp_SysFreeString` at `0x14000aeea`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b016`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b0bb`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b17a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b328`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b583`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b61c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a9ce`
- `OLEAUT32!__imp_SysFreeString` at `0x14000aa90`
- `OLEAUT32!__imp_SysFreeString` at `0x14000abb1`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ac98`
- `OLEAUT32!__imp_SysFreeString` at `0x14000adc7`
- `OLEAUT32!__imp_SysFreeString` at `0x14000aeea`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b016`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b0bb`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b17a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b328`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b583`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b61c`
- `OLEAUT32!__imp_VariantInit` at `0x14000a85a`
- `OLEAUT32!__imp_VariantInit` at `0x14000a87b`
- `OLEAUT32!__imp_VariantInit` at `0x14000a899`
- `OLEAUT32!__imp_VariantInit` at `0x14000a8b3`
- `OLEAUT32!__imp_VariantInit` at `0x14000a85a`
- `OLEAUT32!__imp_VariantInit` at `0x14000a87b`
- `OLEAUT32!__imp_VariantInit` at `0x14000a899`
- `OLEAUT32!__imp_VariantInit` at `0x14000a8b3`
- `OLEAUT32!__imp_VariantClear` at `0x14000aae9`
- `OLEAUT32!__imp_VariantClear` at `0x14000abe9`
- `OLEAUT32!__imp_VariantClear` at `0x14000acfa`
- `OLEAUT32!__imp_VariantClear` at `0x14000adff`
- `OLEAUT32!__imp_VariantClear` at `0x14000aae9`
- `OLEAUT32!__imp_VariantClear` at `0x14000abe9`
- `OLEAUT32!__imp_VariantClear` at `0x14000acfa`
- `OLEAUT32!__imp_VariantClear` at `0x14000adff`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000a827`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000a827`

## string_xrefs

- `0x14000a7df`: `CreateTask`
- `0x14000a7fb`: `22CoCreateTaskScheduler2`

## pseudocode

```c
__int64 __fastcall CreateTask(
        LPVOID *a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int Data)
{
  unsigned int v15; // r12d
  char *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  const wchar_t *v19; // rdx
  const WCHAR *v20; // r8
  unsigned int v21; // ebx
  LPVOID v22; // rdi
  __int64 (__fastcall *v23)(LPVOID, __int128 *, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v24; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v26; // xmm8
  IRecordInfo *v27; // xmm9_8
  __int128 v28; // xmm6
  IRecordInfo *v29; // xmm7_8
  LPVOID v30; // rbx
  __int64 (__fastcall *v31)(LPVOID, __int64, __int64 **); // rdi
  _bstr_t *v32; // rax
  __int64 v33; // rdx
  int v34; // eax
  BSTR *v35; // rbx
  int v36; // edi
  BSTR v37; // rcx
  __int64 *v38; // rbx
  __int64 (__fastcall *v39)(__int64 *, __int64, VARIANTARG *); // rdi
  _bstr_t *v40; // rax
  __int64 v41; // rdx
  int v42; // eax
  BSTR *v43; // rbx
  BSTR v44; // rcx
  __int64 *v45; // rdi
  OLECHAR *v46; // rbx
  __int64 v47; // r14
  __int128 v48; // xmm6
  __int64 v49; // xmm7_8
  _QWORD *v50; // rdx
  __int64 (__fastcall *v51)(__int64 *, _QWORD *, __int128 *, VARIANTARG *); // rax
  int v52; // eax
  BSTR *v53; // rbx
  BSTR v54; // rcx
  __int64 v55; // rbx
  __int64 (__fastcall *v56)(__int64, _QWORD *, __int64); // r14
  _QWORD *v57; // rdx
  int v58; // eax
  BSTR *v59; // rbx
  BSTR v60; // rcx
  __int64 v61; // r14
  OLECHAR *v62; // rbx
  __int64 v63; // r15
  __int128 v64; // xmm6
  __int64 v65; // xmm7_8
  _bstr_t *v66; // rax
  __int64 v67; // rdx
  __int64 (__fastcall *v68)(__int64, __int64, __int128 *, __int64); // rax
  int v69; // eax
  BSTR *v70; // rbx
  BSTR v71; // rcx
  __int64 v72; // rbx
  __int64 (__fastcall *v73)(__int64, __int64); // rdi
  _bstr_t *v74; // rax
  __int64 v75; // rdx
  int v76; // eax
  BSTR *v77; // rbx
  BSTR v78; // rcx
  __int64 v79; // rdi
  __int64 (__fastcall *v80)(__int64, __int128 *); // rbx
  _variant_t *v81; // rax
  __int64 v82; // xmm1_8
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
  void *Block; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v127[3]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v128; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v129; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v130; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v131; // [rsp+80h] [rbp-88h]
  __int64 v132; // [rsp+88h] [rbp-80h] BYREF
  int v133; // [rsp+90h] [rbp-78h]
  __int64 v134; // [rsp+98h] [rbp-70h] BYREF
  __int64 v135; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v136; // [rsp+A8h] [rbp-60h] BYREF
  __int64 (__fastcall ***v137)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-58h] BYREF
  __int64 v138; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v139; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v140; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v141; // [rsp+E8h] [rbp-20h]
  OLECHAR *psz; // [rsp+F8h] [rbp-10h] BYREF
  OLECHAR *v143; // [rsp+100h] [rbp-8h]
  unsigned __int16 *v144; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 *v145; // [rsp+120h] [rbp+18h]
  unsigned __int16 *v146[4]; // [rsp+138h] [rbp+30h] BYREF
  VARIANTARG v147; // [rsp+158h] [rbp+50h] BYREF
  VARIANTARG v148; // [rsp+178h] [rbp+70h] BYREF
  VARIANTARG pvarg; // [rsp+190h] [rbp+88h] BYREF
  __int128 v150; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v151; // [rsp+1B8h] [rbp+B0h]
  __int128 v152; // [rsp+1C8h] [rbp+C0h] BYREF
  IRecordInfo *v153; // [rsp+1D8h] [rbp+D0h]
  int v157; // [rsp+2C8h] [rbp+1C0h]

  v136 = 0;
  *(_QWORD *)&v130.vt = 0;
  v128 = 0;
  v135 = 0;
  v129 = 0;
  v132 = 0;
  v138 = 0;
  v137 = 0;
  v134 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v144);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v146);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&psz);
  v15 = 0;
  if ( Data != 1 )
  {
    LOBYTE(v15) = a10 != 1;
    ++v15;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v144,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;",
                           50)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;",
                           63) )
  {
    goto LABEL_218;
  }
  v133 = 0;
  if ( a8 && (unsigned int)_o__wcsicmp(a8, L"S-1-5-18") )
  {
    v157 = 0;
    if ( !(unsigned int)_o__wcsicmp(a8, L"S-1-5-32-545") )
    {
      v145 = v144;
      *v144 = 0;
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              &v144,
                              L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                              41) )
      {
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v146,
                                L"\\Microsoft\\Windows\\EnterpriseMgmt",
                                33) )
        {
          v143 = psz;
          *psz = 0;
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  &psz,
                                  L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
                                  34) )
          {
            v133 = 1;
            goto LABEL_22;
          }
        }
      }
LABEL_218:
      v21 = -2147024882;
      goto LABEL_219;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v144,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v144,
                             L")",
                             1)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v146,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v146,
                             L"\\EnterpriseMgmt",
                             15)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &psz,
                             a8) )
    {
      goto LABEL_218;
    }
    v18 = 1;
    v19 = L")";
  }
  else
  {
    v145 = v144;
    *v144 = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v144,
                             L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                             41)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v146,
                             L"\\Microsoft\\Windows\\EnterpriseMgmt",
                             33) )
    {
      goto LABEL_218;
    }
    v19 = L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)";
    v143 = psz;
    v18 = 34;
    v157 = 1;
    *psz = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           v19,
                           v18) )
    goto LABEL_218;
LABEL_22:
  Data = CoCreateTaskScheduler(v17, v16, a1);
  v127[0] = "CreateTask";
  v127[1] = &Data;
  if ( Data < 0 )
  {
    v20 = L"22CoCreateTaskScheduler2";
LABEL_24:
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, v20, 4u, &Data, 4u);
    v21 = Data;
LABEL_25:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v127);
LABEL_219:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&psz);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v146);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v144);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v134);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v137);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v138);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v132);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v129);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v135);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v128);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v130);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v136);
    return v21;
  }
  v22 = *a1;
  v23 = *(__int64 (__fastcall **)(LPVOID, __int128 *, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)*a1 + 80LL);
  VariantInit(&pvarg);
  v24 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v148);
  v26 = *(_OWORD *)&v148.vt;
  v27 = v148.pRecInfo;
  VariantInit(&v139);
  v28 = *(_OWORD *)&v139.vt;
  v29 = v139.pRecInfo;
  VariantInit((VARIANTARG *)&v130.decVal.8);
  v140 = *(_OWORD *)&v130.decVal.Lo32;
  v150 = v24;
  v151 = pRecInfo;
  v152 = v26;
  v153 = v27;
  *(_OWORD *)&v147.vt = v28;
  v147.pRecInfo = v29;
  v141 = v131;
  Data = v23(v22, &v140, &v147, &v152, &v150);
  ATL::CComVariant::~CComVariant((VARIANTARG *)&v130.decVal.8);
  ATL::CComVariant::~CComVariant(&v139);
  ATL::CComVariant::~CComVariant(&v148);
  ATL::CComVariant::~CComVariant(&pvarg);
  if ( Data < 0 )
  {
    v20 = L"23Connect";
    goto LABEL_24;
  }
  v30 = *a1;
  v31 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(*(_QWORD *)*a1 + 56LL);
  v32 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"\\");
  if ( *(_QWORD *)v32 )
    v33 = **(_QWORD **)v32;
  else
    v33 = 0;
  v34 = v31(v30, v33, &v136);
  v35 = (BSTR *)Block;
  v36 = v34;
  Data = v34;
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v35 )
    {
      if ( *v35 )
      {
        SysFreeString(*v35);
        *v35 = 0;
      }
      v37 = v35[1];
      if ( v37 )
      {
        operator delete(v37);
        v35[1] = 0;
      }
      operator delete(v35);
    }
    v36 = Data;
  }
  if ( v36 < 0 )
    goto LABEL_41;
  v38 = v136;
  *(_QWORD *)&v139.vt = "spRootFolder->GetFolder()";
  v139.llVal = (LONGLONG)&Data;
  v39 = *(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(*v136 + 72);
  v40 = _bstr_t::_bstr_t((_bstr_t *)&Block, v146[0]);
  if ( *(_QWORD *)v40 )
    v41 = **(_QWORD **)v40;
  else
    v41 = 0;
  v42 = v39(v38, v41, &v130);
  v43 = (BSTR *)Block;
  Data = v42;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v43 )
  {
    if ( *v43 )
    {
      SysFreeString(*v43);
      *v43 = 0;
    }
    v44 = v43[1];
    if ( v44 )
    {
      operator delete(v44);
      v43[1] = 0;
    }
    operator delete(v43);
  }
  if ( (unsigned int)(Data + 2147024894) <= 1 )
  {
    v45 = v136;
    v46 = psz;
    v47 = *v136;
    v130.iVal = 0;
    VariantClear((VARIANTARG *)&v130.decVal.8);
    v130.iVal = 8;
    v130.pRecInfo = (IRecordInfo *)SysAllocString(v46);
    if ( !v130.pRecInfo && v46 )
    {
      v130.iVal = 10;
      *((_DWORD *)&v130.decVal + 4) = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
      __debugbreak();
    }
    v48 = *(_OWORD *)&v130.decVal.Lo32;
    v49 = v131;
    v50 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&Block, v146[0]);
    if ( v50 )
      v50 = (_QWORD *)*v50;
    v51 = *(__int64 (__fastcall **)(__int64 *, _QWORD *, __int128 *, VARIANTARG *))(v47 + 88);
    v140 = v48;
    v141 = v49;
    v52 = v51(v45, v50, &v140, &v130);
    v53 = (BSTR *)Block;
    Data = v52;
    if ( Block )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v53 )
      {
        if ( *v53 )
        {
          SysFreeString(*v53);
          *v53 = 0;
        }
        v54 = v53[1];
        if ( v54 )
        {
          operator delete(v54);
          v53[1] = 0;
        }
        operator delete(v53);
      }
      Block = 0;
    }
    VariantClear((VARIANTARG *)&v130.decVal.8);
    v21 = Data;
    if ( Data < 0 )
    {
LABEL_69:
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v139);
      goto LABEL_25;
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v139);
  if ( a5 )
  {
    v55 = *(_QWORD *)&v130.vt;
    *(_QWORD *)&v139.vt = "spEnterpriseMgmtFolder->GetFolder()";
    v139.llVal = (LONGLONG)&Data;
    v56 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(**(_QWORD **)&v130.vt + 72LL);
    v57 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&Block, a5);
    if ( v57 )
      v57 = (_QWORD *)*v57;
    v58 = v56(v55, v57, a2);
    v59 = (BSTR *)Block;
    Data = v58;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v59 )
    {
      if ( *v59 )
      {
        SysFreeString(*v59);
        *v59 = 0;
      }
      v60 = v59[1];
      if ( v60 )
      {
        operator delete(v60);
        v59[1] = 0;
      }
      operator delete(v59);
    }
    if ( (unsigned int)(Data + 2147024894) <= 1 )
    {
      v61 = *(_QWORD *)&v130.vt;
      v62 = psz;
      v63 = **(_QWORD **)&v130.vt;
      v130.iVal = 0;
      VariantClear((VARIANTARG *)&v130.decVal.8);
      v130.iVal = 8;
      v130.pRecInfo = (IRecordInfo *)SysAllocString(v62);
      if ( !v130.pRecInfo && v62 )
      {
        v130.iVal = 10;
        *((_DWORD *)&v130.decVal + 4) = -2147024882;
        ATL::AtlThrowImpl(-2147024882);
        __debugbreak();
      }
      v64 = *(_OWORD *)&v130.decVal.Lo32;
      v65 = v131;
      v66 = _bstr_t::_bstr_t((_bstr_t *)&Block, a5);
      if ( *(_QWORD *)v66 )
        v67 = **(_QWORD **)v66;
      else
        v67 = 0;
      v68 = *(__int64 (__fastcall **)(__int64, __int64, __int128 *, __int64))(v63 + 88);
      v140 = v64;
      v141 = v65;
      v69 = v68(v61, v67, &v140, a2);
      v70 = (BSTR *)Block;
      Data = v69;
      if ( Block )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v70 )
        {
          if ( *v70 )
          {
            SysFreeString(*v70);
            *v70 = 0;
          }
          v71 = v70[1];
          if ( v71 )
          {
            operator delete(v71);
            v70[1] = 0;
          }
          operator delete(v70);
        }
        Block = 0;
      }
      VariantClear((VARIANTARG *)&v130.decVal.8);
      v21 = Data;
      if ( Data < 0 )
        goto LABEL_69;
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v139);
  }
  else
  {
    ATL::CComPtr<ITaskFolder>::operator=(a2, &v130);
  }
  Data = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD *))(*(_QWORD *)*a1 + 72LL))(*a1, 0, a3);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 56LL))(*a3, &v135);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  v72 = v135;
  v73 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v135 + 80LL);
  v74 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Microsoft Corporation");
  if ( *(_QWORD *)v74 )
    v75 = **(_QWORD **)v74;
  else
    v75 = 0;
  v76 = v73(v72, v75);
  v77 = (BSTR *)Block;
  Data = v76;
  v36 = v76;
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v77 )
    {
      if ( *v77 )
      {
        SysFreeString(*v77);
        *v77 = 0;
      }
      v78 = v77[1];
      if ( v78 )
      {
        operator delete(v78);
        v77[1] = 0;
      }
      operator delete(v77);
    }
    v36 = Data;
  }
  if ( v36 < 0 )
    goto LABEL_41;
  v79 = v135;
  v80 = *(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v135 + 176LL);
  v81 = _variant_t::_variant_t((_variant_t *)&v147, v144);
  v82 = *((_QWORD *)v81 + 2);
  v140 = *(_OWORD *)v81;
  v141 = v82;
  Data = v80(v79, &v140);
  ATL::CComVariant::~CComVariant(&v147);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 120LL))(*a3, &v129);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  v83 = v129;
  v84 = *v129;
  if ( v157 )
  {
    v85 = *(__int64 (__fastcall **)(__int64 *, __int64))(v84 + 128);
    v86 = _bstr_t::_bstr_t((_bstr_t *)&Block, "SYSTEM");
    if ( *(_QWORD *)v86 )
      v87 = **(_QWORD **)v86;
    else
      v87 = 0;
    v88 = v85(v83, v87);
    v89 = (BSTR *)Block;
    v36 = v88;
    Data = v88;
    if ( Block )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v89 )
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
      v36 = Data;
    }
    if ( v36 < 0 )
      goto LABEL_41;
  }
  else if ( v133 )
  {
    v91 = *(__int64 (__fastcall **)(__int64 *, __int64))(v84 + 128);
    v92 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"S-1-5-32-545");
    if ( *(_QWORD *)v92 )
      v93 = **(_QWORD **)v92;
    else
      v93 = 0;
    v94 = v91(v83, v93);
    v95 = (BSTR *)Block;
    v36 = v94;
    Data = v94;
    if ( Block )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v95 )
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
      v36 = Data;
    }
    if ( v36 < 0 )
      goto LABEL_41;
    Data = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v129 + 144))(v129, 1);
    v21 = Data;
    if ( Data < 0 )
      goto LABEL_25;
  }
  else
  {
    v97 = *(__int64 (__fastcall **)(__int64 *, __int64))(v84 + 96);
    v98 = _bstr_t::_bstr_t((_bstr_t *)&Block, a8);
    if ( *(_QWORD *)v98 )
      v99 = **(_QWORD **)v98;
    else
      v99 = 0;
    v100 = v97(v83, v99);
    v101 = (BSTR *)Block;
    v36 = v100;
    Data = v100;
    if ( Block )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v101 )
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
      v36 = Data;
    }
    if ( v36 < 0 )
      goto LABEL_41;
    Data = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v129 + 112))(v129, 3);
    v21 = Data;
    if ( Data < 0 )
      goto LABEL_25;
    Data = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v129 + 144))(v129, 0);
    v21 = Data;
    if ( Data < 0 )
      goto LABEL_25;
  }
  Data = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 88LL))(*a3, &v128);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 128LL))(v128, 0);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 144LL))(v128, 0);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 112LL))(v128, v15);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 352LL))(v128, 0);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  v103 = v128;
  v104 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v128 + 224LL);
  v105 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"PT1H");
  if ( *(_QWORD *)v105 )
    v106 = **(_QWORD **)v105;
  else
    v106 = 0;
  v107 = v104(v103, v106);
  v108 = (BSTR *)Block;
  v36 = v107;
  Data = v107;
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v108 )
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
    v36 = Data;
  }
  if ( v36 < 0 )
    goto LABEL_41;
  Data = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v128)(
           v128,
           &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
           a4);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 176LL))(*a4, (unsigned __int16)((a11 != 1) - 1));
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 208LL))(*a4, (unsigned __int16)((a12 != 1) - 1));
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 400LL))(*a4, 0xFFFFFFFFLL);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v128 + 312LL))(v128, &v132);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v132 + 96LL))(v132, 0);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v132 + 64LL))(v132, 0);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v132 + 80LL))(v132, 0);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 136LL))(*a3, &v138);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v138 + 96LL))(v138, 0, &v137);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  Data = (**v137)(v137, &IID_IExecAction, &v134);
  v21 = Data;
  if ( Data < 0 )
    goto LABEL_25;
  v110 = v134;
  v111 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v134 + 88LL);
  v112 = _bstr_t::_bstr_t((_bstr_t *)&Block, a6);
  if ( *(_QWORD *)v112 )
    v113 = **(_QWORD **)v112;
  else
    v113 = 0;
  v114 = v111(v110, v113);
  v115 = (BSTR *)Block;
  v36 = v114;
  Data = v114;
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v115 )
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
    v36 = Data;
  }
  if ( v36 < 0 )
  {
LABEL_41:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v127);
    v21 = v36;
    goto LABEL_219;
  }
  v117 = v134;
  v118 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v134 + 104LL);
  v119 = _bstr_t::_bstr_t((_bstr_t *)&Block, a7);
  if ( *(_QWORD *)v119 )
    v120 = **(_QWORD **)v119;
  else
    v120 = 0;
  v121 = v118(v117, v120);
  v122 = (BSTR *)Block;
  v123 = v121;
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v122 )
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
    Block = 0;
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v127);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&psz);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v146);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v144);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v134);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v137);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v138);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v132);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v129);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v135);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v128);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v130);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v136);
  return v123;
}

```

## disassembly

```asm
0x14000a51c  mov     rax, rsp
0x14000a51f  mov     [rax+8], rbx
0x14000a523  mov     [rax+20h], r9
0x14000a527  mov     [rax+18h], r8
0x14000a52b  mov     [rax+10h], rdx
0x14000a52f  push    rbp
0x14000a530  push    rsi
0x14000a531  push    rdi
0x14000a532  push    r12
0x14000a534  push    r13
0x14000a536  push    r14
0x14000a538  push    r15
0x14000a53a  lea     rbp, [rax-178h]
0x14000a541  sub     rsp, 240h
0x14000a548  xor     r14d, r14d
0x14000a54b  movaps  xmmword ptr [rax-48h], xmm6
0x14000a54f  movaps  xmmword ptr [rax-58h], xmm7
0x14000a553  mov     r13, rcx
0x14000a556  movaps  xmmword ptr [rax-68h], xmm8
0x14000a55b  lea     rcx, [rbp+170h+var_160]
0x14000a55f  movaps  xmmword ptr [rax-78h], xmm9
0x14000a564  mov     r15, rdx
0x14000a567  movaps  xmmword ptr [rax-88h], xmm10
0x14000a56f  movaps  xmmword ptr [rax-98h], xmm11
0x14000a577  mov     [rbp+170h+var_1D0], r14
0x14000a57b  mov     qword ptr [rsp+270h+var_210], r14
0x14000a580  mov     [rsp+270h+var_220], r14
0x14000a585  mov     [rbp+170h+var_1D8], r14
0x14000a589  mov     [rsp+270h+var_218], r14
0x14000a58e  mov     [rbp+170h+var_1F0], r14
0x14000a592  mov     [rbp+170h+var_1C0], r14
0x14000a596  mov     [rbp+170h+var_1C8], r14
0x14000a59a  mov     [rbp+170h+var_1E0], r14
0x14000a59e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x14000a5a3  lea     rcx, [rbp+170h+var_140]
0x14000a5a7  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x14000a5ac  lea     rcx, [rbp+170h+psz]
0x14000a5b0  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x14000a5b5  lea     ebx, [r14+1]
0x14000a5b9  mov     r12d, r14d
0x14000a5bc  cmp     [rbp+170h+Data], ebx
0x14000a5c2  jz      short loc_14000A5D1
0x14000a5c4  cmp     [rbp+170h+arg_48], ebx
0x14000a5ca  setnz   r12b
0x14000a5ce  add     r12d, ebx
0x14000a5d1  mov     r8d, 32h ; '2'
0x14000a5d7  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x14000a5de  lea     rcx, [rbp+170h+var_160]
0x14000a5e2  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a5e7  test    al, al
0x14000a5e9  jz      loc_14000B6CC
0x14000a5ef  mov     r8d, 3Fh ; '?'
0x14000a5f5  lea     rdx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x14000a5fc  lea     rcx, [rbp+170h+psz]
0x14000a600  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a605  test    al, al
0x14000a607  jz      loc_14000B6CC
0x14000a60d  mov     rsi, [rbp+170h+arg_38]
0x14000a614  mov     [rbp+170h+var_1E8], r14d
0x14000a618  test    rsi, rsi
0x14000a61b  jz      loc_14000A759
0x14000a621  lea     rdx, aS1518; "S-1-5-18"
0x14000a628  mov     rcx, rsi
0x14000a62b  call    cs:__imp__o__wcsicmp
0x14000a632  nop     dword ptr [rax+rax+00h]
0x14000a637  test    eax, eax
0x14000a639  jz      loc_14000A759
0x14000a63f  lea     rdx, aS1532545; "S-1-5-32-545"
0x14000a646  mov     [rbp+170h+arg_40], r14d
0x14000a64d  mov     rcx, rsi
0x14000a650  call    cs:__imp__o__wcsicmp
0x14000a657  nop     dword ptr [rax+rax+00h]
0x14000a65c  test    eax, eax
0x14000a65e  jnz     short loc_14000A6D8
0x14000a660  mov     rcx, [rbp+170h+var_160]
0x14000a664  lea     r8d, [rax+29h]
0x14000a668  mov     [rbp+170h+var_158], rcx
0x14000a66c  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x14000a673  mov     [rcx], r14w
0x14000a677  lea     rcx, [rbp+170h+var_160]
0x14000a67b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a680  test    al, al
0x14000a682  jz      loc_14000B6CC
0x14000a688  mov     r8d, 21h ; '!'
0x14000a68e  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x14000a695  lea     rcx, [rbp+170h+var_140]
0x14000a699  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a69e  test    al, al
0x14000a6a0  jz      loc_14000B6CC
0x14000a6a6  mov     rcx, [rbp+170h+psz]
0x14000a6aa  lea     rdx, psz; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x14000a6b1  mov     [rbp+170h+var_178], rcx
0x14000a6b5  mov     r8d, 22h ; '"'
0x14000a6bb  mov     [rcx], r14w
0x14000a6bf  lea     rcx, [rbp+170h+psz]
0x14000a6c3  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a6c8  test    al, al
0x14000a6ca  jz      loc_14000B6CC
0x14000a6d0  mov     [rbp+170h+var_1E8], ebx
0x14000a6d3  jmp     loc_14000A7D1
0x14000a6d8  mov     rdx, rsi
0x14000a6db  lea     rcx, [rbp+170h+var_160]
0x14000a6df  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14000a6e4  test    al, al
0x14000a6e6  jz      loc_14000B6CC
0x14000a6ec  mov     r8, rbx
0x14000a6ef  lea     rdx, asc_14001CF68; ")"
0x14000a6f6  lea     rcx, [rbp+170h+var_160]
0x14000a6fa  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a6ff  test    al, al
0x14000a701  jz      loc_14000B6CC
0x14000a707  mov     rdx, rsi
0x14000a70a  lea     rcx, [rbp+170h+var_140]
0x14000a70e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14000a713  test    al, al
0x14000a715  jz      loc_14000B6CC
0x14000a71b  mov     r8d, 0Fh
0x14000a721  lea     rdx, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x14000a728  lea     rcx, [rbp+170h+var_140]
0x14000a72c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a731  test    al, al
0x14000a733  jz      loc_14000B6CC
0x14000a739  mov     rdx, rsi
0x14000a73c  lea     rcx, [rbp+170h+psz]
0x14000a740  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14000a745  test    al, al
0x14000a747  jz      loc_14000B6CC
0x14000a74d  mov     r8, rbx
0x14000a750  lea     rdx, asc_14001CF68; ")"
0x14000a757  jmp     short loc_14000A7C0
0x14000a759  mov     rcx, [rbp+170h+var_160]
0x14000a75d  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x14000a764  mov     [rbp+170h+var_158], rcx
0x14000a768  mov     r8d, 29h ; ')'
0x14000a76e  mov     [rcx], r14w
0x14000a772  lea     rcx, [rbp+170h+var_160]
0x14000a776  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a77b  test    al, al
0x14000a77d  jz      loc_14000B6CC
0x14000a783  mov     r8d, 21h ; '!'
0x14000a789  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x14000a790  lea     rcx, [rbp+170h+var_140]
0x14000a794  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a799  test    al, al
0x14000a79b  jz      loc_14000B6CC
0x14000a7a1  mov     rcx, [rbp+170h+psz]
0x14000a7a5  lea     rdx, psz; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x14000a7ac  mov     [rbp+170h+var_178], rcx
0x14000a7b0  mov     r8d, 22h ; '"'
0x14000a7b6  mov     [rbp+170h+arg_40], ebx
0x14000a7bc  mov     [rcx], r14w
0x14000a7c0  lea     rcx, [rbp+170h+psz]
0x14000a7c4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000a7c9  test    al, al
0x14000a7cb  jz      loc_14000B6CC
0x14000a7d1  mov     r8, r13
0x14000a7d4  call    CoCreateTaskScheduler
0x14000a7d9  mov     [rbp+170h+Data], eax
0x14000a7df  lea     rcx, aCreatetask; "CreateTask"
0x14000a7e6  mov     [rsp+270h+var_238], rcx
0x14000a7eb  lea     rcx, [rbp+170h+Data]
0x14000a7f2  mov     [rsp+270h+var_230], rcx
0x14000a7f7  test    eax, eax
0x14000a7f9  jns     short loc_14000A848
0x14000a7fb  lea     r8, a22cocreatetask; "22CoCreateTaskScheduler2"
0x14000a802  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14000a809  lea     rax, [rbp+170h+Data]
0x14000a810  mov     r9d, 4; dwType
0x14000a816  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a81d  mov     [rsp+270h+cbData], r9d; cbData
0x14000a822  mov     [rsp+270h+lpData], rax; lpData
0x14000a827  call    cs:__imp_RegSetKeyValueW
0x14000a82e  nop     dword ptr [rax+rax+00h]
0x14000a833  mov     ebx, [rbp+170h+Data]
0x14000a839  lea     rcx, [rsp+270h+var_238]; this
0x14000a83e  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000a843  jmp     loc_14000B6D1
0x14000a848  mov     rdi, [r13+0]
0x14000a84c  lea     rcx, [rbp+170h+pvarg]; pvarg
0x14000a853  mov     rax, [rdi]
0x14000a856  mov     rbx, [rax+50h]
0x14000a85a  call    cs:__imp_VariantInit
0x14000a861  nop     dword ptr [rax+rax+00h]
0x14000a866  movups  xmm10, xmmword ptr [rbp+170h+pvarg]
0x14000a86e  lea     rcx, [rbp+170h+var_100]; pvarg
0x14000a872  movsd   xmm11, qword ptr [rbp+170h+pvarg+10h]
0x14000a87b  call    cs:__imp_VariantInit
0x14000a882  nop     dword ptr [rax+rax+00h]
0x14000a887  movups  xmm8, xmmword ptr [rbp+170h+var_100]
0x14000a88c  lea     rcx, [rbp+170h+var_1B8]; pvarg
0x14000a890  movsd   xmm9, qword ptr [rbp+170h+var_100+10h]
0x14000a899  call    cs:__imp_VariantInit
0x14000a8a0  nop     dword ptr [rax+rax+00h]
0x14000a8a5  movups  xmm6, xmmword ptr [rbp+170h+var_1B8]
0x14000a8a9  lea     rcx, [rsp+270h+var_210+8]; pvarg
0x14000a8ae  movsd   xmm7, qword ptr [rbp+170h+var_1B8+10h]
0x14000a8b3  call    cs:__imp_VariantInit
0x14000a8ba  nop     dword ptr [rax+rax+00h]
0x14000a8bf  movups  xmm0, xmmword ptr [rsp+270h+var_210+8]
0x14000a8c4  lea     rax, [rbp+170h+var_D0]
0x14000a8cb  mov     rcx, rdi
0x14000a8ce  movsd   xmm1, [rsp+270h+var_1F8]
0x14000a8d4  lea     r9, [rbp+170h+var_B0]
0x14000a8db  mov     [rsp+270h+lpData], rax
0x14000a8e0  lea     r8, [rbp+170h+var_120]
0x14000a8e4  mov     rax, rbx
0x14000a8e7  movaps  [rbp+170h+var_1A0], xmm0
0x14000a8eb  lea     rdx, [rbp+170h+var_1A0]
0x14000a8ef  movaps  [rbp+170h+var_D0], xmm10
0x14000a8f7  movsd   [rbp+170h+var_C0], xmm11
0x14000a900  movaps  [rbp+170h+var_B0], xmm8
0x14000a908  movsd   [rbp+170h+var_A0], xmm9
0x14000a911  movaps  xmmword ptr [rbp+170h+var_120], xmm6
0x14000a915  movsd   qword ptr [rbp+170h+var_120+10h], xmm7
0x14000a91a  movsd   [rbp+170h+var_190], xmm1
0x14000a91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a924  lea     rcx, [rsp+270h+var_210+8]; pvarg
0x14000a929  mov     [rbp+170h+Data], eax
0x14000a92f  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000a934  lea     rcx, [rbp+170h+var_1B8]; pvarg
0x14000a938  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000a93d  lea     rcx, [rbp+170h+var_100]; pvarg
0x14000a941  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000a946  lea     rcx, [rbp+170h+pvarg]; pvarg
0x14000a94d  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000a952  cmp     [rbp+170h+Data], r14d
0x14000a959  jge     short loc_14000A967
0x14000a95b  lea     r8, a23connect; "23Connect"
0x14000a962  jmp     loc_14000A802
0x14000a967  mov     rbx, [r13+0]
0x14000a96b  lea     rdx, asc_14001C460; "\\"
0x14000a972  lea     rcx, [rsp+270h+Block]; this
0x14000a977  mov     rax, [rbx]
0x14000a97a  mov     rdi, [rax+38h]
0x14000a97e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000a983  mov     rcx, [rax]
0x14000a986  test    rcx, rcx
0x14000a989  jz      short loc_14000A990
0x14000a98b  mov     rdx, [rcx]
0x14000a98e  jmp     short loc_14000A993
0x14000a990  mov     rdx, r14
0x14000a993  lea     r8, [rbp+170h+var_1D0]
0x14000a997  mov     rcx, rbx
0x14000a99a  mov     rax, rdi
0x14000a99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9a2  mov     rbx, [rsp+270h+Block]
0x14000a9a7  mov     edi, eax
0x14000a9a9  mov     [rbp+170h+Data], eax
0x14000a9af  test    rbx, rbx
0x14000a9b2  jz      short loc_14000AA02
0x14000a9b4  or      eax, 0FFFFFFFFh
0x14000a9b7  lock xadd [rbx+10h], eax
0x14000a9bc  cmp     eax, 1
0x14000a9bf  jnz     short loc_14000A9FC
0x14000a9c1  test    rbx, rbx
0x14000a9c4  jz      short loc_14000A9FC
0x14000a9c6  mov     rcx, [rbx]; bstrString
0x14000a9c9  test    rcx, rcx
0x14000a9cc  jz      short loc_14000A9DD
0x14000a9ce  call    cs:__imp_SysFreeString
0x14000a9d5  nop     dword ptr [rax+rax+00h]
0x14000a9da  mov     [rbx], r14
0x14000a9dd  mov     rcx, [rbx+8]; Block
0x14000a9e1  test    rcx, rcx
0x14000a9e4  jz      short loc_14000A9EF
0x14000a9e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000a9eb  mov     [rbx+8], r14
0x14000a9ef  mov     edx, 18h
0x14000a9f4  mov     rcx, rbx; Block
0x14000a9f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000a9fc  mov     edi, [rbp+170h+Data]
0x14000aa02  test    edi, edi
0x14000aa04  jns     short loc_14000AA17
0x14000aa06  lea     rcx, [rsp+270h+var_238]; this
0x14000aa0b  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000aa10  mov     ebx, edi
0x14000aa12  jmp     loc_14000B6D1
0x14000aa17  mov     rbx, [rbp+170h+var_1D0]
0x14000aa1b  lea     rax, aSprootfolderGe; "spRootFolder->GetFolder()"
0x14000aa22  mov     rdx, [rbp+170h+var_140]; unsigned __int16 *
0x14000aa26  lea     rcx, [rsp+270h+Block]; this
0x14000aa2b  mov     qword ptr [rbp+170h+var_1B8], rax
0x14000aa2f  lea     rax, [rbp+170h+Data]
0x14000aa36  mov     qword ptr [rbp+170h+var_1B8+8], rax
0x14000aa3a  mov     rax, [rbx]
0x14000aa3d  mov     rdi, [rax+48h]
0x14000aa41  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000aa46  mov     rdx, [rax]
0x14000aa49  test    rdx, rdx
0x14000aa4c  jz      short loc_14000AA53
0x14000aa4e  mov     rdx, [rdx]
0x14000aa51  jmp     short loc_14000AA56
0x14000aa53  mov     rdx, r14
0x14000aa56  lea     r8, [rsp+270h+var_210]
0x14000aa5b  mov     rcx, rbx
0x14000aa5e  mov     rax, rdi
0x14000aa61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa66  mov     rbx, [rsp+270h+Block]
0x14000aa6b  mov     [rbp+170h+Data], eax
0x14000aa71  test    rbx, rbx
  ... truncated ...
```
