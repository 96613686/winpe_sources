# DmIsTaskScheduled(ushort const *,ushort const *,ushort const *,int *)

- ea: `0x1800686e0`
- end: `0x180068c64`
- name: `?DmIsTaskScheduled@@YAJPEBG00PEAH@Z`
- size: `1412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int *)`
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
- `0x1800686e0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068770`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068770`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800687d8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068992`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068c19`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800687d8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068992`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180068c19`
- `OLEAUT32!__imp_SysFreeString` at `0x180068a22`
- `OLEAUT32!__imp_SysFreeString` at `0x180068ad3`
- `OLEAUT32!__imp_SysFreeString` at `0x180068b99`
- `OLEAUT32!__imp_SysFreeString` at `0x180068a22`
- `OLEAUT32!__imp_SysFreeString` at `0x180068ad3`
- `OLEAUT32!__imp_SysFreeString` at `0x180068b99`
- `OLEAUT32!__imp_VariantInit` at `0x1800687ff`
- `OLEAUT32!__imp_VariantInit` at `0x180068827`
- `OLEAUT32!__imp_VariantInit` at `0x18006884f`
- `OLEAUT32!__imp_VariantInit` at `0x180068872`
- `OLEAUT32!__imp_VariantInit` at `0x1800687ff`
- `OLEAUT32!__imp_VariantInit` at `0x180068827`
- `OLEAUT32!__imp_VariantInit` at `0x18006884f`
- `OLEAUT32!__imp_VariantInit` at `0x180068872`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall DmIsTaskScheduled(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  int *v4; // r13
  HRESULT v7; // eax
  unsigned int v8; // ebx
  char v9; // al
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v13; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v15; // xmm8
  IRecordInfo *v16; // xmm9_8
  __int128 v17; // xmm6
  IRecordInfo *v18; // xmm7_8
  int v19; // ebx
  char v20; // al
  LPVOID v21; // rbx
  __int64 v22; // rdi
  __int64 *v23; // rax
  __int64 v24; // rdx
  int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  BSTR *v27; // rbx
  BSTR v28; // rcx
  _QWORD *v29; // rbx
  __int64 v30; // r13
  __int64 *v31; // rax
  __int64 v32; // rdx
  int v33; // eax
  const struct std::nothrow_t *v34; // rdx
  BSTR *v35; // rbx
  BSTR v36; // rcx
  _QWORD *v37; // rbx
  __int64 v38; // r15
  __int64 *v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  const struct std::nothrow_t *v42; // rdx
  BSTR *v43; // rbx
  BSTR v44; // rcx
  int ppv; // [rsp+20h] [rbp-1B8h]
  char v46[8]; // [rsp+30h] [rbp-1A8h] BYREF
  _QWORD *v47; // [rsp+38h] [rbp-1A0h] BYREF
  _QWORD *v48; // [rsp+40h] [rbp-198h] BYREF
  LPVOID v49; // [rsp+48h] [rbp-190h] BYREF
  void *v50; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v51[2]; // [rsp+58h] [rbp-180h] BYREF
  VARIANTARG v52; // [rsp+68h] [rbp-170h] BYREF
  VARIANTARG v53; // [rsp+80h] [rbp-158h] BYREF
  VARIANTARG v54; // [rsp+98h] [rbp-140h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-128h] BYREF
  int v56[4]; // [rsp+D0h] [rbp-108h] BYREF
  IRecordInfo *v57; // [rsp+E0h] [rbp-F8h]
  __int128 v58; // [rsp+F0h] [rbp-E8h] BYREF
  IRecordInfo *v59; // [rsp+100h] [rbp-D8h]
  __int128 v60; // [rsp+110h] [rbp-C8h] BYREF
  IRecordInfo *v61; // [rsp+120h] [rbp-B8h]
  VARIANTARG v62; // [rsp+130h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v4 = a4;
  *a4 = 0;
  wil::CoInitializeEx(v46);
  v49 = 0;
  v48 = 0;
  v47 = 0;
  v51[0] = 0;
  v7 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v49);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v11 = v49;
    v12 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v49 + 80LL);
    VariantInit(&pvarg);
    v13 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v54);
    v15 = *(_OWORD *)&v54.vt;
    v16 = v54.pRecInfo;
    VariantInit(&v53);
    v17 = *(_OWORD *)&v53.vt;
    v18 = v53.pRecInfo;
    VariantInit(&v52);
    *(_OWORD *)v56 = v13;
    v57 = pRecInfo;
    v58 = v15;
    v59 = v16;
    v60 = v17;
    v61 = v18;
    v62 = v52;
    v19 = v12(v11, &v62, &v60, &v58);
    _variant_t::~_variant_t((_variant_t *)&v52);
    _variant_t::~_variant_t((_variant_t *)&v53);
    _variant_t::~_variant_t((_variant_t *)&v54);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( v19 >= 0 )
    {
      v21 = v49;
      v22 = *(_QWORD *)v49;
      v23 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v50, a1);
      if ( v23 )
        v24 = *v23;
      else
        v24 = 0;
      v25 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v22 + 56))(v21, v24, &v48);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CF,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
          (const char *)(unsigned int)v25,
          (int)v56);
      v27 = (BSTR *)v50;
      if ( v50 && _InterlockedExchangeAdd((volatile signed __int32 *)v50 + 4, 0xFFFFFFFF) == 1 && v27 )
      {
        if ( *v27 )
        {
          SysFreeString(*v27);
          *v27 = 0;
        }
        v28 = v27[1];
        if ( v28 )
        {
          operator delete(v28, v26);
          v27[1] = 0;
        }
        operator delete(v27, (const struct std::nothrow_t *)0x18);
      }
      if ( a2 )
      {
        v29 = v48;
        v30 = *v48;
        v31 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v50, a2);
        if ( v31 )
          v32 = *v31;
        else
          v32 = 0;
        v33 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD **))(v30 + 72))(v29, v32, &v47);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1D3,
            (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
            (const char *)(unsigned int)v33,
            (int)v56);
        v35 = (BSTR *)v50;
        if ( v50 && _InterlockedExchangeAdd((volatile signed __int32 *)v50 + 4, 0xFFFFFFFF) == 1 && v35 )
        {
          if ( *v35 )
          {
            SysFreeString(*v35);
            *v35 = 0;
          }
          v36 = v35[1];
          if ( v36 )
          {
            operator delete(v36, v34);
            v35[1] = 0;
          }
          operator delete(v35, (const struct std::nothrow_t *)0x18);
        }
        v4 = a4;
      }
      else
      {
        ATL::CComPtr<ITaskFolder>::operator=(&v47, &v48);
      }
      v37 = v47;
      v38 = *v47;
      v39 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v50, a3);
      if ( v39 )
        v40 = *v39;
      else
        v40 = 0;
      v41 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))(v38 + 104))(v37, v40, v51);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DB,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
          (const char *)(unsigned int)v41,
          (int)v56);
      v43 = (BSTR *)v50;
      if ( v50 && _InterlockedExchangeAdd((volatile signed __int32 *)v50 + 4, 0xFFFFFFFF) == 1 && v43 )
      {
        if ( *v43 )
        {
          SysFreeString(*v43);
          *v43 = 0;
        }
        v44 = v43[1];
        if ( v44 )
        {
          operator delete(v44, v42);
          v43[1] = 0;
        }
        operator delete(v43, (const struct std::nothrow_t *)0x18);
      }
      *v4 = 1;
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v47);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v48);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v49);
      if ( v46[0] )
        CoUninitialize();
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
        (const char *)(unsigned int)v19,
        (int)v56);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(v51);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v47);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v48);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v49);
      v20 = v46[0];
      v46[0] = 0;
      if ( v20 )
        CoUninitialize();
      return (unsigned int)v19;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(v51);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v47);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v48);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v49);
    v9 = v46[0];
    v46[0] = 0;
    if ( v9 )
      CoUninitialize();
    return v8;
  }
}

```

## disassembly

```asm
0x1800686e0  mov     rax, rsp
0x1800686e3  mov     [rax+8], rbx
0x1800686e7  mov     [rax+10h], rsi
0x1800686eb  mov     [rax+20h], r9
0x1800686ef  mov     [rax+18h], r8
0x1800686f3  push    rdi
0x1800686f4  push    r12
0x1800686f6  push    r13
0x1800686f8  push    r14
0x1800686fa  push    r15
0x1800686fc  sub     rsp, 1B0h
0x180068703  movaps  xmmword ptr [rax-38h], xmm6
0x180068707  movaps  xmmword ptr [rax-48h], xmm7
0x18006870b  movaps  xmmword ptr [rax-58h], xmm8
0x180068710  movaps  xmmword ptr [rax-68h], xmm9
0x180068715  movaps  xmmword ptr [rax-78h], xmm10
0x18006871a  movaps  xmmword ptr [rax-88h], xmm11
0x180068722  mov     r13, r9
0x180068725  mov     r15, rdx
0x180068728  mov     r12, rcx
0x18006872b  xor     esi, esi
0x18006872d  mov     r14d, esi
0x180068730  mov     [r9], esi
0x180068733  lea     rcx, [rsp+1D8h+var_1A8]
0x180068738  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x18006873d  nop
0x18006873e  mov     [rsp+1D8h+var_190], rsi
0x180068743  mov     [rsp+1D8h+var_198], rsi
0x180068748  mov     [rsp+1D8h+var_1A0], rsi
0x18006874d  mov     [rsp+1D8h+var_180], rsi
0x180068752  lea     rax, [rsp+1D8h+var_190]
0x180068757  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x18006875c  lea     r9, IID_ITaskService; riid
0x180068763  xor     edx, edx; pUnkOuter
0x180068765  lea     r8d, [rsi+1]; dwClsContext
0x180068769  lea     rcx, CLSID_TaskScheduler; rclsid
0x180068770  call    cs:__imp_CoCreateInstance
0x180068777  nop     dword ptr [rax+rax+00h]
0x18006877c  mov     ebx, eax
0x18006877e  test    eax, eax
0x180068780  jns     short loc_1800687EB
0x180068782  mov     rcx, [rsp+1D8h]; this
0x18006878a  mov     r9d, eax; char *
0x18006878d  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180068794  mov     edx, 1CAh; void *
0x180068799  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006879e  nop
0x18006879f  lea     rcx, [rsp+1D8h+var_180]
0x1800687a4  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800687a9  nop
0x1800687aa  lea     rcx, [rsp+1D8h+var_1A0]
0x1800687af  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800687b4  nop
0x1800687b5  lea     rcx, [rsp+1D8h+var_198]
0x1800687ba  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800687bf  nop
0x1800687c0  lea     rcx, [rsp+1D8h+var_190]
0x1800687c5  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800687ca  nop
0x1800687cb  mov     al, [rsp+1D8h+var_1A8]
0x1800687cf  mov     [rsp+1D8h+var_1A8], sil
0x1800687d4  test    al, al
0x1800687d6  jz      short loc_1800687E4
0x1800687d8  call    cs:__imp_CoUninitialize
0x1800687df  nop     dword ptr [rax+rax+00h]
0x1800687e4  mov     eax, ebx
0x1800687e6  jmp     loc_180068C28
0x1800687eb  mov     rdi, [rsp+1D8h+var_190]
0x1800687f0  mov     rax, [rdi]
0x1800687f3  mov     rbx, [rax+50h]
0x1800687f7  lea     rcx, [rsp+1D8h+pvarg]; pvarg
0x1800687ff  call    cs:__imp_VariantInit
0x180068806  nop     dword ptr [rax+rax+00h]
0x18006880b  nop
0x18006880c  movups  xmm10, xmmword ptr [rsp+1D8h+pvarg]
0x180068815  movsd   xmm11, qword ptr [rsp+1D8h+pvarg+10h]
0x18006881f  lea     rcx, [rsp+1D8h+var_140]; pvarg
0x180068827  call    cs:__imp_VariantInit
0x18006882e  nop     dword ptr [rax+rax+00h]
0x180068833  nop
0x180068834  movups  xmm8, xmmword ptr [rsp+1D8h+var_140]
0x18006883d  movsd   xmm9, qword ptr [rsp+1D8h+var_140+10h]
0x180068847  lea     rcx, [rsp+1D8h+var_158]; pvarg
0x18006884f  call    cs:__imp_VariantInit
0x180068856  nop     dword ptr [rax+rax+00h]
0x18006885b  nop
0x18006885c  movups  xmm6, xmmword ptr [rsp+1D8h+var_158]
0x180068864  movsd   xmm7, qword ptr [rsp+1D8h+var_158+10h]
0x18006886d  lea     rcx, [rsp+1D8h+var_170]; pvarg
0x180068872  call    cs:__imp_VariantInit
0x180068879  nop     dword ptr [rax+rax+00h]
0x18006887e  nop
0x18006887f  movups  xmm0, xmmword ptr [rsp+1D8h+var_170]
0x180068884  movsd   xmm1, qword ptr [rsp+1D8h+var_170+10h]
0x18006888a  movaps  xmmword ptr [rsp+1D8h+var_108], xmm10
0x180068893  movsd   [rsp+1D8h+var_F8], xmm11
0x18006889d  movaps  [rsp+1D8h+var_E8], xmm8
0x1800688a6  movsd   [rsp+1D8h+var_D8], xmm9
0x1800688b0  movaps  [rsp+1D8h+var_C8], xmm6
0x1800688b8  movsd   [rsp+1D8h+var_B8], xmm7
0x1800688c1  movaps  [rsp+1D8h+var_A8], xmm0
0x1800688c9  movsd   [rsp+1D8h+var_98], xmm1
0x1800688d2  lea     rax, [rsp+1D8h+var_108]
0x1800688da  mov     qword ptr [rsp+1D8h+ppv], rax; int
0x1800688df  lea     r9, [rsp+1D8h+var_E8]
0x1800688e7  lea     r8, [rsp+1D8h+var_C8]
0x1800688ef  lea     rdx, [rsp+1D8h+var_A8]
0x1800688f7  mov     rcx, rdi
0x1800688fa  mov     rax, rbx
0x1800688fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068902  mov     ebx, eax
0x180068904  lea     rcx, [rsp+1D8h+var_170]; this
0x180068909  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006890e  nop
0x18006890f  lea     rcx, [rsp+1D8h+var_158]; this
0x180068917  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006891c  nop
0x18006891d  lea     rcx, [rsp+1D8h+var_140]; this
0x180068925  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006892a  nop
0x18006892b  lea     rcx, [rsp+1D8h+pvarg]; this
0x180068933  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180068938  test    ebx, ebx
0x18006893a  jns     short loc_1800689A5
0x18006893c  mov     rcx, [rsp+1D8h]; this
0x180068944  mov     r9d, ebx; char *
0x180068947  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x18006894e  mov     edx, 1CCh; void *
0x180068953  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068958  nop
0x180068959  lea     rcx, [rsp+1D8h+var_180]
0x18006895e  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068963  nop
0x180068964  lea     rcx, [rsp+1D8h+var_1A0]
0x180068969  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006896e  nop
0x18006896f  lea     rcx, [rsp+1D8h+var_198]
0x180068974  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068979  nop
0x18006897a  lea     rcx, [rsp+1D8h+var_190]
0x18006897f  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068984  nop
0x180068985  mov     al, [rsp+1D8h+var_1A8]
0x180068989  mov     [rsp+1D8h+var_1A8], sil
0x18006898e  test    al, al
0x180068990  jz      short loc_18006899E
0x180068992  call    cs:__imp_CoUninitialize
0x180068999  nop     dword ptr [rax+rax+00h]
0x18006899e  mov     eax, ebx
0x1800689a0  jmp     loc_180068C28
0x1800689a5  mov     rbx, [rsp+1D8h+var_190]
0x1800689aa  mov     rdi, [rbx]
0x1800689ad  mov     rdx, r12; unsigned __int16 *
0x1800689b0  lea     rcx, [rsp+1D8h+var_188]; this
0x1800689b5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800689ba  nop
0x1800689bb  mov     rax, [rax]
0x1800689be  test    rax, rax
0x1800689c1  jz      short loc_1800689C8
0x1800689c3  mov     rdx, [rax]
0x1800689c6  jmp     short loc_1800689CB
0x1800689c8  mov     rdx, rsi
0x1800689cb  lea     r8, [rsp+1D8h+var_198]
0x1800689d0  mov     rcx, rbx
0x1800689d3  mov     rax, [rdi+38h]
0x1800689d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689dc  mov     rcx, [rsp+1D8h]; this
0x1800689e4  test    eax, eax
0x1800689e6  jns     short loc_1800689FD
0x1800689e8  mov     r9d, eax; char *
0x1800689eb  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x1800689f2  mov     edx, 1CFh; void *
0x1800689f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800689fd  mov     rbx, [rsp+1D8h+var_188]
0x180068a02  or      edi, 0FFFFFFFFh
0x180068a05  test    rbx, rbx
0x180068a08  jz      short loc_180068A50
0x180068a0a  mov     eax, edi
0x180068a0c  lock xadd [rbx+10h], eax
0x180068a11  add     eax, edi
0x180068a13  jnz     short loc_180068A50
0x180068a15  test    rbx, rbx
0x180068a18  jz      short loc_180068A50
0x180068a1a  cmp     [rbx], rsi
0x180068a1d  jz      short loc_180068A31
0x180068a1f  mov     rcx, [rbx]; bstrString
0x180068a22  call    cs:__imp_SysFreeString
0x180068a29  nop     dword ptr [rax+rax+00h]
0x180068a2e  mov     [rbx], rsi
0x180068a31  mov     rcx, [rbx+8]; void *
0x180068a35  test    rcx, rcx
0x180068a38  jz      short loc_180068A43
0x180068a3a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068a3f  mov     [rbx+8], rsi
0x180068a43  mov     edx, 18h; struct std::nothrow_t *
0x180068a48  mov     rcx, rbx; void *
0x180068a4b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068a50  test    r15, r15
0x180068a53  jz      loc_180068B31
0x180068a59  mov     rbx, [rsp+1D8h+var_198]
0x180068a5e  mov     r13, [rbx]
0x180068a61  mov     rdx, r15; unsigned __int16 *
0x180068a64  lea     rcx, [rsp+1D8h+var_188]; this
0x180068a69  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180068a6e  nop
0x180068a6f  mov     rax, [rax]
0x180068a72  test    rax, rax
0x180068a75  jz      short loc_180068A7C
0x180068a77  mov     rdx, [rax]
0x180068a7a  jmp     short loc_180068A7F
0x180068a7c  mov     rdx, rsi
0x180068a7f  lea     r8, [rsp+1D8h+var_1A0]
0x180068a84  mov     rcx, rbx
0x180068a87  mov     rax, [r13+48h]
0x180068a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a90  mov     rcx, [rsp+1D8h]; this
0x180068a98  test    eax, eax
0x180068a9a  jns     short loc_180068AB1
0x180068a9c  mov     r9d, eax; char *
0x180068a9f  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180068aa6  mov     edx, 1D3h; void *
0x180068aab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068ab1  mov     rbx, [rsp+1D8h+var_188]
0x180068ab6  test    rbx, rbx
0x180068ab9  jz      short loc_180068B01
0x180068abb  mov     eax, edi
0x180068abd  lock xadd [rbx+10h], eax
0x180068ac2  add     eax, edi
0x180068ac4  jnz     short loc_180068B01
0x180068ac6  test    rbx, rbx
0x180068ac9  jz      short loc_180068B01
0x180068acb  cmp     [rbx], rsi
0x180068ace  jz      short loc_180068AE2
0x180068ad0  mov     rcx, [rbx]; bstrString
0x180068ad3  call    cs:__imp_SysFreeString
0x180068ada  nop     dword ptr [rax+rax+00h]
0x180068adf  mov     [rbx], rsi
0x180068ae2  mov     rcx, [rbx+8]; void *
0x180068ae6  test    rcx, rcx
0x180068ae9  jz      short loc_180068AF4
0x180068aeb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068af0  mov     [rbx+8], rsi
0x180068af4  mov     edx, 18h; struct std::nothrow_t *
0x180068af9  mov     rcx, rbx; void *
0x180068afc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068b01  mov     r13, [rsp+1D8h+arg_18]
0x180068b09  mov     rbx, [rsp+1D8h+var_1A0]
0x180068b0e  mov     r15, [rbx]
0x180068b11  mov     rdx, [rsp+1D8h+arg_10]; unsigned __int16 *
0x180068b19  lea     rcx, [rsp+1D8h+var_188]; this
0x180068b1e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180068b23  nop
0x180068b24  mov     rax, [rax]
0x180068b27  test    rax, rax
0x180068b2a  jz      short loc_180068B42
0x180068b2c  mov     rdx, [rax]
0x180068b2f  jmp     short loc_180068B45
0x180068b31  lea     rdx, [rsp+1D8h+var_198]
0x180068b36  lea     rcx, [rsp+1D8h+var_1A0]
0x180068b3b  call    ??4?$CComPtr@UITaskFolder@@@ATL@@QEAAPEAUITaskFolder@@AEBV01@@Z; ATL::CComPtr<ITaskFolder>::operator=(ATL::CComPtr<ITaskFolder> const &)
0x180068b40  jmp     short loc_180068B09
0x180068b42  mov     rdx, rsi
0x180068b45  lea     r8, [rsp+1D8h+var_180]
0x180068b4a  mov     rcx, rbx
0x180068b4d  mov     rax, [r15+68h]
0x180068b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b56  mov     rcx, [rsp+1D8h]; this
0x180068b5e  test    eax, eax
0x180068b60  jns     short loc_180068B77
0x180068b62  mov     r9d, eax; char *
0x180068b65  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180068b6c  mov     edx, 1DBh; void *
0x180068b71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068b77  mov     rbx, [rsp+1D8h+var_188]
0x180068b7c  test    rbx, rbx
0x180068b7f  jz      short loc_180068BC7
0x180068b81  mov     eax, edi
0x180068b83  lock xadd [rbx+10h], eax
0x180068b88  add     eax, edi
0x180068b8a  jnz     short loc_180068BC7
0x180068b8c  test    rbx, rbx
0x180068b8f  jz      short loc_180068BC7
0x180068b91  cmp     [rbx], rsi
0x180068b94  jz      short loc_180068BA8
0x180068b96  mov     rcx, [rbx]; bstrString
0x180068b99  call    cs:__imp_SysFreeString
0x180068ba0  nop     dword ptr [rax+rax+00h]
0x180068ba5  mov     [rbx], rsi
0x180068ba8  mov     rcx, [rbx+8]; void *
0x180068bac  test    rcx, rcx
0x180068baf  jz      short loc_180068BBA
0x180068bb1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068bb6  mov     [rbx+8], rsi
0x180068bba  mov     edx, 18h; struct std::nothrow_t *
0x180068bbf  mov     rcx, rbx; void *
0x180068bc2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068bc7  mov     dword ptr [r13+0], 1
0x180068bcf  lea     rcx, [rsp+1D8h+var_180]
0x180068bd4  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180068bd9  nop
  ... truncated ...
```
