# MigrateExistingSchedules(ushort const *)

- ea: `0x14000c314`
- end: `0x14000cafb`
- name: `?MigrateExistingSchedules@@YAJPEBG@Z`
- size: `2023`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000829c`

## callees

- `0x1400029c0`
- `0x1400029e4`
- `0x14000353c`
- `0x14000476c`
- `0x140004cd0`
- `0x140006bf4`
- `0x140007628`
- `0x140009268`
- `0x14000a134`
- `0x14000c314`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000c5b5`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c745`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c985`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c5b5`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c745`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c985`
- `OLEAUT32!__imp_VariantInit` at `0x14000c423`
- `OLEAUT32!__imp_VariantInit` at `0x14000c43e`
- `OLEAUT32!__imp_VariantInit` at `0x14000c459`
- `OLEAUT32!__imp_VariantInit` at `0x14000c472`
- `OLEAUT32!__imp_VariantInit` at `0x14000c895`
- `OLEAUT32!__imp_VariantInit` at `0x14000c8ae`
- `OLEAUT32!__imp_VariantInit` at `0x14000c8c9`
- `OLEAUT32!__imp_VariantInit` at `0x14000c423`
- `OLEAUT32!__imp_VariantInit` at `0x14000c43e`
- `OLEAUT32!__imp_VariantInit` at `0x14000c459`
- `OLEAUT32!__imp_VariantInit` at `0x14000c472`
- `OLEAUT32!__imp_VariantInit` at `0x14000c895`
- `OLEAUT32!__imp_VariantInit` at `0x14000c8ae`
- `OLEAUT32!__imp_VariantInit` at `0x14000c8c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000c3da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000c3da`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c3a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c621`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ca76`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c3a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c621`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ca76`

## string_xrefs

- `0x14000c687`: `Schedule #1 created by enrollment client`
- `0x14000c675`: `Schedule #2 created by enrollment client`
- `0x14000c6ab`: `Schedule #3 created by enrollment client`
- `0x14000c692`: `Maintenance Schedule created by enrollment client`
- `0x14000c69d`: `Schedule created by enrollment client for renewal of certificate warning`
- `0x14000c6b9`: `Schedule #4 created by enrollment client`
- `0x14000c6c7`: `User Maintenance Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall MigrateExistingSchedules(const unsigned __int16 *a1, unsigned int a2)
{
  int v3; // eax
  HRESULT v4; // ebx
  __int64 v6; // rdx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, VARIANTARG *, __int128 *, int *); // rbx
  __int128 v9; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v11; // xmm8
  IRecordInfo *v12; // xmm9_8
  __int128 v13; // xmm6
  IRecordInfo *v14; // xmm7_8
  LPVOID v15; // rbx
  __int64 (__fastcall *v16)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v17; // rax
  __int64 v18; // rdx
  int v19; // eax
  BSTR *v20; // rbx
  int v21; // edi
  BSTR v22; // rcx
  int *v23; // r14
  __int64 v24; // rbx
  const unsigned __int16 *v25; // rdx
  __int64 (__fastcall *v26)(__int64, __int64, __int64 *); // rsi
  _bstr_t *v27; // rax
  __int64 v28; // rdx
  int v29; // eax
  BSTR *v30; // rbx
  int v31; // esi
  BSTR v32; // rcx
  int v33; // eax
  char v34; // si
  __int64 v35; // rdx
  __int64 v36; // rbx
  __int64 (__fastcall *v37)(__int64, __int64, __int64, __int64); // r15
  __int128 v38; // xmm6
  IRecordInfo *v39; // xmm7_8
  __int128 v40; // xmm8
  IRecordInfo *v41; // xmm9_8
  __int128 v42; // xmm10
  __int64 v43; // rsi
  IRecordInfo *v44; // xmm11_8
  _bstr_t *v45; // rax
  __int64 v46; // rdx
  int v47; // eax
  BSTR *v48; // rbx
  int v49; // esi
  BSTR v50; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  int *ppva; // [rsp+28h] [rbp-E0h]
  __int64 v53; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID v54; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v55; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+70h] [rbp-98h] BYREF
  __int64 v57; // [rsp+78h] [rbp-90h] BYREF
  __int64 v58; // [rsp+80h] [rbp-88h] BYREF
  __int64 v59; // [rsp+88h] [rbp-80h] BYREF
  void *Block[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-68h] BYREF
  void *v62; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v63; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG v64; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  int v66[4]; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v67; // [rsp+108h] [rbp+0h]
  __int128 v68; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v69; // [rsp+128h] [rbp+20h]
  VARIANTARG v70; // [rsp+138h] [rbp+30h] BYREF
  VARIANTARG v71; // [rsp+158h] [rbp+50h] BYREF
  _QWORD v72[7]; // [rsp+170h] [rbp+68h] BYREF
  int v73[4]; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v74; // [rsp+1B8h] [rbp+B0h]
  unsigned __int16 v75[264]; // [rsp+1C8h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+490h] [rbp+388h]

  LODWORD(v53) = 0;
  v3 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v53, a2);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v3,
      ppv);
LABEL_3:
    if ( (_DWORD)v53 )
      CoUninitialize();
    return (unsigned int)v4;
  }
  v54 = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v54);
  if ( v4 < 0 )
  {
    v6 = 3727;
    goto LABEL_8;
  }
  v7 = v54;
  v8 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, int *))(*(_QWORD *)v54 + 80LL);
  VariantInit(&pvarg);
  v9 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v64);
  v11 = *(_OWORD *)&v64.vt;
  v12 = v64.pRecInfo;
  VariantInit(&v63);
  v13 = *(_OWORD *)&v63.vt;
  v14 = v63.pRecInfo;
  VariantInit(&v71);
  ppva = v73;
  v70 = v71;
  *(_OWORD *)v73 = v9;
  v74 = pRecInfo;
  *(_OWORD *)v66 = v11;
  v67 = v12;
  v68 = v13;
  v69 = v14;
  v4 = v8(v7, &v70, &v68, v66);
  ATL::CComVariant::~CComVariant(&v71);
  ATL::CComVariant::~CComVariant(&v63);
  ATL::CComVariant::~CComVariant(&v64);
  ATL::CComVariant::~CComVariant(&pvarg);
  if ( v4 < 0 )
  {
    v6 = 3728;
    goto LABEL_8;
  }
  memset_0(v75, 0, 0x208u);
  v4 = StringCchPrintfW(v75, 0x104u, L"\\Microsoft\\Windows\\EnterpriseMgmt\\%s", a1);
  if ( v4 < 0 )
  {
    v6 = 3731;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v4,
      (int)ppva);
LABEL_9:
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v54);
    goto LABEL_3;
  }
  v15 = v54;
  v56 = 0;
  v16 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v54 + 56LL);
  v17 = _bstr_t::_bstr_t((_bstr_t *)Block, v75);
  if ( *(_QWORD *)v17 )
    v18 = **(_QWORD **)v17;
  else
    v18 = 0;
  v19 = v16(v15, v18, &v56);
  v20 = (BSTR *)Block[0];
  v21 = v19;
  if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v20 )
  {
    if ( *v20 )
    {
      SysFreeString(*v20);
      *v20 = 0;
    }
    v22 = v20[1];
    if ( v22 )
    {
      operator delete(v22);
      v20[1] = 0;
    }
    operator delete(v20);
  }
  if ( v21 >= 0 )
  {
    v21 = 0;
    v72[0] = L"Schedule #2 created by enrollment client";
    v23 = (int *)v72;
    v72[1] = L"Schedule #1 created by enrollment client";
    v72[2] = L"Maintenance Schedule created by enrollment client";
    v72[3] = L"Schedule created by enrollment client for renewal of certificate warning";
    v72[4] = L"Schedule #3 created by enrollment client";
    v72[5] = L"Schedule #4 created by enrollment client";
    v72[6] = L"User Maintenance Schedule created by enrollment client";
    while ( 1 )
    {
      if ( v23 == v73 )
        goto LABEL_27;
      v24 = v56;
      v25 = *(const unsigned __int16 **)v23;
      v59 = 0;
      v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v56 + 104LL);
      v27 = _bstr_t::_bstr_t((_bstr_t *)&v62, v25);
      if ( *(_QWORD *)v27 )
        v28 = **(_QWORD **)v27;
      else
        v28 = 0;
      v29 = v26(v24, v28, &v59);
      v30 = (BSTR *)v62;
      v31 = v29;
      if ( v62 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v62 + 4, 0xFFFFFFFF) == 1 && v30 )
        {
          if ( *v30 )
          {
            SysFreeString(*v30);
            *v30 = 0;
          }
          v32 = v30[1];
          if ( v32 )
          {
            operator delete(v32);
            v30[1] = 0;
          }
          operator delete(v30);
        }
        v62 = 0;
      }
      if ( v31 >= 0 )
        break;
      if ( v31 != -2147024894 )
        v21 = v31;
LABEL_73:
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v59);
      v23 += 2;
    }
    v58 = 0;
    v33 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 152LL))(v59, &v58);
    v4 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEAB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v33,
        (int)ppva);
      goto LABEL_83;
    }
    v55 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 88LL))(v58, &v55);
    if ( v4 < 0 )
    {
      v35 = 3758;
LABEL_81:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v4,
        (int)ppva);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v55);
LABEL_83:
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v58);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v59);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
      goto LABEL_9;
    }
    LOWORD(v57) = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 168LL))(v55, &v57);
    if ( v4 < 0 )
    {
      v35 = 3762;
      goto LABEL_81;
    }
    v34 = 0;
    if ( !(_WORD)v57 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 176LL))(v55, 0xFFFFFFFFLL);
      if ( v4 < 0 )
      {
        v35 = 3765;
        goto LABEL_81;
      }
      v34 = 1;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 200LL))(v55, &v57);
    if ( v4 < 0 )
    {
      v35 = 3769;
      goto LABEL_81;
    }
    if ( (_WORD)v57 )
    {
      if ( !v34 )
      {
LABEL_70:
        ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v55);
        ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v58);
        goto LABEL_73;
      }
    }
    else
    {
      v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 208LL))(v55, 0xFFFFFFFFLL);
      if ( v4 < 0 )
      {
        v35 = 3772;
        goto LABEL_81;
      }
    }
    v36 = v56;
    v61 = 0;
    v37 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v56 + 136LL);
    VariantInit(&v63);
    v38 = *(_OWORD *)&v63.vt;
    v39 = v63.pRecInfo;
    VariantInit(&v64);
    v40 = *(_OWORD *)&v64.vt;
    v41 = v64.pRecInfo;
    VariantInit(&pvarg);
    v42 = *(_OWORD *)&pvarg.vt;
    v43 = v58;
    v44 = pvarg.pRecInfo;
    v45 = _bstr_t::_bstr_t((_bstr_t *)Block, *(const unsigned __int16 **)v23);
    if ( *(_QWORD *)v45 )
      v46 = **(_QWORD **)v45;
    else
      v46 = 0;
    *(_OWORD *)&v70.vt = v38;
    v70.pRecInfo = v39;
    v68 = v40;
    ppva = v66;
    v69 = v41;
    *(_OWORD *)v66 = v42;
    v67 = v44;
    v47 = v37(v36, v46, v43, 4);
    v48 = (BSTR *)Block[0];
    v49 = v47;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v48 )
      {
        if ( *v48 )
        {
          SysFreeString(*v48);
          *v48 = 0;
        }
        v50 = v48[1];
        if ( v50 )
        {
          operator delete(v50);
          v48[1] = 0;
        }
        operator delete(v48);
      }
      Block[0] = 0;
    }
    ATL::CComVariant::~CComVariant(&pvarg);
    ATL::CComVariant::~CComVariant(&v64);
    ATL::CComVariant::~CComVariant(&v63);
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xECB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v49,
        (int)v66);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v61);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v55);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v58);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v59);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v54);
      if ( (_DWORD)v53 )
        CoUninitialize();
      return (unsigned int)v49;
    }
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v61);
    goto LABEL_70;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE96,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
    (const char *)(unsigned int)v21,
    (int)v73);
LABEL_27:
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v54);
  if ( (_DWORD)v53 )
    CoUninitialize();
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x14000c314  mov     rax, rsp
0x14000c317  push    rbp
0x14000c318  push    rbx
0x14000c319  push    rsi
0x14000c31a  push    rdi
0x14000c31b  push    r12
0x14000c31d  push    r13
0x14000c31f  push    r14
0x14000c321  push    r15
0x14000c323  lea     rbp, [rax-388h]
0x14000c32a  sub     rsp, 448h
0x14000c331  movaps  xmmword ptr [rax-58h], xmm6
0x14000c335  movaps  xmmword ptr [rax-68h], xmm7
0x14000c339  movaps  xmmword ptr [rax-78h], xmm8
0x14000c33e  movaps  xmmword ptr [rax-88h], xmm9
0x14000c346  movaps  xmmword ptr [rax-98h], xmm10
0x14000c34e  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000c356  mov     rax, cs:__security_cookie
0x14000c35d  xor     rax, rsp
0x14000c360  mov     [rbp+380h+var_B0], rax
0x14000c367  mov     rsi, rcx
0x14000c36a  xor     r12d, r12d
0x14000c36d  lea     rcx, [rsp+480h+var_430]; this
0x14000c372  mov     dword ptr [rsp+480h+var_430], r12d
0x14000c377  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000c37c  mov     ebx, eax
0x14000c37e  test    eax, eax
0x14000c380  jns     short loc_14000C3B7
0x14000c382  mov     rcx, [rbp+388h]; this
0x14000c389  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000c390  mov     r9d, eax; char *
0x14000c393  mov     edx, 0E8Ch; void *
0x14000c398  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c39d  cmp     dword ptr [rsp+480h+var_430], r12d
0x14000c3a2  jz      short loc_14000C3B0
0x14000c3a4  call    cs:__imp_CoUninitialize
0x14000c3ab  nop     dword ptr [rax+rax+00h]
0x14000c3b0  mov     eax, ebx
0x14000c3b2  jmp     loc_14000C62F
0x14000c3b7  xor     edx, edx; pUnkOuter
0x14000c3b9  mov     [rsp+480h+var_428], r12
0x14000c3be  lea     rax, [rsp+480h+var_428]
0x14000c3c3  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14000c3ca  mov     [rsp+480h+ppv], rax; int
0x14000c3cf  lea     rcx, CLSID_TaskScheduler; rclsid
0x14000c3d6  lea     r8d, [rdx+1]; dwClsContext
0x14000c3da  call    cs:__imp_CoCreateInstance
0x14000c3e1  nop     dword ptr [rax+rax+00h]
0x14000c3e6  mov     ebx, eax
0x14000c3e8  test    eax, eax
0x14000c3ea  jns     short loc_14000C413
0x14000c3ec  mov     edx, 0E8Fh; void *
0x14000c3f1  mov     rcx, [rbp+388h]; this
0x14000c3f8  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000c3ff  mov     r9d, ebx; char *
0x14000c402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c407  lea     rcx, [rsp+480h+var_428]
0x14000c40c  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000c411  jmp     short loc_14000C39D
0x14000c413  mov     rdi, [rsp+480h+var_428]
0x14000c418  lea     rcx, [rbp+380h+pvarg]; pvarg
0x14000c41c  mov     rax, [rdi]
0x14000c41f  mov     rbx, [rax+50h]
0x14000c423  call    cs:__imp_VariantInit
0x14000c42a  nop     dword ptr [rax+rax+00h]
0x14000c42f  movups  xmm10, xmmword ptr [rbp+380h+pvarg]
0x14000c434  lea     rcx, [rbp+380h+var_3C0]; pvarg
0x14000c438  movsd   xmm11, qword ptr [rbp+380h+pvarg+10h]
0x14000c43e  call    cs:__imp_VariantInit
0x14000c445  nop     dword ptr [rax+rax+00h]
0x14000c44a  movups  xmm8, xmmword ptr [rbp+380h+var_3C0]
0x14000c44f  lea     rcx, [rbp+380h+var_3D8]; pvarg
0x14000c453  movsd   xmm9, qword ptr [rbp+380h+var_3C0+10h]
0x14000c459  call    cs:__imp_VariantInit
0x14000c460  nop     dword ptr [rax+rax+00h]
0x14000c465  movups  xmm6, xmmword ptr [rbp+380h+var_3D8]
0x14000c469  lea     rcx, [rbp+380h+var_330]; pvarg
0x14000c46d  movsd   xmm7, qword ptr [rbp+380h+var_3D8+10h]
0x14000c472  call    cs:__imp_VariantInit
0x14000c479  nop     dword ptr [rax+rax+00h]
0x14000c47e  movups  xmm0, xmmword ptr [rbp+380h+var_330]
0x14000c482  lea     rax, [rbp+380h+var_2E0]
0x14000c489  mov     rcx, rdi
0x14000c48c  movsd   xmm1, qword ptr [rbp+380h+var_330+10h]
0x14000c491  lea     r9, [rbp+380h+var_390]
0x14000c495  mov     [rsp+480h+ppv], rax; int
0x14000c49a  lea     r8, [rbp+380h+var_370]
0x14000c49e  mov     rax, rbx
0x14000c4a1  movaps  [rbp+380h+var_350], xmm0
0x14000c4a5  lea     rdx, [rbp+380h+var_350]
0x14000c4a9  movaps  xmmword ptr [rbp+380h+var_2E0], xmm10
0x14000c4b1  movsd   [rbp+380h+var_2D0], xmm11
0x14000c4ba  movaps  xmmword ptr [rbp+380h+var_390], xmm8
0x14000c4bf  movsd   [rbp+380h+var_380], xmm9
0x14000c4c5  movaps  [rbp+380h+var_370], xmm6
0x14000c4c9  movsd   [rbp+380h+var_360], xmm7
0x14000c4ce  movsd   [rbp+380h+var_340], xmm1
0x14000c4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c4d8  lea     rcx, [rbp+380h+var_330]; pvarg
0x14000c4dc  mov     ebx, eax
0x14000c4de  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000c4e3  lea     rcx, [rbp+380h+var_3D8]; pvarg
0x14000c4e7  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000c4ec  lea     rcx, [rbp+380h+var_3C0]; pvarg
0x14000c4f0  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000c4f5  lea     rcx, [rbp+380h+pvarg]; pvarg
0x14000c4f9  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000c4fe  test    ebx, ebx
0x14000c500  jns     short loc_14000C50C
0x14000c502  mov     edx, 0E90h
0x14000c507  jmp     loc_14000C3F1
0x14000c50c  xor     edx, edx; Val
0x14000c50e  lea     rcx, [rbp+380h+var_2C0]; void *
0x14000c515  mov     r8d, 208h; Size
0x14000c51b  call    memset_0
0x14000c520  mov     r9, rsi
0x14000c523  lea     r8, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt\\%"...
0x14000c52a  mov     edx, 104h; unsigned __int64
0x14000c52f  lea     rcx, [rbp+380h+var_2C0]; unsigned __int16 *
0x14000c536  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000c53b  mov     ebx, eax
0x14000c53d  test    eax, eax
0x14000c53f  jns     short loc_14000C54B
0x14000c541  mov     edx, 0E93h
0x14000c546  jmp     loc_14000C3F1
0x14000c54b  mov     rbx, [rsp+480h+var_428]
0x14000c550  lea     rdx, [rbp+380h+var_2C0]; unsigned __int16 *
0x14000c557  mov     [rsp+480h+var_418], r12
0x14000c55c  lea     rcx, [rbp+380h+Block]; this
0x14000c560  mov     rax, [rbx]
0x14000c563  mov     rdi, [rax+38h]
0x14000c567  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000c56c  mov     rcx, [rax]
0x14000c56f  test    rcx, rcx
0x14000c572  jz      short loc_14000C579
0x14000c574  mov     rdx, [rcx]
0x14000c577  jmp     short loc_14000C57C
0x14000c579  mov     rdx, r12
0x14000c57c  lea     r8, [rsp+480h+var_418]
0x14000c581  mov     rcx, rbx
0x14000c584  mov     rax, rdi
0x14000c587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c58c  mov     rbx, [rbp+380h+Block]
0x14000c590  or      r13d, 0FFFFFFFFh
0x14000c594  mov     edi, eax
0x14000c596  test    rbx, rbx
0x14000c599  jz      short loc_14000C5E3
0x14000c59b  mov     ecx, r13d
0x14000c59e  lock xadd [rbx+10h], ecx
0x14000c5a3  add     ecx, r13d
0x14000c5a6  jnz     short loc_14000C5E3
0x14000c5a8  test    rbx, rbx
0x14000c5ab  jz      short loc_14000C5E3
0x14000c5ad  mov     rcx, [rbx]; bstrString
0x14000c5b0  test    rcx, rcx
0x14000c5b3  jz      short loc_14000C5C4
0x14000c5b5  call    cs:__imp_SysFreeString
0x14000c5bc  nop     dword ptr [rax+rax+00h]
0x14000c5c1  mov     [rbx], r12
0x14000c5c4  mov     rcx, [rbx+8]; Block
0x14000c5c8  test    rcx, rcx
0x14000c5cb  jz      short loc_14000C5D6
0x14000c5cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c5d2  mov     [rbx+8], r12
0x14000c5d6  mov     edx, 18h
0x14000c5db  mov     rcx, rbx; Block
0x14000c5de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c5e3  test    edi, edi
0x14000c5e5  jns     loc_14000C675
0x14000c5eb  mov     rcx, [rbp+388h]; this
0x14000c5f2  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000c5f9  mov     r9d, edi; char *
0x14000c5fc  mov     edx, 0E96h; void *
0x14000c601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c606  lea     rcx, [rsp+480h+var_418]
0x14000c60b  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000c610  lea     rcx, [rsp+480h+var_428]
0x14000c615  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000c61a  cmp     dword ptr [rsp+480h+var_430], r12d
0x14000c61f  jz      short loc_14000C62D
0x14000c621  call    cs:__imp_CoUninitialize
0x14000c628  nop     dword ptr [rax+rax+00h]
0x14000c62d  mov     eax, edi
0x14000c62f  mov     rcx, [rbp+380h+var_B0]
0x14000c636  xor     rcx, rsp; StackCookie
0x14000c639  call    __security_check_cookie
0x14000c63e  lea     r11, [rsp+480h+var_38]
0x14000c646  movaps  xmm6, xmmword ptr [r11-18h]
0x14000c64b  movaps  xmm7, xmmword ptr [r11-28h]
0x14000c650  movaps  xmm8, xmmword ptr [r11-38h]
0x14000c655  movaps  xmm9, xmmword ptr [r11-48h]
0x14000c65a  movaps  xmm10, xmmword ptr [r11-58h]
0x14000c65f  movaps  xmm11, xmmword ptr [r11-68h]
0x14000c664  mov     rsp, r11
0x14000c667  pop     r15
0x14000c669  pop     r14
0x14000c66b  pop     r13
0x14000c66d  pop     r12
0x14000c66f  pop     rdi
0x14000c670  pop     rsi
0x14000c671  pop     rbx
0x14000c672  pop     rbp
0x14000c673  retn
0x14000c675  lea     rax, aSchedule2Creat; "Schedule #2 created by enrollment clien"...
0x14000c67c  mov     edi, r12d
0x14000c67f  mov     [rbp+380h+var_318], rax
0x14000c683  lea     r14, [rbp+380h+var_318]
0x14000c687  lea     rax, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x14000c68e  mov     [rbp+380h+var_310], rax
0x14000c692  lea     rax, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x14000c699  mov     [rbp+380h+var_308], rax
0x14000c69d  lea     rax, aScheduleCreate; "Schedule created by enrollment client f"...
0x14000c6a4  mov     [rbp+380h+var_300], rax
0x14000c6ab  lea     rax, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x14000c6b2  mov     [rbp+380h+var_2F8], rax
0x14000c6b9  lea     rax, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x14000c6c0  mov     [rbp+380h+var_2F0], rax
0x14000c6c7  lea     rax, aUserMaintenanc; "User Maintenance Schedule created by en"...
0x14000c6ce  mov     [rbp+380h+var_2E8], rax
0x14000c6d5  lea     rax, [rbp+380h+var_2E0]
0x14000c6dc  cmp     r14, rax
0x14000c6df  jz      loc_14000C606
0x14000c6e5  mov     rbx, [rsp+480h+var_418]
0x14000c6ea  lea     rcx, [rbp+380h+var_3E0]; this
0x14000c6ee  mov     rdx, [r14]; unsigned __int16 *
0x14000c6f1  mov     [rbp+380h+var_400], r12
0x14000c6f5  mov     rax, [rbx]
0x14000c6f8  mov     rsi, [rax+68h]
0x14000c6fc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000c701  mov     rdx, [rax]
0x14000c704  test    rdx, rdx
0x14000c707  jz      short loc_14000C70E
0x14000c709  mov     rdx, [rdx]
0x14000c70c  jmp     short loc_14000C711
0x14000c70e  mov     rdx, r12
0x14000c711  lea     r8, [rbp+380h+var_400]
0x14000c715  mov     rcx, rbx
0x14000c718  mov     rax, rsi
0x14000c71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c720  mov     rbx, [rbp+380h+var_3E0]
0x14000c724  mov     esi, eax
0x14000c726  test    rbx, rbx
0x14000c729  jz      short loc_14000C777
0x14000c72b  mov     ecx, r13d
0x14000c72e  lock xadd [rbx+10h], ecx
0x14000c733  add     ecx, r13d
0x14000c736  jnz     short loc_14000C773
0x14000c738  test    rbx, rbx
0x14000c73b  jz      short loc_14000C773
0x14000c73d  mov     rcx, [rbx]; bstrString
0x14000c740  test    rcx, rcx
0x14000c743  jz      short loc_14000C754
0x14000c745  call    cs:__imp_SysFreeString
0x14000c74c  nop     dword ptr [rax+rax+00h]
0x14000c751  mov     [rbx], r12
0x14000c754  mov     rcx, [rbx+8]; Block
0x14000c758  test    rcx, rcx
0x14000c75b  jz      short loc_14000C766
0x14000c75d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c762  mov     [rbx+8], r12
0x14000c766  mov     edx, 18h
0x14000c76b  mov     rcx, rbx; Block
0x14000c76e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c773  mov     [rbp+380h+var_3E0], r12
0x14000c777  test    esi, esi
0x14000c779  js      loc_14000C9F5
0x14000c77f  mov     rcx, [rbp+380h+var_400]
0x14000c783  lea     rdx, [rsp+480h+var_408]
0x14000c788  mov     [rsp+480h+var_408], r12
0x14000c78d  mov     rax, [rcx]
0x14000c790  mov     rax, [rax+98h]
0x14000c797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c79c  mov     ebx, eax
0x14000c79e  test    eax, eax
0x14000c7a0  js      loc_14000CABE
0x14000c7a6  mov     rcx, [rsp+480h+var_408]
0x14000c7ab  lea     rdx, [rsp+480h+var_420]
0x14000c7b0  mov     [rsp+480h+var_420], r12
0x14000c7b5  mov     rax, [rcx]
0x14000c7b8  mov     rax, [rax+58h]
0x14000c7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7c1  mov     ebx, eax
0x14000c7c3  test    eax, eax
0x14000c7c5  js      loc_14000CA97
0x14000c7cb  mov     rcx, [rsp+480h+var_420]
0x14000c7d0  lea     rdx, [rsp+480h+var_410]
0x14000c7d5  mov     word ptr [rsp+480h+var_410], r12w
0x14000c7db  mov     rax, [rcx]
0x14000c7de  mov     rax, [rax+0A8h]
0x14000c7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7ea  mov     ebx, eax
0x14000c7ec  test    eax, eax
0x14000c7ee  js      loc_14000CA90
0x14000c7f4  mov     sil, r12b
0x14000c7f7  cmp     word ptr [rsp+480h+var_410], r12w
0x14000c7fd  jnz     short loc_14000C823
0x14000c7ff  mov     rcx, [rsp+480h+var_420]
0x14000c804  mov     edx, r13d
0x14000c807  mov     rax, [rcx]
0x14000c80a  mov     rax, [rax+0B0h]
  ... truncated ...
```
