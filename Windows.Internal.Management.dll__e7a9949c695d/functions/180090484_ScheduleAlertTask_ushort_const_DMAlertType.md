# ScheduleAlertTask(ushort const *,DMAlertType)

- ea: `0x180090484`
- end: `0x180090a8c`
- name: `?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z`
- size: `1544`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18009251c`

## callees

- `0x180004d50`
- `0x1800051fc`
- `0x18000a8e8`
- `0x18003c17c`
- `0x18008e360`
- `0x18008e454`
- `0x18008e4c4`
- `0x18008e510`
- `0x18008e5b8`
- `0x18008e5dc`
- `0x18008e7fc`
- `0x18008eb90`
- `0x180090484`
- `0x180092468`
- `0x180093684`
- `0x180094244`
- `0x18009434c`
- `0x1800943dc`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmDisableTask` at `0x180090961`
- `DMCmnUtils!DmDisableTask` at `0x180090961`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800909b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800909b0`
- `RPCRT4!UuidFromStringW` at `0x1800905b8`
- `RPCRT4!UuidFromStringW` at `0x1800905b8`
- `OLEAUT32!__imp_SysFreeString` at `0x180090733`
- `OLEAUT32!__imp_SysFreeString` at `0x180090900`
- `OLEAUT32!__imp_SysFreeString` at `0x180090733`
- `OLEAUT32!__imp_SysFreeString` at `0x180090900`
- `OLEAUT32!__imp_VariantInit` at `0x180090819`
- `OLEAUT32!__imp_VariantInit` at `0x18009082c`
- `OLEAUT32!__imp_VariantInit` at `0x180090819`
- `OLEAUT32!__imp_VariantInit` at `0x18009082c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800909cf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800909ee`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800909cf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800909ee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800909c2`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800909e1`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800909c2`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800909e1`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1800905ee`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1800905ee`

## string_xrefs

- `0x180090596`: `/s "%s" /c /OsEditionUpgradeAlert /SID "%s"`
- `0x18009057f`: `/s "%s" /c /Win10SModeAlert /SID "%s"`
- `0x18009059d`: `OS Edition Upgrade event listener created by enrollment client`
- `0x180090565`: `Wsc Startup event listener created by enrollment client`
- `0x180090950`: `Wsc Startup event listener created by enrollment client`
- `0x180090586`: `Win10 S Mode event listener created by enrollment client`
- `0x180090696`: `%windir%\system32\deviceenroller.exe`

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
0x180090484  mov     rax, rsp
0x180090487  push    rbp
0x180090488  push    rbx
0x180090489  push    rsi
0x18009048a  push    rdi
0x18009048b  push    r12
0x18009048d  push    r13
0x18009048f  push    r14
0x180090491  push    r15
0x180090493  lea     rbp, [rax-378h]
0x18009049a  sub     rsp, 438h
0x1800904a1  movaps  xmmword ptr [rax-58h], xmm6
0x1800904a5  movaps  xmmword ptr [rax-68h], xmm7
0x1800904a9  movaps  xmmword ptr [rax-78h], xmm8
0x1800904ae  movaps  xmmword ptr [rax-88h], xmm9
0x1800904b6  movaps  xmmword ptr [rax-98h], xmm10
0x1800904be  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800904c6  mov     rax, cs:__security_cookie
0x1800904cd  xor     rax, rsp
0x1800904d0  mov     [rbp+370h+var_B0], rax
0x1800904d7  xor     r13d, r13d
0x1800904da  mov     esi, edx
0x1800904dc  mov     r14, rcx
0x1800904df  mov     [rbp+370h+var_3B0], r13
0x1800904e3  lea     rcx, [rbp+370h+var_3D8]
0x1800904e7  mov     [rbp+370h+var_3C0], r13
0x1800904eb  mov     [rbp+370h+var_3E8], r13
0x1800904ef  lea     edx, [r13+8]
0x1800904f3  mov     [rbp+370h+var_3C8], r13
0x1800904f7  mov     [rbp+370h+var_3B8], r13
0x1800904fb  mov     [rbp+370h+var_3E0], r13
0x1800904ff  mov     [rbp+370h+var_3D0], r13
0x180090503  mov     [rbp+370h+var_370], r13
0x180090507  mov     [rbp+370h+var_378], r13
0x18009050b  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x180090510  xor     edx, edx
0x180090512  lea     rcx, [rbp+370h+psa]
0x180090516  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x18009051b  mov     [rbp+370h+var_3F0], r13d
0x18009051f  xorps   xmm0, xmm0
0x180090522  mov     ecx, esi
0x180090524  movups  xmmword ptr [rbp+370h+Uuid.Data1], xmm0
0x18009052b  test    esi, esi
0x18009052d  jz      short loc_18009058F
0x18009052f  sub     ecx, 1
0x180090532  jz      short loc_180090578
0x180090534  cmp     ecx, 1
0x180090537  jz      short loc_180090543
0x180090539  mov     edi, 8000FFFFh
0x18009053e  jmp     loc_18009096B
0x180090543  mov     rax, cs:WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION
0x18009054a  lea     r8, aSSCWscstartupa; "/s \"%s\" /c /WscStartupAlert"
0x180090551  mov     r9, r14
0x180090554  mov     [rsp+470h+var_3F8], rax
0x180090559  mov     edx, 104h; unsigned __int64
0x18009055e  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x180090565  lea     r15, aWscStartupEven; "Wsc Startup event listener created by e"...
0x18009056c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180090571  mov     edi, eax
0x180090573  jmp     loc_180090637
0x180090578  mov     rax, cs:WNF_CI_SMODE_CHANGE
0x18009057f  lea     rbx, aSSCWin10smodea; "/s \"%s\" /c /Win10SModeAlert /SID \"%s"...
0x180090586  lea     r15, aWin10SModeEven; "Win10 S Mode event listener created by "...
0x18009058d  jmp     short loc_1800905A4
0x18009058f  mov     rax, cs:WNF_OLIC_OS_EDITION_CHANGE
0x180090596  lea     rbx, aSSCOseditionup; "/s \"%s\" /c /OsEditionUpgradeAlert /SI"...
0x18009059d  lea     r15, aOsEditionUpgra; "OS Edition Upgrade event listener creat"...
0x1800905a4  lea     rdx, [rbp+370h+Uuid]; Uuid
0x1800905ab  mov     [rsp+470h+var_3F8], rax
0x1800905b0  mov     rcx, r14; StringUuid
0x1800905b3  mov     [rsp+470h+var_400], r13
0x1800905b8  call    cs:__imp_UuidFromStringW
0x1800905be  mov     edi, eax
0x1800905c0  test    eax, eax
0x1800905c2  jz      short loc_1800905D9
0x1800905c4  or      edi, 80010000h
0x1800905ca  lea     rcx, [rsp+470h+var_400]
0x1800905cf  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800905d4  jmp     loc_180090967
0x1800905d9  movaps  xmm0, xmmword ptr [rbp+370h+Uuid.Data1]
0x1800905e0  lea     rdx, [rsp+470h+var_400]
0x1800905e5  lea     rcx, [rbp+370h+Block]
0x1800905e9  movdqa  xmmword ptr [rbp+370h+Block], xmm0
0x1800905ee  call    cs:__imp_GetEnrollmentSID
0x1800905f4  mov     edi, eax
0x1800905f6  test    eax, eax
0x1800905f8  js      short loc_180090601
0x1800905fa  mov     rax, [rsp+470h+var_400]
0x1800905ff  jmp     short loc_18009060F
0x180090601  cmp     eax, 80070002h
0x180090606  jnz     short loc_18009062D
0x180090608  lea     rax, aS110; "S-1-1-0"
0x18009060f  mov     r9, r14
0x180090612  mov     [rsp+470h+var_450], rax
0x180090617  mov     r8, rbx; unsigned __int16 *
0x18009061a  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x180090621  mov     edx, 104h; unsigned __int64
0x180090626  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009062b  mov     edi, eax
0x18009062d  lea     rcx, [rsp+470h+var_400]
0x180090632  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180090637  test    edi, edi
0x180090639  js      loc_18009096B
0x18009063f  lea     rcx, [rbp+370h+var_3F0]; this
0x180090643  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x180090648  mov     edi, eax
0x18009064a  test    eax, eax
0x18009064c  js      loc_18009096B
0x180090652  mov     [rsp+470h+var_410], r13d
0x180090657  lea     rax, aS1518; "S-1-5-18"
0x18009065e  mov     [rsp+470h+var_418], r13d
0x180090663  lea     r9, [rbp+370h+var_3C8]
0x180090667  mov     [rsp+470h+var_420], r13d
0x18009066c  lea     r8, [rbp+370h+var_3E8]
0x180090670  mov     [rsp+470h+var_428], 1
0x180090678  lea     rdx, [rbp+370h+var_3C0]
0x18009067c  mov     [rsp+470h+var_430], r13d
0x180090681  lea     rcx, [rbp+370h+var_3B0]
0x180090685  mov     [rsp+470h+var_438], rax
0x18009068a  lea     rax, [rbp+370h+var_2C0]
0x180090691  mov     [rsp+470h+var_440], rax
0x180090696  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x18009069d  mov     [rsp+470h+var_448], rax
0x1800906a2  mov     [rsp+470h+var_450], r14
0x1800906a7  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x1800906ac  mov     edi, eax
0x1800906ae  test    eax, eax
0x1800906b0  js      loc_18009096B
0x1800906b6  mov     rcx, [rbp+370h+var_3E8]
0x1800906ba  lea     rdx, [rbp+370h+var_3E0]
0x1800906be  mov     rax, [rcx]
0x1800906c1  mov     rax, [rax+78h]
0x1800906c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800906ca  mov     edi, eax
0x1800906cc  test    eax, eax
0x1800906ce  js      loc_18009096B
0x1800906d4  mov     rbx, [rbp+370h+var_3E0]
0x1800906d8  lea     rdx, aLocalsystem; "LocalSystem"
0x1800906df  lea     rcx, [rbp+370h+Block]; this
0x1800906e3  mov     rax, [rbx]
0x1800906e6  mov     rdi, [rax+40h]
0x1800906ea  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800906ef  mov     rcx, [rax]
0x1800906f2  test    rcx, rcx
0x1800906f5  jz      short loc_1800906FC
0x1800906f7  mov     rdx, [rcx]
0x1800906fa  jmp     short loc_1800906FF
0x1800906fc  mov     rdx, r13
0x1800906ff  mov     rcx, rbx
0x180090702  mov     rax, rdi
0x180090705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009070a  mov     rbx, [rbp+370h+Block]
0x18009070e  or      r12d, 0FFFFFFFFh
0x180090712  mov     edi, eax
0x180090714  test    rbx, rbx
0x180090717  jz      short loc_18009075B
0x180090719  mov     eax, r12d
0x18009071c  lock xadd [rbx+10h], eax
0x180090721  add     eax, r12d
0x180090724  jnz     short loc_18009075B
0x180090726  test    rbx, rbx
0x180090729  jz      short loc_18009075B
0x18009072b  mov     rcx, [rbx]; bstrString
0x18009072e  test    rcx, rcx
0x180090731  jz      short loc_18009073C
0x180090733  call    cs:__imp_SysFreeString
0x180090739  mov     [rbx], r13
0x18009073c  mov     rcx, [rbx+8]; Block
0x180090740  test    rcx, rcx
0x180090743  jz      short loc_18009074E
0x180090745  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009074a  mov     [rbx+8], r13
0x18009074e  mov     edx, 18h
0x180090753  mov     rcx, rbx; Block
0x180090756  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009075b  test    edi, edi
0x18009075d  js      loc_18009096B
0x180090763  mov     rcx, [rbp+370h+var_3E0]
0x180090767  mov     edx, 1
0x18009076c  mov     rax, [rcx]
0x18009076f  mov     rax, [rax+90h]
0x180090776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009077b  mov     edi, eax
0x18009077d  test    eax, eax
0x18009077f  js      loc_18009096B
0x180090785  mov     rcx, [rbp+370h+var_3C8]
0x180090789  mov     edx, r12d
0x18009078c  mov     rax, [rcx]
0x18009078f  mov     rax, [rax+0D0h]
0x180090796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009079b  mov     edi, eax
0x18009079d  test    eax, eax
0x18009079f  js      loc_18009096B
0x1800907a5  mov     rcx, [rbp+370h+var_3E8]
0x1800907a9  lea     rdx, [rbp+370h+var_3D0]
0x1800907ad  mov     rax, [rcx]
0x1800907b0  mov     rax, [rax+48h]
0x1800907b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800907b9  mov     edi, eax
0x1800907bb  test    eax, eax
0x1800907bd  js      loc_18009096B
0x1800907c3  mov     ebx, r13d
0x1800907c6  movsxd  rax, ebx
0x1800907c9  cmp     rax, 8
0x1800907cd  jnb     short loc_1800907F0
0x1800907cf  lea     r8, [rsp+470h+var_3F8]
0x1800907d4  mov     edx, ebx
0x1800907d6  add     r8, rax
0x1800907d9  lea     rcx, [rbp+370h+var_3D8]
0x1800907dd  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x1800907e2  mov     edi, eax
0x1800907e4  test    eax, eax
0x1800907e6  js      loc_18009096B
0x1800907ec  inc     ebx
0x1800907ee  jmp     short loc_1800907C6
0x1800907f0  mov     rcx, [rbp+370h+var_3D0]
0x1800907f4  lea     rdx, [rbp+370h+var_3D8]
0x1800907f8  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x1800907fd  mov     edi, eax
0x1800907ff  test    eax, eax
0x180090801  js      loc_18009096B
0x180090807  mov     rbx, [rbp+370h+var_3C0]
0x18009080b  lea     rcx, [rbp+370h+pvarg]; pvarg
0x18009080f  mov     rax, [rbx]
0x180090812  mov     r12, [rax+88h]
0x180090819  call    cs:__imp_VariantInit
0x18009081f  movups  xmm6, xmmword ptr [rbp+370h+pvarg]
0x180090823  lea     rcx, [rbp+370h+Block]; pvarg
0x180090827  movsd   xmm7, qword ptr [rbp+370h+pvarg+10h]
0x18009082c  call    cs:__imp_VariantInit
0x180090832  movups  xmm8, xmmword ptr [rbp+370h+Block]
0x180090837  lea     rdx, aS1518; "S-1-5-18"
0x18009083e  movsd   xmm9, [rbp+370h+var_390]
0x180090844  lea     rcx, [rbp+370h+var_2F0]; this
0x18009084b  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180090850  mov     rdi, [rbp+370h+var_3E8]
0x180090854  lea     rcx, [rsp+470h+var_3F8]; this
0x180090859  mov     rdx, r15; unsigned __int16 *
0x18009085c  movups  xmm10, xmmword ptr [rax]
0x180090860  movsd   xmm11, qword ptr [rax+10h]
0x180090866  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18009086b  mov     rdx, [rax]
0x18009086e  test    rdx, rdx
0x180090871  jz      short loc_180090878
0x180090873  mov     rdx, [rdx]
0x180090876  jmp     short loc_18009087B
0x180090878  mov     rdx, r13
0x18009087b  lea     rax, [rbp+370h+var_3B8]
0x18009087f  movaps  [rbp+370h+var_350], xmm6
0x180090883  mov     qword ptr [rsp+470h+var_430], rax
0x180090888  mov     r9d, 6
0x18009088e  lea     rax, [rbp+370h+var_350]
0x180090892  movsd   [rbp+370h+var_340], xmm7
0x180090897  mov     [rsp+470h+var_438], rax
0x18009089c  mov     r8, rdi
0x18009089f  lea     rax, [rbp+370h+var_330]
0x1800908a3  mov     dword ptr [rsp+470h+var_440], 3
0x1800908ab  mov     [rsp+470h+var_448], rax
0x1800908b0  mov     rcx, rbx
0x1800908b3  lea     rax, [rbp+370h+var_310]
0x1800908b7  movaps  [rbp+370h+var_330], xmm8
0x1800908bc  mov     [rsp+470h+var_450], rax
0x1800908c1  mov     rax, r12
0x1800908c4  movsd   [rbp+370h+var_320], xmm9
0x1800908ca  movaps  [rbp+370h+var_310], xmm10
0x1800908cf  movsd   [rbp+370h+var_300], xmm11
0x1800908d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800908da  mov     rbx, [rsp+470h+var_3F8]
0x1800908df  mov     edi, eax
0x1800908e1  test    rbx, rbx
0x1800908e4  jz      short loc_18009092D
0x1800908e6  or      eax, 0FFFFFFFFh
0x1800908e9  lock xadd [rbx+10h], eax
0x1800908ee  cmp     eax, 1
0x1800908f1  jnz     short loc_180090928
0x1800908f3  test    rbx, rbx
0x1800908f6  jz      short loc_180090928
0x1800908f8  mov     rcx, [rbx]; bstrString
0x1800908fb  test    rcx, rcx
0x1800908fe  jz      short loc_180090909
0x180090900  call    cs:__imp_SysFreeString
0x180090906  mov     [rbx], r13
0x180090909  mov     rcx, [rbx+8]; Block
0x18009090d  test    rcx, rcx
0x180090910  jz      short loc_18009091B
0x180090912  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090917  mov     [rbx+8], r13
0x18009091b  mov     edx, 18h
0x180090920  mov     rcx, rbx; Block
0x180090923  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090928  mov     [rsp+470h+var_3F8], r13
0x18009092d  lea     rcx, [rbp+370h+var_2F0]; this
0x180090934  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180090939  lea     rcx, [rbp+370h+Block]; this
0x18009093d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180090942  lea     rcx, [rbp+370h+pvarg]; this
0x180090946  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18009094b  cmp     esi, 2
0x18009094e  jnz     short loc_180090967
0x180090950  lea     r8, aWscStartupEven; "Wsc Startup event listener created by e"...
  ... truncated ...
```
