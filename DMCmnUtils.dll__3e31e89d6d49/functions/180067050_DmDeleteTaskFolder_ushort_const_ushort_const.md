# DmDeleteTaskFolder(ushort const *,ushort const *)

- ea: `0x180067050`
- end: `0x180067917`
- name: `?DmDeleteTaskFolder@@YAJPEBG0@Z`
- size: `2247`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180057c6c`
- `0x18005e62c`
- `0x18005e708`
- `0x18005e7f8`
- `0x18005e820`
- `0x18005f858`
- `0x1800651fc`
- `0x180067050`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800670d1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800670d1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006714a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067315`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800673ee`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800674c3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800675a5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067602`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067819`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067877`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800678d2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006714a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067315`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800673ee`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800674c3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800675a5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067602`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067819`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067877`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800678d2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006772d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006772d`
- `OLEAUT32!__imp_VariantInit` at `0x180067171`
- `OLEAUT32!__imp_VariantInit` at `0x180067199`
- `OLEAUT32!__imp_VariantInit` at `0x1800671c1`
- `OLEAUT32!__imp_VariantInit` at `0x1800671e4`
- `OLEAUT32!__imp_VariantInit` at `0x180067682`
- `OLEAUT32!__imp_VariantInit` at `0x180067171`
- `OLEAUT32!__imp_VariantInit` at `0x180067199`
- `OLEAUT32!__imp_VariantInit` at `0x1800671c1`
- `OLEAUT32!__imp_VariantInit` at `0x1800671e4`
- `OLEAUT32!__imp_VariantInit` at `0x180067682`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall DmDeleteTaskFolder(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  char v6; // al
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  __int128 v14; // xmm6
  IRecordInfo *v15; // xmm7_8
  int v16; // ebx
  char v17; // al
  LPVOID v18; // rbx
  __int64 v19; // rdi
  __int64 *v20; // rax
  __int64 v21; // rdx
  int v22; // ebx
  char v23; // al
  _QWORD *v24; // rbx
  __int64 v25; // rdi
  __int64 *v26; // rax
  __int64 v27; // rdx
  int v28; // ebx
  char v29; // al
  _QWORD *v30; // rbx
  __int64 v31; // rdi
  __int64 *v32; // rax
  __int64 v33; // rdx
  int v34; // ebx
  char v35; // al
  char v36; // cl
  int v37; // ebx
  LONG i; // edi
  _QWORD *v39; // rdi
  __int64 v40; // r15
  __int64 *v41; // rax
  __int64 v42; // rdx
  _QWORD *v43; // rdi
  __int64 v44; // r14
  __int64 *v45; // rax
  __int64 v46; // rdx
  char v47; // al
  char v48; // al
  int ppv; // [rsp+20h] [rbp-1B8h]
  __int64 v50; // [rsp+30h] [rbp-1A8h] BYREF
  _QWORD *v51; // [rsp+38h] [rbp-1A0h] BYREF
  _bstr_t::Data_t *v52; // [rsp+40h] [rbp-198h] BYREF
  __int64 v53; // [rsp+48h] [rbp-190h] BYREF
  _QWORD *v54; // [rsp+50h] [rbp-188h] BYREF
  LPVOID v55; // [rsp+58h] [rbp-180h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-178h] BYREF
  VARIANTARG v57; // [rsp+68h] [rbp-170h] BYREF
  VARIANTARG v58; // [rsp+80h] [rbp-158h] BYREF
  VARIANTARG v59; // [rsp+A0h] [rbp-138h] BYREF
  VARIANTARG v60; // [rsp+B8h] [rbp-120h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-108h] BYREF
  int v62[4]; // [rsp+F0h] [rbp-E8h] BYREF
  IRecordInfo *v63; // [rsp+100h] [rbp-D8h]
  __int128 v64; // [rsp+110h] [rbp-C8h] BYREF
  IRecordInfo *v65; // [rsp+120h] [rbp-B8h]
  __int128 v66; // [rsp+130h] [rbp-A8h] BYREF
  IRecordInfo *v67; // [rsp+140h] [rbp-98h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]
  char v69; // [rsp+1F0h] [rbp+18h] BYREF
  LONG v70; // [rsp+1F8h] [rbp+20h] BYREF

  wil::CoInitializeEx(&v69);
  v55 = 0;
  v54 = 0;
  v51 = 0;
  v50 = 0;
  v53 = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v55);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15B,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v55);
    v6 = v69;
    v69 = 0;
    if ( v6 )
      CoUninitialize();
    return v5;
  }
  v8 = v55;
  v9 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v55 + 80LL);
  VariantInit(&pvarg);
  v10 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v60);
  v12 = *(_OWORD *)&v60.vt;
  v13 = v60.pRecInfo;
  VariantInit(&v59);
  v14 = *(_OWORD *)&v59.vt;
  v15 = v59.pRecInfo;
  VariantInit(&v57);
  *(_OWORD *)v62 = v10;
  v63 = pRecInfo;
  v64 = v12;
  v65 = v13;
  v66 = v14;
  v67 = v15;
  v58 = v57;
  v16 = v9(v8, &v58, &v66, &v64);
  _variant_t::~_variant_t((_variant_t *)&v57);
  _variant_t::~_variant_t((_variant_t *)&v59);
  _variant_t::~_variant_t((_variant_t *)&v60);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15C,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v16,
      (int)v62);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v55);
    v17 = v69;
    v69 = 0;
    if ( v17 )
      CoUninitialize();
    return (unsigned int)v16;
  }
  v18 = v55;
  v19 = *(_QWORD *)v55;
  v20 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v52, (const unsigned __int16 *)"\\");
  if ( v20 )
    v21 = *v20;
  else
    v21 = 0;
  v22 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v19 + 56))(v18, v21, &v54);
  if ( v52 )
    _bstr_t::Data_t::Release(v52);
  if ( (unsigned int)(v22 + 2147024894) <= 1 )
  {
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v55);
    v48 = v69;
    v69 = 0;
    if ( v48 )
      CoUninitialize();
    return 1;
  }
  else
  {
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x164,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
        (const char *)(unsigned int)v22,
        (int)v62);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v55);
      v23 = v69;
      v69 = 0;
      if ( v23 )
        CoUninitialize();
      return (unsigned int)v22;
    }
    v24 = v54;
    v25 = *v54;
    v26 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v52, a1);
    if ( v26 )
      v27 = *v26;
    else
      v27 = 0;
    v28 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD **))(v25 + 72))(v24, v27, &v51);
    if ( v52 )
      _bstr_t::Data_t::Release(v52);
    if ( (unsigned int)(v28 + 2147024894) <= 1 )
    {
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v55);
      v47 = v69;
      v69 = 0;
      if ( v47 )
        CoUninitialize();
      return 1;
    }
    else
    {
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16C,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
          (const char *)(unsigned int)v28,
          (int)v62);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v55);
        v29 = v69;
        v69 = 0;
        if ( v29 )
          CoUninitialize();
        return (unsigned int)v28;
      }
      if ( !a2 )
      {
        ATL::CComPtr<ITaskFolder>::operator=(&v50, &v51);
LABEL_44:
        v37 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v50 + 112LL))(v50, 1, &v53);
        v70 = 0;
        if ( v37 >= 0 )
          v37 = (*(__int64 (__fastcall **)(__int64, LONG *))(*(_QWORD *)v53 + 56LL))(v53, &v70);
        if ( v37 >= 0 )
        {
          memset(&v57, 0, sizeof(v57));
          VariantInit(&v57);
          v57.vt = 3;
          for ( i = 1; i <= v70; ++i )
          {
            v57.lVal = i;
            v52 = 0;
            v58 = v57;
            if ( (*(int (__fastcall **)(__int64, VARIANTARG *, _bstr_t::Data_t **))(*(_QWORD *)v53 + 64LL))(
                   v53,
                   &v58,
                   &v52) >= 0 )
            {
              bstrString = 0;
              if ( (*(int (__fastcall **)(_bstr_t::Data_t *, BSTR *))(*(_QWORD *)v52 + 56LL))(v52, &bstrString) >= 0 )
                (*(void (__fastcall **)(__int64, BSTR, _QWORD))(*(_QWORD *)v50 + 120LL))(v50, bstrString, 0);
              SysFreeString(bstrString);
            }
            wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
          }
        }
        if ( a2 )
        {
          v39 = v51;
          v40 = *v51;
          v41 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v52, a2);
          if ( v41 )
            v42 = *v41;
          else
            v42 = 0;
          (*(void (__fastcall **)(_QWORD *, __int64, _QWORD))(v40 + 96))(v39, v42, 0);
        }
        else
        {
          v43 = v54;
          v44 = *v54;
          v45 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v52, a1);
          if ( v45 )
            v46 = *v45;
          else
            v46 = 0;
          (*(void (__fastcall **)(_QWORD *, __int64, _QWORD))(v44 + 96))(v43, v46, 0);
        }
        if ( v52 )
          _bstr_t::Data_t::Release(v52);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v55);
        if ( v69 )
          CoUninitialize();
        return (unsigned int)v37;
      }
      v30 = v51;
      v31 = *v51;
      v32 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v52, a2);
      if ( v32 )
        v33 = *v32;
      else
        v33 = 0;
      v34 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v31 + 72))(v30, v33, &v50);
      if ( v52 )
        _bstr_t::Data_t::Release(v52);
      if ( (unsigned int)(v34 + 2147024894) > 1 )
      {
        if ( v34 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
            (const char *)(unsigned int)v34,
            (int)v62);
          wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
          wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
          wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
          wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
          wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v55);
          v35 = v69;
          v69 = 0;
          if ( v35 )
            CoUninitialize();
          return (unsigned int)v34;
        }
        goto LABEL_44;
      }
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v55);
      v36 = v69;
      v69 = 0;
      if ( v36 )
        CoUninitialize();
      return 1;
    }
  }
}

```

## disassembly

```asm
0x180067050  mov     rax, rsp
0x180067053  mov     [rax+8], rbx
0x180067057  push    rsi
0x180067058  push    rdi
0x180067059  push    r12
0x18006705b  push    r14
0x18006705d  push    r15
0x18006705f  sub     rsp, 1B0h
0x180067066  movaps  xmmword ptr [rax-38h], xmm6
0x18006706a  movaps  xmmword ptr [rax-48h], xmm7
0x18006706e  movaps  xmmword ptr [rax-58h], xmm8
0x180067073  movaps  xmmword ptr [rax-68h], xmm9
0x180067078  movaps  xmmword ptr [rax-78h], xmm10
0x18006707d  movaps  xmmword ptr [rax-88h], xmm11
0x180067085  mov     r14, rdx
0x180067088  mov     r15, rcx
0x18006708b  lea     rcx, [rax+18h]
0x18006708f  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x180067094  nop
0x180067095  xor     esi, esi
0x180067097  mov     [rsp+1D8h+var_180], rsi
0x18006709c  mov     [rsp+1D8h+var_188], rsi
0x1800670a1  mov     [rsp+1D8h+var_1A0], rsi
0x1800670a6  mov     [rsp+1D8h+var_1A8], rsi
0x1800670ab  mov     [rsp+1D8h+var_190], rsi
0x1800670b0  lea     rax, [rsp+1D8h+var_180]
0x1800670b5  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x1800670ba  lea     r9, IID_ITaskService; riid
0x1800670c1  lea     r12d, [rsi+1]
0x1800670c5  mov     r8d, r12d; dwClsContext
0x1800670c8  xor     edx, edx; pUnkOuter
0x1800670ca  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800670d1  call    cs:__imp_CoCreateInstance
0x1800670d8  nop     dword ptr [rax+rax+00h]
0x1800670dd  mov     ebx, eax
0x1800670df  test    eax, eax
0x1800670e1  jns     short loc_18006715D
0x1800670e3  mov     rcx, [rsp+1D8h]; this
0x1800670eb  mov     r9d, eax; char *
0x1800670ee  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x1800670f5  mov     edx, 15Bh; void *
0x1800670fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800670ff  nop
0x180067100  lea     rcx, [rsp+1D8h+var_190]
0x180067105  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006710a  nop
0x18006710b  lea     rcx, [rsp+1D8h+var_1A8]
0x180067110  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067115  nop
0x180067116  lea     rcx, [rsp+1D8h+var_1A0]
0x18006711b  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067120  nop
0x180067121  lea     rcx, [rsp+1D8h+var_188]
0x180067126  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006712b  nop
0x18006712c  lea     rcx, [rsp+1D8h+var_180]
0x180067131  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067136  nop
0x180067137  mov     al, [rsp+1D8h+arg_10]
0x18006713e  mov     [rsp+1D8h+arg_10], sil
0x180067146  test    al, al
0x180067148  jz      short loc_180067156
0x18006714a  call    cs:__imp_CoUninitialize
0x180067151  nop     dword ptr [rax+rax+00h]
0x180067156  mov     eax, ebx
0x180067158  jmp     loc_1800678E0
0x18006715d  mov     rdi, [rsp+1D8h+var_180]
0x180067162  mov     rax, [rdi]
0x180067165  mov     rbx, [rax+50h]
0x180067169  lea     rcx, [rsp+1D8h+pvarg]; pvarg
0x180067171  call    cs:__imp_VariantInit
0x180067178  nop     dword ptr [rax+rax+00h]
0x18006717d  nop
0x18006717e  movups  xmm10, xmmword ptr [rsp+1D8h+pvarg]
0x180067187  movsd   xmm11, qword ptr [rsp+1D8h+pvarg+10h]
0x180067191  lea     rcx, [rsp+1D8h+var_120]; pvarg
0x180067199  call    cs:__imp_VariantInit
0x1800671a0  nop     dword ptr [rax+rax+00h]
0x1800671a5  nop
0x1800671a6  movups  xmm8, xmmword ptr [rsp+1D8h+var_120]
0x1800671af  movsd   xmm9, qword ptr [rsp+1D8h+var_120+10h]
0x1800671b9  lea     rcx, [rsp+1D8h+var_138]; pvarg
0x1800671c1  call    cs:__imp_VariantInit
0x1800671c8  nop     dword ptr [rax+rax+00h]
0x1800671cd  nop
0x1800671ce  movups  xmm6, xmmword ptr [rsp+1D8h+var_138]
0x1800671d6  movsd   xmm7, qword ptr [rsp+1D8h+var_138+10h]
0x1800671df  lea     rcx, [rsp+1D8h+var_170]; pvarg
0x1800671e4  call    cs:__imp_VariantInit
0x1800671eb  nop     dword ptr [rax+rax+00h]
0x1800671f0  nop
0x1800671f1  movups  xmm0, xmmword ptr [rsp+1D8h+var_170]
0x1800671f6  movsd   xmm1, qword ptr [rsp+1D8h+var_170+10h]
0x1800671fc  movaps  xmmword ptr [rsp+1D8h+var_E8], xmm10
0x180067205  movsd   [rsp+1D8h+var_D8], xmm11
0x18006720f  movaps  [rsp+1D8h+var_C8], xmm8
0x180067218  movsd   [rsp+1D8h+var_B8], xmm9
0x180067222  movaps  [rsp+1D8h+var_A8], xmm6
0x18006722a  movsd   [rsp+1D8h+var_98], xmm7
0x180067233  movaps  [rsp+1D8h+var_158], xmm0
0x18006723b  movsd   [rsp+1D8h+var_148], xmm1
0x180067244  lea     rax, [rsp+1D8h+var_E8]
0x18006724c  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x180067251  lea     r9, [rsp+1D8h+var_C8]
0x180067259  lea     r8, [rsp+1D8h+var_A8]
0x180067261  lea     rdx, [rsp+1D8h+var_158]
0x180067269  mov     rcx, rdi
0x18006726c  mov     rax, rbx
0x18006726f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067274  mov     ebx, eax
0x180067276  lea     rcx, [rsp+1D8h+var_170]; this
0x18006727b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180067280  nop
0x180067281  lea     rcx, [rsp+1D8h+var_138]; this
0x180067289  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006728e  nop
0x18006728f  lea     rcx, [rsp+1D8h+var_120]; this
0x180067297  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006729c  nop
0x18006729d  lea     rcx, [rsp+1D8h+pvarg]; this
0x1800672a5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800672aa  test    ebx, ebx
0x1800672ac  jns     short loc_180067328
0x1800672ae  mov     rcx, [rsp+1D8h]; this
0x1800672b6  mov     r9d, ebx; char *
0x1800672b9  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x1800672c0  mov     edx, 15Ch; void *
0x1800672c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800672ca  nop
0x1800672cb  lea     rcx, [rsp+1D8h+var_190]
0x1800672d0  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800672d5  nop
0x1800672d6  lea     rcx, [rsp+1D8h+var_1A8]
0x1800672db  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800672e0  nop
0x1800672e1  lea     rcx, [rsp+1D8h+var_1A0]
0x1800672e6  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800672eb  nop
0x1800672ec  lea     rcx, [rsp+1D8h+var_188]
0x1800672f1  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800672f6  nop
0x1800672f7  lea     rcx, [rsp+1D8h+var_180]
0x1800672fc  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067301  nop
0x180067302  mov     al, [rsp+1D8h+arg_10]
0x180067309  mov     [rsp+1D8h+arg_10], sil
0x180067311  test    al, al
0x180067313  jz      short loc_180067321
0x180067315  call    cs:__imp_CoUninitialize
0x18006731c  nop     dword ptr [rax+rax+00h]
0x180067321  mov     eax, ebx
0x180067323  jmp     loc_1800678E0
0x180067328  mov     rbx, [rsp+1D8h+var_180]
0x18006732d  mov     rdi, [rbx]
0x180067330  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned __int16 *
0x180067337  lea     rcx, [rsp+1D8h+var_198]; this
0x18006733c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180067341  nop
0x180067342  mov     rax, [rax]
0x180067345  test    rax, rax
0x180067348  jz      short loc_18006734F
0x18006734a  mov     rdx, [rax]
0x18006734d  jmp     short loc_180067352
0x18006734f  mov     rdx, rsi
0x180067352  lea     r8, [rsp+1D8h+var_188]
0x180067357  mov     rcx, rbx
0x18006735a  mov     rax, [rdi+38h]
0x18006735e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067363  mov     ebx, eax
0x180067365  mov     rcx, [rsp+1D8h+var_198]; this
0x18006736a  test    rcx, rcx
0x18006736d  jz      short loc_180067374
0x18006736f  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x180067374  lea     eax, [rbx+7FF8FFFEh]
0x18006737a  cmp     eax, r12d
0x18006737d  jbe     loc_18006782D
0x180067383  test    ebx, ebx
0x180067385  jns     short loc_180067401
0x180067387  mov     rcx, [rsp+1D8h]; this
0x18006738f  mov     r9d, ebx; char *
0x180067392  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180067399  mov     edx, 164h; void *
0x18006739e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800673a3  nop
0x1800673a4  lea     rcx, [rsp+1D8h+var_190]
0x1800673a9  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800673ae  nop
0x1800673af  lea     rcx, [rsp+1D8h+var_1A8]
0x1800673b4  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800673b9  nop
0x1800673ba  lea     rcx, [rsp+1D8h+var_1A0]
0x1800673bf  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800673c4  nop
0x1800673c5  lea     rcx, [rsp+1D8h+var_188]
0x1800673ca  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800673cf  nop
0x1800673d0  lea     rcx, [rsp+1D8h+var_180]
0x1800673d5  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800673da  nop
0x1800673db  mov     al, [rsp+1D8h+arg_10]
0x1800673e2  mov     [rsp+1D8h+arg_10], sil
0x1800673ea  test    al, al
0x1800673ec  jz      short loc_1800673FA
0x1800673ee  call    cs:__imp_CoUninitialize
0x1800673f5  nop     dword ptr [rax+rax+00h]
0x1800673fa  mov     eax, ebx
0x1800673fc  jmp     loc_1800678E0
0x180067401  mov     rbx, [rsp+1D8h+var_188]
0x180067406  mov     rdi, [rbx]
0x180067409  mov     rdx, r15; unsigned __int16 *
0x18006740c  lea     rcx, [rsp+1D8h+var_198]; this
0x180067411  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180067416  nop
0x180067417  mov     rax, [rax]
0x18006741a  test    rax, rax
0x18006741d  jz      short loc_180067424
0x18006741f  mov     rdx, [rax]
0x180067422  jmp     short loc_180067427
0x180067424  mov     rdx, rsi
0x180067427  lea     r8, [rsp+1D8h+var_1A0]
0x18006742c  mov     rcx, rbx
0x18006742f  mov     rax, [rdi+48h]
0x180067433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067438  mov     ebx, eax
0x18006743a  mov     rcx, [rsp+1D8h+var_198]; this
0x18006743f  test    rcx, rcx
0x180067442  jz      short loc_180067449
0x180067444  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x180067449  lea     eax, [rbx+7FF8FFFEh]
0x18006744f  cmp     eax, r12d
0x180067452  jbe     loc_1800677CF
0x180067458  test    ebx, ebx
0x18006745a  jns     short loc_1800674D6
0x18006745c  mov     rcx, [rsp+1D8h]; this
0x180067464  mov     r9d, ebx; char *
0x180067467  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x18006746e  mov     edx, 16Ch; void *
0x180067473  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067478  nop
0x180067479  lea     rcx, [rsp+1D8h+var_190]
0x18006747e  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067483  nop
0x180067484  lea     rcx, [rsp+1D8h+var_1A8]
0x180067489  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006748e  nop
0x18006748f  lea     rcx, [rsp+1D8h+var_1A0]
0x180067494  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067499  nop
0x18006749a  lea     rcx, [rsp+1D8h+var_188]
0x18006749f  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800674a4  nop
0x1800674a5  lea     rcx, [rsp+1D8h+var_180]
0x1800674aa  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800674af  nop
0x1800674b0  mov     al, [rsp+1D8h+arg_10]
0x1800674b7  mov     [rsp+1D8h+arg_10], sil
0x1800674bf  test    al, al
0x1800674c1  jz      short loc_1800674CF
0x1800674c3  call    cs:__imp_CoUninitialize
0x1800674ca  nop     dword ptr [rax+rax+00h]
0x1800674cf  mov     eax, ebx
0x1800674d1  jmp     loc_1800678E0
0x1800674d6  test    r14, r14
0x1800674d9  jz      loc_180067616
0x1800674df  mov     rbx, [rsp+1D8h+var_1A0]
0x1800674e4  mov     rdi, [rbx]
0x1800674e7  mov     rdx, r14; unsigned __int16 *
0x1800674ea  lea     rcx, [rsp+1D8h+var_198]; this
0x1800674ef  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800674f4  nop
0x1800674f5  mov     rax, [rax]
0x1800674f8  test    rax, rax
0x1800674fb  jz      short loc_180067502
0x1800674fd  mov     rdx, [rax]
0x180067500  jmp     short loc_180067505
0x180067502  mov     rdx, rsi
0x180067505  lea     r8, [rsp+1D8h+var_1A8]
0x18006750a  mov     rcx, rbx
0x18006750d  mov     rax, [rdi+48h]
0x180067511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067516  mov     ebx, eax
0x180067518  mov     rcx, [rsp+1D8h+var_198]; this
0x18006751d  test    rcx, rcx
0x180067520  jz      short loc_180067527
0x180067522  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x180067527  lea     eax, [rbx+7FF8FFFEh]
0x18006752d  cmp     eax, r12d
0x180067530  jbe     loc_1800675B8
0x180067536  test    ebx, ebx
0x180067538  jns     loc_180067625
0x18006753e  mov     rcx, [rsp+1D8h]; this
0x180067546  mov     r9d, ebx; char *
0x180067549  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180067550  mov     edx, 176h; void *
0x180067555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006755a  nop
0x18006755b  lea     rcx, [rsp+1D8h+var_190]
0x180067560  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067565  nop
0x180067566  lea     rcx, [rsp+1D8h+var_1A8]
  ... truncated ...
```
