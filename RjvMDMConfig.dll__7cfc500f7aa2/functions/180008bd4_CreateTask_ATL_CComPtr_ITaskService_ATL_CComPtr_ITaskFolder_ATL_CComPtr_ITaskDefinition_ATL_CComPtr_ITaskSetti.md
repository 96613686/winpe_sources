# CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x180008bd4`
- end: `0x180009e3a`
- name: `?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `4710`
- prototype: ``
- caller_count: `8`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c980`
- `0x18000cfc4`
- `0x18000d590`
- `0x18000db20`
- `0x18000e034`
- `0x18000e40c`
- `0x18000e888`
- `0x18000ef24`

## callees

- `0x180001cc8`
- `0x180006fe4`
- `0x1800071e8`
- `0x180007258`
- `0x1800072d0`
- `0x180007364`
- `0x1800077a0`
- `0x1800079e8`
- `0x180008428`
- `0x180008484`
- `0x1800085c8`
- `0x180008bd4`
- `0x1800114a4`
- `0x18001154c`
- `0x180011574`
- `0x18001e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008ce3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008d08`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008ce3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008d08`
- `OLEAUT32!__imp_SysAllocString` at `0x1800091b8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800093c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800091b8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800093c9`
- `OLEAUT32!__imp_SysFreeString` at `0x180009084`
- `OLEAUT32!__imp_SysFreeString` at `0x180009146`
- `OLEAUT32!__imp_SysFreeString` at `0x180009267`
- `OLEAUT32!__imp_SysFreeString` at `0x18000934e`
- `OLEAUT32!__imp_SysFreeString` at `0x180009479`
- `OLEAUT32!__imp_SysFreeString` at `0x1800095a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180009779`
- `OLEAUT32!__imp_SysFreeString` at `0x180009838`
- `OLEAUT32!__imp_SysFreeString` at `0x1800099e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c41`
- `OLEAUT32!__imp_SysFreeString` at `0x180009cda`
- `OLEAUT32!__imp_SysFreeString` at `0x180009084`
- `OLEAUT32!__imp_SysFreeString` at `0x180009146`
- `OLEAUT32!__imp_SysFreeString` at `0x180009267`
- `OLEAUT32!__imp_SysFreeString` at `0x18000934e`
- `OLEAUT32!__imp_SysFreeString` at `0x180009479`
- `OLEAUT32!__imp_SysFreeString` at `0x1800095a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180009779`
- `OLEAUT32!__imp_SysFreeString` at `0x180009838`
- `OLEAUT32!__imp_SysFreeString` at `0x1800099e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c41`
- `OLEAUT32!__imp_SysFreeString` at `0x180009cda`
- `OLEAUT32!__imp_VariantInit` at `0x180008f11`
- `OLEAUT32!__imp_VariantInit` at `0x180008f32`
- `OLEAUT32!__imp_VariantInit` at `0x180008f50`
- `OLEAUT32!__imp_VariantInit` at `0x180008f6a`
- `OLEAUT32!__imp_VariantInit` at `0x180008f11`
- `OLEAUT32!__imp_VariantInit` at `0x180008f32`
- `OLEAUT32!__imp_VariantInit` at `0x180008f50`
- `OLEAUT32!__imp_VariantInit` at `0x180008f6a`
- `OLEAUT32!__imp_VariantClear` at `0x18000919f`
- `OLEAUT32!__imp_VariantClear` at `0x18000929f`
- `OLEAUT32!__imp_VariantClear` at `0x1800093b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800094b1`
- `OLEAUT32!__imp_VariantClear` at `0x18000919f`
- `OLEAUT32!__imp_VariantClear` at `0x18000929f`
- `OLEAUT32!__imp_VariantClear` at `0x1800093b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800094b1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008edf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008edf`

## string_xrefs

- `0x180008e97`: `CreateTask`
- `0x180008eb3`: `22CoCreateTaskScheduler2`

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
        __int64 a9,
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
  const struct std::nothrow_t *v34; // rdx
  BSTR *v35; // rbx
  int v36; // edi
  BSTR v37; // rcx
  __int64 *v38; // rbx
  __int64 (__fastcall *v39)(__int64 *, __int64, VARIANTARG *); // rdi
  _bstr_t *v40; // rax
  __int64 v41; // rdx
  int v42; // eax
  const struct std::nothrow_t *v43; // rdx
  BSTR *v44; // rbx
  BSTR v45; // rcx
  __int64 *v46; // rdi
  OLECHAR *v47; // rbx
  __int64 v48; // r14
  __int128 v49; // xmm6
  __int64 v50; // xmm7_8
  _QWORD *v51; // rdx
  __int64 (__fastcall *v52)(__int64 *, _QWORD *, __int128 *, VARIANTARG *); // rax
  int v53; // eax
  const struct std::nothrow_t *v54; // rdx
  BSTR *v55; // rbx
  BSTR v56; // rcx
  __int64 v57; // rbx
  __int64 (__fastcall *v58)(__int64, _QWORD *, struct IUnknown **); // r14
  _QWORD *v59; // rdx
  int v60; // eax
  const struct std::nothrow_t *v61; // rdx
  BSTR *v62; // rbx
  BSTR v63; // rcx
  __int64 v64; // r14
  OLECHAR *v65; // rbx
  __int64 v66; // r15
  __int128 v67; // xmm6
  __int64 v68; // xmm7_8
  _bstr_t *v69; // rax
  __int64 v70; // rdx
  __int64 (__fastcall *v71)(__int64, __int64, __int128 *, struct IUnknown **); // rax
  int v72; // eax
  const struct std::nothrow_t *v73; // rdx
  BSTR *v74; // rbx
  BSTR v75; // rcx
  __int64 v76; // rbx
  __int64 (__fastcall *v77)(__int64, __int64); // rdi
  _bstr_t *v78; // rax
  __int64 v79; // rdx
  int v80; // eax
  const struct std::nothrow_t *v81; // rdx
  BSTR *v82; // rbx
  BSTR v83; // rcx
  __int64 v84; // rdi
  __int64 (__fastcall *v85)(__int64, __int128 *); // rbx
  _variant_t *v86; // rax
  __int64 v87; // xmm1_8
  __int64 *v88; // rbx
  __int64 v89; // rax
  __int64 (__fastcall *v90)(__int64 *, __int64); // rdi
  _bstr_t *v91; // rax
  __int64 v92; // rdx
  int v93; // eax
  const struct std::nothrow_t *v94; // rdx
  BSTR *v95; // rbx
  BSTR v96; // rcx
  __int64 (__fastcall *v97)(__int64 *, __int64); // rdi
  _bstr_t *v98; // rax
  __int64 v99; // rdx
  int v100; // eax
  const struct std::nothrow_t *v101; // rdx
  BSTR *v102; // rbx
  BSTR v103; // rcx
  __int64 (__fastcall *v104)(__int64 *, __int64); // rdi
  _bstr_t *v105; // rax
  __int64 v106; // rdx
  int v107; // eax
  const struct std::nothrow_t *v108; // rdx
  BSTR *v109; // rbx
  BSTR v110; // rcx
  __int64 v111; // rbx
  __int64 (__fastcall *v112)(__int64, __int64); // rdi
  _bstr_t *v113; // rax
  __int64 v114; // rdx
  int v115; // eax
  const struct std::nothrow_t *v116; // rdx
  BSTR *v117; // rbx
  BSTR v118; // rcx
  __int64 v119; // rbx
  __int64 (__fastcall *v120)(__int64, __int64); // rdi
  _bstr_t *v121; // rax
  __int64 v122; // rdx
  int v123; // eax
  const struct std::nothrow_t *v124; // rdx
  BSTR *v125; // rbx
  BSTR v126; // rcx
  __int64 v127; // rbx
  __int64 (__fastcall *v128)(__int64, __int64); // rdi
  _bstr_t *v129; // rax
  __int64 v130; // rdx
  unsigned int v131; // eax
  const struct std::nothrow_t *v132; // rdx
  BSTR *v133; // rbx
  unsigned int v134; // edi
  BSTR v135; // rcx
  void *v137; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v138[3]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v139; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v140; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v141; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v142; // [rsp+80h] [rbp-88h]
  __int64 v143; // [rsp+88h] [rbp-80h] BYREF
  int v144; // [rsp+90h] [rbp-78h]
  __int64 v145; // [rsp+98h] [rbp-70h] BYREF
  __int64 v146; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v147; // [rsp+A8h] [rbp-60h] BYREF
  __int64 (__fastcall ***v148)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-58h] BYREF
  __int64 v149; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v150; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v151; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v152; // [rsp+E8h] [rbp-20h]
  OLECHAR *psz; // [rsp+F8h] [rbp-10h] BYREF
  OLECHAR *v154; // [rsp+100h] [rbp-8h]
  unsigned __int16 *v155; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 *v156; // [rsp+120h] [rbp+18h]
  unsigned __int16 *v157[4]; // [rsp+138h] [rbp+30h] BYREF
  __int128 v158; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v159; // [rsp+168h] [rbp+60h]
  VARIANTARG v160; // [rsp+178h] [rbp+70h] BYREF
  VARIANTARG pvarg; // [rsp+190h] [rbp+88h] BYREF
  __int128 v162; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v163; // [rsp+1B8h] [rbp+B0h]
  __int128 v164; // [rsp+1C8h] [rbp+C0h] BYREF
  IRecordInfo *v165; // [rsp+1D8h] [rbp+D0h]
  int v169; // [rsp+2C8h] [rbp+1C0h]
  __int64 Data; // [rsp+2E8h] [rbp+1E0h] BYREF
  va_list Dataa; // [rsp+2E8h] [rbp+1E0h]
  va_list va1; // [rsp+2F0h] [rbp+1E8h] BYREF

  va_start(va1, a12);
  va_start(Dataa, a12);
  Data = va_arg(va1, _QWORD);
  v12 = a1;
  v147 = 0;
  *(_QWORD *)&v141.vt = 0;
  v139 = 0;
  v146 = 0;
  v140 = 0;
  v143 = 0;
  v149 = 0;
  v148 = 0;
  v145 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v155);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v157);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&psz);
  v14 = 0;
  if ( (_DWORD)Data != 1 )
  {
    LOBYTE(v14) = a10 != 1;
    ++v14;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v155,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;",
                           50)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;",
                           63) )
  {
    goto LABEL_220;
  }
  v144 = 0;
  if ( a8 && (unsigned int)_o__wcsicmp(a8, L"S-1-5-18") )
  {
    v169 = 0;
    if ( !(unsigned int)_o__wcsicmp(a8, L"S-1-5-32-545") )
    {
      v156 = v155;
      *v155 = 0;
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              &v155,
                              L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                              41) )
      {
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v157,
                                L"\\Microsoft\\Windows\\EnterpriseMgmt",
                                33) )
        {
          v154 = psz;
          *psz = 0;
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  &psz,
                                  L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
                                  34) )
          {
            v144 = 1;
            goto LABEL_22;
          }
        }
      }
LABEL_220:
      v20 = -2147024882;
      goto LABEL_221;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v155,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v155,
                             L")",
                             1)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v157,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v157,
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
    v156 = v155;
    *v155 = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v155,
                             L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                             41)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v157,
                             L"\\Microsoft\\Windows\\EnterpriseMgmt",
                             33) )
    {
      goto LABEL_220;
    }
    v18 = L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)";
    v154 = psz;
    v17 = 34;
    v169 = 1;
    *psz = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           v18,
                           v17) )
    goto LABEL_220;
LABEL_22:
  LODWORD(Data) = CoCreateTaskScheduler(v16, v15, v12);
  v138[0] = "CreateTask";
  va_copy((va_list)&v138[1], Dataa);
  if ( (int)Data < 0 )
  {
    v19 = L"22CoCreateTaskScheduler2";
LABEL_24:
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, v19, 4u, Dataa, 4u);
    v20 = Data;
LABEL_25:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v138);
LABEL_221:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&psz);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v157);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v155);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v145);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v148);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v149);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v143);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v140);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v146);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v139);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v141);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v147);
    return v20;
  }
  v21 = *v12;
  v22 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*v12 + 80LL);
  VariantInit(&pvarg);
  v23 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v160);
  v25 = *(_OWORD *)&v160.vt;
  v26 = v160.pRecInfo;
  VariantInit(&v150);
  v27 = *(_OWORD *)&v150.vt;
  v28 = v150.pRecInfo;
  VariantInit((VARIANTARG *)&v141.decVal.8);
  v151 = *(_OWORD *)&v141.decVal.Lo32;
  v162 = v23;
  v163 = pRecInfo;
  v164 = v25;
  v165 = v26;
  v158 = v27;
  v159 = v28;
  v152 = v142;
  LODWORD(Data) = v22(v21, &v151, &v158, &v164, &v162);
  _variant_t::~_variant_t((_variant_t *)&v141.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v150);
  _variant_t::~_variant_t((_variant_t *)&v160);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( (int)Data < 0 )
  {
    v19 = L"23Connect";
    goto LABEL_24;
  }
  v29 = *v12;
  v30 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(*(_QWORD *)*v12 + 56LL);
  v31 = _bstr_t::_bstr_t((_bstr_t *)&v137, L"\\");
  if ( *(_QWORD *)v31 )
    v32 = **(_QWORD **)v31;
  else
    v32 = 0;
  v33 = v30(v29, v32, &v147);
  v35 = (BSTR *)v137;
  v36 = v33;
  LODWORD(Data) = v33;
  if ( v137 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v35 )
    {
      if ( *v35 )
      {
        SysFreeString(*v35);
        *v35 = 0;
      }
      v37 = v35[1];
      if ( v37 )
      {
        operator delete(v37, v34);
        v35[1] = 0;
      }
      operator delete(v35, (const struct std::nothrow_t *)0x18);
    }
    v36 = Data;
  }
  if ( v36 < 0 )
    goto LABEL_41;
  v38 = v147;
  *(_QWORD *)&v150.vt = "spRootFolder->GetFolder()";
  va_copy(v150.pcVal, Dataa);
  v39 = *(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(*v147 + 72);
  v40 = _bstr_t::_bstr_t((_bstr_t *)&v137, v157[0]);
  if ( *(_QWORD *)v40 )
    v41 = **(_QWORD **)v40;
  else
    v41 = 0;
  v42 = v39(v38, v41, &v141);
  v44 = (BSTR *)v137;
  LODWORD(Data) = v42;
  if ( v137 && _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v44 )
  {
    if ( *v44 )
    {
      SysFreeString(*v44);
      *v44 = 0;
    }
    v45 = v44[1];
    if ( v45 )
    {
      operator delete(v45, v43);
      v44[1] = 0;
    }
    operator delete(v44, (const struct std::nothrow_t *)0x18);
  }
  if ( (unsigned int)(Data + 2147024894) <= 1 )
  {
    v46 = v147;
    v47 = psz;
    v48 = *v147;
    v141.iVal = 0;
    VariantClear((VARIANTARG *)&v141.decVal.8);
    v141.iVal = 8;
    v141.pRecInfo = (IRecordInfo *)SysAllocString(v47);
    if ( !v141.pRecInfo && v47 )
    {
      v141.iVal = 10;
      *((_DWORD *)&v141.decVal + 4) = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
      __debugbreak();
    }
    v49 = *(_OWORD *)&v141.decVal.Lo32;
    v50 = v142;
    v51 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v137, v157[0]);
    if ( v51 )
      v51 = (_QWORD *)*v51;
    v52 = *(__int64 (__fastcall **)(__int64 *, _QWORD *, __int128 *, VARIANTARG *))(v48 + 88);
    v151 = v49;
    v152 = v50;
    v53 = v52(v46, v51, &v151, &v141);
    v55 = (BSTR *)v137;
    LODWORD(Data) = v53;
    if ( v137 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v55 )
      {
        if ( *v55 )
        {
          SysFreeString(*v55);
          *v55 = 0;
        }
        v56 = v55[1];
        if ( v56 )
        {
          operator delete(v56, v54);
          v55[1] = 0;
        }
        operator delete(v55, (const struct std::nothrow_t *)0x18);
      }
      v137 = 0;
    }
    VariantClear((VARIANTARG *)&v141.decVal.8);
    v20 = Data;
    if ( (int)Data < 0 )
    {
LABEL_69:
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v150);
      goto LABEL_25;
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v150);
  if ( a5 )
  {
    v57 = *(_QWORD *)&v141.vt;
    *(_QWORD *)&v150.vt = "spEnterpriseMgmtFolder->GetFolder()";
    va_copy(v150.pcVal, Dataa);
    v58 = *(__int64 (__fastcall **)(__int64, _QWORD *, struct IUnknown **))(**(_QWORD **)&v141.vt + 72LL);
    v59 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v137, a5);
    if ( v59 )
      v59 = (_QWORD *)*v59;
    v60 = v58(v57, v59, a2);
    v62 = (BSTR *)v137;
    LODWORD(Data) = v60;
    if ( v137 && _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v62 )
    {
      if ( *v62 )
      {
        SysFreeString(*v62);
        *v62 = 0;
      }
      v63 = v62[1];
      if ( v63 )
      {
        operator delete(v63, v61);
        v62[1] = 0;
      }
      operator delete(v62, (const struct std::nothrow_t *)0x18);
    }
    if ( (unsigned int)(Data + 2147024894) <= 1 )
    {
      v64 = *(_QWORD *)&v141.vt;
      v65 = psz;
      v66 = **(_QWORD **)&v141.vt;
      v141.iVal = 0;
      VariantClear((VARIANTARG *)&v141.decVal.8);
      v141.iVal = 8;
      v141.pRecInfo = (IRecordInfo *)SysAllocString(v65);
      if ( !v141.pRecInfo && v65 )
      {
        v141.iVal = 10;
        *((_DWORD *)&v141.decVal + 4) = -2147024882;
        ATL::AtlThrowImpl(-2147024882);
        __debugbreak();
      }
      v67 = *(_OWORD *)&v141.decVal.Lo32;
      v68 = v142;
      v69 = _bstr_t::_bstr_t((_bstr_t *)&v137, a5);
      if ( *(_QWORD *)v69 )
        v70 = **(_QWORD **)v69;
      else
        v70 = 0;
      v71 = *(__int64 (__fastcall **)(__int64, __int64, __int128 *, struct IUnknown **))(v66 + 88);
      v151 = v67;
      v152 = v68;
      v72 = v71(v64, v70, &v151, a2);
      v74 = (BSTR *)v137;
      LODWORD(Data) = v72;
      if ( v137 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v74 )
        {
          if ( *v74 )
          {
            SysFreeString(*v74);
            *v74 = 0;
          }
          v75 = v74[1];
          if ( v75 )
          {
            operator delete(v75, v73);
            v74[1] = 0;
          }
          operator delete(v74, (const struct std::nothrow_t *)0x18);
        }
        v137 = 0;
      }
      VariantClear((VARIANTARG *)&v141.decVal.8);
      v20 = Data;
      if ( (int)Data < 0 )
        goto LABEL_69;
      v12 = a1;
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v150);
  }
  else if ( *a2 != *(struct IUnknown **)&v141.vt )
  {
    ATL::AtlComPtrAssign(a2, *(struct IUnknown **)&v141.vt);
  }
  LODWORD(Data) = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD *))(*(_QWORD *)*v12 + 72LL))(*v12, 0, a3);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 56LL))(*a3, &v146);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v76 = v146;
  v77 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v146 + 80LL);
  v78 = _bstr_t::_bstr_t((_bstr_t *)&v137, L"Microsoft Corporation");
  if ( *(_QWORD *)v78 )
    v79 = **(_QWORD **)v78;
  else
    v79 = 0;
  v80 = v77(v76, v79);
  v82 = (BSTR *)v137;
  LODWORD(Data) = v80;
  v36 = v80;
  if ( v137 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v82 )
    {
      if ( *v82 )
      {
        SysFreeString(*v82);
        *v82 = 0;
      }
      v83 = v82[1];
      if ( v83 )
      {
        operator delete(v83, v81);
        v82[1] = 0;
      }
      operator delete(v82, (const struct std::nothrow_t *)0x18);
    }
    v36 = Data;
  }
  if ( v36 < 0 )
    goto LABEL_41;
  v84 = v146;
  v85 = *(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v146 + 176LL);
  v86 = _variant_t::_variant_t((_variant_t *)&v158, v155);
  v87 = *((_QWORD *)v86 + 2);
  v151 = *(_OWORD *)v86;
  v152 = v87;
  LODWORD(Data) = v85(v84, &v151);
  _variant_t::~_variant_t((_variant_t *)&v158);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 120LL))(*a3, &v140);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v88 = v140;
  v89 = *v140;
  if ( v169 )
  {
    v90 = *(__int64 (__fastcall **)(__int64 *, __int64))(v89 + 128);
    v91 = _bstr_t::_bstr_t((_bstr_t *)&v137, "SYSTEM");
    if ( *(_QWORD *)v91 )
      v92 = **(_QWORD **)v91;
    else
      v92 = 0;
    v93 = v90(v88, v92);
    v95 = (BSTR *)v137;
    v36 = v93;
    LODWORD(Data) = v93;
    if ( v137 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v95 )
      {
        if ( *v95 )
        {
          SysFreeString(*v95);
          *v95 = 0;
        }
        v96 = v95[1];
        if ( v96 )
        {
          operator delete(v96, v94);
          v95[1] = 0;
        }
        operator delete(v95, (const struct std::nothrow_t *)0x18);
      }
      v36 = Data;
    }
    if ( v36 < 0 )
      goto LABEL_41;
  }
  else if ( v144 )
  {
    v97 = *(__int64 (__fastcall **)(__int64 *, __int64))(v89 + 128);
    v98 = _bstr_t::_bstr_t((_bstr_t *)&v137, L"S-1-5-32-545");
    if ( *(_QWORD *)v98 )
      v99 = **(_QWORD **)v98;
    else
      v99 = 0;
    v100 = v97(v88, v99);
    v102 = (BSTR *)v137;
    v36 = v100;
    LODWORD(Data) = v100;
    if ( v137 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v102 )
      {
        if ( *v102 )
        {
          SysFreeString(*v102);
          *v102 = 0;
        }
        v103 = v102[1];
        if ( v103 )
        {
          operator delete(v103, v101);
          v102[1] = 0;
        }
        operator delete(v102, (const struct std::nothrow_t *)0x18);
      }
      v36 = Data;
    }
    if ( v36 < 0 )
      goto LABEL_41;
    LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v140 + 144))(v140, 1);
    v20 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
  }
  else
  {
    v104 = *(__int64 (__fastcall **)(__int64 *, __int64))(v89 + 96);
    v105 = _bstr_t::_bstr_t((_bstr_t *)&v137, a8);
    if ( *(_QWORD *)v105 )
      v106 = **(_QWORD **)v105;
    else
      v106 = 0;
    v107 = v104(v88, v106);
    v109 = (BSTR *)v137;
    v36 = v107;
    LODWORD(Data) = v107;
    if ( v137 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v109 )
      {
        if ( *v109 )
        {
          SysFreeString(*v109);
          *v109 = 0;
        }
        v110 = v109[1];
        if ( v110 )
        {
          operator delete(v110, v108);
          v109[1] = 0;
        }
        operator delete(v109, (const struct std::nothrow_t *)0x18);
      }
      v36 = Data;
    }
    if ( v36 < 0 )
      goto LABEL_41;
    LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v140 + 112))(v140, 3);
    v20 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
    LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v140 + 144))(v140, 0);
    v20 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
  }
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 88LL))(*a3, &v139);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v139 + 128LL))(v139, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v139 + 144LL))(v139, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v139 + 112LL))(v139, v14);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v139 + 352LL))(v139, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v111 = v139;
  v112 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v139 + 224LL);
  v113 = _bstr_t::_bstr_t((_bstr_t *)&v137, L"PT1H");
  if ( *(_QWORD *)v113 )
    v114 = **(_QWORD **)v113;
  else
    v114 = 0;
  v115 = v112(v111, v114);
  v117 = (BSTR *)v137;
  v36 = v115;
  LODWORD(Data) = v115;
  if ( v137 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v117 )
    {
      if ( *v117 )
      {
        SysFreeString(*v117);
        *v117 = 0;
      }
      v118 = v117[1];
      if ( v118 )
      {
        operator delete(v118, v116);
        v117[1] = 0;
      }
      operator delete(v117, (const struct std::nothrow_t *)0x18);
    }
    v36 = Data;
  }
  if ( v36 < 0 )
    goto LABEL_41;
  LODWORD(Data) = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v139)(
                    v139,
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
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v139 + 312LL))(v139, &v143);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v143 + 96LL))(v143, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v143 + 64LL))(v143, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v143 + 80LL))(v143, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 136LL))(*a3, &v149);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v149 + 96LL))(v149, 0, &v148);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (**v148)(v148, &IID_IExecAction, &v145);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v119 = v145;
  v120 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v145 + 88LL);
  v121 = _bstr_t::_bstr_t((_bstr_t *)&v137, a6);
  if ( *(_QWORD *)v121 )
    v122 = **(_QWORD **)v121;
  else
    v122 = 0;
  v123 = v120(v119, v122);
  v125 = (BSTR *)v137;
  v36 = v123;
  LODWORD(Data) = v123;
  if ( v137 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v125 )
    {
      if ( *v125 )
      {
        SysFreeString(*v125);
        *v125 = 0;
      }
      v126 = v125[1];
      if ( v126 )
      {
        operator delete(v126, v124);
        v125[1] = 0;
      }
      operator delete(v125, (const struct std::nothrow_t *)0x18);
    }
    v36 = Data;
  }
  if ( v36 < 0 )
  {
LABEL_41:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v138);
    v20 = v36;
    goto LABEL_221;
  }
  v127 = v145;
  v128 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v145 + 104LL);
  v129 = _bstr_t::_bstr_t((_bstr_t *)&v137, a7);
  if ( *(_QWORD *)v129 )
    v130 = **(_QWORD **)v129;
  else
    v130 = 0;
  v131 = v128(v127, v130);
  v133 = (BSTR *)v137;
  v134 = v131;
  if ( v137 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 4, 0xFFFFFFFF) == 1 && v133 )
    {
      if ( *v133 )
      {
        SysFreeString(*v133);
        *v133 = 0;
      }
      v135 = v133[1];
      if ( v135 )
      {
        operator delete(v135, v132);
        v133[1] = 0;
      }
      operator delete(v133, (const struct std::nothrow_t *)0x18);
    }
    v137 = 0;
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v138);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&psz);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v157);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v155);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v145);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v148);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v149);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v143);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v140);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v146);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v139);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v141);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v147);
  return v134;
}

```

## disassembly

```asm
0x180008bd4  mov     rax, rsp
0x180008bd7  mov     [rax+10h], rbx
0x180008bdb  mov     [rax+20h], r9
0x180008bdf  mov     [rax+18h], r8
0x180008be3  mov     [rax+8], rcx
0x180008be7  push    rbp
0x180008be8  push    rsi
0x180008be9  push    rdi
0x180008bea  push    r12
0x180008bec  push    r13
0x180008bee  push    r14
0x180008bf0  push    r15
0x180008bf2  lea     rbp, [rax-178h]
0x180008bf9  sub     rsp, 240h
0x180008c00  xor     r14d, r14d
0x180008c03  movaps  xmmword ptr [rax-48h], xmm6
0x180008c07  movaps  xmmword ptr [rax-58h], xmm7
0x180008c0b  mov     r15, rcx
0x180008c0e  movaps  xmmword ptr [rax-68h], xmm8
0x180008c13  lea     rcx, [rbp+170h+var_160]
0x180008c17  movaps  xmmword ptr [rax-78h], xmm9
0x180008c1c  mov     r12, rdx
0x180008c1f  movaps  xmmword ptr [rax-88h], xmm10
0x180008c27  movaps  xmmword ptr [rax-98h], xmm11
0x180008c2f  mov     [rbp+170h+var_1D0], r14
0x180008c33  mov     qword ptr [rsp+270h+var_210], r14
0x180008c38  mov     [rsp+270h+var_220], r14
0x180008c3d  mov     [rbp+170h+var_1D8], r14
0x180008c41  mov     [rsp+270h+var_218], r14
0x180008c46  mov     [rbp+170h+var_1F0], r14
0x180008c4a  mov     [rbp+170h+var_1C0], r14
0x180008c4e  mov     [rbp+170h+var_1C8], r14
0x180008c52  mov     [rbp+170h+var_1E0], r14
0x180008c56  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180008c5b  lea     rcx, [rbp+170h+var_140]
0x180008c5f  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180008c64  lea     rcx, [rbp+170h+psz]
0x180008c68  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180008c6d  lea     ebx, [r14+1]
0x180008c71  mov     r13d, r14d
0x180008c74  cmp     dword ptr [rbp+170h+Data], ebx
0x180008c7a  jz      short loc_180008C89
0x180008c7c  cmp     [rbp+170h+arg_48], ebx
0x180008c82  setnz   r13b
0x180008c86  add     r13d, ebx
0x180008c89  mov     r8d, 32h ; '2'
0x180008c8f  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x180008c96  lea     rcx, [rbp+170h+var_160]
0x180008c9a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008c9f  test    al, al
0x180008ca1  jz      loc_180009D8A
0x180008ca7  mov     r8d, 3Fh ; '?'
0x180008cad  lea     rdx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x180008cb4  lea     rcx, [rbp+170h+psz]
0x180008cb8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008cbd  test    al, al
0x180008cbf  jz      loc_180009D8A
0x180008cc5  mov     rsi, [rbp+170h+arg_38]
0x180008ccc  mov     [rbp+170h+var_1E8], r14d
0x180008cd0  test    rsi, rsi
0x180008cd3  jz      loc_180008E11
0x180008cd9  lea     rdx, aS1518; "S-1-5-18"
0x180008ce0  mov     rcx, rsi
0x180008ce3  call    cs:__imp__o__wcsicmp
0x180008cea  nop     dword ptr [rax+rax+00h]
0x180008cef  test    eax, eax
0x180008cf1  jz      loc_180008E11
0x180008cf7  lea     rdx, aS1532545; "S-1-5-32-545"
0x180008cfe  mov     [rbp+170h+arg_40], r14d
0x180008d05  mov     rcx, rsi
0x180008d08  call    cs:__imp__o__wcsicmp
0x180008d0f  nop     dword ptr [rax+rax+00h]
0x180008d14  test    eax, eax
0x180008d16  jnz     short loc_180008D90
0x180008d18  mov     rcx, [rbp+170h+var_160]
0x180008d1c  lea     r8d, [rax+29h]
0x180008d20  mov     [rbp+170h+var_158], rcx
0x180008d24  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x180008d2b  mov     [rcx], r14w
0x180008d2f  lea     rcx, [rbp+170h+var_160]
0x180008d33  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008d38  test    al, al
0x180008d3a  jz      loc_180009D8A
0x180008d40  mov     r8d, 21h ; '!'
0x180008d46  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180008d4d  lea     rcx, [rbp+170h+var_140]
0x180008d51  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008d56  test    al, al
0x180008d58  jz      loc_180009D8A
0x180008d5e  mov     rcx, [rbp+170h+psz]
0x180008d62  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x180008d69  mov     [rbp+170h+var_178], rcx
0x180008d6d  mov     r8d, 22h ; '"'
0x180008d73  mov     [rcx], r14w
0x180008d77  lea     rcx, [rbp+170h+psz]
0x180008d7b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008d80  test    al, al
0x180008d82  jz      loc_180009D8A
0x180008d88  mov     [rbp+170h+var_1E8], ebx
0x180008d8b  jmp     loc_180008E89
0x180008d90  mov     rdx, rsi
0x180008d93  lea     rcx, [rbp+170h+var_160]
0x180008d97  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180008d9c  test    al, al
0x180008d9e  jz      loc_180009D8A
0x180008da4  mov     r8, rbx
0x180008da7  lea     rdx, asc_180021794; ")"
0x180008dae  lea     rcx, [rbp+170h+var_160]
0x180008db2  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008db7  test    al, al
0x180008db9  jz      loc_180009D8A
0x180008dbf  mov     rdx, rsi
0x180008dc2  lea     rcx, [rbp+170h+var_140]
0x180008dc6  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180008dcb  test    al, al
0x180008dcd  jz      loc_180009D8A
0x180008dd3  mov     r8d, 0Fh
0x180008dd9  lea     rdx, aEnterprisemgmt; "\\EnterpriseMgmt"
0x180008de0  lea     rcx, [rbp+170h+var_140]
0x180008de4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008de9  test    al, al
0x180008deb  jz      loc_180009D8A
0x180008df1  mov     rdx, rsi
0x180008df4  lea     rcx, [rbp+170h+psz]
0x180008df8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180008dfd  test    al, al
0x180008dff  jz      loc_180009D8A
0x180008e05  mov     r8, rbx
0x180008e08  lea     rdx, asc_180021794; ")"
0x180008e0f  jmp     short loc_180008E78
0x180008e11  mov     rcx, [rbp+170h+var_160]
0x180008e15  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x180008e1c  mov     [rbp+170h+var_158], rcx
0x180008e20  mov     r8d, 29h ; ')'
0x180008e26  mov     [rcx], r14w
0x180008e2a  lea     rcx, [rbp+170h+var_160]
0x180008e2e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008e33  test    al, al
0x180008e35  jz      loc_180009D8A
0x180008e3b  mov     r8d, 21h ; '!'
0x180008e41  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180008e48  lea     rcx, [rbp+170h+var_140]
0x180008e4c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008e51  test    al, al
0x180008e53  jz      loc_180009D8A
0x180008e59  mov     rcx, [rbp+170h+psz]
0x180008e5d  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x180008e64  mov     [rbp+170h+var_178], rcx
0x180008e68  mov     r8d, 22h ; '"'
0x180008e6e  mov     [rbp+170h+arg_40], ebx
0x180008e74  mov     [rcx], r14w
0x180008e78  lea     rcx, [rbp+170h+psz]
0x180008e7c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008e81  test    al, al
0x180008e83  jz      loc_180009D8A
0x180008e89  mov     r8, r15
0x180008e8c  call    CoCreateTaskScheduler
0x180008e91  mov     dword ptr [rbp+170h+Data], eax
0x180008e97  lea     rcx, aCreatetask; "CreateTask"
0x180008e9e  mov     [rsp+270h+var_238], rcx
0x180008ea3  lea     rcx, [rbp+170h+Data]
0x180008eaa  mov     [rsp+270h+var_230], rcx
0x180008eaf  test    eax, eax
0x180008eb1  jns     short loc_180008F00
0x180008eb3  lea     r8, a22cocreatetask; "22CoCreateTaskScheduler2"
0x180008eba  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180008ec1  lea     rax, [rbp+170h+Data]
0x180008ec8  mov     r9d, 4; dwType
0x180008ece  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008ed5  mov     [rsp+270h+cbData], r9d; cbData
0x180008eda  mov     [rsp+270h+lpData], rax; lpData
0x180008edf  call    cs:__imp_RegSetKeyValueW
0x180008ee6  nop     dword ptr [rax+rax+00h]
0x180008eeb  mov     ebx, dword ptr [rbp+170h+Data]
0x180008ef1  lea     rcx, [rsp+270h+var_238]; this
0x180008ef6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180008efb  jmp     loc_180009D8F
0x180008f00  mov     rdi, [r15]
0x180008f03  lea     rcx, [rbp+170h+pvarg]; pvarg
0x180008f0a  mov     rax, [rdi]
0x180008f0d  mov     rbx, [rax+50h]
0x180008f11  call    cs:__imp_VariantInit
0x180008f18  nop     dword ptr [rax+rax+00h]
0x180008f1d  movups  xmm10, xmmword ptr [rbp+170h+pvarg]
0x180008f25  lea     rcx, [rbp+170h+var_100]; pvarg
0x180008f29  movsd   xmm11, qword ptr [rbp+170h+pvarg+10h]
0x180008f32  call    cs:__imp_VariantInit
0x180008f39  nop     dword ptr [rax+rax+00h]
0x180008f3e  movups  xmm8, xmmword ptr [rbp+170h+var_100]
0x180008f43  lea     rcx, [rbp+170h+var_1B8]; pvarg
0x180008f47  movsd   xmm9, qword ptr [rbp+170h+var_100+10h]
0x180008f50  call    cs:__imp_VariantInit
0x180008f57  nop     dword ptr [rax+rax+00h]
0x180008f5c  movups  xmm6, xmmword ptr [rbp+170h+var_1B8]
0x180008f60  lea     rcx, [rsp+270h+var_210+8]; pvarg
0x180008f65  movsd   xmm7, qword ptr [rbp+170h+var_1B8+10h]
0x180008f6a  call    cs:__imp_VariantInit
0x180008f71  nop     dword ptr [rax+rax+00h]
0x180008f76  movups  xmm0, xmmword ptr [rsp+270h+var_210+8]
0x180008f7b  lea     rax, [rbp+170h+var_D0]
0x180008f82  mov     rcx, rdi
0x180008f85  movsd   xmm1, [rsp+270h+var_1F8]
0x180008f8b  lea     r9, [rbp+170h+var_B0]
0x180008f92  mov     [rsp+270h+lpData], rax
0x180008f97  lea     r8, [rbp+170h+var_120]
0x180008f9b  mov     rax, rbx
0x180008f9e  movaps  [rbp+170h+var_1A0], xmm0
0x180008fa2  lea     rdx, [rbp+170h+var_1A0]
0x180008fa6  movaps  [rbp+170h+var_D0], xmm10
0x180008fae  movsd   [rbp+170h+var_C0], xmm11
0x180008fb7  movaps  [rbp+170h+var_B0], xmm8
0x180008fbf  movsd   [rbp+170h+var_A0], xmm9
0x180008fc8  movaps  [rbp+170h+var_120], xmm6
0x180008fcc  movsd   [rbp+170h+var_110], xmm7
0x180008fd1  movsd   [rbp+170h+var_190], xmm1
0x180008fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fdb  lea     rcx, [rsp+270h+var_210+8]; this
0x180008fe0  mov     dword ptr [rbp+170h+Data], eax
0x180008fe6  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180008feb  lea     rcx, [rbp+170h+var_1B8]; this
0x180008fef  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180008ff4  lea     rcx, [rbp+170h+var_100]; this
0x180008ff8  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180008ffd  lea     rcx, [rbp+170h+pvarg]; this
0x180009004  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180009009  cmp     dword ptr [rbp+170h+Data], r14d
0x180009010  jge     short loc_18000901E
0x180009012  lea     r8, a23connect; "23Connect"
0x180009019  jmp     loc_180008EBA
0x18000901e  mov     rbx, [r15]
0x180009021  lea     rdx, asc_180020DAC; "\\"
0x180009028  lea     rcx, [rsp+270h+var_240]; this
0x18000902d  mov     rax, [rbx]
0x180009030  mov     rdi, [rax+38h]
0x180009034  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180009039  mov     rcx, [rax]
0x18000903c  test    rcx, rcx
0x18000903f  jz      short loc_180009046
0x180009041  mov     rdx, [rcx]
0x180009044  jmp     short loc_180009049
0x180009046  mov     rdx, r14
0x180009049  lea     r8, [rbp+170h+var_1D0]
0x18000904d  mov     rcx, rbx
0x180009050  mov     rax, rdi
0x180009053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009058  mov     rbx, [rsp+270h+var_240]
0x18000905d  mov     edi, eax
0x18000905f  mov     dword ptr [rbp+170h+Data], eax
0x180009065  test    rbx, rbx
0x180009068  jz      short loc_1800090B8
0x18000906a  or      eax, 0FFFFFFFFh
0x18000906d  lock xadd [rbx+10h], eax
0x180009072  cmp     eax, 1
0x180009075  jnz     short loc_1800090B2
0x180009077  test    rbx, rbx
0x18000907a  jz      short loc_1800090B2
0x18000907c  mov     rcx, [rbx]; bstrString
0x18000907f  test    rcx, rcx
0x180009082  jz      short loc_180009093
0x180009084  call    cs:__imp_SysFreeString
0x18000908b  nop     dword ptr [rax+rax+00h]
0x180009090  mov     [rbx], r14
0x180009093  mov     rcx, [rbx+8]; void *
0x180009097  test    rcx, rcx
0x18000909a  jz      short loc_1800090A5
0x18000909c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800090a1  mov     [rbx+8], r14
0x1800090a5  mov     edx, 18h; struct std::nothrow_t *
0x1800090aa  mov     rcx, rbx; void *
0x1800090ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800090b2  mov     edi, dword ptr [rbp+170h+Data]
0x1800090b8  test    edi, edi
0x1800090ba  jns     short loc_1800090CD
0x1800090bc  lea     rcx, [rsp+270h+var_238]; this
0x1800090c1  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800090c6  mov     ebx, edi
0x1800090c8  jmp     loc_180009D8F
0x1800090cd  mov     rbx, [rbp+170h+var_1D0]
0x1800090d1  lea     rax, aSprootfolderGe; "spRootFolder->GetFolder()"
0x1800090d8  mov     rdx, [rbp+170h+var_140]; unsigned __int16 *
0x1800090dc  lea     rcx, [rsp+270h+var_240]; this
0x1800090e1  mov     qword ptr [rbp+170h+var_1B8], rax
0x1800090e5  lea     rax, [rbp+170h+Data]
0x1800090ec  mov     qword ptr [rbp+170h+var_1B8+8], rax
0x1800090f0  mov     rax, [rbx]
0x1800090f3  mov     rdi, [rax+48h]
0x1800090f7  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800090fc  mov     rdx, [rax]
0x1800090ff  test    rdx, rdx
0x180009102  jz      short loc_180009109
0x180009104  mov     rdx, [rdx]
0x180009107  jmp     short loc_18000910C
0x180009109  mov     rdx, r14
0x18000910c  lea     r8, [rsp+270h+var_210]
0x180009111  mov     rcx, rbx
0x180009114  mov     rax, rdi
0x180009117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000911c  mov     rbx, [rsp+270h+var_240]
0x180009121  mov     dword ptr [rbp+170h+Data], eax
0x180009127  test    rbx, rbx
  ... truncated ...
```
