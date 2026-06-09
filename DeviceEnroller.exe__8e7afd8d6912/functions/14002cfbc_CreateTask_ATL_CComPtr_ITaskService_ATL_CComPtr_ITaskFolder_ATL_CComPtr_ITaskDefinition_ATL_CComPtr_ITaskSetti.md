# CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x14002cfbc`
- end: `0x14002e07f`
- name: `?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `4291`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *, _QWORD *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, int, int, int, int Data)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14002e088`
- `0x14003154c`
- `0x140058dc0`

## callees

- `0x1400045a8`
- `0x14000e548`
- `0x14001ea48`
- `0x14001ef20`
- `0x14001ef94`
- `0x14002a970`
- `0x14002a9ec`
- `0x14002cb58`
- `0x14002cfbc`
- `0x140033088`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002d0e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002d0ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002d0e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002d0ff`
- `OLEAUT32!__imp_SysAllocString` at `0x14002d6c2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002d802`
- `OLEAUT32!__imp_SysAllocString` at `0x14002d982`
- `OLEAUT32!__imp_SysAllocString` at `0x14002d6c2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002d802`
- `OLEAUT32!__imp_SysAllocString` at `0x14002d982`
- `OLEAUT32!__imp_VariantInit` at `0x14002d4e1`
- `OLEAUT32!__imp_VariantInit` at `0x14002d4f6`
- `OLEAUT32!__imp_VariantInit` at `0x14002d50b`
- `OLEAUT32!__imp_VariantInit` at `0x14002d51e`
- `OLEAUT32!__imp_VariantInit` at `0x14002d4e1`
- `OLEAUT32!__imp_VariantInit` at `0x14002d4f6`
- `OLEAUT32!__imp_VariantInit` at `0x14002d50b`
- `OLEAUT32!__imp_VariantInit` at `0x14002d51e`
- `OLEAUT32!__imp_VariantClear` at `0x14002d6b0`
- `OLEAUT32!__imp_VariantClear` at `0x14002d735`
- `OLEAUT32!__imp_VariantClear` at `0x14002d7f0`
- `OLEAUT32!__imp_VariantClear` at `0x14002d872`
- `OLEAUT32!__imp_VariantClear` at `0x14002d6b0`
- `OLEAUT32!__imp_VariantClear` at `0x14002d735`
- `OLEAUT32!__imp_VariantClear` at `0x14002d7f0`
- `OLEAUT32!__imp_VariantClear` at `0x14002d872`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14002d1ca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14002d1ca`

## string_xrefs

- `0x14002d180`: `CreateTask`
- `0x14002d19e`: `22CoCreateTaskScheduler2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateTask(
        _QWORD *a1,
        _QWORD *a2,
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
        int Data)
{
  _QWORD *v14; // r13
  char v16; // al
  _WORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  const WCHAR *v20; // r8
  unsigned int v21; // edi
  void (*v22)(void); // rax
  const wchar_t *v23; // rdx
  char v24; // al
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v28; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v30; // xmm8
  IRecordInfo *v31; // xmm9_8
  __int128 v32; // xmm6
  IRecordInfo *v33; // xmm7_8
  __int64 v34; // rbx
  __int64 (__fastcall *v35)(__int64, __int64, __int64 **); // rdi
  _bstr_t *v36; // rax
  __int64 v37; // rdx
  __int64 *v38; // rbx
  __int64 (__fastcall *v39)(__int64 *, __int64, __int64 **); // rdi
  _bstr_t *v40; // rax
  __int64 v41; // rdx
  __int64 *v42; // rdi
  const OLECHAR *v43; // rbx
  __int64 v44; // r15
  __int128 v45; // xmm6
  IRecordInfo *v46; // xmm7_8
  _QWORD *v47; // rdx
  __int64 (__fastcall *v48)(__int64 *, _QWORD *, VARIANTARG *, __int64 **); // rax
  __int64 *v49; // rdi
  __int64 (__fastcall *v50)(__int64 *, _QWORD *, _QWORD *); // r15
  _QWORD *v51; // rdx
  __int64 *v52; // r15
  const OLECHAR *v53; // rdi
  __int64 v54; // r13
  __int128 v55; // xmm6
  IRecordInfo *v56; // xmm7_8
  _QWORD *v57; // rdx
  __int64 (__fastcall *v58)(__int64 *, _QWORD *, VARIANTARG *, _QWORD *); // rax
  __int64 *v59; // rbx
  __int64 *v60; // rbx
  __int64 (__fastcall *v61)(__int64 *, __int64); // rdi
  _bstr_t *v62; // rax
  __int64 v63; // rdx
  __int64 *v64; // rdi
  OLECHAR *v65; // rbx
  __int64 v66; // r14
  BSTR v67; // rax
  __int64 (__fastcall *v68)(__int64 *, VARIANTARG *); // rax
  const char *v69; // rdx
  __int64 *v70; // rbx
  __int64 v71; // rax
  __int64 (__fastcall *v72)(__int64 *, __int64); // rdi
  _bstr_t *v73; // rax
  __int64 v74; // rdx
  __int64 (__fastcall *v75)(__int64 *, __int64); // rdi
  _bstr_t *v76; // rax
  __int64 v77; // rdx
  __int64 (__fastcall *v78)(__int64 *, __int64); // rdi
  _bstr_t *v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rbx
  __int64 (__fastcall *v82)(__int64, __int64); // rdi
  _bstr_t *v83; // rax
  __int64 v84; // rdx
  __int64 v85; // rbx
  __int64 (__fastcall *v86)(__int64, __int64); // rdi
  _bstr_t *v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rbx
  __int64 (__fastcall *v90)(__int64, __int64); // rdi
  _bstr_t *v91; // rax
  __int64 v92; // rdx
  __int64 v93; // [rsp+38h] [rbp-D0h] BYREF
  __int64 *v94; // [rsp+40h] [rbp-C8h] BYREF
  __int64 *v95; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v96; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v97; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v98; // [rsp+60h] [rbp-A8h] BYREF
  __int64 *v99; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v100; // [rsp+70h] [rbp-98h] BYREF
  __int64 v101; // [rsp+78h] [rbp-90h] BYREF
  void *Block; // [rsp+80h] [rbp-88h] BYREF
  _WORD *v103; // [rsp+88h] [rbp-80h]
  _WORD v104[8]; // [rsp+90h] [rbp-78h] BYREF
  OLECHAR *psz; // [rsp+A0h] [rbp-68h] BYREF
  OLECHAR *v106; // [rsp+A8h] [rbp-60h]
  _WORD v107[8]; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int16 *v108[2]; // [rsp+C0h] [rbp-48h] BYREF
  _WORD v109[8]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v110[8]; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v111[2]; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG v112; // [rsp+F8h] [rbp-10h] BYREF
  int v113; // [rsp+110h] [rbp+8h]
  int v114; // [rsp+114h] [rbp+Ch]
  unsigned int v115; // [rsp+118h] [rbp+10h]
  VARIANTARG v116; // [rsp+120h] [rbp+18h] BYREF
  VARIANTARG v117; // [rsp+138h] [rbp+30h] BYREF
  VARIANTARG v118; // [rsp+158h] [rbp+50h] BYREF
  VARIANTARG pvarg; // [rsp+170h] [rbp+68h] BYREF
  __int128 v120; // [rsp+188h] [rbp+80h] BYREF
  IRecordInfo *v121; // [rsp+198h] [rbp+90h]
  __int128 v122; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v123; // [rsp+1B8h] [rbp+B0h]
  __int128 v124; // [rsp+1C8h] [rbp+C0h] BYREF
  IRecordInfo *v125; // [rsp+1D8h] [rbp+D0h]

  v14 = a1;
  v99 = 0;
  psz = v107;
  v106 = v107;
  v108[0] = v109;
  v108[1] = v109;
  Block = v104;
  v103 = v104;
  v95 = 0;
  v93 = 0;
  v115 = (a10 != 1) + 1;
  v98 = 0;
  v94 = 0;
  v96 = 0;
  v101 = 0;
  v100 = 0;
  v97 = 0;
  v107[0] = 0;
  v109[0] = 0;
  v104[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;")
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &Block,
                           L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;") )
  {
    goto LABEL_47;
  }
  v114 = 0;
  if ( !a8 || !(unsigned int)_o__wcsicmp(a8, L"S-1-5-18") )
  {
    v106 = psz;
    *psz = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &psz,
                             L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)") )
      goto LABEL_47;
    v24 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            v108,
            L"\\Microsoft\\Windows\\EnterpriseMgmt");
    v17 = Block;
    if ( !v24 )
      goto LABEL_48;
    v103 = Block;
    v23 = L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)";
    *(_WORD *)Block = 0;
    v113 = 1;
LABEL_46:
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            &Block,
                            v23) )
    {
LABEL_10:
      Data = CoCreateTaskScheduler(v19, v18, v14);
      v111[0] = "CreateTask";
      v111[1] = &Data;
      if ( Data < 0 )
      {
        v20 = L"22CoCreateTaskScheduler2";
LABEL_12:
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, v20, 4u, &Data, 4u);
        v21 = Data;
LABEL_13:
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v111);
        if ( Block != v104 )
          operator delete(Block);
        if ( v108[0] != v109 )
          operator delete(v108[0]);
        if ( psz != v107 )
          operator delete(psz);
        if ( v97 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        if ( v100 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
        if ( v101 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
        if ( v96 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
        if ( v94 )
          (*(void (__fastcall **)(__int64 *))(*v94 + 16))(v94);
        if ( v98 )
          (*(void (__fastcall **)(__int64 *))(*v98 + 16))(v98);
        if ( v93 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
        if ( v95 )
          (*(void (__fastcall **)(__int64 *))(*v95 + 16))(v95);
        if ( !v99 )
          return v21;
        v22 = *(void (**)(void))(*v99 + 16);
LABEL_187:
        v22();
        return v21;
      }
      v26 = *v14;
      v27 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*v14 + 80LL);
      VariantInit(&pvarg);
      v28 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v118);
      v30 = *(_OWORD *)&v118.vt;
      v31 = v118.pRecInfo;
      VariantInit(&v116);
      v32 = *(_OWORD *)&v116.vt;
      v33 = v116.pRecInfo;
      VariantInit(&v112);
      v117 = v112;
      v120 = v28;
      v121 = pRecInfo;
      v122 = v30;
      v123 = v31;
      v124 = v32;
      v125 = v33;
      Data = v27(v26, &v117, &v124, &v122, &v120);
      _variant_t::~_variant_t((_variant_t *)&v112);
      _variant_t::~_variant_t((_variant_t *)&v116);
      _variant_t::~_variant_t((_variant_t *)&v118);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      if ( Data < 0 )
      {
        v20 = L"23Connect";
        goto LABEL_12;
      }
      v34 = *v14;
      v35 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)*v14 + 56LL);
      v36 = _bstr_t::_bstr_t((_bstr_t *)v110, L"\\");
      if ( *(_QWORD *)v36 )
        v37 = **(_QWORD **)v36;
      else
        v37 = 0;
      Data = v35(v34, v37, &v99);
      _bstr_t::~_bstr_t((_bstr_t *)v110);
      v21 = Data;
      if ( Data < 0 )
        goto LABEL_13;
      v38 = v99;
      *(_QWORD *)&v116.vt = "spRootFolder->GetFolder()";
      v116.llVal = (LONGLONG)&Data;
      v39 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(*v99 + 72);
      v40 = _bstr_t::_bstr_t((_bstr_t *)v110, v108[0]);
      if ( *(_QWORD *)v40 )
        v41 = **(_QWORD **)v40;
      else
        v41 = 0;
      Data = v39(v38, v41, &v95);
      _bstr_t::~_bstr_t((_bstr_t *)v110);
      if ( (unsigned int)(Data + 2147024894) <= 1 )
      {
        v42 = v99;
        v43 = (const OLECHAR *)Block;
        v44 = *v99;
        v112.vt = 0;
        VariantClear(&v112);
        v112.vt = 8;
        v112.llVal = (LONGLONG)SysAllocString(v43);
        if ( !v112.llVal && v43 )
        {
          v112.lVal = -2147024882;
          v112.vt = 10;
          ATL::AtlThrowImpl(-2147024882);
        }
        v45 = *(_OWORD *)&v112.vt;
        v46 = v112.pRecInfo;
        v47 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v110, v108[0]);
        if ( v47 )
          v47 = (_QWORD *)*v47;
        v48 = *(__int64 (__fastcall **)(__int64 *, _QWORD *, VARIANTARG *, __int64 **))(v44 + 88);
        *(_OWORD *)&v117.vt = v45;
        v117.pRecInfo = v46;
        Data = v48(v42, v47, &v117, &v95);
        _bstr_t::~_bstr_t((_bstr_t *)v110);
        VariantClear(&v112);
        v21 = Data;
        if ( Data < 0 )
        {
LABEL_88:
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v116);
          goto LABEL_13;
        }
      }
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v116);
      if ( a5 )
      {
        v49 = v95;
        *(_QWORD *)&v116.vt = "spEnterpriseMgmtFolder->GetFolder()";
        v116.llVal = (LONGLONG)&Data;
        v50 = *(__int64 (__fastcall **)(__int64 *, _QWORD *, _QWORD *))(*v95 + 72);
        v51 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v110, a5);
        if ( v51 )
          v51 = (_QWORD *)*v51;
        Data = v50(v49, v51, a2);
        _bstr_t::~_bstr_t((_bstr_t *)v110);
        if ( (unsigned int)(Data + 2147024894) <= 1 )
        {
          v52 = v95;
          v53 = (const OLECHAR *)Block;
          v54 = *v95;
          v112.vt = 0;
          VariantClear(&v112);
          v112.vt = 8;
          v112.llVal = (LONGLONG)SysAllocString(v53);
          if ( !v112.llVal && v53 )
          {
            v112.lVal = -2147024882;
            v112.vt = 10;
            ATL::AtlThrowImpl(-2147024882);
          }
          v55 = *(_OWORD *)&v112.vt;
          v56 = v112.pRecInfo;
          v57 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v110, a5);
          if ( v57 )
            v57 = (_QWORD *)*v57;
          v58 = *(__int64 (__fastcall **)(__int64 *, _QWORD *, VARIANTARG *, _QWORD *))(v54 + 88);
          *(_OWORD *)&v117.vt = v55;
          v117.pRecInfo = v56;
          Data = v58(v52, v57, &v117, a2);
          _bstr_t::~_bstr_t((_bstr_t *)v110);
          VariantClear(&v112);
          v21 = Data;
          if ( Data < 0 )
            goto LABEL_88;
          v14 = a1;
        }
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v116);
      }
      else
      {
        v59 = v95;
        if ( (__int64 *)*a2 != v95 )
        {
          if ( v95 )
            (*(void (__fastcall **)(__int64 *))(*v95 + 8))(v95);
          if ( *a2 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
          *a2 = v59;
        }
      }
      Data = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(*(_QWORD *)*v14 + 72LL))(*v14, 0, a3);
      v21 = Data;
      if ( Data >= 0 )
      {
        Data = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 56LL))(*a3, &v98);
        v21 = Data;
        if ( Data >= 0 )
        {
          v60 = v98;
          v61 = *(__int64 (__fastcall **)(__int64 *, __int64))(*v98 + 80);
          v62 = _bstr_t::_bstr_t((_bstr_t *)v110, L"Microsoft Corporation");
          if ( *(_QWORD *)v62 )
            v63 = **(_QWORD **)v62;
          else
            v63 = 0;
          Data = v61(v60, v63);
          _bstr_t::~_bstr_t((_bstr_t *)v110);
          v21 = Data;
          if ( Data < 0 )
            goto LABEL_13;
          v64 = v98;
          v65 = psz;
          v66 = *v98;
          v67 = SysAllocString(psz);
          if ( !v67 && v65 )
            _com_issue_error(-2147024882);
          v112.llVal = (LONGLONG)v67;
          v68 = *(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v66 + 176);
          v112.vt = 8;
          v117 = v112;
          Data = v68(v64, &v117);
          _variant_t::~_variant_t((_variant_t *)&v112);
          v21 = Data;
          if ( Data < 0 )
            goto LABEL_13;
          Data = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 120LL))(*a3, &v94);
          v21 = Data;
          if ( Data >= 0 )
          {
            v70 = v94;
            v71 = *v94;
            if ( v113 )
            {
              v72 = *(__int64 (__fastcall **)(__int64 *, __int64))(v71 + 128);
              v73 = _bstr_t::_bstr_t((_bstr_t *)v110, v69);
              if ( *(_QWORD *)v73 )
                v74 = **(_QWORD **)v73;
              else
                v74 = 0;
              Data = v72(v70, v74);
              _bstr_t::~_bstr_t((_bstr_t *)v110);
              v21 = Data;
              if ( Data < 0 )
                goto LABEL_13;
            }
            else if ( v114 )
            {
              v75 = *(__int64 (__fastcall **)(__int64 *, __int64))(v71 + 128);
              v76 = _bstr_t::_bstr_t((_bstr_t *)v110, L"S-1-5-32-545");
              if ( *(_QWORD *)v76 )
                v77 = **(_QWORD **)v76;
              else
                v77 = 0;
              Data = v75(v70, v77);
              _bstr_t::~_bstr_t((_bstr_t *)v110);
              v21 = Data;
              if ( Data < 0 )
                goto LABEL_13;
              Data = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v94 + 144))(v94, 1);
              v21 = Data;
              if ( Data < 0 )
                goto LABEL_163;
            }
            else
            {
              v78 = *(__int64 (__fastcall **)(__int64 *, __int64))(v71 + 96);
              v79 = _bstr_t::_bstr_t((_bstr_t *)v110, a8);
              if ( *(_QWORD *)v79 )
                v80 = **(_QWORD **)v79;
              else
                v80 = 0;
              Data = v78(v70, v80);
              _bstr_t::~_bstr_t((_bstr_t *)v110);
              v21 = Data;
              if ( Data < 0 )
                goto LABEL_13;
              Data = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v94 + 112))(v94, 3);
              v21 = Data;
              if ( Data < 0 )
                goto LABEL_163;
              Data = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v94 + 144))(v94, a9);
              v21 = Data;
              if ( Data < 0 )
                goto LABEL_163;
            }
            Data = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 88LL))(*a3, &v93);
            v21 = Data;
            if ( Data >= 0 )
            {
              Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 128LL))(v93, 0);
              v21 = Data;
              if ( Data >= 0 )
              {
                Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 144LL))(v93, 0);
                v21 = Data;
                if ( Data >= 0 )
                {
                  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 112LL))(v93, v115);
                  v21 = Data;
                  if ( Data >= 0 )
                  {
                    Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 352LL))(v93, 0);
                    v21 = Data;
                    if ( Data >= 0 )
                    {
                      v81 = v93;
                      v82 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v93 + 224LL);
                      v83 = _bstr_t::_bstr_t((_bstr_t *)v110, L"PT1H");
                      if ( *(_QWORD *)v83 )
                        v84 = **(_QWORD **)v83;
                      else
                        v84 = 0;
                      Data = v82(v81, v84);
                      _bstr_t::~_bstr_t((_bstr_t *)v110);
                      v21 = Data;
                      if ( Data < 0 )
                        goto LABEL_13;
                      Data = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v93)(
                               v93,
                               &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                               a4);
                      v21 = Data;
                      if ( Data >= 0 )
                      {
                        Data = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 176LL))(
                                 *a4,
                                 (unsigned __int16)((a11 != 1) - 1));
                        v21 = Data;
                        if ( Data >= 0 )
                        {
                          Data = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 208LL))(
                                   *a4,
                                   (unsigned __int16)((a12 != 1) - 1));
                          v21 = Data;
                          if ( Data >= 0 )
                          {
                            Data = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 400LL))(
                                     *a4,
                                     0xFFFFFFFFLL);
                            v21 = Data;
                            if ( Data >= 0 )
                            {
                              Data = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v93 + 312LL))(v93, &v96);
                              v21 = Data;
                              if ( Data >= 0 )
                              {
                                Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 96LL))(v96, 0);
                                v21 = Data;
                                if ( Data >= 0 )
                                {
                                  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 64LL))(v96, 0);
                                  v21 = Data;
                                  if ( Data >= 0 )
                                  {
                                    Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 80LL))(v96, 0);
                                    v21 = Data;
                                    if ( Data >= 0 )
                                    {
                                      Data = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 136LL))(
                                               *a3,
                                               &v101);
                                      v21 = Data;
                                      if ( Data >= 0 )
                                      {
                                        Data = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v101 + 96LL))(
                                                 v101,
                                                 0,
                                                 &v100);
                                        v21 = Data;
                                        if ( Data >= 0 )
                                        {
                                          Data = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v100)(
                                                   v100,
                                                   &IID_IExecAction,
                                                   &v97);
                                          v21 = Data;
                                          if ( Data >= 0 )
                                          {
                                            v85 = v97;
                                            v86 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v97 + 88LL);
                                            v87 = _bstr_t::_bstr_t((_bstr_t *)v110, a6);
                                            if ( *(_QWORD *)v87 )
                                              v88 = **(_QWORD **)v87;
                                            else
                                              v88 = 0;
                                            Data = v86(v85, v88);
                                            _bstr_t::~_bstr_t((_bstr_t *)v110);
                                            v21 = Data;
                                            if ( Data < 0 )
                                              goto LABEL_13;
                                            v89 = v97;
                                            v90 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v97 + 104LL);
                                            v91 = _bstr_t::_bstr_t((_bstr_t *)v110, a7);
                                            if ( *(_QWORD *)v91 )
                                              v92 = **(_QWORD **)v91;
                                            else
                                              v92 = 0;
                                            v21 = v90(v89, v92);
                                            _bstr_t::~_bstr_t((_bstr_t *)v110);
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_163:
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v111);
      if ( Block != v104 )
        operator delete(Block);
      if ( v108[0] != v109 )
        operator delete(v108[0]);
      if ( psz != v107 )
        operator delete(psz);
      if ( v97 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
      if ( v100 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
      if ( v101 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
      if ( v96 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
      if ( v94 )
        (*(void (__fastcall **)(__int64 *))(*v94 + 16))(v94);
      if ( v98 )
        (*(void (__fastcall **)(__int64 *))(*v98 + 16))(v98);
      if ( v93 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
      if ( v95 )
        (*(void (__fastcall **)(__int64 *))(*v95 + 16))(v95);
      if ( !v99 )
        return v21;
      v22 = *(void (**)(void))(*v99 + 16);
      goto LABEL_187;
    }
    goto LABEL_47;
  }
  v113 = 0;
  if ( (unsigned int)_o__wcsicmp(a8, L"S-1-5-32-545") )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &psz,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &psz,
                             L")")
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v108,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v108,
                             L"\\EnterpriseMgmt")
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &Block,
                             a8) )
    {
      goto LABEL_47;
    }
    v23 = L")";
    goto LABEL_46;
  }
  v106 = psz;
  *psz = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)") )
  {
LABEL_47:
    v17 = Block;
    goto LABEL_48;
  }
  v16 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          v108,
          L"\\Microsoft\\Windows\\EnterpriseMgmt");
  v17 = Block;
  if ( v16 )
  {
    v103 = Block;
    *(_WORD *)Block = 0;
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            &Block,
                            L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)") )
    {
      v114 = 1;
      goto LABEL_10;
    }
    goto LABEL_47;
  }
LABEL_48:
  if ( v17 != v104 )
    operator delete(v17);
  if ( v108[0] != v109 )
    operator delete(v108[0]);
  if ( psz != v107 )
    operator delete(psz);
  if ( v97 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  if ( v100 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
  if ( v101 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
  if ( v96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  if ( v94 )
    (*(void (__fastcall **)(__int64 *))(*v94 + 16))(v94);
  if ( v98 )
    (*(void (__fastcall **)(__int64 *))(*v98 + 16))(v98);
  if ( v93 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
  if ( v95 )
    (*(void (__fastcall **)(__int64 *))(*v95 + 16))(v95);
  if ( v99 )
    (*(void (__fastcall **)(__int64 *))(*v99 + 16))(v99);
  return 2147942414LL;
}

```

## disassembly

```asm
0x14002cfbc  mov     rax, rsp
0x14002cfbf  mov     [rax+10h], rbx
0x14002cfc3  mov     [rax+20h], r9
0x14002cfc7  mov     [rax+8], rcx
0x14002cfcb  push    rbp
0x14002cfcc  push    rsi
0x14002cfcd  push    rdi
0x14002cfce  push    r12
0x14002cfd0  push    r13
0x14002cfd2  push    r14
0x14002cfd4  push    r15
0x14002cfd6  lea     rbp, [rax-178h]
0x14002cfdd  sub     rsp, 240h
0x14002cfe4  movaps  xmmword ptr [rax-48h], xmm6
0x14002cfe8  xor     r15d, r15d
0x14002cfeb  movaps  xmmword ptr [rax-58h], xmm7
0x14002cfef  mov     r14, rdx
0x14002cff2  movaps  xmmword ptr [rax-68h], xmm8
0x14002cff7  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x14002cffe  movaps  xmmword ptr [rax-78h], xmm9
0x14002d003  mov     r13, rcx
0x14002d006  movaps  xmmword ptr [rax-88h], xmm10
0x14002d00e  lea     ebx, [r15+1]
0x14002d012  cmp     [rbp+170h+arg_48], ebx
0x14002d018  lea     rcx, [rbp+170h+psz]
0x14002d01c  movaps  xmmword ptr [rax-98h], xmm11
0x14002d024  mov     r12, r8
0x14002d027  lea     rax, [rbp+170h+var_1C8]
0x14002d02b  mov     [rsp+270h+var_210], r15
0x14002d030  mov     [rbp+170h+psz], rax
0x14002d034  lea     rax, [rbp+170h+var_1C8]
0x14002d038  mov     [rbp+170h+var_1D0], rax
0x14002d03c  lea     rax, [rbp+170h+var_1A8]
0x14002d040  mov     [rbp+170h+var_1B8], rax
0x14002d044  lea     rax, [rbp+170h+var_1A8]
0x14002d048  mov     [rbp+170h+var_1B0], rax
0x14002d04c  lea     rax, [rbp+170h+var_1E8]
0x14002d050  mov     [rsp+270h+Block], rax
0x14002d055  lea     rax, [rbp+170h+var_1E8]
0x14002d059  mov     [rbp+170h+var_1F0], rax
0x14002d05d  mov     eax, r15d
0x14002d060  setnz   al
0x14002d063  mov     [rsp+270h+var_230], r15
0x14002d068  add     eax, ebx
0x14002d06a  mov     [rsp+270h+var_240], r15
0x14002d06f  mov     [rbp+170h+var_160], eax
0x14002d072  mov     [rsp+270h+var_218], r15
0x14002d077  mov     [rsp+270h+var_238], r15
0x14002d07c  mov     [rsp+270h+var_228], r15
0x14002d081  mov     [rsp+270h+var_200], r15
0x14002d086  mov     [rsp+270h+var_208], r15
0x14002d08b  mov     [rsp+270h+var_220], r15
0x14002d090  mov     [rbp+170h+var_1C8], r15w
0x14002d095  mov     [rbp+170h+var_1A8], r15w
0x14002d09a  mov     [rbp+170h+var_1E8], r15w
0x14002d09f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d0a4  test    al, al
0x14002d0a6  jz      loc_14002D3BB
0x14002d0ac  lea     rdx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x14002d0b3  lea     rcx, [rsp+270h+Block]
0x14002d0b8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d0bd  test    al, al
0x14002d0bf  jz      loc_14002D3BB
0x14002d0c5  mov     rsi, [rbp+170h+arg_38]
0x14002d0cc  mov     [rbp+170h+var_164], r15d
0x14002d0d0  test    rsi, rsi
0x14002d0d3  jz      loc_14002D35E
0x14002d0d9  lea     rdx, aS1518; "S-1-5-18"
0x14002d0e0  mov     rcx, rsi
0x14002d0e3  call    cs:__imp__o__wcsicmp
0x14002d0e9  test    eax, eax
0x14002d0eb  jz      loc_14002D35E
0x14002d0f1  lea     rdx, aS1532545; "S-1-5-32-545"
0x14002d0f8  mov     [rbp+170h+var_168], r15d
0x14002d0fc  mov     rcx, rsi
0x14002d0ff  call    cs:__imp__o__wcsicmp
0x14002d105  test    eax, eax
0x14002d107  jnz     loc_14002D2F0
0x14002d10d  mov     rcx, [rbp+170h+psz]
0x14002d111  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x14002d118  mov     [rbp+170h+var_1D0], rcx
0x14002d11c  mov     [rcx], r15w
0x14002d120  lea     rcx, [rbp+170h+psz]
0x14002d124  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d129  test    al, al
0x14002d12b  jz      loc_14002D3BB
0x14002d131  lea     rdx, aMicrosoftWindo_4; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x14002d138  lea     rcx, [rbp+170h+var_1B8]
0x14002d13c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d141  mov     rcx, [rsp+270h+Block]
0x14002d146  test    al, al
0x14002d148  jz      loc_14002D3C0
0x14002d14e  mov     [rbp+170h+var_1F0], rcx
0x14002d152  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x14002d159  mov     [rcx], r15w
0x14002d15d  lea     rcx, [rsp+270h+Block]
0x14002d162  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d167  test    al, al
0x14002d169  jz      loc_14002D3BB
0x14002d16f  mov     [rbp+170h+var_164], ebx
0x14002d172  mov     r8, r13
0x14002d175  call    CoCreateTaskScheduler
0x14002d17a  mov     [rbp+170h+Data], eax
0x14002d180  lea     rcx, aCreatetask; "CreateTask"
0x14002d187  mov     [rbp+170h+var_190], rcx
0x14002d18b  lea     rcx, [rbp+170h+Data]
0x14002d192  mov     [rbp+170h+var_188], rcx
0x14002d196  test    eax, eax
0x14002d198  jns     loc_14002D4D2
0x14002d19e  lea     r8, ValueName; "22CoCreateTaskScheduler2"
0x14002d1a5  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14002d1ac  lea     rax, [rbp+170h+Data]
0x14002d1b3  mov     r9d, 4; dwType
0x14002d1b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002d1c0  mov     [rsp+270h+cbData], r9d; cbData
0x14002d1c5  mov     [rsp+270h+lpData], rax; lpData
0x14002d1ca  call    cs:__imp_RegSetKeyValueW
0x14002d1d0  mov     edi, [rbp+170h+Data]
0x14002d1d6  lea     rcx, [rbp+170h+var_190]; this
0x14002d1da  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14002d1df  mov     rcx, [rsp+270h+Block]; Block
0x14002d1e4  lea     rax, [rbp+170h+var_1E8]
0x14002d1e8  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14002d1ef  cmp     rcx, rax
0x14002d1f2  jz      short loc_14002D1FC
0x14002d1f4  mov     rdx, rbx
0x14002d1f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d1fc  mov     rcx, [rbp+170h+var_1B8]; Block
0x14002d200  lea     rax, [rbp+170h+var_1A8]
0x14002d204  cmp     rcx, rax
0x14002d207  jz      short loc_14002D211
0x14002d209  mov     rdx, rbx
0x14002d20c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d211  mov     rcx, [rbp+170h+psz]; Block
0x14002d215  lea     rax, [rbp+170h+var_1C8]
0x14002d219  cmp     rcx, rax
0x14002d21c  jz      short loc_14002D226
0x14002d21e  mov     rdx, rbx
0x14002d221  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d226  mov     rcx, [rsp+270h+var_220]
0x14002d22b  test    rcx, rcx
0x14002d22e  jz      short loc_14002D23C
0x14002d230  mov     rax, [rcx]
0x14002d233  mov     rax, [rax+10h]
0x14002d237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d23c  mov     rcx, [rsp+270h+var_208]
0x14002d241  test    rcx, rcx
0x14002d244  jz      short loc_14002D252
0x14002d246  mov     rax, [rcx]
0x14002d249  mov     rax, [rax+10h]
0x14002d24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d252  mov     rcx, [rsp+270h+var_200]
0x14002d257  test    rcx, rcx
0x14002d25a  jz      short loc_14002D268
0x14002d25c  mov     rax, [rcx]
0x14002d25f  mov     rax, [rax+10h]
0x14002d263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d268  mov     rcx, [rsp+270h+var_228]
0x14002d26d  test    rcx, rcx
0x14002d270  jz      short loc_14002D27E
0x14002d272  mov     rax, [rcx]
0x14002d275  mov     rax, [rax+10h]
0x14002d279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d27e  mov     rcx, [rsp+270h+var_238]
0x14002d283  test    rcx, rcx
0x14002d286  jz      short loc_14002D294
0x14002d288  mov     rax, [rcx]
0x14002d28b  mov     rax, [rax+10h]
0x14002d28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d294  mov     rcx, [rsp+270h+var_218]
0x14002d299  test    rcx, rcx
0x14002d29c  jz      short loc_14002D2AA
0x14002d29e  mov     rax, [rcx]
0x14002d2a1  mov     rax, [rax+10h]
0x14002d2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d2aa  mov     rcx, [rsp+270h+var_240]
0x14002d2af  test    rcx, rcx
0x14002d2b2  jz      short loc_14002D2C0
0x14002d2b4  mov     rax, [rcx]
0x14002d2b7  mov     rax, [rax+10h]
0x14002d2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d2c0  mov     rcx, [rsp+270h+var_230]
0x14002d2c5  test    rcx, rcx
0x14002d2c8  jz      short loc_14002D2D6
0x14002d2ca  mov     rax, [rcx]
0x14002d2cd  mov     rax, [rax+10h]
0x14002d2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d2d6  mov     rcx, [rsp+270h+var_210]
0x14002d2db  test    rcx, rcx
0x14002d2de  jz      loc_14002E003
0x14002d2e4  mov     rdx, [rcx]
0x14002d2e7  mov     rax, [rdx+10h]
0x14002d2eb  jmp     loc_14002DFFE
0x14002d2f0  mov     rdx, rsi
0x14002d2f3  lea     rcx, [rbp+170h+psz]
0x14002d2f7  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d2fc  test    al, al
0x14002d2fe  jz      loc_14002D3BB
0x14002d304  lea     rdx, asc_140065E14; ")"
0x14002d30b  lea     rcx, [rbp+170h+psz]
0x14002d30f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d314  test    al, al
0x14002d316  jz      loc_14002D3BB
0x14002d31c  mov     rdx, rsi
0x14002d31f  lea     rcx, [rbp+170h+var_1B8]
0x14002d323  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d328  test    al, al
0x14002d32a  jz      loc_14002D3BB
0x14002d330  lea     rdx, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x14002d337  lea     rcx, [rbp+170h+var_1B8]
0x14002d33b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d340  test    al, al
0x14002d342  jz      short loc_14002D3BB
0x14002d344  mov     rdx, rsi
0x14002d347  lea     rcx, [rsp+270h+Block]
0x14002d34c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d351  test    al, al
0x14002d353  jz      short loc_14002D3BB
0x14002d355  lea     rdx, asc_140065E14; ")"
0x14002d35c  jmp     short loc_14002D3A9
0x14002d35e  mov     rcx, [rbp+170h+psz]
0x14002d362  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x14002d369  mov     [rbp+170h+var_1D0], rcx
0x14002d36d  mov     [rcx], r15w
0x14002d371  lea     rcx, [rbp+170h+psz]
0x14002d375  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d37a  test    al, al
0x14002d37c  jz      short loc_14002D3BB
0x14002d37e  lea     rdx, aMicrosoftWindo_4; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x14002d385  lea     rcx, [rbp+170h+var_1B8]
0x14002d389  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d38e  mov     rcx, [rsp+270h+Block]
0x14002d393  test    al, al
0x14002d395  jz      short loc_14002D3C0
0x14002d397  mov     [rbp+170h+var_1F0], rcx
0x14002d39b  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x14002d3a2  mov     [rcx], r15w
0x14002d3a6  mov     [rbp+170h+var_168], ebx
0x14002d3a9  lea     rcx, [rsp+270h+Block]
0x14002d3ae  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14002d3b3  test    al, al
0x14002d3b5  jnz     loc_14002D172
0x14002d3bb  mov     rcx, [rsp+270h+Block]; Block
0x14002d3c0  lea     rax, [rbp+170h+var_1E8]
0x14002d3c4  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14002d3cb  cmp     rcx, rax
0x14002d3ce  jz      short loc_14002D3D8
0x14002d3d0  mov     rdx, rbx
0x14002d3d3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d3d8  mov     rcx, [rbp+170h+var_1B8]; Block
0x14002d3dc  lea     rax, [rbp+170h+var_1A8]
0x14002d3e0  cmp     rcx, rax
0x14002d3e3  jz      short loc_14002D3ED
0x14002d3e5  mov     rdx, rbx
0x14002d3e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d3ed  mov     rcx, [rbp+170h+psz]; Block
0x14002d3f1  lea     rax, [rbp+170h+var_1C8]
0x14002d3f5  cmp     rcx, rax
0x14002d3f8  jz      short loc_14002D402
0x14002d3fa  mov     rdx, rbx
0x14002d3fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d402  mov     rcx, [rsp+270h+var_220]
0x14002d407  test    rcx, rcx
0x14002d40a  jz      short loc_14002D418
0x14002d40c  mov     rax, [rcx]
0x14002d40f  mov     rax, [rax+10h]
0x14002d413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d418  mov     rcx, [rsp+270h+var_208]
0x14002d41d  test    rcx, rcx
0x14002d420  jz      short loc_14002D42E
0x14002d422  mov     rax, [rcx]
0x14002d425  mov     rax, [rax+10h]
0x14002d429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d42e  mov     rcx, [rsp+270h+var_200]
0x14002d433  test    rcx, rcx
0x14002d436  jz      short loc_14002D444
0x14002d438  mov     rax, [rcx]
0x14002d43b  mov     rax, [rax+10h]
0x14002d43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d444  mov     rcx, [rsp+270h+var_228]
0x14002d449  test    rcx, rcx
0x14002d44c  jz      short loc_14002D45A
0x14002d44e  mov     rax, [rcx]
0x14002d451  mov     rax, [rax+10h]
0x14002d455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d45a  mov     rcx, [rsp+270h+var_238]
0x14002d45f  test    rcx, rcx
0x14002d462  jz      short loc_14002D470
0x14002d464  mov     rax, [rcx]
0x14002d467  mov     rax, [rax+10h]
0x14002d46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d470  mov     rcx, [rsp+270h+var_218]
0x14002d475  test    rcx, rcx
0x14002d478  jz      short loc_14002D486
0x14002d47a  mov     rax, [rcx]
0x14002d47d  mov     rax, [rax+10h]
0x14002d481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d486  mov     rcx, [rsp+270h+var_240]
0x14002d48b  test    rcx, rcx
0x14002d48e  jz      short loc_14002D49C
  ... truncated ...
```
