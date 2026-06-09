# DmRunTask(ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x180069260`
- end: `0x180069796`
- name: `?DmRunTask@@YAJPEBG00PEAPEAX@Z`
- size: `1334`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180007640`
- `0x18005e62c`
- `0x18005e708`
- `0x18005e7f8`
- `0x18005e820`
- `0x1800651fc`
- `0x180069260`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800696eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800696eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800692e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800692e7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180069752`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180069752`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800696da`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800696da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800694b8`
- `OLEAUT32!__imp_SysFreeString` at `0x180069555`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800694b8`
- `OLEAUT32!__imp_SysFreeString` at `0x180069555`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695f8`
- `OLEAUT32!__imp_VariantInit` at `0x18006930f`
- `OLEAUT32!__imp_VariantInit` at `0x180069334`
- `OLEAUT32!__imp_VariantInit` at `0x18006935c`
- `OLEAUT32!__imp_VariantInit` at `0x180069382`
- `OLEAUT32!__imp_VariantInit` at `0x180069640`
- `OLEAUT32!__imp_VariantInit` at `0x18006930f`
- `OLEAUT32!__imp_VariantInit` at `0x180069334`
- `OLEAUT32!__imp_VariantInit` at `0x18006935c`
- `OLEAUT32!__imp_VariantInit` at `0x180069382`
- `OLEAUT32!__imp_VariantInit` at `0x180069640`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DmRunTask(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void **a4)
{
  int v8; // ebx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v11; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v13; // xmm8
  IRecordInfo *v14; // xmm9_8
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  wil *v17; // rcx
  LPVOID v18; // rbx
  __int64 v19; // rdi
  __int64 *v20; // rax
  __int64 v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  BSTR *v23; // rdi
  BSTR v24; // rcx
  _QWORD *v25; // rbx
  __int64 v26; // rdi
  __int64 *v27; // rax
  __int64 v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  BSTR *v30; // rdi
  BSTR v31; // rcx
  _QWORD *v32; // rbx
  __int64 v33; // rdi
  __int64 *v34; // rax
  __int64 v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  BSTR *v37; // rdi
  BSTR v38; // rcx
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, VARIANTARG *, __int64); // rbx
  HANDLE v41; // rax
  signed int LastError; // eax
  char v44[4]; // [rsp+40h] [rbp-1B8h] BYREF
  DWORD dwProcessId; // [rsp+44h] [rbp-1B4h] BYREF
  void *v46; // [rsp+48h] [rbp-1B0h] BYREF
  _QWORD *v47; // [rsp+50h] [rbp-1A8h] BYREF
  _QWORD *v48; // [rsp+58h] [rbp-1A0h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-198h] BYREF
  __int64 v50; // [rsp+68h] [rbp-190h] BYREF
  __int64 v51; // [rsp+70h] [rbp-188h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-180h] BYREF
  VARIANTARG v53; // [rsp+90h] [rbp-168h] BYREF
  VARIANTARG v54; // [rsp+B0h] [rbp-148h] BYREF
  VARIANTARG v55; // [rsp+C8h] [rbp-130h] BYREF
  VARIANTARG v56; // [rsp+E0h] [rbp-118h] BYREF
  __int128 v57; // [rsp+100h] [rbp-F8h] BYREF
  IRecordInfo *v58; // [rsp+110h] [rbp-E8h]
  __int128 v59; // [rsp+120h] [rbp-D8h] BYREF
  IRecordInfo *v60; // [rsp+130h] [rbp-C8h]
  __int128 v61; // [rsp+140h] [rbp-B8h] BYREF
  IRecordInfo *v62; // [rsp+150h] [rbp-A8h]

  wil::CoInitializeEx(v44);
  ppv = 0;
  v48 = 0;
  v47 = 0;
  v51 = 0;
  v50 = 0;
  v8 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v8 < 0 )
    goto LABEL_58;
  v9 = ppv;
  v10 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v11 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v56);
  v13 = *(_OWORD *)&v56.vt;
  v14 = v56.pRecInfo;
  VariantInit(&v55);
  v15 = *(_OWORD *)&v55.vt;
  v16 = v55.pRecInfo;
  VariantInit(&v54);
  try
  {
    v57 = v11;
    v58 = pRecInfo;
    v59 = v13;
    v60 = v14;
    v61 = v15;
    v62 = v16;
    v53 = v54;
    v8 = v10(v9, &v53, &v61, &v59, &v57);
    _variant_t::~_variant_t((_variant_t *)&v54);
    _variant_t::~_variant_t((_variant_t *)&v55);
    _variant_t::~_variant_t((_variant_t *)&v56);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( v8 < 0 )
      goto LABEL_58;
    v18 = ppv;
    v19 = *(_QWORD *)ppv;
    v20 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v46, a1);
    if ( v20 )
      v21 = *v20;
    else
      v21 = 0;
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v19 + 56))(v18, v21, &v48);
    v23 = (BSTR *)v46;
    if ( v46 && !_InterlockedDecrement((volatile signed __int32 *)v46 + 4) && v23 )
    {
      if ( *v23 )
      {
        SysFreeString(*v23);
        *v23 = 0;
      }
      v24 = v23[1];
      if ( v24 )
      {
        operator delete(v24, v22);
        v23[1] = 0;
      }
      operator delete(v23, (const struct std::nothrow_t *)0x18);
    }
    if ( v8 < 0 )
      goto LABEL_58;
    if ( a2 )
    {
      v25 = v48;
      v26 = *v48;
      v27 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v46, a2);
      if ( v27 )
        v28 = *v27;
      else
        v28 = 0;
      v8 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD **))(v26 + 72))(v25, v28, &v47);
      v30 = (BSTR *)v46;
      if ( v46 && !_InterlockedDecrement((volatile signed __int32 *)v46 + 4) && v30 )
      {
        if ( *v30 )
        {
          SysFreeString(*v30);
          *v30 = 0;
        }
        v31 = v30[1];
        if ( v31 )
        {
          operator delete(v31, v29);
          v30[1] = 0;
        }
        operator delete(v30, (const struct std::nothrow_t *)0x18);
      }
      if ( v8 < 0 )
        goto LABEL_58;
    }
    else
    {
      ATL::CComPtr<ITaskFolder>::operator=(&v47, &v48);
    }
    v32 = v47;
    v33 = *v47;
    v34 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v46, a3);
    if ( v34 )
      v35 = *v34;
    else
      v35 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v33 + 104))(v32, v35, &v51);
    v37 = (BSTR *)v46;
    if ( v46 && !_InterlockedDecrement((volatile signed __int32 *)v46 + 4) && v37 )
    {
      if ( *v37 )
      {
        SysFreeString(*v37);
        *v37 = 0;
      }
      v38 = v37[1];
      if ( v38 )
      {
        operator delete(v38, v36);
        v37[1] = 0;
      }
      operator delete(v37, (const struct std::nothrow_t *)0x18);
    }
    if ( v8 >= 0 )
    {
      v39 = v51;
      v40 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64))(*(_QWORD *)v51 + 104LL);
      VariantInit(&pvarg);
      v53 = pvarg;
      v8 = v40(v39, &v53, 2);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      if ( v8 >= 0 )
      {
        if ( a4 )
        {
          dwProcessId = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v50 + 112LL))(v50, &dwProcessId);
          if ( v8 >= 0 )
          {
            v41 = OpenProcess(0x101000u, 0, dwProcessId);
            if ( v41 )
            {
              *a4 = v41;
            }
            else
            {
              LastError = GetLastError();
              v8 = LastError;
              if ( LastError > 0 )
                v8 = (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
    }
  }
  catch ( ... )
  {
    dwProcessId = wil::ResultFromCaughtException(v17);
    v8 = dwProcessId;
  }
LABEL_58:
  wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v50);
  wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v51);
  wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v47);
  wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v48);
  wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&ppv);
  if ( v44[0] )
    CoUninitialize();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180069260  mov     rax, rsp
0x180069263  push    rbx
0x180069264  push    rsi
0x180069265  push    rdi
0x180069266  push    r12
0x180069268  push    r13
0x18006926a  push    r14
0x18006926c  push    r15
0x18006926e  sub     rsp, 1C0h
0x180069275  movaps  xmmword ptr [rax-48h], xmm6
0x180069279  movaps  xmmword ptr [rax-58h], xmm7
0x18006927d  movaps  xmmword ptr [rax-68h], xmm8
0x180069282  movaps  xmmword ptr [rax-78h], xmm9
0x180069287  movaps  xmmword ptr [rax-88h], xmm10
0x18006928f  movaps  xmmword ptr [rax-98h], xmm11
0x180069297  mov     r12, r9
0x18006929a  mov     r13, r8
0x18006929d  mov     r15, rdx
0x1800692a0  mov     r14, rcx
0x1800692a3  lea     rcx, [rsp+1F8h+var_1B8]
0x1800692a8  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x1800692ad  nop
0x1800692ae  xor     esi, esi
0x1800692b0  mov     [rsp+1F8h+var_198], rsi
0x1800692b5  mov     [rsp+1F8h+var_1A0], rsi
0x1800692ba  mov     [rsp+1F8h+var_1A8], rsi
0x1800692bf  mov     [rsp+1F8h+var_188], rsi
0x1800692c4  mov     [rsp+1F8h+var_190], rsi
0x1800692c9  lea     rax, [rsp+1F8h+var_198]
0x1800692ce  mov     [rsp+1F8h+ppv], rax; ppv
0x1800692d3  lea     r9, IID_ITaskService; riid
0x1800692da  xor     edx, edx; pUnkOuter
0x1800692dc  lea     r8d, [rsi+1]; dwClsContext
0x1800692e0  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800692e7  call    cs:__imp_CoCreateInstance
0x1800692ee  nop     dword ptr [rax+rax+00h]
0x1800692f3  mov     ebx, eax
0x1800692f5  test    eax, eax
0x1800692f7  jns     short loc_1800692FE
0x1800692f9  jmp     loc_180069714
0x1800692fe  mov     rdi, [rsp+1F8h+var_198]
0x180069303  mov     rax, [rdi]
0x180069306  mov     rbx, [rax+50h]
0x18006930a  lea     rcx, [rsp+1F8h+pvarg]; pvarg
0x18006930f  call    cs:__imp_VariantInit
0x180069316  nop     dword ptr [rax+rax+00h]
0x18006931b  nop
0x18006931c  movups  xmm10, xmmword ptr [rsp+1F8h+pvarg]
0x180069322  movsd   xmm11, qword ptr [rsp+1F8h+pvarg+10h]
0x18006932c  lea     rcx, [rsp+1F8h+var_118]; pvarg
0x180069334  call    cs:__imp_VariantInit
0x18006933b  nop     dword ptr [rax+rax+00h]
0x180069340  nop
0x180069341  movups  xmm8, xmmword ptr [rsp+1F8h+var_118]
0x18006934a  movsd   xmm9, qword ptr [rsp+1F8h+var_118+10h]
0x180069354  lea     rcx, [rsp+1F8h+var_130]; pvarg
0x18006935c  call    cs:__imp_VariantInit
0x180069363  nop     dword ptr [rax+rax+00h]
0x180069368  nop
0x180069369  movups  xmm6, xmmword ptr [rsp+1F8h+var_130]
0x180069371  movsd   xmm7, qword ptr [rsp+1F8h+var_130+10h]
0x18006937a  lea     rcx, [rsp+1F8h+var_148]; pvarg
0x180069382  call    cs:__imp_VariantInit
0x180069389  nop     dword ptr [rax+rax+00h]
0x18006938e  nop
0x18006938f  movups  xmm0, xmmword ptr [rsp+1F8h+var_148]
0x180069397  movsd   xmm1, qword ptr [rsp+1F8h+var_148+10h]
0x1800693a0  movaps  [rsp+1F8h+var_F8], xmm10
0x1800693a9  movsd   [rsp+1F8h+var_E8], xmm11
0x1800693b3  movaps  [rsp+1F8h+var_D8], xmm8
0x1800693bc  movsd   [rsp+1F8h+var_C8], xmm9
0x1800693c6  movaps  [rsp+1F8h+var_B8], xmm6
0x1800693ce  movsd   [rsp+1F8h+var_A8], xmm7
0x1800693d7  movaps  [rsp+1F8h+var_168], xmm0
0x1800693df  movsd   [rsp+1F8h+var_158], xmm1
0x1800693e8  lea     rax, [rsp+1F8h+var_F8]
0x1800693f0  mov     [rsp+1F8h+ppv], rax
0x1800693f5  lea     r9, [rsp+1F8h+var_D8]
0x1800693fd  lea     r8, [rsp+1F8h+var_B8]
0x180069405  lea     rdx, [rsp+1F8h+var_168]
0x18006940d  mov     rcx, rdi
0x180069410  mov     rax, rbx
0x180069413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069418  mov     ebx, eax
0x18006941a  lea     rcx, [rsp+1F8h+var_148]; this
0x180069422  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180069427  nop
0x180069428  lea     rcx, [rsp+1F8h+var_130]; this
0x180069430  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180069435  nop
0x180069436  lea     rcx, [rsp+1F8h+var_118]; this
0x18006943e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180069443  nop
0x180069444  lea     rcx, [rsp+1F8h+pvarg]; this
0x180069449  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006944e  test    ebx, ebx
0x180069450  jns     short loc_180069457
0x180069452  jmp     loc_180069714
0x180069457  mov     rbx, [rsp+1F8h+var_198]
0x18006945c  mov     rdi, [rbx]
0x18006945f  mov     rdx, r14; unsigned __int16 *
0x180069462  lea     rcx, [rsp+1F8h+var_1B0]; this
0x180069467  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006946c  nop
0x18006946d  mov     rax, [rax]
0x180069470  test    rax, rax
0x180069473  jz      short loc_18006947A
0x180069475  mov     rdx, [rax]
0x180069478  jmp     short loc_18006947D
0x18006947a  mov     rdx, rsi
0x18006947d  lea     r8, [rsp+1F8h+var_1A0]
0x180069482  mov     rcx, rbx
0x180069485  mov     rax, [rdi+38h]
0x180069489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006948e  mov     ebx, eax
0x180069490  mov     rdi, [rsp+1F8h+var_1B0]
0x180069495  or      r14d, 0FFFFFFFFh
0x180069499  test    rdi, rdi
0x18006949c  jz      short loc_1800694E6
0x18006949e  mov     eax, r14d
0x1800694a1  lock xadd [rdi+10h], eax
0x1800694a6  add     eax, r14d
0x1800694a9  jnz     short loc_1800694E6
0x1800694ab  test    rdi, rdi
0x1800694ae  jz      short loc_1800694E6
0x1800694b0  cmp     [rdi], rsi
0x1800694b3  jz      short loc_1800694C7
0x1800694b5  mov     rcx, [rdi]; bstrString
0x1800694b8  call    cs:__imp_SysFreeString
0x1800694bf  nop     dword ptr [rax+rax+00h]
0x1800694c4  mov     [rdi], rsi
0x1800694c7  mov     rcx, [rdi+8]; void *
0x1800694cb  test    rcx, rcx
0x1800694ce  jz      short loc_1800694D9
0x1800694d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800694d5  mov     [rdi+8], rsi
0x1800694d9  mov     edx, 18h; struct std::nothrow_t *
0x1800694de  mov     rcx, rdi; void *
0x1800694e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800694e6  test    ebx, ebx
0x1800694e8  jns     short loc_1800694EF
0x1800694ea  jmp     loc_180069714
0x1800694ef  test    r15, r15
0x1800694f2  jz      loc_18006958C
0x1800694f8  mov     rbx, [rsp+1F8h+var_1A0]
0x1800694fd  mov     rdi, [rbx]
0x180069500  mov     rdx, r15; unsigned __int16 *
0x180069503  lea     rcx, [rsp+1F8h+var_1B0]; this
0x180069508  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006950d  nop
0x18006950e  mov     rax, [rax]
0x180069511  test    rax, rax
0x180069514  jz      short loc_18006951B
0x180069516  mov     rdx, [rax]
0x180069519  jmp     short loc_18006951E
0x18006951b  mov     rdx, rsi
0x18006951e  lea     r8, [rsp+1F8h+var_1A8]
0x180069523  mov     rcx, rbx
0x180069526  mov     rax, [rdi+48h]
0x18006952a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006952f  mov     ebx, eax
0x180069531  mov     rdi, [rsp+1F8h+var_1B0]
0x180069536  test    rdi, rdi
0x180069539  jz      short loc_180069583
0x18006953b  mov     eax, r14d
0x18006953e  lock xadd [rdi+10h], eax
0x180069543  add     eax, r14d
0x180069546  jnz     short loc_180069583
0x180069548  test    rdi, rdi
0x18006954b  jz      short loc_180069583
0x18006954d  cmp     [rdi], rsi
0x180069550  jz      short loc_180069564
0x180069552  mov     rcx, [rdi]; bstrString
0x180069555  call    cs:__imp_SysFreeString
0x18006955c  nop     dword ptr [rax+rax+00h]
0x180069561  mov     [rdi], rsi
0x180069564  mov     rcx, [rdi+8]; void *
0x180069568  test    rcx, rcx
0x18006956b  jz      short loc_180069576
0x18006956d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069572  mov     [rdi+8], rsi
0x180069576  mov     edx, 18h; struct std::nothrow_t *
0x18006957b  mov     rcx, rdi; void *
0x18006957e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069583  test    ebx, ebx
0x180069585  jns     short loc_18006959B
0x180069587  jmp     loc_180069714
0x18006958c  lea     rdx, [rsp+1F8h+var_1A0]
0x180069591  lea     rcx, [rsp+1F8h+var_1A8]
0x180069596  call    ??4?$CComPtr@UITaskFolder@@@ATL@@QEAAPEAUITaskFolder@@AEBV01@@Z; ATL::CComPtr<ITaskFolder>::operator=(ATL::CComPtr<ITaskFolder> const &)
0x18006959b  mov     rbx, [rsp+1F8h+var_1A8]
0x1800695a0  mov     rdi, [rbx]
0x1800695a3  mov     rdx, r13; unsigned __int16 *
0x1800695a6  lea     rcx, [rsp+1F8h+var_1B0]; this
0x1800695ab  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800695b0  nop
0x1800695b1  mov     rax, [rax]
0x1800695b4  test    rax, rax
0x1800695b7  jz      short loc_1800695BE
0x1800695b9  mov     rdx, [rax]
0x1800695bc  jmp     short loc_1800695C1
0x1800695be  mov     rdx, rsi
0x1800695c1  lea     r8, [rsp+1F8h+var_188]
0x1800695c6  mov     rcx, rbx
0x1800695c9  mov     rax, [rdi+68h]
0x1800695cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695d2  mov     ebx, eax
0x1800695d4  mov     rdi, [rsp+1F8h+var_1B0]
0x1800695d9  test    rdi, rdi
0x1800695dc  jz      short loc_180069626
0x1800695de  mov     eax, r14d
0x1800695e1  lock xadd [rdi+10h], eax
0x1800695e6  add     eax, r14d
0x1800695e9  jnz     short loc_180069626
0x1800695eb  test    rdi, rdi
0x1800695ee  jz      short loc_180069626
0x1800695f0  cmp     [rdi], rsi
0x1800695f3  jz      short loc_180069607
0x1800695f5  mov     rcx, [rdi]; bstrString
0x1800695f8  call    cs:__imp_SysFreeString
0x1800695ff  nop     dword ptr [rax+rax+00h]
0x180069604  mov     [rdi], rsi
0x180069607  mov     rcx, [rdi+8]; void *
0x18006960b  test    rcx, rcx
0x18006960e  jz      short loc_180069619
0x180069610  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069615  mov     [rdi+8], rsi
0x180069619  mov     edx, 18h; struct std::nothrow_t *
0x18006961e  mov     rcx, rdi; void *
0x180069621  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069626  test    ebx, ebx
0x180069628  jns     short loc_18006962F
0x18006962a  jmp     loc_180069714
0x18006962f  mov     rdi, [rsp+1F8h+var_188]
0x180069634  mov     rax, [rdi]
0x180069637  mov     rbx, [rax+68h]
0x18006963b  lea     rcx, [rsp+1F8h+pvarg]; pvarg
0x180069640  call    cs:__imp_VariantInit
0x180069647  nop     dword ptr [rax+rax+00h]
0x18006964c  nop
0x18006964d  movups  xmm0, xmmword ptr [rsp+1F8h+pvarg]
0x180069652  movaps  [rsp+1F8h+var_168], xmm0
0x18006965a  movsd   xmm1, qword ptr [rsp+1F8h+pvarg+10h]
0x180069663  movsd   [rsp+1F8h+var_158], xmm1
0x18006966c  lea     rax, [rsp+1F8h+var_190]
0x180069671  mov     [rsp+1F8h+var_1D0], rax
0x180069676  mov     [rsp+1F8h+ppv], rsi
0x18006967b  xor     r9d, r9d
0x18006967e  lea     r8d, [r9+2]
0x180069682  lea     rdx, [rsp+1F8h+var_168]
0x18006968a  mov     rcx, rdi
0x18006968d  mov     rax, rbx
0x180069690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069695  mov     ebx, eax
0x180069697  lea     rcx, [rsp+1F8h+pvarg]; this
0x18006969c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800696a1  test    ebx, ebx
0x1800696a3  jns     short loc_1800696A7
0x1800696a5  jmp     short loc_180069714
0x1800696a7  test    r12, r12
0x1800696aa  jz      short loc_18006970C
0x1800696ac  mov     [rsp+1F8h+dwProcessId], esi
0x1800696b0  mov     rcx, [rsp+1F8h+var_190]
0x1800696b5  mov     rax, [rcx]
0x1800696b8  lea     rdx, [rsp+1F8h+dwProcessId]
0x1800696bd  mov     rax, [rax+70h]
0x1800696c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696c6  mov     ebx, eax
0x1800696c8  test    eax, eax
0x1800696ca  jns     short loc_1800696CE
0x1800696cc  jmp     short loc_180069714
0x1800696ce  mov     r8d, [rsp+1F8h+dwProcessId]; dwProcessId
0x1800696d3  xor     edx, edx; bInheritHandle
0x1800696d5  mov     ecx, 101000h; dwDesiredAccess
0x1800696da  call    cs:__imp_OpenProcess
0x1800696e1  nop     dword ptr [rax+rax+00h]
0x1800696e6  test    rax, rax
0x1800696e9  jnz     short loc_180069708
0x1800696eb  call    cs:__imp_GetLastError
0x1800696f2  nop     dword ptr [rax+rax+00h]
0x1800696f7  mov     ebx, eax
0x1800696f9  test    eax, eax
0x1800696fb  jle     short loc_180069706
0x1800696fd  movzx   ebx, ax
0x180069700  or      ebx, 80070000h
0x180069706  jmp     short loc_180069714
0x180069708  mov     [r12], rax
0x18006970c  jmp     short loc_180069714
0x18006970e  xor     esi, esi
0x180069710  mov     ebx, [rsp+1F8h+dwProcessId]
0x180069714  lea     rcx, [rsp+1F8h+var_190]
0x180069719  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x18006971e  nop
0x18006971f  lea     rcx, [rsp+1F8h+var_188]
0x180069724  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180069729  nop
0x18006972a  lea     rcx, [rsp+1F8h+var_1A8]
0x18006972f  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180069734  nop
0x180069735  lea     rcx, [rsp+1F8h+var_1A0]
  ... truncated ...
```
