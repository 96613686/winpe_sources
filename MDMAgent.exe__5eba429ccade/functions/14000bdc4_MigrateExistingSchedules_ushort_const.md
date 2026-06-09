# MigrateExistingSchedules(ushort const *)

- ea: `0x14000bdc4`
- end: `0x14000c553`
- name: `?MigrateExistingSchedules@@YAJPEBG@Z`
- size: `1935`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140007f34`

## callees

- `0x140002930`
- `0x140002954`
- `0x14000349c`
- `0x1400046a4`
- `0x140004c34`
- `0x140006984`
- `0x140007368`
- `0x140008e48`
- `0x140009cd8`
- `0x14000bdc4`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000c041`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c1c4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3ec`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c041`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c1c4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3ec`
- `OLEAUT32!__imp_VariantInit` at `0x14000bec7`
- `OLEAUT32!__imp_VariantInit` at `0x14000bedc`
- `OLEAUT32!__imp_VariantInit` at `0x14000bef1`
- `OLEAUT32!__imp_VariantInit` at `0x14000bf04`
- `OLEAUT32!__imp_VariantInit` at `0x14000c30e`
- `OLEAUT32!__imp_VariantInit` at `0x14000c321`
- `OLEAUT32!__imp_VariantInit` at `0x14000c336`
- `OLEAUT32!__imp_VariantInit` at `0x14000bec7`
- `OLEAUT32!__imp_VariantInit` at `0x14000bedc`
- `OLEAUT32!__imp_VariantInit` at `0x14000bef1`
- `OLEAUT32!__imp_VariantInit` at `0x14000bf04`
- `OLEAUT32!__imp_VariantInit` at `0x14000c30e`
- `OLEAUT32!__imp_VariantInit` at `0x14000c321`
- `OLEAUT32!__imp_VariantInit` at `0x14000c336`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000be84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000be84`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000be54`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c0a7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c4d4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000be54`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c0a7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c4d4`

## string_xrefs

- `0x14000c106`: `Schedule #1 created by enrollment client`
- `0x14000c0f4`: `Schedule #2 created by enrollment client`
- `0x14000c12a`: `Schedule #3 created by enrollment client`
- `0x14000c111`: `Maintenance Schedule created by enrollment client`
- `0x14000c11c`: `Schedule created by enrollment client for renewal of certificate warning`
- `0x14000c138`: `Schedule #4 created by enrollment client`
- `0x14000c146`: `User Maintenance Schedule created by enrollment client`

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
0x14000bdc4  mov     rax, rsp
0x14000bdc7  push    rbp
0x14000bdc8  push    rbx
0x14000bdc9  push    rsi
0x14000bdca  push    rdi
0x14000bdcb  push    r12
0x14000bdcd  push    r13
0x14000bdcf  push    r14
0x14000bdd1  push    r15
0x14000bdd3  lea     rbp, [rax-388h]
0x14000bdda  sub     rsp, 448h
0x14000bde1  movaps  xmmword ptr [rax-58h], xmm6
0x14000bde5  movaps  xmmword ptr [rax-68h], xmm7
0x14000bde9  movaps  xmmword ptr [rax-78h], xmm8
0x14000bdee  movaps  xmmword ptr [rax-88h], xmm9
0x14000bdf6  movaps  xmmword ptr [rax-98h], xmm10
0x14000bdfe  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000be06  mov     rax, cs:__security_cookie
0x14000be0d  xor     rax, rsp
0x14000be10  mov     [rbp+380h+var_B0], rax
0x14000be17  mov     rsi, rcx
0x14000be1a  xor     r12d, r12d
0x14000be1d  lea     rcx, [rsp+480h+var_430]; this
0x14000be22  mov     dword ptr [rsp+480h+var_430], r12d
0x14000be27  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000be2c  mov     ebx, eax
0x14000be2e  test    eax, eax
0x14000be30  jns     short loc_14000BE61
0x14000be32  mov     rcx, [rbp+388h]; this
0x14000be39  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000be40  mov     r9d, eax; char *
0x14000be43  mov     edx, 0E8Ch; void *
0x14000be48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000be4d  cmp     dword ptr [rsp+480h+var_430], r12d
0x14000be52  jz      short loc_14000BE5A
0x14000be54  call    cs:__imp_CoUninitialize
0x14000be5a  mov     eax, ebx
0x14000be5c  jmp     loc_14000C0AF
0x14000be61  xor     edx, edx; pUnkOuter
0x14000be63  mov     [rsp+480h+var_428], r12
0x14000be68  lea     rax, [rsp+480h+var_428]
0x14000be6d  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14000be74  mov     [rsp+480h+ppv], rax; int
0x14000be79  lea     rcx, CLSID_TaskScheduler; rclsid
0x14000be80  lea     r8d, [rdx+1]; dwClsContext
0x14000be84  call    cs:__imp_CoCreateInstance
0x14000be8a  mov     ebx, eax
0x14000be8c  test    eax, eax
0x14000be8e  jns     short loc_14000BEB7
0x14000be90  mov     edx, 0E8Fh; void *
0x14000be95  mov     rcx, [rbp+388h]; this
0x14000be9c  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000bea3  mov     r9d, ebx; char *
0x14000bea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000beab  lea     rcx, [rsp+480h+var_428]
0x14000beb0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000beb5  jmp     short loc_14000BE4D
0x14000beb7  mov     rdi, [rsp+480h+var_428]
0x14000bebc  lea     rcx, [rbp+380h+pvarg]; pvarg
0x14000bec0  mov     rax, [rdi]
0x14000bec3  mov     rbx, [rax+50h]
0x14000bec7  call    cs:__imp_VariantInit
0x14000becd  movups  xmm10, xmmword ptr [rbp+380h+pvarg]
0x14000bed2  lea     rcx, [rbp+380h+var_3C0]; pvarg
0x14000bed6  movsd   xmm11, qword ptr [rbp+380h+pvarg+10h]
0x14000bedc  call    cs:__imp_VariantInit
0x14000bee2  movups  xmm8, xmmword ptr [rbp+380h+var_3C0]
0x14000bee7  lea     rcx, [rbp+380h+var_3D8]; pvarg
0x14000beeb  movsd   xmm9, qword ptr [rbp+380h+var_3C0+10h]
0x14000bef1  call    cs:__imp_VariantInit
0x14000bef7  movups  xmm6, xmmword ptr [rbp+380h+var_3D8]
0x14000befb  lea     rcx, [rbp+380h+var_330]; pvarg
0x14000beff  movsd   xmm7, qword ptr [rbp+380h+var_3D8+10h]
0x14000bf04  call    cs:__imp_VariantInit
0x14000bf0a  movups  xmm0, xmmword ptr [rbp+380h+var_330]
0x14000bf0e  lea     rax, [rbp+380h+var_2E0]
0x14000bf15  mov     rcx, rdi
0x14000bf18  movsd   xmm1, qword ptr [rbp+380h+var_330+10h]
0x14000bf1d  lea     r9, [rbp+380h+var_390]
0x14000bf21  mov     [rsp+480h+ppv], rax; int
0x14000bf26  lea     r8, [rbp+380h+var_370]
0x14000bf2a  mov     rax, rbx
0x14000bf2d  movaps  [rbp+380h+var_350], xmm0
0x14000bf31  lea     rdx, [rbp+380h+var_350]
0x14000bf35  movaps  xmmword ptr [rbp+380h+var_2E0], xmm10
0x14000bf3d  movsd   [rbp+380h+var_2D0], xmm11
0x14000bf46  movaps  xmmword ptr [rbp+380h+var_390], xmm8
0x14000bf4b  movsd   [rbp+380h+var_380], xmm9
0x14000bf51  movaps  [rbp+380h+var_370], xmm6
0x14000bf55  movsd   [rbp+380h+var_360], xmm7
0x14000bf5a  movsd   [rbp+380h+var_340], xmm1
0x14000bf5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf64  lea     rcx, [rbp+380h+var_330]; pvarg
0x14000bf68  mov     ebx, eax
0x14000bf6a  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000bf6f  lea     rcx, [rbp+380h+var_3D8]; pvarg
0x14000bf73  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000bf78  lea     rcx, [rbp+380h+var_3C0]; pvarg
0x14000bf7c  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000bf81  lea     rcx, [rbp+380h+pvarg]; pvarg
0x14000bf85  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000bf8a  test    ebx, ebx
0x14000bf8c  jns     short loc_14000BF98
0x14000bf8e  mov     edx, 0E90h
0x14000bf93  jmp     loc_14000BE95
0x14000bf98  xor     edx, edx; Val
0x14000bf9a  lea     rcx, [rbp+380h+var_2C0]; void *
0x14000bfa1  mov     r8d, 208h; Size
0x14000bfa7  call    memset_0
0x14000bfac  mov     r9, rsi
0x14000bfaf  lea     r8, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt\\%"...
0x14000bfb6  mov     edx, 104h; unsigned __int64
0x14000bfbb  lea     rcx, [rbp+380h+var_2C0]; unsigned __int16 *
0x14000bfc2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000bfc7  mov     ebx, eax
0x14000bfc9  test    eax, eax
0x14000bfcb  jns     short loc_14000BFD7
0x14000bfcd  mov     edx, 0E93h
0x14000bfd2  jmp     loc_14000BE95
0x14000bfd7  mov     rbx, [rsp+480h+var_428]
0x14000bfdc  lea     rdx, [rbp+380h+var_2C0]; unsigned __int16 *
0x14000bfe3  mov     [rsp+480h+var_418], r12
0x14000bfe8  lea     rcx, [rbp+380h+Block]; this
0x14000bfec  mov     rax, [rbx]
0x14000bfef  mov     rdi, [rax+38h]
0x14000bff3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000bff8  mov     rcx, [rax]
0x14000bffb  test    rcx, rcx
0x14000bffe  jz      short loc_14000C005
0x14000c000  mov     rdx, [rcx]
0x14000c003  jmp     short loc_14000C008
0x14000c005  mov     rdx, r12
0x14000c008  lea     r8, [rsp+480h+var_418]
0x14000c00d  mov     rcx, rbx
0x14000c010  mov     rax, rdi
0x14000c013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c018  mov     rbx, [rbp+380h+Block]
0x14000c01c  or      r13d, 0FFFFFFFFh
0x14000c020  mov     edi, eax
0x14000c022  test    rbx, rbx
0x14000c025  jz      short loc_14000C069
0x14000c027  mov     ecx, r13d
0x14000c02a  lock xadd [rbx+10h], ecx
0x14000c02f  add     ecx, r13d
0x14000c032  jnz     short loc_14000C069
0x14000c034  test    rbx, rbx
0x14000c037  jz      short loc_14000C069
0x14000c039  mov     rcx, [rbx]; bstrString
0x14000c03c  test    rcx, rcx
0x14000c03f  jz      short loc_14000C04A
0x14000c041  call    cs:__imp_SysFreeString
0x14000c047  mov     [rbx], r12
0x14000c04a  mov     rcx, [rbx+8]; Block
0x14000c04e  test    rcx, rcx
0x14000c051  jz      short loc_14000C05C
0x14000c053  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c058  mov     [rbx+8], r12
0x14000c05c  mov     edx, 18h
0x14000c061  mov     rcx, rbx; Block
0x14000c064  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c069  test    edi, edi
0x14000c06b  jns     loc_14000C0F4
0x14000c071  mov     rcx, [rbp+388h]; this
0x14000c078  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000c07f  mov     r9d, edi; char *
0x14000c082  mov     edx, 0E96h; void *
0x14000c087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c08c  lea     rcx, [rsp+480h+var_418]
0x14000c091  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000c096  lea     rcx, [rsp+480h+var_428]
0x14000c09b  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000c0a0  cmp     dword ptr [rsp+480h+var_430], r12d
0x14000c0a5  jz      short loc_14000C0AD
0x14000c0a7  call    cs:__imp_CoUninitialize
0x14000c0ad  mov     eax, edi
0x14000c0af  mov     rcx, [rbp+380h+var_B0]
0x14000c0b6  xor     rcx, rsp; StackCookie
0x14000c0b9  call    __security_check_cookie
0x14000c0be  lea     r11, [rsp+480h+var_38]
0x14000c0c6  movaps  xmm6, xmmword ptr [r11-18h]
0x14000c0cb  movaps  xmm7, xmmword ptr [r11-28h]
0x14000c0d0  movaps  xmm8, xmmword ptr [r11-38h]
0x14000c0d5  movaps  xmm9, xmmword ptr [r11-48h]
0x14000c0da  movaps  xmm10, xmmword ptr [r11-58h]
0x14000c0df  movaps  xmm11, xmmword ptr [r11-68h]
0x14000c0e4  mov     rsp, r11
0x14000c0e7  pop     r15
0x14000c0e9  pop     r14
0x14000c0eb  pop     r13
0x14000c0ed  pop     r12
0x14000c0ef  pop     rdi
0x14000c0f0  pop     rsi
0x14000c0f1  pop     rbx
0x14000c0f2  pop     rbp
0x14000c0f3  retn
0x14000c0f4  lea     rax, aSchedule2Creat; "Schedule #2 created by enrollment clien"...
0x14000c0fb  mov     edi, r12d
0x14000c0fe  mov     [rbp+380h+var_318], rax
0x14000c102  lea     r14, [rbp+380h+var_318]
0x14000c106  lea     rax, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x14000c10d  mov     [rbp+380h+var_310], rax
0x14000c111  lea     rax, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x14000c118  mov     [rbp+380h+var_308], rax
0x14000c11c  lea     rax, aScheduleCreate; "Schedule created by enrollment client f"...
0x14000c123  mov     [rbp+380h+var_300], rax
0x14000c12a  lea     rax, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x14000c131  mov     [rbp+380h+var_2F8], rax
0x14000c138  lea     rax, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x14000c13f  mov     [rbp+380h+var_2F0], rax
0x14000c146  lea     rax, aUserMaintenanc; "User Maintenance Schedule created by en"...
0x14000c14d  mov     [rbp+380h+var_2E8], rax
0x14000c154  lea     rax, [rbp+380h+var_2E0]
0x14000c15b  cmp     r14, rax
0x14000c15e  jz      loc_14000C08C
0x14000c164  mov     rbx, [rsp+480h+var_418]
0x14000c169  lea     rcx, [rbp+380h+var_3E0]; this
0x14000c16d  mov     rdx, [r14]; unsigned __int16 *
0x14000c170  mov     [rbp+380h+var_400], r12
0x14000c174  mov     rax, [rbx]
0x14000c177  mov     rsi, [rax+68h]
0x14000c17b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000c180  mov     rdx, [rax]
0x14000c183  test    rdx, rdx
0x14000c186  jz      short loc_14000C18D
0x14000c188  mov     rdx, [rdx]
0x14000c18b  jmp     short loc_14000C190
0x14000c18d  mov     rdx, r12
0x14000c190  lea     r8, [rbp+380h+var_400]
0x14000c194  mov     rcx, rbx
0x14000c197  mov     rax, rsi
0x14000c19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c19f  mov     rbx, [rbp+380h+var_3E0]
0x14000c1a3  mov     esi, eax
0x14000c1a5  test    rbx, rbx
0x14000c1a8  jz      short loc_14000C1F0
0x14000c1aa  mov     ecx, r13d
0x14000c1ad  lock xadd [rbx+10h], ecx
0x14000c1b2  add     ecx, r13d
0x14000c1b5  jnz     short loc_14000C1EC
0x14000c1b7  test    rbx, rbx
0x14000c1ba  jz      short loc_14000C1EC
0x14000c1bc  mov     rcx, [rbx]; bstrString
0x14000c1bf  test    rcx, rcx
0x14000c1c2  jz      short loc_14000C1CD
0x14000c1c4  call    cs:__imp_SysFreeString
0x14000c1ca  mov     [rbx], r12
0x14000c1cd  mov     rcx, [rbx+8]; Block
0x14000c1d1  test    rcx, rcx
0x14000c1d4  jz      short loc_14000C1DF
0x14000c1d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c1db  mov     [rbx+8], r12
0x14000c1df  mov     edx, 18h
0x14000c1e4  mov     rcx, rbx; Block
0x14000c1e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c1ec  mov     [rbp+380h+var_3E0], r12
0x14000c1f0  test    esi, esi
0x14000c1f2  js      loc_14000C456
0x14000c1f8  mov     rcx, [rbp+380h+var_400]
0x14000c1fc  lea     rdx, [rsp+480h+var_408]
0x14000c201  mov     [rsp+480h+var_408], r12
0x14000c206  mov     rax, [rcx]
0x14000c209  mov     rax, [rax+98h]
0x14000c210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c215  mov     ebx, eax
0x14000c217  test    eax, eax
0x14000c219  js      loc_14000C516
0x14000c21f  mov     rcx, [rsp+480h+var_408]
0x14000c224  lea     rdx, [rsp+480h+var_420]
0x14000c229  mov     [rsp+480h+var_420], r12
0x14000c22e  mov     rax, [rcx]
0x14000c231  mov     rax, [rax+58h]
0x14000c235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c23a  mov     ebx, eax
0x14000c23c  test    eax, eax
0x14000c23e  js      loc_14000C4EF
0x14000c244  mov     rcx, [rsp+480h+var_420]
0x14000c249  lea     rdx, [rsp+480h+var_410]
0x14000c24e  mov     word ptr [rsp+480h+var_410], r12w
0x14000c254  mov     rax, [rcx]
0x14000c257  mov     rax, [rax+0A8h]
0x14000c25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c263  mov     ebx, eax
0x14000c265  test    eax, eax
0x14000c267  js      loc_14000C4E8
0x14000c26d  mov     sil, r12b
0x14000c270  cmp     word ptr [rsp+480h+var_410], r12w
0x14000c276  jnz     short loc_14000C29C
0x14000c278  mov     rcx, [rsp+480h+var_420]
0x14000c27d  mov     edx, r13d
0x14000c280  mov     rax, [rcx]
0x14000c283  mov     rax, [rax+0B0h]
0x14000c28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c28f  mov     ebx, eax
0x14000c291  test    eax, eax
0x14000c293  js      loc_14000C471
0x14000c299  mov     sil, 1
0x14000c29c  mov     rcx, [rsp+480h+var_420]
0x14000c2a1  lea     rdx, [rsp+480h+var_410]
0x14000c2a6  mov     rax, [rcx]
0x14000c2a9  mov     rax, [rax+0C8h]
  ... truncated ...
```
