# DmDisableTask(ushort const *,ushort const *,ushort const *)

- ea: `0x1800163f4`
- end: `0x180016afe`
- name: `?DmDisableTask@@YAJPEBG00@Z`
- size: `1802`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000c980`

## callees

- `0x180001cc8`
- `0x180007258`
- `0x180007364`
- `0x1800079e8`
- `0x180008428`
- `0x18000c938`
- `0x180015ddc`
- `0x1800163f4`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016710`
- `OLEAUT32!__imp_SysFreeString` at `0x18001681f`
- `OLEAUT32!__imp_SysFreeString` at `0x180016949`
- `OLEAUT32!__imp_SysFreeString` at `0x180016710`
- `OLEAUT32!__imp_SysFreeString` at `0x18001681f`
- `OLEAUT32!__imp_SysFreeString` at `0x180016949`
- `OLEAUT32!__imp_VariantInit` at `0x180016509`
- `OLEAUT32!__imp_VariantInit` at `0x180016531`
- `OLEAUT32!__imp_VariantInit` at `0x180016556`
- `OLEAUT32!__imp_VariantInit` at `0x180016573`
- `OLEAUT32!__imp_VariantInit` at `0x180016509`
- `OLEAUT32!__imp_VariantInit` at `0x180016531`
- `OLEAUT32!__imp_VariantInit` at `0x180016556`
- `OLEAUT32!__imp_VariantInit` at `0x180016573`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800164e1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016699`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800167a2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800168b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800169db`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016a68`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016abd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800164e1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016699`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800167a2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800168b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800169db`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016a68`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016abd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016470`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016470`

## string_xrefs

- `0x1800168f1`: `Wsc Startup event listener created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall DmDisableTask(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
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
  const struct std::nothrow_t *v22; // rdx
  int v23; // r14d
  BSTR *v24; // rbx
  BSTR v25; // rcx
  char v26; // al
  struct IUnknown *v27; // rbx
  struct IUnknownVtbl *lpVtbl; // r14
  __int64 *v29; // rax
  __int64 v30; // rdx
  const struct std::nothrow_t *v31; // rdx
  int v32; // r14d
  BSTR *v33; // rbx
  BSTR v34; // rcx
  char v35; // al
  struct IUnknown *v36; // rbx
  struct IUnknownVtbl *v37; // r14
  __int64 *v38; // rax
  __int64 v39; // rdx
  const struct std::nothrow_t *v40; // rdx
  int v41; // r14d
  BSTR *v42; // rbx
  BSTR v43; // rcx
  char v44; // al
  int v45; // eax
  unsigned int v46; // ebx
  char v47; // al
  int ppv; // [rsp+20h] [rbp-198h]
  struct IUnknown *v49; // [rsp+30h] [rbp-188h] BYREF
  LPVOID v50; // [rsp+38h] [rbp-180h] BYREF
  __int64 v51; // [rsp+40h] [rbp-178h] BYREF
  void *v52; // [rsp+48h] [rbp-170h] BYREF
  VARIANTARG v53; // [rsp+50h] [rbp-168h] BYREF
  VARIANTARG v54; // [rsp+68h] [rbp-150h] BYREF
  VARIANTARG v55; // [rsp+80h] [rbp-138h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-120h] BYREF
  int v57[4]; // [rsp+B0h] [rbp-108h] BYREF
  IRecordInfo *v58; // [rsp+C0h] [rbp-F8h]
  __int128 v59; // [rsp+D0h] [rbp-E8h] BYREF
  IRecordInfo *v60; // [rsp+E0h] [rbp-D8h]
  __int128 v61; // [rsp+F0h] [rbp-C8h] BYREF
  IRecordInfo *v62; // [rsp+100h] [rbp-B8h]
  VARIANTARG v63; // [rsp+110h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]
  const unsigned __int16 *v65; // [rsp+1D0h] [rbp+18h] BYREF
  struct IUnknown *v66; // [rsp+1D8h] [rbp+20h] BYREF

  v65 = a3;
  wil::CoInitializeEx(&v65);
  v50 = 0;
  v49 = 0;
  v66 = 0;
  v51 = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v50);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x267,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v66);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
    v6 = (char)v65;
    LOBYTE(v65) = 0;
    if ( v6 )
      CoUninitialize();
    return v5;
  }
  v8 = v50;
  v9 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v50 + 80LL);
  VariantInit(&pvarg);
  v10 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v55);
  v12 = *(_OWORD *)&v55.vt;
  v13 = v55.pRecInfo;
  VariantInit(&v54);
  v14 = *(_OWORD *)&v54.vt;
  v15 = v54.pRecInfo;
  VariantInit(&v53);
  *(_OWORD *)v57 = v10;
  v58 = pRecInfo;
  v59 = v12;
  v60 = v13;
  v61 = v14;
  v62 = v15;
  v63 = v53;
  v16 = v9(v8, &v63, &v61, &v59);
  _variant_t::~_variant_t((_variant_t *)&v53);
  _variant_t::~_variant_t((_variant_t *)&v54);
  _variant_t::~_variant_t((_variant_t *)&v55);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x269,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v16,
      (int)v57);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v66);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
    v17 = (char)v65;
    LOBYTE(v65) = 0;
    if ( v17 )
      CoUninitialize();
    return (unsigned int)v16;
  }
  v18 = v50;
  v19 = *(_QWORD *)v50;
  v20 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v52, L"\\Microsoft\\Windows\\EnterpriseMgmt");
  if ( v20 )
    v21 = *v20;
  else
    v21 = 0;
  v23 = (*(__int64 (__fastcall **)(LPVOID, __int64, struct IUnknown **))(v19 + 56))(v18, v21, &v49);
  v24 = (BSTR *)v52;
  if ( v52 && _InterlockedExchangeAdd((volatile signed __int32 *)v52 + 4, 0xFFFFFFFF) == 1 && v24 )
  {
    if ( *v24 )
    {
      SysFreeString(*v24);
      *v24 = 0;
    }
    v25 = v24[1];
    if ( v25 )
    {
      operator delete(v25, v22);
      v24[1] = 0;
    }
    operator delete(v24, (const struct std::nothrow_t *)0x18);
  }
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26B,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v23,
      (int)v57);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v66);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
    v26 = (char)v65;
    LOBYTE(v65) = 0;
    if ( v26 )
      CoUninitialize();
    return (unsigned int)v23;
  }
  if ( a2 )
  {
    v27 = v49;
    lpVtbl = v49->lpVtbl;
    v29 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v52, a2);
    if ( v29 )
      v30 = *v29;
    else
      v30 = 0;
    v32 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))lpVtbl[3].QueryInterface)(
            v27,
            v30,
            &v66);
    v33 = (BSTR *)v52;
    if ( v52 && _InterlockedExchangeAdd((volatile signed __int32 *)v52 + 4, 0xFFFFFFFF) == 1 && v33 )
    {
      if ( *v33 )
      {
        SysFreeString(*v33);
        *v33 = 0;
      }
      v34 = v33[1];
      if ( v34 )
      {
        operator delete(v34, v31);
        v33[1] = 0;
      }
      operator delete(v33, (const struct std::nothrow_t *)0x18);
    }
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26F,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
        (const char *)(unsigned int)v32,
        (int)v57);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v66);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
      v35 = (char)v65;
      LOBYTE(v65) = 0;
      if ( v35 )
        CoUninitialize();
      return (unsigned int)v32;
    }
  }
  else if ( v66 != v49 )
  {
    ATL::AtlComPtrAssign(&v66, v49);
  }
  v36 = v66;
  v37 = v66->lpVtbl;
  v38 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v52, L"Wsc Startup event listener created by enrollment client");
  if ( v38 )
    v39 = *v38;
  else
    v39 = 0;
  v41 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))v37[4].AddRef)(v36, v39, &v51);
  v42 = (BSTR *)v52;
  if ( v52 && _InterlockedExchangeAdd((volatile signed __int32 *)v52 + 4, 0xFFFFFFFF) == 1 && v42 )
  {
    if ( *v42 )
    {
      SysFreeString(*v42);
      *v42 = 0;
    }
    v43 = v42[1];
    if ( v43 )
    {
      operator delete(v43, v40);
      v42[1] = 0;
    }
    operator delete(v42, (const struct std::nothrow_t *)0x18);
  }
  if ( v41 >= 0 )
  {
    v45 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v51 + 88LL))(v51, 0);
    v46 = v45;
    if ( v45 >= 0 )
    {
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v66);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
      if ( (_BYTE)v65 )
        CoUninitialize();
      return v46;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27A,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
        (const char *)(unsigned int)v45,
        (int)v57);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v66);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
      v47 = (char)v65;
      LOBYTE(v65) = 0;
      if ( v47 )
        CoUninitialize();
      return v46;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x277,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v41,
      (int)v57);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v66);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
    v44 = (char)v65;
    LOBYTE(v65) = 0;
    if ( v44 )
      CoUninitialize();
    return (unsigned int)v41;
  }
}

```

## disassembly

```asm
0x1800163f4  mov     rax, rsp
0x1800163f7  mov     [rax+18h], r8
0x1800163fb  mov     [rax+8], rcx
0x1800163ff  push    rbx
0x180016400  push    rsi
0x180016401  push    rdi
0x180016402  push    r14
0x180016404  push    r15
0x180016406  sub     rsp, 190h
0x18001640d  movaps  xmmword ptr [rax-38h], xmm6
0x180016411  movaps  xmmword ptr [rax-48h], xmm7
0x180016415  movaps  xmmword ptr [rax-58h], xmm8
0x18001641a  movaps  xmmword ptr [rax-68h], xmm9
0x18001641f  movaps  xmmword ptr [rax-78h], xmm10
0x180016424  movaps  xmmword ptr [rax-88h], xmm11
0x18001642c  mov     r15, rdx
0x18001642f  lea     rcx, [rax+18h]
0x180016433  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x180016438  nop
0x180016439  xor     esi, esi
0x18001643b  mov     [rsp+1B8h+var_180], rsi
0x180016440  mov     [rsp+1B8h+var_188], rsi
0x180016445  mov     [rsp+1B8h+arg_18], rsi
0x18001644d  mov     [rsp+1B8h+var_178], rsi
0x180016452  lea     rax, [rsp+1B8h+var_180]
0x180016457  mov     qword ptr [rsp+1B8h+ppv], rax; int
0x18001645c  lea     r9, IID_ITaskService; riid
0x180016463  xor     edx, edx; pUnkOuter
0x180016465  lea     r8d, [rsi+1]; dwClsContext
0x180016469  lea     rcx, CLSID_TaskScheduler; rclsid
0x180016470  call    cs:__imp_CoCreateInstance
0x180016477  nop     dword ptr [rax+rax+00h]
0x18001647c  mov     ebx, eax
0x18001647e  test    eax, eax
0x180016480  jns     short loc_1800164F5
0x180016482  mov     rcx, [rsp+1B8h]; this
0x18001648a  mov     r9d, eax; char *
0x18001648d  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180016494  mov     edx, 267h; void *
0x180016499  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001649e  nop
0x18001649f  lea     rcx, [rsp+1B8h+var_178]
0x1800164a4  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800164a9  nop
0x1800164aa  lea     rcx, [rsp+1B8h+arg_18]
0x1800164b2  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800164b7  nop
0x1800164b8  lea     rcx, [rsp+1B8h+var_188]
0x1800164bd  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800164c2  nop
0x1800164c3  lea     rcx, [rsp+1B8h+var_180]
0x1800164c8  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800164cd  nop
0x1800164ce  mov     al, byte ptr [rsp+1B8h+arg_10]
0x1800164d5  mov     byte ptr [rsp+1B8h+arg_10], sil
0x1800164dd  test    al, al
0x1800164df  jz      short loc_1800164EE
0x1800164e1  call    cs:__imp_CoUninitialize
0x1800164e8  nop     dword ptr [rax+rax+00h]
0x1800164ed  nop
0x1800164ee  mov     eax, ebx
0x1800164f0  jmp     loc_180016ACC
0x1800164f5  mov     rdi, [rsp+1B8h+var_180]
0x1800164fa  mov     rax, [rdi]
0x1800164fd  mov     rbx, [rax+50h]
0x180016501  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x180016509  call    cs:__imp_VariantInit
0x180016510  nop     dword ptr [rax+rax+00h]
0x180016515  nop
0x180016516  movups  xmm10, xmmword ptr [rsp+1B8h+pvarg]
0x18001651f  movsd   xmm11, qword ptr [rsp+1B8h+pvarg+10h]
0x180016529  lea     rcx, [rsp+1B8h+var_138]; pvarg
0x180016531  call    cs:__imp_VariantInit
0x180016538  nop     dword ptr [rax+rax+00h]
0x18001653d  nop
0x18001653e  movups  xmm8, xmmword ptr [rsp+1B8h+var_138]
0x180016547  movsd   xmm9, qword ptr [rsp+1B8h+var_138+10h]
0x180016551  lea     rcx, [rsp+1B8h+var_150]; pvarg
0x180016556  call    cs:__imp_VariantInit
0x18001655d  nop     dword ptr [rax+rax+00h]
0x180016562  nop
0x180016563  movups  xmm6, xmmword ptr [rsp+1B8h+var_150]
0x180016568  movsd   xmm7, qword ptr [rsp+1B8h+var_150+10h]
0x18001656e  lea     rcx, [rsp+1B8h+var_168]; pvarg
0x180016573  call    cs:__imp_VariantInit
0x18001657a  nop     dword ptr [rax+rax+00h]
0x18001657f  nop
0x180016580  movups  xmm0, xmmword ptr [rsp+1B8h+var_168]
0x180016585  movsd   xmm1, qword ptr [rsp+1B8h+var_168+10h]
0x18001658b  movaps  xmmword ptr [rsp+1B8h+var_108], xmm10
0x180016594  movsd   [rsp+1B8h+var_F8], xmm11
0x18001659e  movaps  [rsp+1B8h+var_E8], xmm8
0x1800165a7  movsd   [rsp+1B8h+var_D8], xmm9
0x1800165b1  movaps  [rsp+1B8h+var_C8], xmm6
0x1800165b9  movsd   [rsp+1B8h+var_B8], xmm7
0x1800165c2  movaps  [rsp+1B8h+var_A8], xmm0
0x1800165ca  movsd   [rsp+1B8h+var_98], xmm1
0x1800165d3  lea     rax, [rsp+1B8h+var_108]
0x1800165db  mov     qword ptr [rsp+1B8h+ppv], rax; int
0x1800165e0  lea     r9, [rsp+1B8h+var_E8]
0x1800165e8  lea     r8, [rsp+1B8h+var_C8]
0x1800165f0  lea     rdx, [rsp+1B8h+var_A8]
0x1800165f8  mov     rcx, rdi
0x1800165fb  mov     rax, rbx
0x1800165fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016603  mov     ebx, eax
0x180016605  lea     rcx, [rsp+1B8h+var_168]; this
0x18001660a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18001660f  nop
0x180016610  lea     rcx, [rsp+1B8h+var_150]; this
0x180016615  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18001661a  nop
0x18001661b  lea     rcx, [rsp+1B8h+var_138]; this
0x180016623  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180016628  nop
0x180016629  lea     rcx, [rsp+1B8h+pvarg]; this
0x180016631  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180016636  test    ebx, ebx
0x180016638  jns     short loc_1800166AD
0x18001663a  mov     rcx, [rsp+1B8h]; this
0x180016642  mov     r9d, ebx; char *
0x180016645  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x18001664c  mov     edx, 269h; void *
0x180016651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016656  nop
0x180016657  lea     rcx, [rsp+1B8h+var_178]
0x18001665c  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016661  nop
0x180016662  lea     rcx, [rsp+1B8h+arg_18]
0x18001666a  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18001666f  nop
0x180016670  lea     rcx, [rsp+1B8h+var_188]
0x180016675  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18001667a  nop
0x18001667b  lea     rcx, [rsp+1B8h+var_180]
0x180016680  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016685  nop
0x180016686  mov     al, byte ptr [rsp+1B8h+arg_10]
0x18001668d  mov     byte ptr [rsp+1B8h+arg_10], sil
0x180016695  test    al, al
0x180016697  jz      short loc_1800166A6
0x180016699  call    cs:__imp_CoUninitialize
0x1800166a0  nop     dword ptr [rax+rax+00h]
0x1800166a5  nop
0x1800166a6  mov     eax, ebx
0x1800166a8  jmp     loc_180016ACC
0x1800166ad  mov     rbx, [rsp+1B8h+var_180]
0x1800166b2  mov     rdi, [rbx]
0x1800166b5  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800166bc  lea     rcx, [rsp+1B8h+var_170]; this
0x1800166c1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800166c6  nop
0x1800166c7  mov     rax, [rax]
0x1800166ca  test    rax, rax
0x1800166cd  jz      short loc_1800166D4
0x1800166cf  mov     rdx, [rax]
0x1800166d2  jmp     short loc_1800166D7
0x1800166d4  mov     rdx, rsi
0x1800166d7  lea     r8, [rsp+1B8h+var_188]
0x1800166dc  mov     rcx, rbx
0x1800166df  mov     rax, [rdi+38h]
0x1800166e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166e8  mov     r14d, eax
0x1800166eb  mov     rbx, [rsp+1B8h+var_170]
0x1800166f0  or      edi, 0FFFFFFFFh
0x1800166f3  test    rbx, rbx
0x1800166f6  jz      short loc_18001673E
0x1800166f8  mov     ecx, edi
0x1800166fa  lock xadd [rbx+10h], ecx
0x1800166ff  add     ecx, edi
0x180016701  jnz     short loc_18001673E
0x180016703  test    rbx, rbx
0x180016706  jz      short loc_18001673E
0x180016708  cmp     [rbx], rsi
0x18001670b  jz      short loc_18001671F
0x18001670d  mov     rcx, [rbx]; bstrString
0x180016710  call    cs:__imp_SysFreeString
0x180016717  nop     dword ptr [rax+rax+00h]
0x18001671c  mov     [rbx], rsi
0x18001671f  mov     rcx, [rbx+8]; void *
0x180016723  test    rcx, rcx
0x180016726  jz      short loc_180016731
0x180016728  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001672d  mov     [rbx+8], rsi
0x180016731  mov     edx, 18h; struct std::nothrow_t *
0x180016736  mov     rcx, rbx; void *
0x180016739  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001673e  test    r14d, r14d
0x180016741  jns     short loc_1800167B7
0x180016743  mov     rcx, [rsp+1B8h]; this
0x18001674b  mov     r9d, r14d; char *
0x18001674e  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180016755  mov     edx, 26Bh; void *
0x18001675a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001675f  nop
0x180016760  lea     rcx, [rsp+1B8h+var_178]
0x180016765  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18001676a  nop
0x18001676b  lea     rcx, [rsp+1B8h+arg_18]
0x180016773  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016778  nop
0x180016779  lea     rcx, [rsp+1B8h+var_188]
0x18001677e  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016783  nop
0x180016784  lea     rcx, [rsp+1B8h+var_180]
0x180016789  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18001678e  nop
0x18001678f  mov     al, byte ptr [rsp+1B8h+arg_10]
0x180016796  mov     byte ptr [rsp+1B8h+arg_10], sil
0x18001679e  test    al, al
0x1800167a0  jz      short loc_1800167AF
0x1800167a2  call    cs:__imp_CoUninitialize
0x1800167a9  nop     dword ptr [rax+rax+00h]
0x1800167ae  nop
0x1800167af  mov     eax, r14d
0x1800167b2  jmp     loc_180016ACC
0x1800167b7  test    r15, r15
0x1800167ba  jz      loc_1800168CA
0x1800167c0  mov     rbx, [rsp+1B8h+var_188]
0x1800167c5  mov     r14, [rbx]
0x1800167c8  mov     rdx, r15; unsigned __int16 *
0x1800167cb  lea     rcx, [rsp+1B8h+var_170]; this
0x1800167d0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800167d5  nop
0x1800167d6  mov     rax, [rax]
0x1800167d9  test    rax, rax
0x1800167dc  jz      short loc_1800167E3
0x1800167de  mov     rdx, [rax]
0x1800167e1  jmp     short loc_1800167E6
0x1800167e3  mov     rdx, rsi
0x1800167e6  lea     r8, [rsp+1B8h+arg_18]
0x1800167ee  mov     rcx, rbx
0x1800167f1  mov     rax, [r14+48h]
0x1800167f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167fa  mov     r14d, eax
0x1800167fd  mov     rbx, [rsp+1B8h+var_170]
0x180016802  test    rbx, rbx
0x180016805  jz      short loc_18001684D
0x180016807  mov     ecx, edi
0x180016809  lock xadd [rbx+10h], ecx
0x18001680e  add     ecx, edi
0x180016810  jnz     short loc_18001684D
0x180016812  test    rbx, rbx
0x180016815  jz      short loc_18001684D
0x180016817  cmp     [rbx], rsi
0x18001681a  jz      short loc_18001682E
0x18001681c  mov     rcx, [rbx]; bstrString
0x18001681f  call    cs:__imp_SysFreeString
0x180016826  nop     dword ptr [rax+rax+00h]
0x18001682b  mov     [rbx], rsi
0x18001682e  mov     rcx, [rbx+8]; void *
0x180016832  test    rcx, rcx
0x180016835  jz      short loc_180016840
0x180016837  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001683c  mov     [rbx+8], rsi
0x180016840  mov     edx, 18h; struct std::nothrow_t *
0x180016845  mov     rcx, rbx; void *
0x180016848  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001684d  test    r14d, r14d
0x180016850  jns     loc_1800168E6
0x180016856  mov     rcx, [rsp+1B8h]; this
0x18001685e  mov     r9d, r14d; char *
0x180016861  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180016868  mov     edx, 26Fh; void *
0x18001686d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016872  nop
0x180016873  lea     rcx, [rsp+1B8h+var_178]
0x180016878  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18001687d  nop
0x18001687e  lea     rcx, [rsp+1B8h+arg_18]
0x180016886  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18001688b  nop
0x18001688c  lea     rcx, [rsp+1B8h+var_188]
0x180016891  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016896  nop
0x180016897  lea     rcx, [rsp+1B8h+var_180]
0x18001689c  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800168a1  nop
0x1800168a2  mov     al, byte ptr [rsp+1B8h+arg_10]
0x1800168a9  mov     byte ptr [rsp+1B8h+arg_10], sil
0x1800168b1  test    al, al
0x1800168b3  jz      short loc_1800168C2
0x1800168b5  call    cs:__imp_CoUninitialize
0x1800168bc  nop     dword ptr [rax+rax+00h]
0x1800168c1  nop
0x1800168c2  mov     eax, r14d
0x1800168c5  jmp     loc_180016ACC
0x1800168ca  mov     rdx, [rsp+1B8h+var_188]; struct IUnknown *
0x1800168cf  cmp     [rsp+1B8h+arg_18], rdx
0x1800168d7  jz      short loc_1800168E6
0x1800168d9  lea     rcx, [rsp+1B8h+arg_18]; struct IUnknown **
0x1800168e1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800168e6  mov     rbx, [rsp+1B8h+arg_18]
0x1800168ee  mov     r14, [rbx]
0x1800168f1  lea     rdx, aWscStartupEven; "Wsc Startup event listener created by e"...
0x1800168f8  lea     rcx, [rsp+1B8h+var_170]; this
0x1800168fd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180016902  nop
0x180016903  mov     rax, [rax]
0x180016906  test    rax, rax
  ... truncated ...
```
