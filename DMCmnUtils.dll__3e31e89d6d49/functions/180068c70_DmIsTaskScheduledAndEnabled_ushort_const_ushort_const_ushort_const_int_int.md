# DmIsTaskScheduledAndEnabled(ushort const *,ushort const *,ushort const *,int *,int *)

- ea: `0x180068c70`
- end: `0x18006924c`
- name: `?DmIsTaskScheduledAndEnabled@@YAJPEBG00PEAH1@Z`
- size: `1500`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, int *@<r9>, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180007640`
- `0x180057c6c`
- `0x18005bb94`
- `0x18005e62c`
- `0x18005e708`
- `0x18005e7f8`
- `0x18005e820`
- `0x1800651fc`
- `0x180068c70`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068d0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068d0e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068d76`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068f30`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180069201`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068d76`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068f30`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180069201`
- `OLEAUT32!__imp_SysFreeString` at `0x180068fc0`
- `OLEAUT32!__imp_SysFreeString` at `0x180069071`
- `OLEAUT32!__imp_SysFreeString` at `0x180069137`
- `OLEAUT32!__imp_SysFreeString` at `0x180068fc0`
- `OLEAUT32!__imp_SysFreeString` at `0x180069071`
- `OLEAUT32!__imp_SysFreeString` at `0x180069137`
- `OLEAUT32!__imp_VariantInit` at `0x180068d9d`
- `OLEAUT32!__imp_VariantInit` at `0x180068dc5`
- `OLEAUT32!__imp_VariantInit` at `0x180068ded`
- `OLEAUT32!__imp_VariantInit` at `0x180068e10`
- `OLEAUT32!__imp_VariantInit` at `0x180068d9d`
- `OLEAUT32!__imp_VariantInit` at `0x180068dc5`
- `OLEAUT32!__imp_VariantInit` at `0x180068ded`
- `OLEAUT32!__imp_VariantInit` at `0x180068e10`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall DmIsTaskScheduledAndEnabled(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int *a4,
        int *a5)
{
  int *v7; // r13
  HRESULT v8; // eax
  unsigned int v9; // ebx
  char v10; // al
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v14; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v16; // xmm8
  IRecordInfo *v17; // xmm9_8
  __int128 v18; // xmm6
  IRecordInfo *v19; // xmm7_8
  int v20; // ebx
  char v21; // al
  LPVOID v22; // rbx
  __int64 v23; // rdi
  __int64 *v24; // rax
  __int64 v25; // rdx
  int v26; // eax
  const struct std::nothrow_t *v27; // rdx
  BSTR *v28; // rbx
  BSTR v29; // rcx
  _QWORD *v30; // rbx
  __int64 v31; // r13
  __int64 *v32; // rax
  __int64 v33; // rdx
  int v34; // eax
  const struct std::nothrow_t *v35; // rdx
  BSTR *v36; // rbx
  BSTR v37; // rcx
  _QWORD *v38; // rbx
  __int64 v39; // r15
  __int64 *v40; // rax
  __int64 v41; // rdx
  int v42; // eax
  const struct std::nothrow_t *v43; // rdx
  BSTR *v44; // rbx
  BSTR v45; // rcx
  int v46; // eax
  int ppv; // [rsp+20h] [rbp-1B8h]
  char v48[4]; // [rsp+30h] [rbp-1A8h] BYREF
  __int16 v49; // [rsp+34h] [rbp-1A4h] BYREF
  _QWORD *v50; // [rsp+38h] [rbp-1A0h] BYREF
  _QWORD *v51; // [rsp+40h] [rbp-198h] BYREF
  LPVOID v52; // [rsp+48h] [rbp-190h] BYREF
  __int64 v53; // [rsp+50h] [rbp-188h] BYREF
  void *v54[2]; // [rsp+58h] [rbp-180h] BYREF
  VARIANTARG v55; // [rsp+68h] [rbp-170h] BYREF
  VARIANTARG v56; // [rsp+80h] [rbp-158h] BYREF
  VARIANTARG v57; // [rsp+98h] [rbp-140h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-128h] BYREF
  int v59[4]; // [rsp+D0h] [rbp-108h] BYREF
  IRecordInfo *v60; // [rsp+E0h] [rbp-F8h]
  __int128 v61; // [rsp+F0h] [rbp-E8h] BYREF
  IRecordInfo *v62; // [rsp+100h] [rbp-D8h]
  __int128 v63; // [rsp+110h] [rbp-C8h] BYREF
  IRecordInfo *v64; // [rsp+120h] [rbp-B8h]
  VARIANTARG v65; // [rsp+130h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  *a4 = 0;
  v7 = a5;
  *a5 = 0;
  v49 = 0;
  wil::CoInitializeEx(v48);
  v52 = 0;
  v51 = 0;
  v50 = 0;
  v53 = 0;
  v8 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v52);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v12 = v52;
    v13 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v52 + 80LL);
    VariantInit(&pvarg);
    v14 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v57);
    v16 = *(_OWORD *)&v57.vt;
    v17 = v57.pRecInfo;
    VariantInit(&v56);
    v18 = *(_OWORD *)&v56.vt;
    v19 = v56.pRecInfo;
    VariantInit(&v55);
    *(_OWORD *)v59 = v14;
    v60 = pRecInfo;
    v61 = v16;
    v62 = v17;
    v63 = v18;
    v64 = v19;
    v65 = v55;
    v20 = v13(v12, &v65, &v63, &v61);
    _variant_t::~_variant_t((_variant_t *)&v55);
    _variant_t::~_variant_t((_variant_t *)&v56);
    _variant_t::~_variant_t((_variant_t *)&v57);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( v20 >= 0 )
    {
      v22 = v52;
      v23 = *(_QWORD *)v52;
      v24 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)v54, a1);
      if ( v24 )
        v25 = *v24;
      else
        v25 = 0;
      v26 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v23 + 56))(v22, v25, &v51);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x208,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
          (const char *)(unsigned int)v26,
          (int)v59);
      v28 = (BSTR *)v54[0];
      if ( v54[0] && _InterlockedExchangeAdd((volatile signed __int32 *)v54[0] + 4, 0xFFFFFFFF) == 1 && v28 )
      {
        if ( *v28 )
        {
          SysFreeString(*v28);
          *v28 = 0;
        }
        v29 = v28[1];
        if ( v29 )
        {
          operator delete(v29, v27);
          v28[1] = 0;
        }
        operator delete(v28, (const struct std::nothrow_t *)0x18);
      }
      if ( a2 )
      {
        v30 = v51;
        v31 = *v51;
        v32 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)v54, a2);
        if ( v32 )
          v33 = *v32;
        else
          v33 = 0;
        v34 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD **))(v31 + 72))(v30, v33, &v50);
        if ( v34 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x20C,
            (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
            (const char *)(unsigned int)v34,
            (int)v59);
        v36 = (BSTR *)v54[0];
        if ( v54[0] && _InterlockedExchangeAdd((volatile signed __int32 *)v54[0] + 4, 0xFFFFFFFF) == 1 && v36 )
        {
          if ( *v36 )
          {
            SysFreeString(*v36);
            *v36 = 0;
          }
          v37 = v36[1];
          if ( v37 )
          {
            operator delete(v37, v35);
            v36[1] = 0;
          }
          operator delete(v36, (const struct std::nothrow_t *)0x18);
        }
        v7 = a5;
      }
      else
      {
        ATL::CComPtr<ITaskFolder>::operator=(&v50, &v51);
      }
      v38 = v50;
      v39 = *v50;
      v40 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)v54, a3);
      if ( v40 )
        v41 = *v40;
      else
        v41 = 0;
      v42 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v39 + 104))(v38, v41, &v53);
      if ( v42 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x214,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
          (const char *)(unsigned int)v42,
          (int)v59);
      v44 = (BSTR *)v54[0];
      if ( v54[0] && _InterlockedExchangeAdd((volatile signed __int32 *)v54[0] + 4, 0xFFFFFFFF) == 1 && v44 )
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
      *a4 = 1;
      v46 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v53 + 80LL))(v53, &v49);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x218,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
          (const char *)(unsigned int)v46,
          (int)v59);
      *v7 = v49 == -1;
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
      if ( v48[0] )
        CoUninitialize();
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x205,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
        (const char *)(unsigned int)v20,
        (int)v59);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
      v21 = v48[0];
      v48[0] = 0;
      if ( v21 )
        CoUninitialize();
      return (unsigned int)v20;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v8,
      ppv);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v53);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v52);
    v10 = v48[0];
    v48[0] = 0;
    if ( v10 )
      CoUninitialize();
    return v9;
  }
}

```

## disassembly

```asm
0x180068c70  mov     rax, rsp
0x180068c73  mov     [rax+8], rbx
0x180068c77  mov     [rax+10h], rsi
0x180068c7b  mov     [rax+20h], r9
0x180068c7f  mov     [rax+18h], r8
0x180068c83  push    rdi
0x180068c84  push    r12
0x180068c86  push    r13
0x180068c88  push    r14
0x180068c8a  push    r15
0x180068c8c  sub     rsp, 1B0h
0x180068c93  movaps  xmmword ptr [rax-38h], xmm6
0x180068c97  movaps  xmmword ptr [rax-48h], xmm7
0x180068c9b  movaps  xmmword ptr [rax-58h], xmm8
0x180068ca0  movaps  xmmword ptr [rax-68h], xmm9
0x180068ca5  movaps  xmmword ptr [rax-78h], xmm10
0x180068caa  movaps  xmmword ptr [rax-88h], xmm11
0x180068cb2  mov     r15, rdx
0x180068cb5  mov     r12, rcx
0x180068cb8  xor     esi, esi
0x180068cba  mov     r14d, esi
0x180068cbd  mov     [r9], esi
0x180068cc0  mov     r13, [rsp+1D8h+arg_20]
0x180068cc8  mov     [r13+0], esi
0x180068ccc  mov     [rsp+1D8h+var_1A4], si
0x180068cd1  lea     rcx, [rsp+1D8h+var_1A8]
0x180068cd6  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x180068cdb  nop
0x180068cdc  mov     [rsp+1D8h+var_190], rsi
0x180068ce1  mov     [rsp+1D8h+var_198], rsi
0x180068ce6  mov     [rsp+1D8h+var_1A0], rsi
0x180068ceb  mov     [rsp+1D8h+var_188], rsi
0x180068cf0  lea     rax, [rsp+1D8h+var_190]
0x180068cf5  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x180068cfa  lea     r9, IID_ITaskService; riid
0x180068d01  xor     edx, edx; pUnkOuter
0x180068d03  lea     r8d, [rsi+1]; dwClsContext
0x180068d07  lea     rcx, CLSID_TaskScheduler; rclsid
0x180068d0e  call    cs:__imp_CoCreateInstance
0x180068d15  nop     dword ptr [rax+rax+00h]
0x180068d1a  mov     ebx, eax
0x180068d1c  test    eax, eax
0x180068d1e  jns     short loc_180068D89
0x180068d20  mov     rcx, [rsp+1D8h]; this
0x180068d28  mov     r9d, eax; char *
0x180068d2b  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180068d32  mov     edx, 203h; void *
0x180068d37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068d3c  nop
0x180068d3d  lea     rcx, [rsp+1D8h+var_188]
0x180068d42  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068d47  nop
0x180068d48  lea     rcx, [rsp+1D8h+var_1A0]
0x180068d4d  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068d52  nop
0x180068d53  lea     rcx, [rsp+1D8h+var_198]
0x180068d58  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068d5d  nop
0x180068d5e  lea     rcx, [rsp+1D8h+var_190]
0x180068d63  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068d68  nop
0x180068d69  mov     al, [rsp+1D8h+var_1A8]
0x180068d6d  mov     [rsp+1D8h+var_1A8], sil
0x180068d72  test    al, al
0x180068d74  jz      short loc_180068D82
0x180068d76  call    cs:__imp_CoUninitialize
0x180068d7d  nop     dword ptr [rax+rax+00h]
0x180068d82  mov     eax, ebx
0x180068d84  jmp     loc_180069210
0x180068d89  mov     rdi, [rsp+1D8h+var_190]
0x180068d8e  mov     rax, [rdi]
0x180068d91  mov     rbx, [rax+50h]
0x180068d95  lea     rcx, [rsp+1D8h+pvarg]; pvarg
0x180068d9d  call    cs:__imp_VariantInit
0x180068da4  nop     dword ptr [rax+rax+00h]
0x180068da9  nop
0x180068daa  movups  xmm10, xmmword ptr [rsp+1D8h+pvarg]
0x180068db3  movsd   xmm11, qword ptr [rsp+1D8h+pvarg+10h]
0x180068dbd  lea     rcx, [rsp+1D8h+var_140]; pvarg
0x180068dc5  call    cs:__imp_VariantInit
0x180068dcc  nop     dword ptr [rax+rax+00h]
0x180068dd1  nop
0x180068dd2  movups  xmm8, xmmword ptr [rsp+1D8h+var_140]
0x180068ddb  movsd   xmm9, qword ptr [rsp+1D8h+var_140+10h]
0x180068de5  lea     rcx, [rsp+1D8h+var_158]; pvarg
0x180068ded  call    cs:__imp_VariantInit
0x180068df4  nop     dword ptr [rax+rax+00h]
0x180068df9  nop
0x180068dfa  movups  xmm6, xmmword ptr [rsp+1D8h+var_158]
0x180068e02  movsd   xmm7, qword ptr [rsp+1D8h+var_158+10h]
0x180068e0b  lea     rcx, [rsp+1D8h+var_170]; pvarg
0x180068e10  call    cs:__imp_VariantInit
0x180068e17  nop     dword ptr [rax+rax+00h]
0x180068e1c  nop
0x180068e1d  movups  xmm0, xmmword ptr [rsp+1D8h+var_170]
0x180068e22  movsd   xmm1, qword ptr [rsp+1D8h+var_170+10h]
0x180068e28  movaps  xmmword ptr [rsp+1D8h+var_108], xmm10
0x180068e31  movsd   [rsp+1D8h+var_F8], xmm11
0x180068e3b  movaps  [rsp+1D8h+var_E8], xmm8
0x180068e44  movsd   [rsp+1D8h+var_D8], xmm9
0x180068e4e  movaps  [rsp+1D8h+var_C8], xmm6
0x180068e56  movsd   [rsp+1D8h+var_B8], xmm7
0x180068e5f  movaps  [rsp+1D8h+var_A8], xmm0
0x180068e67  movsd   [rsp+1D8h+var_98], xmm1
0x180068e70  lea     rax, [rsp+1D8h+var_108]
0x180068e78  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x180068e7d  lea     r9, [rsp+1D8h+var_E8]
0x180068e85  lea     r8, [rsp+1D8h+var_C8]
0x180068e8d  lea     rdx, [rsp+1D8h+var_A8]
0x180068e95  mov     rcx, rdi
0x180068e98  mov     rax, rbx
0x180068e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ea0  mov     ebx, eax
0x180068ea2  lea     rcx, [rsp+1D8h+var_170]; this
0x180068ea7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180068eac  nop
0x180068ead  lea     rcx, [rsp+1D8h+var_158]; this
0x180068eb5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180068eba  nop
0x180068ebb  lea     rcx, [rsp+1D8h+var_140]; this
0x180068ec3  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180068ec8  nop
0x180068ec9  lea     rcx, [rsp+1D8h+pvarg]; this
0x180068ed1  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180068ed6  test    ebx, ebx
0x180068ed8  jns     short loc_180068F43
0x180068eda  mov     rcx, [rsp+1D8h]; this
0x180068ee2  mov     r9d, ebx; char *
0x180068ee5  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180068eec  mov     edx, 205h; void *
0x180068ef1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068ef6  nop
0x180068ef7  lea     rcx, [rsp+1D8h+var_188]
0x180068efc  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068f01  nop
0x180068f02  lea     rcx, [rsp+1D8h+var_1A0]
0x180068f07  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068f0c  nop
0x180068f0d  lea     rcx, [rsp+1D8h+var_198]
0x180068f12  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068f17  nop
0x180068f18  lea     rcx, [rsp+1D8h+var_190]
0x180068f1d  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068f22  nop
0x180068f23  mov     al, [rsp+1D8h+var_1A8]
0x180068f27  mov     [rsp+1D8h+var_1A8], sil
0x180068f2c  test    al, al
0x180068f2e  jz      short loc_180068F3C
0x180068f30  call    cs:__imp_CoUninitialize
0x180068f37  nop     dword ptr [rax+rax+00h]
0x180068f3c  mov     eax, ebx
0x180068f3e  jmp     loc_180069210
0x180068f43  mov     rbx, [rsp+1D8h+var_190]
0x180068f48  mov     rdi, [rbx]
0x180068f4b  mov     rdx, r12; unsigned __int16 *
0x180068f4e  lea     rcx, [rsp+1D8h+var_180]; this
0x180068f53  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180068f58  nop
0x180068f59  mov     rax, [rax]
0x180068f5c  test    rax, rax
0x180068f5f  jz      short loc_180068F66
0x180068f61  mov     rdx, [rax]
0x180068f64  jmp     short loc_180068F69
0x180068f66  mov     rdx, rsi
0x180068f69  lea     r8, [rsp+1D8h+var_198]
0x180068f6e  mov     rcx, rbx
0x180068f71  mov     rax, [rdi+38h]
0x180068f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f7a  mov     rcx, [rsp+1D8h]; this
0x180068f82  test    eax, eax
0x180068f84  jns     short loc_180068F9B
0x180068f86  mov     r9d, eax; char *
0x180068f89  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180068f90  mov     edx, 208h; void *
0x180068f95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068f9b  mov     rbx, [rsp+1D8h+var_180]
0x180068fa0  or      edi, 0FFFFFFFFh
0x180068fa3  test    rbx, rbx
0x180068fa6  jz      short loc_180068FEE
0x180068fa8  mov     eax, edi
0x180068faa  lock xadd [rbx+10h], eax
0x180068faf  add     eax, edi
0x180068fb1  jnz     short loc_180068FEE
0x180068fb3  test    rbx, rbx
0x180068fb6  jz      short loc_180068FEE
0x180068fb8  cmp     [rbx], rsi
0x180068fbb  jz      short loc_180068FCF
0x180068fbd  mov     rcx, [rbx]; bstrString
0x180068fc0  call    cs:__imp_SysFreeString
0x180068fc7  nop     dword ptr [rax+rax+00h]
0x180068fcc  mov     [rbx], rsi
0x180068fcf  mov     rcx, [rbx+8]; void *
0x180068fd3  test    rcx, rcx
0x180068fd6  jz      short loc_180068FE1
0x180068fd8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068fdd  mov     [rbx+8], rsi
0x180068fe1  mov     edx, 18h; struct std::nothrow_t *
0x180068fe6  mov     rcx, rbx; void *
0x180068fe9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068fee  test    r15, r15
0x180068ff1  jz      loc_1800690CF
0x180068ff7  mov     rbx, [rsp+1D8h+var_198]
0x180068ffc  mov     r13, [rbx]
0x180068fff  mov     rdx, r15; unsigned __int16 *
0x180069002  lea     rcx, [rsp+1D8h+var_180]; this
0x180069007  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006900c  nop
0x18006900d  mov     rax, [rax]
0x180069010  test    rax, rax
0x180069013  jz      short loc_18006901A
0x180069015  mov     rdx, [rax]
0x180069018  jmp     short loc_18006901D
0x18006901a  mov     rdx, rsi
0x18006901d  lea     r8, [rsp+1D8h+var_1A0]
0x180069022  mov     rcx, rbx
0x180069025  mov     rax, [r13+48h]
0x180069029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006902e  mov     rcx, [rsp+1D8h]; this
0x180069036  test    eax, eax
0x180069038  jns     short loc_18006904F
0x18006903a  mov     r9d, eax; char *
0x18006903d  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180069044  mov     edx, 20Ch; void *
0x180069049  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006904f  mov     rbx, [rsp+1D8h+var_180]
0x180069054  test    rbx, rbx
0x180069057  jz      short loc_18006909F
0x180069059  mov     eax, edi
0x18006905b  lock xadd [rbx+10h], eax
0x180069060  add     eax, edi
0x180069062  jnz     short loc_18006909F
0x180069064  test    rbx, rbx
0x180069067  jz      short loc_18006909F
0x180069069  cmp     [rbx], rsi
0x18006906c  jz      short loc_180069080
0x18006906e  mov     rcx, [rbx]; bstrString
0x180069071  call    cs:__imp_SysFreeString
0x180069078  nop     dword ptr [rax+rax+00h]
0x18006907d  mov     [rbx], rsi
0x180069080  mov     rcx, [rbx+8]; void *
0x180069084  test    rcx, rcx
0x180069087  jz      short loc_180069092
0x180069089  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006908e  mov     [rbx+8], rsi
0x180069092  mov     edx, 18h; struct std::nothrow_t *
0x180069097  mov     rcx, rbx; void *
0x18006909a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006909f  mov     r13, [rsp+1D8h+arg_20]
0x1800690a7  mov     rbx, [rsp+1D8h+var_1A0]
0x1800690ac  mov     r15, [rbx]
0x1800690af  mov     rdx, [rsp+1D8h+arg_10]; unsigned __int16 *
0x1800690b7  lea     rcx, [rsp+1D8h+var_180]; this
0x1800690bc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800690c1  nop
0x1800690c2  mov     rax, [rax]
0x1800690c5  test    rax, rax
0x1800690c8  jz      short loc_1800690E0
0x1800690ca  mov     rdx, [rax]
0x1800690cd  jmp     short loc_1800690E3
0x1800690cf  lea     rdx, [rsp+1D8h+var_198]
0x1800690d4  lea     rcx, [rsp+1D8h+var_1A0]
0x1800690d9  call    ??4?$CComPtr@UITaskFolder@@@ATL@@QEAAPEAUITaskFolder@@AEBV01@@Z; ATL::CComPtr<ITaskFolder>::operator=(ATL::CComPtr<ITaskFolder> const &)
0x1800690de  jmp     short loc_1800690A7
0x1800690e0  mov     rdx, rsi
0x1800690e3  lea     r8, [rsp+1D8h+var_188]
0x1800690e8  mov     rcx, rbx
0x1800690eb  mov     rax, [r15+68h]
0x1800690ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690f4  mov     rcx, [rsp+1D8h]; this
0x1800690fc  test    eax, eax
0x1800690fe  jns     short loc_180069115
0x180069100  mov     r9d, eax; char *
0x180069103  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x18006910a  mov     edx, 214h; void *
0x18006910f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069115  mov     rbx, [rsp+1D8h+var_180]
0x18006911a  test    rbx, rbx
0x18006911d  jz      short loc_180069165
0x18006911f  mov     eax, edi
0x180069121  lock xadd [rbx+10h], eax
0x180069126  add     eax, edi
0x180069128  jnz     short loc_180069165
0x18006912a  test    rbx, rbx
0x18006912d  jz      short loc_180069165
0x18006912f  cmp     [rbx], rsi
0x180069132  jz      short loc_180069146
0x180069134  mov     rcx, [rbx]; bstrString
0x180069137  call    cs:__imp_SysFreeString
0x18006913e  nop     dword ptr [rax+rax+00h]
0x180069143  mov     [rbx], rsi
0x180069146  mov     rcx, [rbx+8]; void *
0x18006914a  test    rcx, rcx
0x18006914d  jz      short loc_180069158
0x18006914f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069154  mov     [rbx+8], rsi
0x180069158  mov     edx, 18h; struct std::nothrow_t *
0x18006915d  mov     rcx, rbx; void *
0x180069160  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069165  mov     rax, [rsp+1D8h+arg_18]
0x18006916d  mov     dword ptr [rax], 1
  ... truncated ...
```
