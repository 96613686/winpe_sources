# DmDeleteTask(ushort const *,ushort const *,ushort const *)

- ea: `0x180015e1c`
- end: `0x1800163eb`
- name: `?DmDeleteTask@@YAJPEBG00@Z`
- size: `1487`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180010804`

## callees

- `0x180001cc8`
- `0x180007258`
- `0x180007364`
- `0x1800079e8`
- `0x180008428`
- `0x18000c938`
- `0x180015ddc`
- `0x180015e1c`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016114`
- `OLEAUT32!__imp_SysFreeString` at `0x180016218`
- `OLEAUT32!__imp_SysFreeString` at `0x180016335`
- `OLEAUT32!__imp_SysFreeString` at `0x180016114`
- `OLEAUT32!__imp_SysFreeString` at `0x180016218`
- `OLEAUT32!__imp_SysFreeString` at `0x180016335`
- `OLEAUT32!__imp_VariantInit` at `0x180015f21`
- `OLEAUT32!__imp_VariantInit` at `0x180015f46`
- `OLEAUT32!__imp_VariantInit` at `0x180015f68`
- `OLEAUT32!__imp_VariantInit` at `0x180015f85`
- `OLEAUT32!__imp_VariantInit` at `0x180015f21`
- `OLEAUT32!__imp_VariantInit` at `0x180015f46`
- `OLEAUT32!__imp_VariantInit` at `0x180015f68`
- `OLEAUT32!__imp_VariantInit` at `0x180015f85`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015ef9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001609d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001619b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800162a3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800163aa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015ef9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001609d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001619b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800162a3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800163aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015e93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015e93`

## string_xrefs

- `0x1800162df`: `Schedule #4 created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall DmDeleteTask(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
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
  unsigned int v41; // r14d
  BSTR *v42; // rbx
  BSTR v43; // rcx
  unsigned int v44; // ebx
  int ppv; // [rsp+20h] [rbp-198h]
  struct IUnknown *v46; // [rsp+30h] [rbp-188h] BYREF
  LPVOID v47; // [rsp+38h] [rbp-180h] BYREF
  void *v48; // [rsp+40h] [rbp-178h] BYREF
  VARIANTARG v49; // [rsp+48h] [rbp-170h] BYREF
  VARIANTARG v50; // [rsp+60h] [rbp-158h] BYREF
  VARIANTARG v51; // [rsp+78h] [rbp-140h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-128h] BYREF
  int v53[4]; // [rsp+B0h] [rbp-108h] BYREF
  IRecordInfo *v54; // [rsp+C0h] [rbp-F8h]
  __int128 v55; // [rsp+D0h] [rbp-E8h] BYREF
  IRecordInfo *v56; // [rsp+E0h] [rbp-D8h]
  __int128 v57; // [rsp+F0h] [rbp-C8h] BYREF
  IRecordInfo *v58; // [rsp+100h] [rbp-B8h]
  VARIANTARG v59; // [rsp+110h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]
  const unsigned __int16 *v61; // [rsp+1D0h] [rbp+18h] BYREF
  struct IUnknown *v62; // [rsp+1D8h] [rbp+20h] BYREF

  v61 = a3;
  wil::CoInitializeEx(&v61);
  v47 = 0;
  v46 = 0;
  v62 = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v47);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v62);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v46);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v47);
    v6 = (char)v61;
    LOBYTE(v61) = 0;
    if ( v6 )
      CoUninitialize();
    return v5;
  }
  v8 = v47;
  v9 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v47 + 80LL);
  VariantInit(&pvarg);
  v10 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v51);
  v12 = *(_OWORD *)&v51.vt;
  v13 = v51.pRecInfo;
  VariantInit(&v50);
  v14 = *(_OWORD *)&v50.vt;
  v15 = v50.pRecInfo;
  VariantInit(&v49);
  *(_OWORD *)v53 = v10;
  v54 = pRecInfo;
  v55 = v12;
  v56 = v13;
  v57 = v14;
  v58 = v15;
  v59 = v49;
  v16 = v9(v8, &v59, &v57, &v55);
  _variant_t::~_variant_t((_variant_t *)&v49);
  _variant_t::~_variant_t((_variant_t *)&v50);
  _variant_t::~_variant_t((_variant_t *)&v51);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v16,
      (int)v53);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v62);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v46);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v47);
    v17 = (char)v61;
    LOBYTE(v61) = 0;
    if ( v17 )
      CoUninitialize();
    return (unsigned int)v16;
  }
  v18 = v47;
  v19 = *(_QWORD *)v47;
  v20 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v48, L"\\Microsoft\\Windows\\EnterpriseMgmt");
  if ( v20 )
    v21 = *v20;
  else
    v21 = 0;
  v23 = (*(__int64 (__fastcall **)(LPVOID, __int64, struct IUnknown **))(v19 + 56))(v18, v21, &v46);
  v24 = (BSTR *)v48;
  if ( v48 && _InterlockedExchangeAdd((volatile signed __int32 *)v48 + 4, 0xFFFFFFFF) == 1 && v24 )
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
      (void *)0x131,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
      (const char *)(unsigned int)v23,
      (int)v53);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v62);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v46);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v47);
    v26 = (char)v61;
    LOBYTE(v61) = 0;
    if ( v26 )
      CoUninitialize();
    return (unsigned int)v23;
  }
  if ( a2 )
  {
    v27 = v46;
    lpVtbl = v46->lpVtbl;
    v29 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v48, a2);
    if ( v29 )
      v30 = *v29;
    else
      v30 = 0;
    v32 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))lpVtbl[3].QueryInterface)(
            v27,
            v30,
            &v62);
    v33 = (BSTR *)v48;
    if ( v48 && _InterlockedExchangeAdd((volatile signed __int32 *)v48 + 4, 0xFFFFFFFF) == 1 && v33 )
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
        (void *)0x135,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\scheduleutils\\scheduleutils.cpp",
        (const char *)(unsigned int)v32,
        (int)v53);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v62);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v46);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v47);
      v35 = (char)v61;
      LOBYTE(v61) = 0;
      if ( v35 )
        CoUninitialize();
      return (unsigned int)v32;
    }
  }
  else if ( v62 != v46 )
  {
    ATL::AtlComPtrAssign(&v62, v46);
  }
  v36 = v62;
  v37 = v62->lpVtbl;
  v38 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v48, L"Schedule #4 created by enrollment client");
  if ( v38 )
    v39 = *v38;
  else
    v39 = 0;
  v41 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v37[5].QueryInterface)(v36, v39, 0);
  v42 = (BSTR *)v48;
  if ( v48 && _InterlockedExchangeAdd((volatile signed __int32 *)v48 + 4, 0xFFFFFFFF) == 1 && v42 )
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
  v44 = 0;
  if ( v41 != -2147024894 )
    v44 = v41;
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v62);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v46);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v47);
  if ( (_BYTE)v61 )
    CoUninitialize();
  return v44;
}

```

## disassembly

```asm
0x180015e1c  mov     rax, rsp
0x180015e1f  mov     [rax+18h], r8
0x180015e23  mov     [rax+8], rcx
0x180015e27  push    rbx
0x180015e28  push    rsi
0x180015e29  push    rdi
0x180015e2a  push    r14
0x180015e2c  push    r15
0x180015e2e  sub     rsp, 190h
0x180015e35  movaps  xmmword ptr [rax-38h], xmm6
0x180015e39  movaps  xmmword ptr [rax-48h], xmm7
0x180015e3d  movaps  xmmword ptr [rax-58h], xmm8
0x180015e42  movaps  xmmword ptr [rax-68h], xmm9
0x180015e47  movaps  xmmword ptr [rax-78h], xmm10
0x180015e4c  movaps  xmmword ptr [rax-88h], xmm11
0x180015e54  mov     r15, rdx
0x180015e57  lea     rcx, [rax+18h]
0x180015e5b  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x180015e60  nop
0x180015e61  xor     esi, esi
0x180015e63  mov     [rsp+1B8h+var_180], rsi
0x180015e68  mov     [rsp+1B8h+var_188], rsi
0x180015e6d  mov     [rsp+1B8h+arg_18], rsi
0x180015e75  lea     rax, [rsp+1B8h+var_180]
0x180015e7a  mov     qword ptr [rsp+1B8h+ppv], rax; int
0x180015e7f  lea     r9, IID_ITaskService; riid
0x180015e86  xor     edx, edx; pUnkOuter
0x180015e88  lea     r8d, [rsi+1]; dwClsContext
0x180015e8c  lea     rcx, CLSID_TaskScheduler; rclsid
0x180015e93  call    cs:__imp_CoCreateInstance
0x180015e9a  nop     dword ptr [rax+rax+00h]
0x180015e9f  mov     ebx, eax
0x180015ea1  test    eax, eax
0x180015ea3  jns     short loc_180015F0D
0x180015ea5  mov     rcx, [rsp+1B8h]; this
0x180015ead  mov     r9d, eax; char *
0x180015eb0  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180015eb7  mov     edx, 12Ch; void *
0x180015ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ec1  nop
0x180015ec2  lea     rcx, [rsp+1B8h+arg_18]
0x180015eca  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180015ecf  nop
0x180015ed0  lea     rcx, [rsp+1B8h+var_188]
0x180015ed5  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180015eda  nop
0x180015edb  lea     rcx, [rsp+1B8h+var_180]
0x180015ee0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180015ee5  nop
0x180015ee6  mov     al, byte ptr [rsp+1B8h+arg_10]
0x180015eed  mov     byte ptr [rsp+1B8h+arg_10], sil
0x180015ef5  test    al, al
0x180015ef7  jz      short loc_180015F06
0x180015ef9  call    cs:__imp_CoUninitialize
0x180015f00  nop     dword ptr [rax+rax+00h]
0x180015f05  nop
0x180015f06  mov     eax, ebx
0x180015f08  jmp     loc_1800163B9
0x180015f0d  mov     rdi, [rsp+1B8h+var_180]
0x180015f12  mov     rax, [rdi]
0x180015f15  mov     rbx, [rax+50h]
0x180015f19  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x180015f21  call    cs:__imp_VariantInit
0x180015f28  nop     dword ptr [rax+rax+00h]
0x180015f2d  nop
0x180015f2e  movups  xmm10, xmmword ptr [rsp+1B8h+pvarg]
0x180015f37  movsd   xmm11, qword ptr [rsp+1B8h+pvarg+10h]
0x180015f41  lea     rcx, [rsp+1B8h+var_140]; pvarg
0x180015f46  call    cs:__imp_VariantInit
0x180015f4d  nop     dword ptr [rax+rax+00h]
0x180015f52  nop
0x180015f53  movups  xmm8, xmmword ptr [rsp+1B8h+var_140]
0x180015f59  movsd   xmm9, qword ptr [rsp+1B8h+var_140+10h]
0x180015f63  lea     rcx, [rsp+1B8h+var_158]; pvarg
0x180015f68  call    cs:__imp_VariantInit
0x180015f6f  nop     dword ptr [rax+rax+00h]
0x180015f74  nop
0x180015f75  movups  xmm6, xmmword ptr [rsp+1B8h+var_158]
0x180015f7a  movsd   xmm7, qword ptr [rsp+1B8h+var_158+10h]
0x180015f80  lea     rcx, [rsp+1B8h+var_170]; pvarg
0x180015f85  call    cs:__imp_VariantInit
0x180015f8c  nop     dword ptr [rax+rax+00h]
0x180015f91  nop
0x180015f92  movups  xmm0, xmmword ptr [rsp+1B8h+var_170]
0x180015f97  movsd   xmm1, qword ptr [rsp+1B8h+var_170+10h]
0x180015f9d  movaps  xmmword ptr [rsp+1B8h+var_108], xmm10
0x180015fa6  movsd   [rsp+1B8h+var_F8], xmm11
0x180015fb0  movaps  [rsp+1B8h+var_E8], xmm8
0x180015fb9  movsd   [rsp+1B8h+var_D8], xmm9
0x180015fc3  movaps  [rsp+1B8h+var_C8], xmm6
0x180015fcb  movsd   [rsp+1B8h+var_B8], xmm7
0x180015fd4  movaps  [rsp+1B8h+var_A8], xmm0
0x180015fdc  movsd   [rsp+1B8h+var_98], xmm1
0x180015fe5  lea     rax, [rsp+1B8h+var_108]
0x180015fed  mov     qword ptr [rsp+1B8h+ppv], rax; int
0x180015ff2  lea     r9, [rsp+1B8h+var_E8]
0x180015ffa  lea     r8, [rsp+1B8h+var_C8]
0x180016002  lea     rdx, [rsp+1B8h+var_A8]
0x18001600a  mov     rcx, rdi
0x18001600d  mov     rax, rbx
0x180016010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016015  mov     ebx, eax
0x180016017  lea     rcx, [rsp+1B8h+var_170]; this
0x18001601c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180016021  nop
0x180016022  lea     rcx, [rsp+1B8h+var_158]; this
0x180016027  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18001602c  nop
0x18001602d  lea     rcx, [rsp+1B8h+var_140]; this
0x180016032  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180016037  nop
0x180016038  lea     rcx, [rsp+1B8h+pvarg]; this
0x180016040  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180016045  test    ebx, ebx
0x180016047  jns     short loc_1800160B1
0x180016049  mov     rcx, [rsp+1B8h]; this
0x180016051  mov     r9d, ebx; char *
0x180016054  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x18001605b  mov     edx, 12Eh; void *
0x180016060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016065  nop
0x180016066  lea     rcx, [rsp+1B8h+arg_18]
0x18001606e  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016073  nop
0x180016074  lea     rcx, [rsp+1B8h+var_188]
0x180016079  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18001607e  nop
0x18001607f  lea     rcx, [rsp+1B8h+var_180]
0x180016084  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016089  nop
0x18001608a  mov     al, byte ptr [rsp+1B8h+arg_10]
0x180016091  mov     byte ptr [rsp+1B8h+arg_10], sil
0x180016099  test    al, al
0x18001609b  jz      short loc_1800160AA
0x18001609d  call    cs:__imp_CoUninitialize
0x1800160a4  nop     dword ptr [rax+rax+00h]
0x1800160a9  nop
0x1800160aa  mov     eax, ebx
0x1800160ac  jmp     loc_1800163B9
0x1800160b1  mov     rbx, [rsp+1B8h+var_180]
0x1800160b6  mov     rdi, [rbx]
0x1800160b9  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800160c0  lea     rcx, [rsp+1B8h+var_178]; this
0x1800160c5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800160ca  nop
0x1800160cb  mov     rax, [rax]
0x1800160ce  test    rax, rax
0x1800160d1  jz      short loc_1800160D8
0x1800160d3  mov     rdx, [rax]
0x1800160d6  jmp     short loc_1800160DB
0x1800160d8  mov     rdx, rsi
0x1800160db  lea     r8, [rsp+1B8h+var_188]
0x1800160e0  mov     rcx, rbx
0x1800160e3  mov     rax, [rdi+38h]
0x1800160e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ec  mov     r14d, eax
0x1800160ef  mov     rbx, [rsp+1B8h+var_178]
0x1800160f4  or      edi, 0FFFFFFFFh
0x1800160f7  test    rbx, rbx
0x1800160fa  jz      short loc_180016142
0x1800160fc  mov     ecx, edi
0x1800160fe  lock xadd [rbx+10h], ecx
0x180016103  add     ecx, edi
0x180016105  jnz     short loc_180016142
0x180016107  test    rbx, rbx
0x18001610a  jz      short loc_180016142
0x18001610c  cmp     [rbx], rsi
0x18001610f  jz      short loc_180016123
0x180016111  mov     rcx, [rbx]; bstrString
0x180016114  call    cs:__imp_SysFreeString
0x18001611b  nop     dword ptr [rax+rax+00h]
0x180016120  mov     [rbx], rsi
0x180016123  mov     rcx, [rbx+8]; void *
0x180016127  test    rcx, rcx
0x18001612a  jz      short loc_180016135
0x18001612c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016131  mov     [rbx+8], rsi
0x180016135  mov     edx, 18h; struct std::nothrow_t *
0x18001613a  mov     rcx, rbx; void *
0x18001613d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016142  test    r14d, r14d
0x180016145  jns     short loc_1800161B0
0x180016147  mov     rcx, [rsp+1B8h]; this
0x18001614f  mov     r9d, r14d; char *
0x180016152  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180016159  mov     edx, 131h; void *
0x18001615e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016163  nop
0x180016164  lea     rcx, [rsp+1B8h+arg_18]
0x18001616c  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016171  nop
0x180016172  lea     rcx, [rsp+1B8h+var_188]
0x180016177  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18001617c  nop
0x18001617d  lea     rcx, [rsp+1B8h+var_180]
0x180016182  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016187  nop
0x180016188  mov     al, byte ptr [rsp+1B8h+arg_10]
0x18001618f  mov     byte ptr [rsp+1B8h+arg_10], sil
0x180016197  test    al, al
0x180016199  jz      short loc_1800161A8
0x18001619b  call    cs:__imp_CoUninitialize
0x1800161a2  nop     dword ptr [rax+rax+00h]
0x1800161a7  nop
0x1800161a8  mov     eax, r14d
0x1800161ab  jmp     loc_1800163B9
0x1800161b0  test    r15, r15
0x1800161b3  jz      loc_1800162B8
0x1800161b9  mov     rbx, [rsp+1B8h+var_188]
0x1800161be  mov     r14, [rbx]
0x1800161c1  mov     rdx, r15; unsigned __int16 *
0x1800161c4  lea     rcx, [rsp+1B8h+var_178]; this
0x1800161c9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800161ce  nop
0x1800161cf  mov     rax, [rax]
0x1800161d2  test    rax, rax
0x1800161d5  jz      short loc_1800161DC
0x1800161d7  mov     rdx, [rax]
0x1800161da  jmp     short loc_1800161DF
0x1800161dc  mov     rdx, rsi
0x1800161df  lea     r8, [rsp+1B8h+arg_18]
0x1800161e7  mov     rcx, rbx
0x1800161ea  mov     rax, [r14+48h]
0x1800161ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161f3  mov     r14d, eax
0x1800161f6  mov     rbx, [rsp+1B8h+var_178]
0x1800161fb  test    rbx, rbx
0x1800161fe  jz      short loc_180016246
0x180016200  mov     ecx, edi
0x180016202  lock xadd [rbx+10h], ecx
0x180016207  add     ecx, edi
0x180016209  jnz     short loc_180016246
0x18001620b  test    rbx, rbx
0x18001620e  jz      short loc_180016246
0x180016210  cmp     [rbx], rsi
0x180016213  jz      short loc_180016227
0x180016215  mov     rcx, [rbx]; bstrString
0x180016218  call    cs:__imp_SysFreeString
0x18001621f  nop     dword ptr [rax+rax+00h]
0x180016224  mov     [rbx], rsi
0x180016227  mov     rcx, [rbx+8]; void *
0x18001622b  test    rcx, rcx
0x18001622e  jz      short loc_180016239
0x180016230  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016235  mov     [rbx+8], rsi
0x180016239  mov     edx, 18h; struct std::nothrow_t *
0x18001623e  mov     rcx, rbx; void *
0x180016241  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016246  test    r14d, r14d
0x180016249  jns     loc_1800162D4
0x18001624f  mov     rcx, [rsp+1B8h]; this
0x180016257  mov     r9d, r14d; char *
0x18001625a  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\dmcmnutils\\sche"...
0x180016261  mov     edx, 135h; void *
0x180016266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001626b  nop
0x18001626c  lea     rcx, [rsp+1B8h+arg_18]
0x180016274  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016279  nop
0x18001627a  lea     rcx, [rsp+1B8h+var_188]
0x18001627f  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180016284  nop
0x180016285  lea     rcx, [rsp+1B8h+var_180]
0x18001628a  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18001628f  nop
0x180016290  mov     al, byte ptr [rsp+1B8h+arg_10]
0x180016297  mov     byte ptr [rsp+1B8h+arg_10], sil
0x18001629f  test    al, al
0x1800162a1  jz      short loc_1800162B0
0x1800162a3  call    cs:__imp_CoUninitialize
0x1800162aa  nop     dword ptr [rax+rax+00h]
0x1800162af  nop
0x1800162b0  mov     eax, r14d
0x1800162b3  jmp     loc_1800163B9
0x1800162b8  mov     rdx, [rsp+1B8h+var_188]; struct IUnknown *
0x1800162bd  cmp     [rsp+1B8h+arg_18], rdx
0x1800162c5  jz      short loc_1800162D4
0x1800162c7  lea     rcx, [rsp+1B8h+arg_18]; struct IUnknown **
0x1800162cf  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800162d4  mov     rbx, [rsp+1B8h+arg_18]
0x1800162dc  mov     r14, [rbx]
0x1800162df  lea     rdx, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x1800162e6  lea     rcx, [rsp+1B8h+var_178]; this
0x1800162eb  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800162f0  nop
0x1800162f1  mov     rax, [rax]
0x1800162f4  test    rax, rax
0x1800162f7  jz      short loc_1800162FE
0x1800162f9  mov     rdx, [rax]
0x1800162fc  jmp     short loc_180016301
0x1800162fe  mov     rdx, rsi
0x180016301  xor     r8d, r8d
0x180016304  mov     rcx, rbx
0x180016307  mov     rax, [r14+78h]
0x18001630b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016310  mov     r14d, eax
0x180016313  mov     rbx, [rsp+1B8h+var_178]
0x180016318  test    rbx, rbx
0x18001631b  jz      short loc_180016364
0x18001631d  mov     ecx, edi
  ... truncated ...
```
