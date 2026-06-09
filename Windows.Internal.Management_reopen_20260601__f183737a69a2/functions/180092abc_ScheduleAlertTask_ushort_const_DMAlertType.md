# ScheduleAlertTask(ushort const *,DMAlertType)

- ea: `0x180092abc`
- end: `0x18009310d`
- name: `?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z`
- size: `1617`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180094c70`

## callees

- `0x180004eb0`
- `0x18000535c`
- `0x18000ac30`
- `0x18003b93c`
- `0x180090864`
- `0x180090968`
- `0x1800909e0`
- `0x180090a34`
- `0x180090ae4`
- `0x180090b0c`
- `0x180090d60`
- `0x180091100`
- `0x180092abc`
- `0x180094bac`
- `0x180095efc`
- `0x180096ae8`
- `0x180096bf4`
- `0x180096c88`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmDisableTask` at `0x180092fbd`
- `DMCmnUtils!DmDisableTask` at `0x180092fbd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180093012`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180093012`
- `RPCRT4!UuidFromStringW` at `0x180092bf0`
- `RPCRT4!UuidFromStringW` at `0x180092bf0`
- `OLEAUT32!__imp_SysFreeString` at `0x180092d77`
- `OLEAUT32!__imp_SysFreeString` at `0x180092f56`
- `OLEAUT32!__imp_SysFreeString` at `0x180092d77`
- `OLEAUT32!__imp_SysFreeString` at `0x180092f56`
- `OLEAUT32!__imp_VariantInit` at `0x180092e63`
- `OLEAUT32!__imp_VariantInit` at `0x180092e7c`
- `OLEAUT32!__imp_VariantInit` at `0x180092e63`
- `OLEAUT32!__imp_VariantInit` at `0x180092e7c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009303d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180093068`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009303d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180093068`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18009302a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180093055`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18009302a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180093055`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180092c2c`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180092c2c`

## string_xrefs

- `0x180092bce`: `/s "%s" /c /OsEditionUpgradeAlert /SID "%s"`
- `0x180092bb7`: `/s "%s" /c /Win10SModeAlert /SID "%s"`
- `0x180092bd5`: `OS Edition Upgrade event listener created by enrollment client`
- `0x180092b9d`: `Wsc Startup event listener created by enrollment client`
- `0x180092fac`: `Wsc Startup event listener created by enrollment client`
- `0x180092bbe`: `Win10 S Mode event listener created by enrollment client`
- `0x180092cda`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
__int64 __fastcall ScheduleAlertTask(unsigned __int16 *a1, int a2)
{
  signed int v4; // edi
  const unsigned __int16 *v5; // r15
  unsigned int v6; // edx
  void *v7; // rax
  const unsigned __int16 *v8; // rbx
  RPC_STATUS v9; // edi
  int EnrollmentSID; // eax
  const wchar_t *v11; // rax
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, __int64); // rdi
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  signed int v16; // eax
  __int64 v17; // rbx
  void *v18; // rcx
  unsigned int i; // ebx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r12
  __int128 v22; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v24; // xmm8
  IRecordInfo *v25; // xmm9_8
  _variant_t *v26; // rax
  __int64 v27; // rdi
  __int128 v28; // xmm10
  __int64 v29; // xmm11_8
  _bstr_t *v30; // rax
  __int64 v31; // rdx
  signed int v32; // eax
  BSTR *v33; // rbx
  BSTR v34; // rcx
  int v35; // esi
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v37; // rax
  CEnrollmentLogger *v38; // rax
  SAFEARRAY *v39; // rbx
  SAFEARRAY *v40; // rbx
  const wchar_t *v42; // [rsp+78h] [rbp-90h] BYREF
  void *v43; // [rsp+80h] [rbp-88h] BYREF
  int v44; // [rsp+88h] [rbp-80h] BYREF
  __int64 v45; // [rsp+90h] [rbp-78h] BYREF
  __int64 v46; // [rsp+98h] [rbp-70h] BYREF
  SAFEARRAY *v47; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v52[2]; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG Block; // [rsp+D8h] [rbp-30h] BYREF
  SAFEARRAY *psa; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v55; // [rsp+100h] [rbp-8h] BYREF
  __int64 v56; // [rsp+108h] [rbp+0h] BYREF
  VARIANTARG pvarg; // [rsp+110h] [rbp+8h] BYREF
  __int128 v58; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v59; // [rsp+138h] [rbp+30h]
  __int128 v60; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v61; // [rsp+158h] [rbp+50h]
  __int128 v62; // [rsp+168h] [rbp+60h] BYREF
  __int64 v63; // [rsp+178h] [rbp+70h]
  _BYTE v64[32]; // [rsp+188h] [rbp+80h] BYREF
  UUID Uuid; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v66[264]; // [rsp+1B8h] [rbp+B0h] BYREF

  v52[0] = 0;
  v50 = 0;
  v45 = 0;
  v49 = 0;
  v51 = 0;
  v46 = 0;
  v48 = 0;
  v56 = 0;
  v55 = 0;
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&v47, 8);
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&psa, 0);
  v44 = 0;
  Uuid = 0;
  switch ( a2 )
  {
    case 0:
      v7 = (void *)WNF_OLIC_OS_EDITION_CHANGE;
      v8 = L"/s \"%s\" /c /OsEditionUpgradeAlert /SID \"%s\"";
      v5 = L"OS Edition Upgrade event listener created by enrollment client";
LABEL_8:
      v43 = v7;
      v42 = 0;
      v9 = UuidFromStringW(a1, &Uuid);
      if ( v9 )
      {
        v4 = v9 | 0x80010000;
        CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v42);
        goto LABEL_54;
      }
      *(UUID *)&Block.vt = Uuid;
      EnrollmentSID = GetEnrollmentSID(&Block, &v42);
      v4 = EnrollmentSID;
      if ( EnrollmentSID < 0 )
      {
        if ( EnrollmentSID != -2147024894 )
        {
LABEL_15:
          CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v42);
LABEL_16:
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v44, v6);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = CreateTask(
                 v52,
                 &v50,
                 &v45,
                 &v49,
                 a1,
                 L"%windir%\\system32\\deviceenroller.exe",
                 v66,
                 L"S-1-5-18",
                 0,
                 1,
                 0,
                 0,
                 0);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 120LL))(v45, &v46);
          if ( v4 < 0 )
            goto LABEL_55;
          v12 = v46;
          v13 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 64LL);
          v14 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"LocalSystem");
          if ( *(_QWORD *)v14 )
            v15 = **(_QWORD **)v14;
          else
            v15 = 0;
          v16 = v13(v12, v15);
          v17 = *(_QWORD *)&Block.vt;
          v4 = v16;
          if ( *(_QWORD *)&Block.vt
            && !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&Block.vt + 16LL))
            && v17 )
          {
            if ( *(_QWORD *)v17 )
            {
              SysFreeString(*(BSTR *)v17);
              *(_QWORD *)v17 = 0;
            }
            v18 = *(void **)(v17 + 8);
            if ( v18 )
            {
              operator delete(v18);
              *(_QWORD *)(v17 + 8) = 0;
            }
            operator delete((void *)v17);
          }
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 144LL))(v46, 1);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 208LL))(v49, 0xFFFFFFFFLL);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 72LL))(v45, &v48);
          if ( v4 < 0 )
            goto LABEL_55;
          for ( i = 0; (unsigned __int64)(int)i < 8; ++i )
          {
            v4 = ATL::CComSafeArray<unsigned char,17>::SetAt(&v47, i, (char *)&v43 + (int)i);
            if ( v4 < 0 )
              goto LABEL_55;
          }
          v4 = AddTaskWNFTrigger(v48, &v47);
          if ( v4 < 0 )
            goto LABEL_55;
          v20 = v50;
          v21 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(*(_QWORD *)v50 + 136LL);
          VariantInit(&pvarg);
          v22 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&Block);
          v24 = *(_OWORD *)&Block.vt;
          v25 = Block.pRecInfo;
          v26 = _variant_t::_variant_t((_variant_t *)v64, L"S-1-5-18");
          v27 = v45;
          v28 = *(_OWORD *)v26;
          v29 = *((_QWORD *)v26 + 2);
          v30 = _bstr_t::_bstr_t((_bstr_t *)&v43, v5);
          if ( *(_QWORD *)v30 )
            v31 = **(_QWORD **)v30;
          else
            v31 = 0;
          v58 = v22;
          v59 = pRecInfo;
          v60 = v24;
          v61 = v25;
          v62 = v28;
          v63 = v29;
          v32 = v21(v20, v31, v27, 6, &v62, &v60, 3, &v58, &v51);
          v33 = (BSTR *)v43;
          v4 = v32;
          if ( v43 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43 + 4, 0xFFFFFFFF) == 1 && v33 )
            {
              if ( *v33 )
              {
                SysFreeString(*v33);
                *v33 = 0;
              }
              v34 = v33[1];
              if ( v34 )
              {
                operator delete(v34);
                v33[1] = 0;
              }
              operator delete(v33);
            }
            v43 = 0;
          }
          _variant_t::~_variant_t((_variant_t *)v64);
          _variant_t::~_variant_t((_variant_t *)&Block);
          _variant_t::~_variant_t((_variant_t *)&pvarg);
          if ( a2 == 2 )
            DmDisableTask(
              L"\\Microsoft\\Windows\\EnterpriseMgmt",
              a1,
              L"Wsc Startup event listener created by enrollment client");
LABEL_54:
          if ( v4 >= 0 )
            goto LABEL_61;
          goto LABEL_55;
        }
        v11 = L"S-1-1-0";
      }
      else
      {
        v11 = v42;
      }
      v4 = StringCchPrintfW(v66, 0x104u, v8, a1, v11);
      goto LABEL_15;
    case 1:
      v7 = (void *)WNF_CI_SMODE_CHANGE;
      v8 = L"/s \"%s\" /c /Win10SModeAlert /SID \"%s\"";
      v5 = L"Win10 S Mode event listener created by enrollment client";
      goto LABEL_8;
    case 2:
      v43 = (void *)WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION;
      v5 = L"Wsc Startup event listener created by enrollment client";
      v4 = StringCchPrintfW(v66, 0x104u, L"/s \"%s\" /c /WscStartupAlert", a1);
      goto LABEL_16;
  }
  v4 = -2147418113;
LABEL_55:
  if ( a2 )
  {
    v35 = a2 - 1;
    if ( v35 )
    {
      if ( v35 == 1 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogWscStartupAlertScheduleSetupFail(Logger, v4);
      }
    }
    else
    {
      v37 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogWin10SModeScheduleSetupFail(v37, v4);
    }
  }
  else
  {
    v38 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogOsEditionUpgradeScheduleSetupFail(v38, v4);
  }
LABEL_61:
  if ( v44 )
    CoUninitialize();
  v39 = psa;
  if ( psa && SafeArrayUnlock(psa) >= 0 )
    SafeArrayDestroy(v39);
  v40 = v47;
  if ( v47 && SafeArrayUnlock(v47) >= 0 )
    SafeArrayDestroy(v40);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v55);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v48);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v46);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v45);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v52);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180092abc  mov     rax, rsp
0x180092abf  push    rbp
0x180092ac0  push    rbx
0x180092ac1  push    rsi
0x180092ac2  push    rdi
0x180092ac3  push    r12
0x180092ac5  push    r13
0x180092ac7  push    r14
0x180092ac9  push    r15
0x180092acb  lea     rbp, [rax-378h]
0x180092ad2  sub     rsp, 438h
0x180092ad9  movaps  xmmword ptr [rax-58h], xmm6
0x180092add  movaps  xmmword ptr [rax-68h], xmm7
0x180092ae1  movaps  xmmword ptr [rax-78h], xmm8
0x180092ae6  movaps  xmmword ptr [rax-88h], xmm9
0x180092aee  movaps  xmmword ptr [rax-98h], xmm10
0x180092af6  movaps  xmmword ptr [rax-0A8h], xmm11
0x180092afe  mov     rax, cs:__security_cookie
0x180092b05  xor     rax, rsp
0x180092b08  mov     [rbp+370h+var_B0], rax
0x180092b0f  xor     r13d, r13d
0x180092b12  mov     esi, edx
0x180092b14  mov     r14, rcx
0x180092b17  mov     [rbp+370h+var_3B0], r13
0x180092b1b  lea     rcx, [rbp+370h+var_3D8]
0x180092b1f  mov     [rbp+370h+var_3C0], r13
0x180092b23  mov     [rbp+370h+var_3E8], r13
0x180092b27  lea     edx, [r13+8]
0x180092b2b  mov     [rbp+370h+var_3C8], r13
0x180092b2f  mov     [rbp+370h+var_3B8], r13
0x180092b33  mov     [rbp+370h+var_3E0], r13
0x180092b37  mov     [rbp+370h+var_3D0], r13
0x180092b3b  mov     [rbp+370h+var_370], r13
0x180092b3f  mov     [rbp+370h+var_378], r13
0x180092b43  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x180092b48  xor     edx, edx
0x180092b4a  lea     rcx, [rbp+370h+psa]
0x180092b4e  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x180092b53  mov     [rbp+370h+var_3F0], r13d
0x180092b57  xorps   xmm0, xmm0
0x180092b5a  mov     ecx, esi
0x180092b5c  movups  xmmword ptr [rbp+370h+Uuid.Data1], xmm0
0x180092b63  test    esi, esi
0x180092b65  jz      short loc_180092BC7
0x180092b67  sub     ecx, 1
0x180092b6a  jz      short loc_180092BB0
0x180092b6c  cmp     ecx, 1
0x180092b6f  jz      short loc_180092B7B
0x180092b71  mov     edi, 8000FFFFh
0x180092b76  jmp     loc_180092FCD
0x180092b7b  mov     rax, cs:WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION
0x180092b82  lea     r8, aSSCWscstartupa; "/s \"%s\" /c /WscStartupAlert"
0x180092b89  mov     r9, r14
0x180092b8c  mov     [rsp+470h+var_3F8], rax
0x180092b91  mov     edx, 104h; unsigned __int64
0x180092b96  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x180092b9d  lea     r15, aWscStartupEven; "Wsc Startup event listener created by e"...
0x180092ba4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180092ba9  mov     edi, eax
0x180092bab  jmp     loc_180092C7B
0x180092bb0  mov     rax, cs:WNF_CI_SMODE_CHANGE
0x180092bb7  lea     rbx, aSSCWin10smodea; "/s \"%s\" /c /Win10SModeAlert /SID \"%s"...
0x180092bbe  lea     r15, aWin10SModeEven; "Win10 S Mode event listener created by "...
0x180092bc5  jmp     short loc_180092BDC
0x180092bc7  mov     rax, cs:WNF_OLIC_OS_EDITION_CHANGE
0x180092bce  lea     rbx, aSSCOseditionup; "/s \"%s\" /c /OsEditionUpgradeAlert /SI"...
0x180092bd5  lea     r15, aOsEditionUpgra; "OS Edition Upgrade event listener creat"...
0x180092bdc  lea     rdx, [rbp+370h+Uuid]; Uuid
0x180092be3  mov     [rsp+470h+var_3F8], rax
0x180092be8  mov     rcx, r14; StringUuid
0x180092beb  mov     [rsp+470h+var_400], r13
0x180092bf0  call    cs:__imp_UuidFromStringW
0x180092bf7  nop     dword ptr [rax+rax+00h]
0x180092bfc  mov     edi, eax
0x180092bfe  test    eax, eax
0x180092c00  jz      short loc_180092C17
0x180092c02  or      edi, 80010000h
0x180092c08  lea     rcx, [rsp+470h+var_400]
0x180092c0d  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180092c12  jmp     loc_180092FC9
0x180092c17  movaps  xmm0, xmmword ptr [rbp+370h+Uuid.Data1]
0x180092c1e  lea     rdx, [rsp+470h+var_400]
0x180092c23  lea     rcx, [rbp+370h+Block]
0x180092c27  movdqa  xmmword ptr [rbp+370h+Block], xmm0
0x180092c2c  call    cs:__imp_GetEnrollmentSID
0x180092c33  nop     dword ptr [rax+rax+00h]
0x180092c38  mov     edi, eax
0x180092c3a  test    eax, eax
0x180092c3c  js      short loc_180092C45
0x180092c3e  mov     rax, [rsp+470h+var_400]
0x180092c43  jmp     short loc_180092C53
0x180092c45  cmp     eax, 80070002h
0x180092c4a  jnz     short loc_180092C71
0x180092c4c  lea     rax, aS110; "S-1-1-0"
0x180092c53  mov     r9, r14
0x180092c56  mov     [rsp+470h+var_450], rax
0x180092c5b  mov     r8, rbx; unsigned __int16 *
0x180092c5e  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x180092c65  mov     edx, 104h; unsigned __int64
0x180092c6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180092c6f  mov     edi, eax
0x180092c71  lea     rcx, [rsp+470h+var_400]
0x180092c76  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180092c7b  test    edi, edi
0x180092c7d  js      loc_180092FCD
0x180092c83  lea     rcx, [rbp+370h+var_3F0]; this
0x180092c87  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x180092c8c  mov     edi, eax
0x180092c8e  test    eax, eax
0x180092c90  js      loc_180092FCD
0x180092c96  mov     [rsp+470h+var_410], r13d
0x180092c9b  lea     rax, aS1518; "S-1-5-18"
0x180092ca2  mov     [rsp+470h+var_418], r13d
0x180092ca7  lea     r9, [rbp+370h+var_3C8]
0x180092cab  mov     [rsp+470h+var_420], r13d
0x180092cb0  lea     r8, [rbp+370h+var_3E8]
0x180092cb4  mov     [rsp+470h+var_428], 1
0x180092cbc  lea     rdx, [rbp+370h+var_3C0]
0x180092cc0  mov     [rsp+470h+var_430], r13d
0x180092cc5  lea     rcx, [rbp+370h+var_3B0]
0x180092cc9  mov     [rsp+470h+var_438], rax
0x180092cce  lea     rax, [rbp+370h+var_2C0]
0x180092cd5  mov     [rsp+470h+var_440], rax
0x180092cda  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x180092ce1  mov     [rsp+470h+var_448], rax
0x180092ce6  mov     [rsp+470h+var_450], r14
0x180092ceb  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180092cf0  mov     edi, eax
0x180092cf2  test    eax, eax
0x180092cf4  js      loc_180092FCD
0x180092cfa  mov     rcx, [rbp+370h+var_3E8]
0x180092cfe  lea     rdx, [rbp+370h+var_3E0]
0x180092d02  mov     rax, [rcx]
0x180092d05  mov     rax, [rax+78h]
0x180092d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092d0e  mov     edi, eax
0x180092d10  test    eax, eax
0x180092d12  js      loc_180092FCD
0x180092d18  mov     rbx, [rbp+370h+var_3E0]
0x180092d1c  lea     rdx, aLocalsystem; "LocalSystem"
0x180092d23  lea     rcx, [rbp+370h+Block]; this
0x180092d27  mov     rax, [rbx]
0x180092d2a  mov     rdi, [rax+40h]
0x180092d2e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180092d33  mov     rcx, [rax]
0x180092d36  test    rcx, rcx
0x180092d39  jz      short loc_180092D40
0x180092d3b  mov     rdx, [rcx]
0x180092d3e  jmp     short loc_180092D43
0x180092d40  mov     rdx, r13
0x180092d43  mov     rcx, rbx
0x180092d46  mov     rax, rdi
0x180092d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092d4e  mov     rbx, [rbp+370h+Block]
0x180092d52  or      r12d, 0FFFFFFFFh
0x180092d56  mov     edi, eax
0x180092d58  test    rbx, rbx
0x180092d5b  jz      short loc_180092DA5
0x180092d5d  mov     eax, r12d
0x180092d60  lock xadd [rbx+10h], eax
0x180092d65  add     eax, r12d
0x180092d68  jnz     short loc_180092DA5
0x180092d6a  test    rbx, rbx
0x180092d6d  jz      short loc_180092DA5
0x180092d6f  mov     rcx, [rbx]; bstrString
0x180092d72  test    rcx, rcx
0x180092d75  jz      short loc_180092D86
0x180092d77  call    cs:__imp_SysFreeString
0x180092d7e  nop     dword ptr [rax+rax+00h]
0x180092d83  mov     [rbx], r13
0x180092d86  mov     rcx, [rbx+8]; Block
0x180092d8a  test    rcx, rcx
0x180092d8d  jz      short loc_180092D98
0x180092d8f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180092d94  mov     [rbx+8], r13
0x180092d98  mov     edx, 18h
0x180092d9d  mov     rcx, rbx; Block
0x180092da0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180092da5  test    edi, edi
0x180092da7  js      loc_180092FCD
0x180092dad  mov     rcx, [rbp+370h+var_3E0]
0x180092db1  mov     edx, 1
0x180092db6  mov     rax, [rcx]
0x180092db9  mov     rax, [rax+90h]
0x180092dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092dc5  mov     edi, eax
0x180092dc7  test    eax, eax
0x180092dc9  js      loc_180092FCD
0x180092dcf  mov     rcx, [rbp+370h+var_3C8]
0x180092dd3  mov     edx, r12d
0x180092dd6  mov     rax, [rcx]
0x180092dd9  mov     rax, [rax+0D0h]
0x180092de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092de5  mov     edi, eax
0x180092de7  test    eax, eax
0x180092de9  js      loc_180092FCD
0x180092def  mov     rcx, [rbp+370h+var_3E8]
0x180092df3  lea     rdx, [rbp+370h+var_3D0]
0x180092df7  mov     rax, [rcx]
0x180092dfa  mov     rax, [rax+48h]
0x180092dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092e03  mov     edi, eax
0x180092e05  test    eax, eax
0x180092e07  js      loc_180092FCD
0x180092e0d  mov     ebx, r13d
0x180092e10  movsxd  rax, ebx
0x180092e13  cmp     rax, 8
0x180092e17  jnb     short loc_180092E3A
0x180092e19  lea     r8, [rsp+470h+var_3F8]
0x180092e1e  mov     edx, ebx
0x180092e20  add     r8, rax
0x180092e23  lea     rcx, [rbp+370h+var_3D8]
0x180092e27  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x180092e2c  mov     edi, eax
0x180092e2e  test    eax, eax
0x180092e30  js      loc_180092FCD
0x180092e36  inc     ebx
0x180092e38  jmp     short loc_180092E10
0x180092e3a  mov     rcx, [rbp+370h+var_3D0]
0x180092e3e  lea     rdx, [rbp+370h+var_3D8]
0x180092e42  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x180092e47  mov     edi, eax
0x180092e49  test    eax, eax
0x180092e4b  js      loc_180092FCD
0x180092e51  mov     rbx, [rbp+370h+var_3C0]
0x180092e55  lea     rcx, [rbp+370h+pvarg]; pvarg
0x180092e59  mov     rax, [rbx]
0x180092e5c  mov     r12, [rax+88h]
0x180092e63  call    cs:__imp_VariantInit
0x180092e6a  nop     dword ptr [rax+rax+00h]
0x180092e6f  movups  xmm6, xmmword ptr [rbp+370h+pvarg]
0x180092e73  lea     rcx, [rbp+370h+Block]; pvarg
0x180092e77  movsd   xmm7, qword ptr [rbp+370h+pvarg+10h]
0x180092e7c  call    cs:__imp_VariantInit
0x180092e83  nop     dword ptr [rax+rax+00h]
0x180092e88  movups  xmm8, xmmword ptr [rbp+370h+Block]
0x180092e8d  lea     rdx, aS1518; "S-1-5-18"
0x180092e94  movsd   xmm9, [rbp+370h+var_390]
0x180092e9a  lea     rcx, [rbp+370h+var_2F0]; this
0x180092ea1  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180092ea6  mov     rdi, [rbp+370h+var_3E8]
0x180092eaa  lea     rcx, [rsp+470h+var_3F8]; this
0x180092eaf  mov     rdx, r15; unsigned __int16 *
0x180092eb2  movups  xmm10, xmmword ptr [rax]
0x180092eb6  movsd   xmm11, qword ptr [rax+10h]
0x180092ebc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180092ec1  mov     rdx, [rax]
0x180092ec4  test    rdx, rdx
0x180092ec7  jz      short loc_180092ECE
0x180092ec9  mov     rdx, [rdx]
0x180092ecc  jmp     short loc_180092ED1
0x180092ece  mov     rdx, r13
0x180092ed1  lea     rax, [rbp+370h+var_3B8]
0x180092ed5  movaps  [rbp+370h+var_350], xmm6
0x180092ed9  mov     qword ptr [rsp+470h+var_430], rax
0x180092ede  mov     r9d, 6
0x180092ee4  lea     rax, [rbp+370h+var_350]
0x180092ee8  movsd   [rbp+370h+var_340], xmm7
0x180092eed  mov     [rsp+470h+var_438], rax
0x180092ef2  mov     r8, rdi
0x180092ef5  lea     rax, [rbp+370h+var_330]
0x180092ef9  mov     dword ptr [rsp+470h+var_440], 3
0x180092f01  mov     [rsp+470h+var_448], rax
0x180092f06  mov     rcx, rbx
0x180092f09  lea     rax, [rbp+370h+var_310]
0x180092f0d  movaps  [rbp+370h+var_330], xmm8
0x180092f12  mov     [rsp+470h+var_450], rax
0x180092f17  mov     rax, r12
0x180092f1a  movsd   [rbp+370h+var_320], xmm9
0x180092f20  movaps  [rbp+370h+var_310], xmm10
0x180092f25  movsd   [rbp+370h+var_300], xmm11
0x180092f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092f30  mov     rbx, [rsp+470h+var_3F8]
0x180092f35  mov     edi, eax
0x180092f37  test    rbx, rbx
0x180092f3a  jz      short loc_180092F89
0x180092f3c  or      eax, 0FFFFFFFFh
0x180092f3f  lock xadd [rbx+10h], eax
0x180092f44  cmp     eax, 1
0x180092f47  jnz     short loc_180092F84
0x180092f49  test    rbx, rbx
0x180092f4c  jz      short loc_180092F84
0x180092f4e  mov     rcx, [rbx]; bstrString
0x180092f51  test    rcx, rcx
0x180092f54  jz      short loc_180092F65
0x180092f56  call    cs:__imp_SysFreeString
0x180092f5d  nop     dword ptr [rax+rax+00h]
0x180092f62  mov     [rbx], r13
0x180092f65  mov     rcx, [rbx+8]; Block
0x180092f69  test    rcx, rcx
0x180092f6c  jz      short loc_180092F77
0x180092f6e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180092f73  mov     [rbx+8], r13
0x180092f77  mov     edx, 18h
0x180092f7c  mov     rcx, rbx; Block
0x180092f7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180092f84  mov     [rsp+470h+var_3F8], r13
0x180092f89  lea     rcx, [rbp+370h+var_2F0]; this
0x180092f90  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180092f95  lea     rcx, [rbp+370h+Block]; this
  ... truncated ...
```
