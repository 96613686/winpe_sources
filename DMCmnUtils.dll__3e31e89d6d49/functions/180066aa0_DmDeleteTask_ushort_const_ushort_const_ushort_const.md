# DmDeleteTask(ushort const *,ushort const *,ushort const *)

- ea: `0x180066aa0`
- end: `0x180067047`
- name: `?DmDeleteTask@@YAJPEBG00@Z`
- size: `1447`
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
- `0x180066aa0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180066b17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180066b17`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180066b7a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180066d26`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180066e1c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180066f19`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067005`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180066b7a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180066d26`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180066e1c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180066f19`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180067005`
- `OLEAUT32!__imp_SysFreeString` at `0x180066d98`
- `OLEAUT32!__imp_SysFreeString` at `0x180066e95`
- `OLEAUT32!__imp_SysFreeString` at `0x180066f96`
- `OLEAUT32!__imp_SysFreeString` at `0x180066d98`
- `OLEAUT32!__imp_SysFreeString` at `0x180066e95`
- `OLEAUT32!__imp_SysFreeString` at `0x180066f96`
- `OLEAUT32!__imp_VariantInit` at `0x180066ba1`
- `OLEAUT32!__imp_VariantInit` at `0x180066bc9`
- `OLEAUT32!__imp_VariantInit` at `0x180066bee`
- `OLEAUT32!__imp_VariantInit` at `0x180066c0e`
- `OLEAUT32!__imp_VariantInit` at `0x180066ba1`
- `OLEAUT32!__imp_VariantInit` at `0x180066bc9`
- `OLEAUT32!__imp_VariantInit` at `0x180066bee`
- `OLEAUT32!__imp_VariantInit` at `0x180066c0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall DmDeleteTask(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
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
  unsigned int v43; // r14d
  BSTR *v44; // rbx
  BSTR v45; // rcx
  unsigned int v46; // ebx
  int ppv; // [rsp+20h] [rbp-1B8h]
  _QWORD *v48; // [rsp+38h] [rbp-1A0h] BYREF
  _QWORD *v49; // [rsp+40h] [rbp-198h] BYREF
  LPVOID v50; // [rsp+48h] [rbp-190h] BYREF
  void *v51; // [rsp+50h] [rbp-188h] BYREF
  VARIANTARG v52; // [rsp+58h] [rbp-180h] BYREF
  VARIANTARG v53; // [rsp+70h] [rbp-168h] BYREF
  VARIANTARG v54; // [rsp+88h] [rbp-150h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-138h] BYREF
  int v56[4]; // [rsp+C0h] [rbp-118h] BYREF
  IRecordInfo *v57; // [rsp+D0h] [rbp-108h]
  __int128 v58; // [rsp+E0h] [rbp-F8h] BYREF
  IRecordInfo *v59; // [rsp+F0h] [rbp-E8h]
  __int128 v60; // [rsp+100h] [rbp-D8h] BYREF
  IRecordInfo *v61; // [rsp+110h] [rbp-C8h]
  VARIANTARG v62; // [rsp+120h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]
  char v64; // [rsp+1F8h] [rbp+20h] BYREF

  wil::CoInitializeEx(&v64);
  v50 = 0;
  v49 = 0;
  v48 = 0;
  v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v50);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v48);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v49);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
    v8 = v64;
    v64 = 0;
    if ( v8 )
      CoUninitialize();
    return v7;
  }
  v10 = v50;
  v11 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v50 + 80LL);
  VariantInit(&pvarg);
  v12 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v54);
  v14 = *(_OWORD *)&v54.vt;
  v15 = v54.pRecInfo;
  VariantInit(&v53);
  v16 = *(_OWORD *)&v53.vt;
  v17 = v53.pRecInfo;
  VariantInit(&v52);
  *(_OWORD *)v56 = v12;
  v57 = pRecInfo;
  v58 = v14;
  v59 = v15;
  v60 = v16;
  v61 = v17;
  v62 = v52;
  v18 = v11(v10, &v62, &v60, &v58);
  _variant_t::~_variant_t((_variant_t *)&v52);
  _variant_t::~_variant_t((_variant_t *)&v53);
  _variant_t::~_variant_t((_variant_t *)&v54);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v18,
      (int)v56);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v48);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v49);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
    v19 = v64;
    v64 = 0;
    if ( v19 )
      CoUninitialize();
    return (unsigned int)v18;
  }
  v20 = v50;
  v21 = *(_QWORD *)v50;
  v22 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v51, a1);
  if ( v22 )
    v23 = *v22;
  else
    v23 = 0;
  v25 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v21 + 56))(v20, v23, &v49);
  v26 = (BSTR *)v51;
  if ( v51 && _InterlockedExchangeAdd((volatile signed __int32 *)v51 + 4, 0xFFFFFFFF) == 1 && v26 )
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
      (void *)0x131,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v25,
      (int)v56);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v48);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v49);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
    v28 = v64;
    v64 = 0;
    if ( v28 )
      CoUninitialize();
    return (unsigned int)v25;
  }
  if ( a2 )
  {
    v29 = v49;
    v30 = *v49;
    v31 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v51, a2);
    if ( v31 )
      v32 = *v31;
    else
      v32 = 0;
    v34 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD **))(v30 + 72))(v29, v32, &v48);
    v35 = (BSTR *)v51;
    if ( v51 && _InterlockedExchangeAdd((volatile signed __int32 *)v51 + 4, 0xFFFFFFFF) == 1 && v35 )
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
        (void *)0x135,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
        (const char *)(unsigned int)v34,
        (int)v56);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v48);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v49);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
      v37 = v64;
      v64 = 0;
      if ( v37 )
        CoUninitialize();
      return (unsigned int)v34;
    }
  }
  else
  {
    ATL::CComPtr<ITaskFolder>::operator=(&v48, &v49);
  }
  v38 = v48;
  v39 = *v48;
  v40 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v51, a3);
  if ( v40 )
    v41 = *v40;
  else
    v41 = 0;
  v43 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))(v39 + 120))(v38, v41, 0);
  v44 = (BSTR *)v51;
  if ( v51 && _InterlockedExchangeAdd((volatile signed __int32 *)v51 + 4, 0xFFFFFFFF) == 1 && v44 )
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
  v46 = 0;
  if ( v43 != -2147024894 )
    v46 = v43;
  wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v48);
  wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v49);
  wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
  if ( v64 )
    CoUninitialize();
  return v46;
}

```

## disassembly

```asm
0x180066aa0  mov     rax, rsp
0x180066aa3  push    rbx
0x180066aa4  push    rsi
0x180066aa5  push    rdi
0x180066aa6  push    r12
0x180066aa8  push    r14
0x180066aaa  push    r15
0x180066aac  sub     rsp, 1A8h
0x180066ab3  movaps  xmmword ptr [rax-48h], xmm6
0x180066ab7  movaps  xmmword ptr [rax-58h], xmm7
0x180066abb  movaps  xmmword ptr [rax-68h], xmm8
0x180066ac0  movaps  xmmword ptr [rax-78h], xmm9
0x180066ac5  movaps  xmmword ptr [rax-88h], xmm10
0x180066acd  movaps  xmmword ptr [rax-98h], xmm11
0x180066ad5  mov     r12, r8
0x180066ad8  mov     r15, rdx
0x180066adb  mov     r14, rcx
0x180066ade  lea     rcx, [rax+20h]
0x180066ae2  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x180066ae7  nop
0x180066ae8  xor     esi, esi
0x180066aea  mov     [rsp+1D8h+var_190], rsi
0x180066aef  mov     [rsp+1D8h+var_198], rsi
0x180066af4  mov     [rsp+1D8h+var_1A0], rsi
0x180066af9  lea     rax, [rsp+1D8h+var_190]
0x180066afe  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x180066b03  lea     r9, IID_ITaskService; riid
0x180066b0a  xor     edx, edx; pUnkOuter
0x180066b0c  lea     r8d, [rsi+1]; dwClsContext
0x180066b10  lea     rcx, CLSID_TaskScheduler; rclsid
0x180066b17  call    cs:__imp_CoCreateInstance
0x180066b1e  nop     dword ptr [rax+rax+00h]
0x180066b23  mov     ebx, eax
0x180066b25  test    eax, eax
0x180066b27  jns     short loc_180066B8D
0x180066b29  mov     rcx, [rsp+1D8h]; this
0x180066b31  mov     r9d, eax; char *
0x180066b34  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180066b3b  mov     edx, 12Ch; void *
0x180066b40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066b45  nop
0x180066b46  lea     rcx, [rsp+1D8h+var_1A0]
0x180066b4b  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066b50  nop
0x180066b51  lea     rcx, [rsp+1D8h+var_198]
0x180066b56  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066b5b  nop
0x180066b5c  lea     rcx, [rsp+1D8h+var_190]
0x180066b61  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066b66  nop
0x180066b67  mov     al, [rsp+1D8h+arg_18]
0x180066b6e  mov     [rsp+1D8h+arg_18], sil
0x180066b76  test    al, al
0x180066b78  jz      short loc_180066B86
0x180066b7a  call    cs:__imp_CoUninitialize
0x180066b81  nop     dword ptr [rax+rax+00h]
0x180066b86  mov     eax, ebx
0x180066b88  jmp     loc_180067013
0x180066b8d  mov     rdi, [rsp+1D8h+var_190]
0x180066b92  mov     rax, [rdi]
0x180066b95  mov     rbx, [rax+50h]
0x180066b99  lea     rcx, [rsp+1D8h+pvarg]; pvarg
0x180066ba1  call    cs:__imp_VariantInit
0x180066ba8  nop     dword ptr [rax+rax+00h]
0x180066bad  nop
0x180066bae  movups  xmm10, xmmword ptr [rsp+1D8h+pvarg]
0x180066bb7  movsd   xmm11, qword ptr [rsp+1D8h+pvarg+10h]
0x180066bc1  lea     rcx, [rsp+1D8h+var_150]; pvarg
0x180066bc9  call    cs:__imp_VariantInit
0x180066bd0  nop     dword ptr [rax+rax+00h]
0x180066bd5  nop
0x180066bd6  movups  xmm8, xmmword ptr [rsp+1D8h+var_150]
0x180066bdf  movsd   xmm9, qword ptr [rsp+1D8h+var_150+10h]
0x180066be9  lea     rcx, [rsp+1D8h+var_168]; pvarg
0x180066bee  call    cs:__imp_VariantInit
0x180066bf5  nop     dword ptr [rax+rax+00h]
0x180066bfa  nop
0x180066bfb  movups  xmm6, xmmword ptr [rsp+1D8h+var_168]
0x180066c00  movsd   xmm7, qword ptr [rsp+1D8h+var_168+10h]
0x180066c09  lea     rcx, [rsp+1D8h+var_180]; pvarg
0x180066c0e  call    cs:__imp_VariantInit
0x180066c15  nop     dword ptr [rax+rax+00h]
0x180066c1a  nop
0x180066c1b  movups  xmm0, xmmword ptr [rsp+1D8h+var_180]
0x180066c20  movsd   xmm1, qword ptr [rsp+1D8h+var_180+10h]
0x180066c26  movaps  xmmword ptr [rsp+1D8h+var_118], xmm10
0x180066c2f  movsd   [rsp+1D8h+var_108], xmm11
0x180066c39  movaps  [rsp+1D8h+var_F8], xmm8
0x180066c42  movsd   [rsp+1D8h+var_E8], xmm9
0x180066c4c  movaps  [rsp+1D8h+var_D8], xmm6
0x180066c54  movsd   [rsp+1D8h+var_C8], xmm7
0x180066c5d  movaps  [rsp+1D8h+var_B8], xmm0
0x180066c65  movsd   [rsp+1D8h+var_A8], xmm1
0x180066c6e  lea     rax, [rsp+1D8h+var_118]
0x180066c76  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x180066c7b  lea     r9, [rsp+1D8h+var_F8]
0x180066c83  lea     r8, [rsp+1D8h+var_D8]
0x180066c8b  lea     rdx, [rsp+1D8h+var_B8]
0x180066c93  mov     rcx, rdi
0x180066c96  mov     rax, rbx
0x180066c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c9e  mov     ebx, eax
0x180066ca0  lea     rcx, [rsp+1D8h+var_180]; this
0x180066ca5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180066caa  nop
0x180066cab  lea     rcx, [rsp+1D8h+var_168]; this
0x180066cb0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180066cb5  nop
0x180066cb6  lea     rcx, [rsp+1D8h+var_150]; this
0x180066cbe  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180066cc3  nop
0x180066cc4  lea     rcx, [rsp+1D8h+pvarg]; this
0x180066ccc  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180066cd1  test    ebx, ebx
0x180066cd3  jns     short loc_180066D39
0x180066cd5  mov     rcx, [rsp+1D8h]; this
0x180066cdd  mov     r9d, ebx; char *
0x180066ce0  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180066ce7  mov     edx, 12Eh; void *
0x180066cec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066cf1  nop
0x180066cf2  lea     rcx, [rsp+1D8h+var_1A0]
0x180066cf7  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066cfc  nop
0x180066cfd  lea     rcx, [rsp+1D8h+var_198]
0x180066d02  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066d07  nop
0x180066d08  lea     rcx, [rsp+1D8h+var_190]
0x180066d0d  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066d12  nop
0x180066d13  mov     al, [rsp+1D8h+arg_18]
0x180066d1a  mov     [rsp+1D8h+arg_18], sil
0x180066d22  test    al, al
0x180066d24  jz      short loc_180066D32
0x180066d26  call    cs:__imp_CoUninitialize
0x180066d2d  nop     dword ptr [rax+rax+00h]
0x180066d32  mov     eax, ebx
0x180066d34  jmp     loc_180067013
0x180066d39  mov     rbx, [rsp+1D8h+var_190]
0x180066d3e  mov     rdi, [rbx]
0x180066d41  mov     rdx, r14; unsigned __int16 *
0x180066d44  lea     rcx, [rsp+1D8h+var_188]; this
0x180066d49  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180066d4e  nop
0x180066d4f  mov     rax, [rax]
0x180066d52  test    rax, rax
0x180066d55  jz      short loc_180066D5C
0x180066d57  mov     rdx, [rax]
0x180066d5a  jmp     short loc_180066D5F
0x180066d5c  mov     rdx, rsi
0x180066d5f  lea     r8, [rsp+1D8h+var_198]
0x180066d64  mov     rcx, rbx
0x180066d67  mov     rax, [rdi+38h]
0x180066d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d70  mov     r14d, eax
0x180066d73  mov     rbx, [rsp+1D8h+var_188]
0x180066d78  or      edi, 0FFFFFFFFh
0x180066d7b  test    rbx, rbx
0x180066d7e  jz      short loc_180066DC6
0x180066d80  mov     ecx, edi
0x180066d82  lock xadd [rbx+10h], ecx
0x180066d87  add     ecx, edi
0x180066d89  jnz     short loc_180066DC6
0x180066d8b  test    rbx, rbx
0x180066d8e  jz      short loc_180066DC6
0x180066d90  cmp     [rbx], rsi
0x180066d93  jz      short loc_180066DA7
0x180066d95  mov     rcx, [rbx]; bstrString
0x180066d98  call    cs:__imp_SysFreeString
0x180066d9f  nop     dword ptr [rax+rax+00h]
0x180066da4  mov     [rbx], rsi
0x180066da7  mov     rcx, [rbx+8]; void *
0x180066dab  test    rcx, rcx
0x180066dae  jz      short loc_180066DB9
0x180066db0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180066db5  mov     [rbx+8], rsi
0x180066db9  mov     edx, 18h; struct std::nothrow_t *
0x180066dbe  mov     rcx, rbx; void *
0x180066dc1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180066dc6  test    r14d, r14d
0x180066dc9  jns     short loc_180066E30
0x180066dcb  mov     rcx, [rsp+1D8h]; this
0x180066dd3  mov     r9d, r14d; char *
0x180066dd6  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180066ddd  mov     edx, 131h; void *
0x180066de2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066de7  nop
0x180066de8  lea     rcx, [rsp+1D8h+var_1A0]
0x180066ded  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066df2  nop
0x180066df3  lea     rcx, [rsp+1D8h+var_198]
0x180066df8  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066dfd  nop
0x180066dfe  lea     rcx, [rsp+1D8h+var_190]
0x180066e03  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066e08  nop
0x180066e09  mov     al, [rsp+1D8h+arg_18]
0x180066e10  mov     [rsp+1D8h+arg_18], sil
0x180066e18  test    al, al
0x180066e1a  jz      short loc_180066E28
0x180066e1c  call    cs:__imp_CoUninitialize
0x180066e23  nop     dword ptr [rax+rax+00h]
0x180066e28  mov     eax, r14d
0x180066e2b  jmp     loc_180067013
0x180066e30  test    r15, r15
0x180066e33  jz      loc_180066F2D
0x180066e39  mov     rbx, [rsp+1D8h+var_198]
0x180066e3e  mov     r14, [rbx]
0x180066e41  mov     rdx, r15; unsigned __int16 *
0x180066e44  lea     rcx, [rsp+1D8h+var_188]; this
0x180066e49  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180066e4e  nop
0x180066e4f  mov     rax, [rax]
0x180066e52  test    rax, rax
0x180066e55  jz      short loc_180066E5C
0x180066e57  mov     rdx, [rax]
0x180066e5a  jmp     short loc_180066E5F
0x180066e5c  mov     rdx, rsi
0x180066e5f  lea     r8, [rsp+1D8h+var_1A0]
0x180066e64  mov     rcx, rbx
0x180066e67  mov     rax, [r14+48h]
0x180066e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e70  mov     r14d, eax
0x180066e73  mov     rbx, [rsp+1D8h+var_188]
0x180066e78  test    rbx, rbx
0x180066e7b  jz      short loc_180066EC3
0x180066e7d  mov     ecx, edi
0x180066e7f  lock xadd [rbx+10h], ecx
0x180066e84  add     ecx, edi
0x180066e86  jnz     short loc_180066EC3
0x180066e88  test    rbx, rbx
0x180066e8b  jz      short loc_180066EC3
0x180066e8d  cmp     [rbx], rsi
0x180066e90  jz      short loc_180066EA4
0x180066e92  mov     rcx, [rbx]; bstrString
0x180066e95  call    cs:__imp_SysFreeString
0x180066e9c  nop     dword ptr [rax+rax+00h]
0x180066ea1  mov     [rbx], rsi
0x180066ea4  mov     rcx, [rbx+8]; void *
0x180066ea8  test    rcx, rcx
0x180066eab  jz      short loc_180066EB6
0x180066ead  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180066eb2  mov     [rbx+8], rsi
0x180066eb6  mov     edx, 18h; struct std::nothrow_t *
0x180066ebb  mov     rcx, rbx; void *
0x180066ebe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180066ec3  test    r14d, r14d
0x180066ec6  jns     short loc_180066F3C
0x180066ec8  mov     rcx, [rsp+1D8h]; this
0x180066ed0  mov     r9d, r14d; char *
0x180066ed3  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180066eda  mov     edx, 135h; void *
0x180066edf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066ee4  nop
0x180066ee5  lea     rcx, [rsp+1D8h+var_1A0]
0x180066eea  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066eef  nop
0x180066ef0  lea     rcx, [rsp+1D8h+var_198]
0x180066ef5  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066efa  nop
0x180066efb  lea     rcx, [rsp+1D8h+var_190]
0x180066f00  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180066f05  nop
0x180066f06  mov     al, [rsp+1D8h+arg_18]
0x180066f0d  mov     [rsp+1D8h+arg_18], sil
0x180066f15  test    al, al
0x180066f17  jz      short loc_180066F25
0x180066f19  call    cs:__imp_CoUninitialize
0x180066f20  nop     dword ptr [rax+rax+00h]
0x180066f25  mov     eax, r14d
0x180066f28  jmp     loc_180067013
0x180066f2d  lea     rdx, [rsp+1D8h+var_198]
0x180066f32  lea     rcx, [rsp+1D8h+var_1A0]
0x180066f37  call    ??4?$CComPtr@UITaskFolder@@@ATL@@QEAAPEAUITaskFolder@@AEBV01@@Z; ATL::CComPtr<ITaskFolder>::operator=(ATL::CComPtr<ITaskFolder> const &)
0x180066f3c  mov     rbx, [rsp+1D8h+var_1A0]
0x180066f41  mov     r14, [rbx]
0x180066f44  mov     rdx, r12; unsigned __int16 *
0x180066f47  lea     rcx, [rsp+1D8h+var_188]; this
0x180066f4c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180066f51  nop
0x180066f52  mov     rax, [rax]
0x180066f55  test    rax, rax
0x180066f58  jz      short loc_180066F5F
0x180066f5a  mov     rdx, [rax]
0x180066f5d  jmp     short loc_180066F62
0x180066f5f  mov     rdx, rsi
0x180066f62  xor     r8d, r8d
0x180066f65  mov     rcx, rbx
0x180066f68  mov     rax, [r14+78h]
0x180066f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f71  mov     r14d, eax
0x180066f74  mov     rbx, [rsp+1D8h+var_188]
0x180066f79  test    rbx, rbx
0x180066f7c  jz      short loc_180066FC5
0x180066f7e  mov     ecx, edi
0x180066f80  lock xadd [rbx+10h], ecx
0x180066f85  add     ecx, edi
0x180066f87  jnz     short loc_180066FC5
0x180066f89  test    rbx, rbx
0x180066f8c  jz      short loc_180066FC5
  ... truncated ...
```
