# DmDisableTask(ushort const *,ushort const *,ushort const *)

- ea: `0x180067920`
- end: `0x180067ff1`
- name: `?DmDisableTask@@YAJPEBG00@Z`
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
- `0x180067920`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006799c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006799c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067a0a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067bc1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067cc2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067dca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067ed8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067f61`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067faf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067a0a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067bc1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067cc2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067dca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067ed8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067f61`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067faf`
- `OLEAUT32!__imp_SysFreeString` at `0x180067c33`
- `OLEAUT32!__imp_SysFreeString` at `0x180067d3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180067e49`
- `OLEAUT32!__imp_SysFreeString` at `0x180067c33`
- `OLEAUT32!__imp_SysFreeString` at `0x180067d3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180067e49`
- `OLEAUT32!__imp_VariantInit` at `0x180067a31`
- `OLEAUT32!__imp_VariantInit` at `0x180067a59`
- `OLEAUT32!__imp_VariantInit` at `0x180067a7e`
- `OLEAUT32!__imp_VariantInit` at `0x180067a9e`
- `OLEAUT32!__imp_VariantInit` at `0x180067a31`
- `OLEAUT32!__imp_VariantInit` at `0x180067a59`
- `OLEAUT32!__imp_VariantInit` at `0x180067a7e`
- `OLEAUT32!__imp_VariantInit` at `0x180067a9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall DmDisableTask(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
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
      (void *)0x267,
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
      (void *)0x269,
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
      (void *)0x26B,
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
        (void *)0x26F,
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
    v47 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v54 + 88LL))(v54, 0);
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
        (void *)0x27A,
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
      (void *)0x277,
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
0x180067920  mov     rax, rsp
0x180067923  push    rbx
0x180067924  push    rsi
0x180067925  push    rdi
0x180067926  push    r12
0x180067928  push    r14
0x18006792a  push    r15
0x18006792c  sub     rsp, 1A8h
0x180067933  movaps  xmmword ptr [rax-48h], xmm6
0x180067937  movaps  xmmword ptr [rax-58h], xmm7
0x18006793b  movaps  xmmword ptr [rax-68h], xmm8
0x180067940  movaps  xmmword ptr [rax-78h], xmm9
0x180067945  movaps  xmmword ptr [rax-88h], xmm10
0x18006794d  movaps  xmmword ptr [rax-98h], xmm11
0x180067955  mov     r12, r8
0x180067958  mov     r15, rdx
0x18006795b  mov     r14, rcx
0x18006795e  lea     rcx, [rax+20h]
0x180067962  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x180067967  nop
0x180067968  xor     esi, esi
0x18006796a  mov     [rsp+1D8h+var_198], rsi
0x18006796f  mov     [rsp+1D8h+var_1A0], rsi
0x180067974  mov     [rsp+1D8h+var_1A8], rsi
0x180067979  mov     [rsp+1D8h+var_188], rsi
0x18006797e  lea     rax, [rsp+1D8h+var_198]
0x180067983  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x180067988  lea     r9, IID_ITaskService; riid
0x18006798f  xor     edx, edx; pUnkOuter
0x180067991  lea     r8d, [rsi+1]; dwClsContext
0x180067995  lea     rcx, CLSID_TaskScheduler; rclsid
0x18006799c  call    cs:__imp_CoCreateInstance
0x1800679a3  nop     dword ptr [rax+rax+00h]
0x1800679a8  mov     ebx, eax
0x1800679aa  test    eax, eax
0x1800679ac  jns     short loc_180067A1D
0x1800679ae  mov     rcx, [rsp+1D8h]; this
0x1800679b6  mov     r9d, eax; char *
0x1800679b9  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x1800679c0  mov     edx, 267h; void *
0x1800679c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800679ca  nop
0x1800679cb  lea     rcx, [rsp+1D8h+var_188]
0x1800679d0  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800679d5  nop
0x1800679d6  lea     rcx, [rsp+1D8h+var_1A8]
0x1800679db  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800679e0  nop
0x1800679e1  lea     rcx, [rsp+1D8h+var_1A0]
0x1800679e6  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800679eb  nop
0x1800679ec  lea     rcx, [rsp+1D8h+var_198]
0x1800679f1  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800679f6  nop
0x1800679f7  mov     al, [rsp+1D8h+arg_18]
0x1800679fe  mov     [rsp+1D8h+arg_18], sil
0x180067a06  test    al, al
0x180067a08  jz      short loc_180067A16
0x180067a0a  call    cs:__imp_CoUninitialize
0x180067a11  nop     dword ptr [rax+rax+00h]
0x180067a16  mov     eax, ebx
0x180067a18  jmp     loc_180067FBD
0x180067a1d  mov     rdi, [rsp+1D8h+var_198]
0x180067a22  mov     rax, [rdi]
0x180067a25  mov     rbx, [rax+50h]
0x180067a29  lea     rcx, [rsp+1D8h+pvarg]; pvarg
0x180067a31  call    cs:__imp_VariantInit
0x180067a38  nop     dword ptr [rax+rax+00h]
0x180067a3d  nop
0x180067a3e  movups  xmm10, xmmword ptr [rsp+1D8h+pvarg]
0x180067a47  movsd   xmm11, qword ptr [rsp+1D8h+pvarg+10h]
0x180067a51  lea     rcx, [rsp+1D8h+var_148]; pvarg
0x180067a59  call    cs:__imp_VariantInit
0x180067a60  nop     dword ptr [rax+rax+00h]
0x180067a65  nop
0x180067a66  movups  xmm8, xmmword ptr [rsp+1D8h+var_148]
0x180067a6f  movsd   xmm9, qword ptr [rsp+1D8h+var_148+10h]
0x180067a79  lea     rcx, [rsp+1D8h+var_160]; pvarg
0x180067a7e  call    cs:__imp_VariantInit
0x180067a85  nop     dword ptr [rax+rax+00h]
0x180067a8a  nop
0x180067a8b  movups  xmm6, xmmword ptr [rsp+1D8h+var_160]
0x180067a90  movsd   xmm7, qword ptr [rsp+1D8h+var_160+10h]
0x180067a99  lea     rcx, [rsp+1D8h+var_178]; pvarg
0x180067a9e  call    cs:__imp_VariantInit
0x180067aa5  nop     dword ptr [rax+rax+00h]
0x180067aaa  nop
0x180067aab  movups  xmm0, xmmword ptr [rsp+1D8h+var_178]
0x180067ab0  movsd   xmm1, qword ptr [rsp+1D8h+var_178+10h]
0x180067ab6  movaps  xmmword ptr [rsp+1D8h+var_118], xmm10
0x180067abf  movsd   [rsp+1D8h+var_108], xmm11
0x180067ac9  movaps  [rsp+1D8h+var_F8], xmm8
0x180067ad2  movsd   [rsp+1D8h+var_E8], xmm9
0x180067adc  movaps  [rsp+1D8h+var_D8], xmm6
0x180067ae4  movsd   [rsp+1D8h+var_C8], xmm7
0x180067aed  movaps  [rsp+1D8h+var_B8], xmm0
0x180067af5  movsd   [rsp+1D8h+var_A8], xmm1
0x180067afe  lea     rax, [rsp+1D8h+var_118]
0x180067b06  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x180067b0b  lea     r9, [rsp+1D8h+var_F8]
0x180067b13  lea     r8, [rsp+1D8h+var_D8]
0x180067b1b  lea     rdx, [rsp+1D8h+var_B8]
0x180067b23  mov     rcx, rdi
0x180067b26  mov     rax, rbx
0x180067b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b2e  mov     ebx, eax
0x180067b30  lea     rcx, [rsp+1D8h+var_178]; this
0x180067b35  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180067b3a  nop
0x180067b3b  lea     rcx, [rsp+1D8h+var_160]; this
0x180067b40  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180067b45  nop
0x180067b46  lea     rcx, [rsp+1D8h+var_148]; this
0x180067b4e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180067b53  nop
0x180067b54  lea     rcx, [rsp+1D8h+pvarg]; this
0x180067b5c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180067b61  test    ebx, ebx
0x180067b63  jns     short loc_180067BD4
0x180067b65  mov     rcx, [rsp+1D8h]; this
0x180067b6d  mov     r9d, ebx; char *
0x180067b70  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180067b77  mov     edx, 269h; void *
0x180067b7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067b81  nop
0x180067b82  lea     rcx, [rsp+1D8h+var_188]
0x180067b87  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067b8c  nop
0x180067b8d  lea     rcx, [rsp+1D8h+var_1A8]
0x180067b92  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067b97  nop
0x180067b98  lea     rcx, [rsp+1D8h+var_1A0]
0x180067b9d  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067ba2  nop
0x180067ba3  lea     rcx, [rsp+1D8h+var_198]
0x180067ba8  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067bad  nop
0x180067bae  mov     al, [rsp+1D8h+arg_18]
0x180067bb5  mov     [rsp+1D8h+arg_18], sil
0x180067bbd  test    al, al
0x180067bbf  jz      short loc_180067BCD
0x180067bc1  call    cs:__imp_CoUninitialize
0x180067bc8  nop     dword ptr [rax+rax+00h]
0x180067bcd  mov     eax, ebx
0x180067bcf  jmp     loc_180067FBD
0x180067bd4  mov     rbx, [rsp+1D8h+var_198]
0x180067bd9  mov     rdi, [rbx]
0x180067bdc  mov     rdx, r14; unsigned __int16 *
0x180067bdf  lea     rcx, [rsp+1D8h+var_180]; this
0x180067be4  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180067be9  nop
0x180067bea  mov     rax, [rax]
0x180067bed  test    rax, rax
0x180067bf0  jz      short loc_180067BF7
0x180067bf2  mov     rdx, [rax]
0x180067bf5  jmp     short loc_180067BFA
0x180067bf7  mov     rdx, rsi
0x180067bfa  lea     r8, [rsp+1D8h+var_1A0]
0x180067bff  mov     rcx, rbx
0x180067c02  mov     rax, [rdi+38h]
0x180067c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c0b  mov     r14d, eax
0x180067c0e  mov     rbx, [rsp+1D8h+var_180]
0x180067c13  or      edi, 0FFFFFFFFh
0x180067c16  test    rbx, rbx
0x180067c19  jz      short loc_180067C61
0x180067c1b  mov     ecx, edi
0x180067c1d  lock xadd [rbx+10h], ecx
0x180067c22  add     ecx, edi
0x180067c24  jnz     short loc_180067C61
0x180067c26  test    rbx, rbx
0x180067c29  jz      short loc_180067C61
0x180067c2b  cmp     [rbx], rsi
0x180067c2e  jz      short loc_180067C42
0x180067c30  mov     rcx, [rbx]; bstrString
0x180067c33  call    cs:__imp_SysFreeString
0x180067c3a  nop     dword ptr [rax+rax+00h]
0x180067c3f  mov     [rbx], rsi
0x180067c42  mov     rcx, [rbx+8]; void *
0x180067c46  test    rcx, rcx
0x180067c49  jz      short loc_180067C54
0x180067c4b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067c50  mov     [rbx+8], rsi
0x180067c54  mov     edx, 18h; struct std::nothrow_t *
0x180067c59  mov     rcx, rbx; void *
0x180067c5c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067c61  test    r14d, r14d
0x180067c64  jns     short loc_180067CD6
0x180067c66  mov     rcx, [rsp+1D8h]; this
0x180067c6e  mov     r9d, r14d; char *
0x180067c71  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180067c78  mov     edx, 26Bh; void *
0x180067c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067c82  nop
0x180067c83  lea     rcx, [rsp+1D8h+var_188]
0x180067c88  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067c8d  nop
0x180067c8e  lea     rcx, [rsp+1D8h+var_1A8]
0x180067c93  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067c98  nop
0x180067c99  lea     rcx, [rsp+1D8h+var_1A0]
0x180067c9e  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067ca3  nop
0x180067ca4  lea     rcx, [rsp+1D8h+var_198]
0x180067ca9  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067cae  nop
0x180067caf  mov     al, [rsp+1D8h+arg_18]
0x180067cb6  mov     [rsp+1D8h+arg_18], sil
0x180067cbe  test    al, al
0x180067cc0  jz      short loc_180067CCE
0x180067cc2  call    cs:__imp_CoUninitialize
0x180067cc9  nop     dword ptr [rax+rax+00h]
0x180067cce  mov     eax, r14d
0x180067cd1  jmp     loc_180067FBD
0x180067cd6  test    r15, r15
0x180067cd9  jz      loc_180067DDE
0x180067cdf  mov     rbx, [rsp+1D8h+var_1A0]
0x180067ce4  mov     r14, [rbx]
0x180067ce7  mov     rdx, r15; unsigned __int16 *
0x180067cea  lea     rcx, [rsp+1D8h+var_180]; this
0x180067cef  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180067cf4  nop
0x180067cf5  mov     rax, [rax]
0x180067cf8  test    rax, rax
0x180067cfb  jz      short loc_180067D02
0x180067cfd  mov     rdx, [rax]
0x180067d00  jmp     short loc_180067D05
0x180067d02  mov     rdx, rsi
0x180067d05  lea     r8, [rsp+1D8h+var_1A8]
0x180067d0a  mov     rcx, rbx
0x180067d0d  mov     rax, [r14+48h]
0x180067d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d16  mov     r14d, eax
0x180067d19  mov     rbx, [rsp+1D8h+var_180]
0x180067d1e  test    rbx, rbx
0x180067d21  jz      short loc_180067D69
0x180067d23  mov     ecx, edi
0x180067d25  lock xadd [rbx+10h], ecx
0x180067d2a  add     ecx, edi
0x180067d2c  jnz     short loc_180067D69
0x180067d2e  test    rbx, rbx
0x180067d31  jz      short loc_180067D69
0x180067d33  cmp     [rbx], rsi
0x180067d36  jz      short loc_180067D4A
0x180067d38  mov     rcx, [rbx]; bstrString
0x180067d3b  call    cs:__imp_SysFreeString
0x180067d42  nop     dword ptr [rax+rax+00h]
0x180067d47  mov     [rbx], rsi
0x180067d4a  mov     rcx, [rbx+8]; void *
0x180067d4e  test    rcx, rcx
0x180067d51  jz      short loc_180067D5C
0x180067d53  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067d58  mov     [rbx+8], rsi
0x180067d5c  mov     edx, 18h; struct std::nothrow_t *
0x180067d61  mov     rcx, rbx; void *
0x180067d64  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067d69  test    r14d, r14d
0x180067d6c  jns     short loc_180067DED
0x180067d6e  mov     rcx, [rsp+1D8h]; this
0x180067d76  mov     r9d, r14d; char *
0x180067d79  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180067d80  mov     edx, 26Fh; void *
0x180067d85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067d8a  nop
0x180067d8b  lea     rcx, [rsp+1D8h+var_188]
0x180067d90  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067d95  nop
0x180067d96  lea     rcx, [rsp+1D8h+var_1A8]
0x180067d9b  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067da0  nop
0x180067da1  lea     rcx, [rsp+1D8h+var_1A0]
0x180067da6  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067dab  nop
0x180067dac  lea     rcx, [rsp+1D8h+var_198]
0x180067db1  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180067db6  nop
0x180067db7  mov     al, [rsp+1D8h+arg_18]
0x180067dbe  mov     [rsp+1D8h+arg_18], sil
0x180067dc6  test    al, al
0x180067dc8  jz      short loc_180067DD6
0x180067dca  call    cs:__imp_CoUninitialize
0x180067dd1  nop     dword ptr [rax+rax+00h]
0x180067dd6  mov     eax, r14d
0x180067dd9  jmp     loc_180067FBD
0x180067dde  lea     rdx, [rsp+1D8h+var_1A0]
0x180067de3  lea     rcx, [rsp+1D8h+var_1A8]
0x180067de8  call    ??4?$CComPtr@UITaskFolder@@@ATL@@QEAAPEAUITaskFolder@@AEBV01@@Z; ATL::CComPtr<ITaskFolder>::operator=(ATL::CComPtr<ITaskFolder> const &)
0x180067ded  mov     rbx, [rsp+1D8h+var_1A8]
0x180067df2  mov     r14, [rbx]
0x180067df5  mov     rdx, r12; unsigned __int16 *
0x180067df8  lea     rcx, [rsp+1D8h+var_180]; this
0x180067dfd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180067e02  nop
0x180067e03  mov     rax, [rax]
0x180067e06  test    rax, rax
0x180067e09  jz      short loc_180067E10
0x180067e0b  mov     rdx, [rax]
0x180067e0e  jmp     short loc_180067E13
0x180067e10  mov     rdx, rsi
0x180067e13  lea     r8, [rsp+1D8h+var_188]
  ... truncated ...
```
