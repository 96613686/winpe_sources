# DmEnableTask(ushort const *,ushort const *,ushort const *)

- ea: `0x180068000`
- end: `0x1800686d1`
- name: `?DmEnableTask@@YAJPEBG00@Z`
- size: `1745`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180007640`
- `0x180057c6c`
- `0x18005e62c`
- `0x18005e708`
- `0x18005e7f8`
- `0x18005e820`
- `0x1800651fc`
- `0x180068000`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006807c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006807c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800680ea`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800682a1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800683a2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800684aa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800685b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068641`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006868f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800680ea`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800682a1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800683a2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800684aa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800685b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068641`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006868f`
- `OLEAUT32!__imp_SysFreeString` at `0x180068313`
- `OLEAUT32!__imp_SysFreeString` at `0x18006841b`
- `OLEAUT32!__imp_SysFreeString` at `0x180068529`
- `OLEAUT32!__imp_SysFreeString` at `0x180068313`
- `OLEAUT32!__imp_SysFreeString` at `0x18006841b`
- `OLEAUT32!__imp_SysFreeString` at `0x180068529`
- `OLEAUT32!__imp_VariantInit` at `0x180068111`
- `OLEAUT32!__imp_VariantInit` at `0x180068139`
- `OLEAUT32!__imp_VariantInit` at `0x18006815e`
- `OLEAUT32!__imp_VariantInit` at `0x18006817e`
- `OLEAUT32!__imp_VariantInit` at `0x180068111`
- `OLEAUT32!__imp_VariantInit` at `0x180068139`
- `OLEAUT32!__imp_VariantInit` at `0x18006815e`
- `OLEAUT32!__imp_VariantInit` at `0x18006817e`

## pseudocode

```c
__int64 __fastcall DmEnableTask(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  char v8; // al
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v12; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v14; // xmm8
  IRecordInfo *v15; // xmm9_8
  __int128 v16; // xmm6
  IRecordInfo *v17; // xmm7_8
  int v18; // ebx
  char v19; // al
  LPVOID v20; // rbx
  __int64 v21; // rdi
  __int64 *v22; // rax
  __int64 v23; // rdx
  const struct std::nothrow_t *v24; // rdx
  int v25; // r14d
  BSTR *v26; // rbx
  BSTR v27; // rcx
  char v28; // al
  _QWORD *v29; // rbx
  __int64 v30; // r14
  __int64 *v31; // rax
  __int64 v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  int v34; // r14d
  BSTR *v35; // rbx
  BSTR v36; // rcx
  char v37; // al
  _QWORD *v38; // rbx
  __int64 v39; // r14
  __int64 *v40; // rax
  __int64 v41; // rdx
  const struct std::nothrow_t *v42; // rdx
  int v43; // r14d
  BSTR *v44; // rbx
  BSTR v45; // rcx
  char v46; // al
  int v47; // eax
  unsigned int v48; // ebx
  char v49; // al
  int ppv; // [rsp+20h] [rbp-1B8h]
  _QWORD *v51; // [rsp+30h] [rbp-1A8h] BYREF
  _QWORD *v52; // [rsp+38h] [rbp-1A0h] BYREF
  LPVOID v53; // [rsp+40h] [rbp-198h] BYREF
  __int64 v54; // [rsp+50h] [rbp-188h] BYREF
  void *v55; // [rsp+58h] [rbp-180h] BYREF
  VARIANTARG v56; // [rsp+60h] [rbp-178h] BYREF
  VARIANTARG v57; // [rsp+78h] [rbp-160h] BYREF
  VARIANTARG v58; // [rsp+90h] [rbp-148h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-130h] BYREF
  int v60[4]; // [rsp+C0h] [rbp-118h] BYREF
  IRecordInfo *v61; // [rsp+D0h] [rbp-108h]
  __int128 v62; // [rsp+E0h] [rbp-F8h] BYREF
  IRecordInfo *v63; // [rsp+F0h] [rbp-E8h]
  __int128 v64; // [rsp+100h] [rbp-D8h] BYREF
  IRecordInfo *v65; // [rsp+110h] [rbp-C8h]
  VARIANTARG v66; // [rsp+120h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]
  char v68; // [rsp+1F8h] [rbp+20h] BYREF

  wil::CoInitializeEx(&v68);
  v53 = 0;
  v52 = 0;
  v51 = 0;
  v54 = 0;
  v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v53);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x239,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
    v8 = v68;
    v68 = 0;
    if ( v8 )
      CoUninitialize();
    return v7;
  }
  v10 = v53;
  v11 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v53 + 80LL);
  VariantInit(&pvarg);
  v12 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v58);
  v14 = *(_OWORD *)&v58.vt;
  v15 = v58.pRecInfo;
  VariantInit(&v57);
  v16 = *(_OWORD *)&v57.vt;
  v17 = v57.pRecInfo;
  VariantInit(&v56);
  *(_OWORD *)v60 = v12;
  v61 = pRecInfo;
  v62 = v14;
  v63 = v15;
  v64 = v16;
  v65 = v17;
  v66 = v56;
  v18 = v11(v10, &v66, &v64, &v62);
  _variant_t::~_variant_t((_variant_t *)&v56);
  _variant_t::~_variant_t((_variant_t *)&v57);
  _variant_t::~_variant_t((_variant_t *)&v58);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23B,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v18,
      (int)v60);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
    v19 = v68;
    v68 = 0;
    if ( v19 )
      CoUninitialize();
    return (unsigned int)v18;
  }
  v20 = v53;
  v21 = *(_QWORD *)v53;
  v22 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v55, a1);
  if ( v22 )
    v23 = *v22;
  else
    v23 = 0;
  v25 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v21 + 56))(v20, v23, &v52);
  v26 = (BSTR *)v55;
  if ( v55 && _InterlockedExchangeAdd((volatile signed __int32 *)v55 + 4, 0xFFFFFFFF) == 1 && v26 )
  {
    if ( *v26 )
    {
      SysFreeString(*v26);
      *v26 = 0;
    }
    v27 = v26[1];
    if ( v27 )
    {
      operator delete(v27, v24);
      v26[1] = 0;
    }
    operator delete(v26, (const struct std::nothrow_t *)0x18);
  }
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v25,
      (int)v60);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
    v28 = v68;
    v68 = 0;
    if ( v28 )
      CoUninitialize();
    return (unsigned int)v25;
  }
  if ( a2 )
  {
    v29 = v52;
    v30 = *v52;
    v31 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v55, a2);
    if ( v31 )
      v32 = *v31;
    else
      v32 = 0;
    v34 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD **))(v30 + 72))(v29, v32, &v51);
    v35 = (BSTR *)v55;
    if ( v55 && _InterlockedExchangeAdd((volatile signed __int32 *)v55 + 4, 0xFFFFFFFF) == 1 && v35 )
    {
      if ( *v35 )
      {
        SysFreeString(*v35);
        *v35 = 0;
      }
      v36 = v35[1];
      if ( v36 )
      {
        operator delete(v36, v33);
        v35[1] = 0;
      }
      operator delete(v35, (const struct std::nothrow_t *)0x18);
    }
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
        (const char *)(unsigned int)v34,
        (int)v60);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
      v37 = v68;
      v68 = 0;
      if ( v37 )
        CoUninitialize();
      return (unsigned int)v34;
    }
  }
  else
  {
    ATL::CComPtr<ITaskFolder>::operator=(&v51, &v52);
  }
  v38 = v51;
  v39 = *v51;
  v40 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v55, a3);
  if ( v40 )
    v41 = *v40;
  else
    v41 = 0;
  v43 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v39 + 104))(v38, v41, &v54);
  v44 = (BSTR *)v55;
  if ( v55 && _InterlockedExchangeAdd((volatile signed __int32 *)v55 + 4, 0xFFFFFFFF) == 1 && v44 )
  {
    if ( *v44 )
    {
      SysFreeString(*v44);
      *v44 = 0;
    }
    v45 = v44[1];
    if ( v45 )
    {
      operator delete(v45, v42);
      v44[1] = 0;
    }
    operator delete(v44, (const struct std::nothrow_t *)0x18);
  }
  if ( v43 >= 0 )
  {
    v47 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 88LL))(v54, 0xFFFFFFFFLL);
    v48 = v47;
    if ( v47 >= 0 )
    {
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
      if ( v68 )
        CoUninitialize();
      return v48;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24C,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
        (const char *)(unsigned int)v47,
        (int)v60);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
      v49 = v68;
      v68 = 0;
      if ( v49 )
        CoUninitialize();
      return v48;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v43,
      (int)v60);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v54);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
    v46 = v68;
    v68 = 0;
    if ( v46 )
      CoUninitialize();
    return (unsigned int)v43;
  }
}

```

## disassembly

```asm
0x180068000  mov     rax, rsp
0x180068003  push    rbx
0x180068004  push    rsi
0x180068005  push    rdi
0x180068006  push    r12
0x180068008  push    r14
0x18006800a  push    r15
0x18006800c  sub     rsp, 1A8h
0x180068013  movaps  xmmword ptr [rax-48h], xmm6
0x180068017  movaps  xmmword ptr [rax-58h], xmm7
0x18006801b  movaps  xmmword ptr [rax-68h], xmm8
0x180068020  movaps  xmmword ptr [rax-78h], xmm9
0x180068025  movaps  xmmword ptr [rax-88h], xmm10
0x18006802d  movaps  xmmword ptr [rax-98h], xmm11
0x180068035  mov     r12, r8
0x180068038  mov     r15, rdx
0x18006803b  mov     r14, rcx
0x18006803e  lea     rcx, [rax+20h]
0x180068042  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x180068047  nop
0x180068048  xor     esi, esi
0x18006804a  mov     [rsp+1D8h+var_198], rsi
0x18006804f  mov     [rsp+1D8h+var_1A0], rsi
0x180068054  mov     [rsp+1D8h+var_1A8], rsi
0x180068059  mov     [rsp+1D8h+var_188], rsi
0x18006805e  lea     rax, [rsp+1D8h+var_198]
0x180068063  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x180068068  lea     r9, IID_ITaskService; riid
0x18006806f  xor     edx, edx; pUnkOuter
0x180068071  lea     r8d, [rsi+1]; dwClsContext
0x180068075  lea     rcx, CLSID_TaskScheduler; rclsid
0x18006807c  call    cs:__imp_CoCreateInstance
0x180068083  nop     dword ptr [rax+rax+00h]
0x180068088  mov     ebx, eax
0x18006808a  test    eax, eax
0x18006808c  jns     short loc_1800680FD
0x18006808e  mov     rcx, [rsp+1D8h]; this
0x180068096  mov     r9d, eax; char *
0x180068099  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x1800680a0  mov     edx, 239h; void *
0x1800680a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800680aa  nop
0x1800680ab  lea     rcx, [rsp+1D8h+var_188]
0x1800680b0  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800680b5  nop
0x1800680b6  lea     rcx, [rsp+1D8h+var_1A8]
0x1800680bb  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800680c0  nop
0x1800680c1  lea     rcx, [rsp+1D8h+var_1A0]
0x1800680c6  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800680cb  nop
0x1800680cc  lea     rcx, [rsp+1D8h+var_198]
0x1800680d1  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800680d6  nop
0x1800680d7  mov     al, [rsp+1D8h+arg_18]
0x1800680de  mov     [rsp+1D8h+arg_18], sil
0x1800680e6  test    al, al
0x1800680e8  jz      short loc_1800680F6
0x1800680ea  call    cs:__imp_CoUninitialize
0x1800680f1  nop     dword ptr [rax+rax+00h]
0x1800680f6  mov     eax, ebx
0x1800680f8  jmp     loc_18006869D
0x1800680fd  mov     rdi, [rsp+1D8h+var_198]
0x180068102  mov     rax, [rdi]
0x180068105  mov     rbx, [rax+50h]
0x180068109  lea     rcx, [rsp+1D8h+pvarg]; pvarg
0x180068111  call    cs:__imp_VariantInit
0x180068118  nop     dword ptr [rax+rax+00h]
0x18006811d  nop
0x18006811e  movups  xmm10, xmmword ptr [rsp+1D8h+pvarg]
0x180068127  movsd   xmm11, qword ptr [rsp+1D8h+pvarg+10h]
0x180068131  lea     rcx, [rsp+1D8h+var_148]; pvarg
0x180068139  call    cs:__imp_VariantInit
0x180068140  nop     dword ptr [rax+rax+00h]
0x180068145  nop
0x180068146  movups  xmm8, xmmword ptr [rsp+1D8h+var_148]
0x18006814f  movsd   xmm9, qword ptr [rsp+1D8h+var_148+10h]
0x180068159  lea     rcx, [rsp+1D8h+var_160]; pvarg
0x18006815e  call    cs:__imp_VariantInit
0x180068165  nop     dword ptr [rax+rax+00h]
0x18006816a  nop
0x18006816b  movups  xmm6, xmmword ptr [rsp+1D8h+var_160]
0x180068170  movsd   xmm7, qword ptr [rsp+1D8h+var_160+10h]
0x180068179  lea     rcx, [rsp+1D8h+var_178]; pvarg
0x18006817e  call    cs:__imp_VariantInit
0x180068185  nop     dword ptr [rax+rax+00h]
0x18006818a  nop
0x18006818b  movups  xmm0, xmmword ptr [rsp+1D8h+var_178]
0x180068190  movsd   xmm1, qword ptr [rsp+1D8h+var_178+10h]
0x180068196  movaps  xmmword ptr [rsp+1D8h+var_118], xmm10
0x18006819f  movsd   [rsp+1D8h+var_108], xmm11
0x1800681a9  movaps  [rsp+1D8h+var_F8], xmm8
0x1800681b2  movsd   [rsp+1D8h+var_E8], xmm9
0x1800681bc  movaps  [rsp+1D8h+var_D8], xmm6
0x1800681c4  movsd   [rsp+1D8h+var_C8], xmm7
0x1800681cd  movaps  [rsp+1D8h+var_B8], xmm0
0x1800681d5  movsd   [rsp+1D8h+var_A8], xmm1
0x1800681de  lea     rax, [rsp+1D8h+var_118]
0x1800681e6  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x1800681eb  lea     r9, [rsp+1D8h+var_F8]
0x1800681f3  lea     r8, [rsp+1D8h+var_D8]
0x1800681fb  lea     rdx, [rsp+1D8h+var_B8]
0x180068203  mov     rcx, rdi
0x180068206  mov     rax, rbx
0x180068209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006820e  mov     ebx, eax
0x180068210  lea     rcx, [rsp+1D8h+var_178]; this
0x180068215  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006821a  nop
0x18006821b  lea     rcx, [rsp+1D8h+var_160]; this
0x180068220  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180068225  nop
0x180068226  lea     rcx, [rsp+1D8h+var_148]; this
0x18006822e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180068233  nop
0x180068234  lea     rcx, [rsp+1D8h+pvarg]; this
0x18006823c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180068241  test    ebx, ebx
0x180068243  jns     short loc_1800682B4
0x180068245  mov     rcx, [rsp+1D8h]; this
0x18006824d  mov     r9d, ebx; char *
0x180068250  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180068257  mov     edx, 23Bh; void *
0x18006825c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068261  nop
0x180068262  lea     rcx, [rsp+1D8h+var_188]
0x180068267  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006826c  nop
0x18006826d  lea     rcx, [rsp+1D8h+var_1A8]
0x180068272  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068277  nop
0x180068278  lea     rcx, [rsp+1D8h+var_1A0]
0x18006827d  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068282  nop
0x180068283  lea     rcx, [rsp+1D8h+var_198]
0x180068288  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006828d  nop
0x18006828e  mov     al, [rsp+1D8h+arg_18]
0x180068295  mov     [rsp+1D8h+arg_18], sil
0x18006829d  test    al, al
0x18006829f  jz      short loc_1800682AD
0x1800682a1  call    cs:__imp_CoUninitialize
0x1800682a8  nop     dword ptr [rax+rax+00h]
0x1800682ad  mov     eax, ebx
0x1800682af  jmp     loc_18006869D
0x1800682b4  mov     rbx, [rsp+1D8h+var_198]
0x1800682b9  mov     rdi, [rbx]
0x1800682bc  mov     rdx, r14; unsigned __int16 *
0x1800682bf  lea     rcx, [rsp+1D8h+var_180]; this
0x1800682c4  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800682c9  nop
0x1800682ca  mov     rax, [rax]
0x1800682cd  test    rax, rax
0x1800682d0  jz      short loc_1800682D7
0x1800682d2  mov     rdx, [rax]
0x1800682d5  jmp     short loc_1800682DA
0x1800682d7  mov     rdx, rsi
0x1800682da  lea     r8, [rsp+1D8h+var_1A0]
0x1800682df  mov     rcx, rbx
0x1800682e2  mov     rax, [rdi+38h]
0x1800682e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800682eb  mov     r14d, eax
0x1800682ee  mov     rbx, [rsp+1D8h+var_180]
0x1800682f3  or      edi, 0FFFFFFFFh
0x1800682f6  test    rbx, rbx
0x1800682f9  jz      short loc_180068341
0x1800682fb  mov     ecx, edi
0x1800682fd  lock xadd [rbx+10h], ecx
0x180068302  add     ecx, edi
0x180068304  jnz     short loc_180068341
0x180068306  test    rbx, rbx
0x180068309  jz      short loc_180068341
0x18006830b  cmp     [rbx], rsi
0x18006830e  jz      short loc_180068322
0x180068310  mov     rcx, [rbx]; bstrString
0x180068313  call    cs:__imp_SysFreeString
0x18006831a  nop     dword ptr [rax+rax+00h]
0x18006831f  mov     [rbx], rsi
0x180068322  mov     rcx, [rbx+8]; void *
0x180068326  test    rcx, rcx
0x180068329  jz      short loc_180068334
0x18006832b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068330  mov     [rbx+8], rsi
0x180068334  mov     edx, 18h; struct std::nothrow_t *
0x180068339  mov     rcx, rbx; void *
0x18006833c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068341  test    r14d, r14d
0x180068344  jns     short loc_1800683B6
0x180068346  mov     rcx, [rsp+1D8h]; this
0x18006834e  mov     r9d, r14d; char *
0x180068351  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180068358  mov     edx, 23Dh; void *
0x18006835d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068362  nop
0x180068363  lea     rcx, [rsp+1D8h+var_188]
0x180068368  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006836d  nop
0x18006836e  lea     rcx, [rsp+1D8h+var_1A8]
0x180068373  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068378  nop
0x180068379  lea     rcx, [rsp+1D8h+var_1A0]
0x18006837e  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068383  nop
0x180068384  lea     rcx, [rsp+1D8h+var_198]
0x180068389  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006838e  nop
0x18006838f  mov     al, [rsp+1D8h+arg_18]
0x180068396  mov     [rsp+1D8h+arg_18], sil
0x18006839e  test    al, al
0x1800683a0  jz      short loc_1800683AE
0x1800683a2  call    cs:__imp_CoUninitialize
0x1800683a9  nop     dword ptr [rax+rax+00h]
0x1800683ae  mov     eax, r14d
0x1800683b1  jmp     loc_18006869D
0x1800683b6  test    r15, r15
0x1800683b9  jz      loc_1800684BE
0x1800683bf  mov     rbx, [rsp+1D8h+var_1A0]
0x1800683c4  mov     r14, [rbx]
0x1800683c7  mov     rdx, r15; unsigned __int16 *
0x1800683ca  lea     rcx, [rsp+1D8h+var_180]; this
0x1800683cf  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800683d4  nop
0x1800683d5  mov     rax, [rax]
0x1800683d8  test    rax, rax
0x1800683db  jz      short loc_1800683E2
0x1800683dd  mov     rdx, [rax]
0x1800683e0  jmp     short loc_1800683E5
0x1800683e2  mov     rdx, rsi
0x1800683e5  lea     r8, [rsp+1D8h+var_1A8]
0x1800683ea  mov     rcx, rbx
0x1800683ed  mov     rax, [r14+48h]
0x1800683f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683f6  mov     r14d, eax
0x1800683f9  mov     rbx, [rsp+1D8h+var_180]
0x1800683fe  test    rbx, rbx
0x180068401  jz      short loc_180068449
0x180068403  mov     ecx, edi
0x180068405  lock xadd [rbx+10h], ecx
0x18006840a  add     ecx, edi
0x18006840c  jnz     short loc_180068449
0x18006840e  test    rbx, rbx
0x180068411  jz      short loc_180068449
0x180068413  cmp     [rbx], rsi
0x180068416  jz      short loc_18006842A
0x180068418  mov     rcx, [rbx]; bstrString
0x18006841b  call    cs:__imp_SysFreeString
0x180068422  nop     dword ptr [rax+rax+00h]
0x180068427  mov     [rbx], rsi
0x18006842a  mov     rcx, [rbx+8]; void *
0x18006842e  test    rcx, rcx
0x180068431  jz      short loc_18006843C
0x180068433  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068438  mov     [rbx+8], rsi
0x18006843c  mov     edx, 18h; struct std::nothrow_t *
0x180068441  mov     rcx, rbx; void *
0x180068444  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068449  test    r14d, r14d
0x18006844c  jns     short loc_1800684CD
0x18006844e  mov     rcx, [rsp+1D8h]; this
0x180068456  mov     r9d, r14d; char *
0x180068459  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180068460  mov     edx, 241h; void *
0x180068465  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006846a  nop
0x18006846b  lea     rcx, [rsp+1D8h+var_188]
0x180068470  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068475  nop
0x180068476  lea     rcx, [rsp+1D8h+var_1A8]
0x18006847b  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068480  nop
0x180068481  lea     rcx, [rsp+1D8h+var_1A0]
0x180068486  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006848b  nop
0x18006848c  lea     rcx, [rsp+1D8h+var_198]
0x180068491  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068496  nop
0x180068497  mov     al, [rsp+1D8h+arg_18]
0x18006849e  mov     [rsp+1D8h+arg_18], sil
0x1800684a6  test    al, al
0x1800684a8  jz      short loc_1800684B6
0x1800684aa  call    cs:__imp_CoUninitialize
0x1800684b1  nop     dword ptr [rax+rax+00h]
0x1800684b6  mov     eax, r14d
0x1800684b9  jmp     loc_18006869D
0x1800684be  lea     rdx, [rsp+1D8h+var_1A0]
0x1800684c3  lea     rcx, [rsp+1D8h+var_1A8]
0x1800684c8  call    ??4?$CComPtr@UITaskFolder@@@ATL@@QEAAPEAUITaskFolder@@AEBV01@@Z; ATL::CComPtr<ITaskFolder>::operator=(ATL::CComPtr<ITaskFolder> const &)
0x1800684cd  mov     rbx, [rsp+1D8h+var_1A8]
0x1800684d2  mov     r14, [rbx]
0x1800684d5  mov     rdx, r12; unsigned __int16 *
0x1800684d8  lea     rcx, [rsp+1D8h+var_180]; this
0x1800684dd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800684e2  nop
0x1800684e3  mov     rax, [rax]
0x1800684e6  test    rax, rax
0x1800684e9  jz      short loc_1800684F0
0x1800684eb  mov     rdx, [rax]
0x1800684ee  jmp     short loc_1800684F3
0x1800684f0  mov     rdx, rsi
0x1800684f3  lea     r8, [rsp+1D8h+var_188]
  ... truncated ...
```
