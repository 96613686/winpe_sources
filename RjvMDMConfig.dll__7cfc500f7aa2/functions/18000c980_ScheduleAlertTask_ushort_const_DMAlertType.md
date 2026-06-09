# ScheduleAlertTask(ushort const *,DMAlertType)

- ea: `0x18000c980`
- end: `0x18000cfbc`
- name: `?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z`
- size: `1596`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fc24`

## callees

- `0x180001c60`
- `0x180001cc8`
- `0x1800051d8`
- `0x180006f74`
- `0x180007258`
- `0x1800072d0`
- `0x180007364`
- `0x1800079e8`
- `0x180007e2c`
- `0x1800086c4`
- `0x180008bd4`
- `0x18000c5dc`
- `0x18000c980`
- `0x18000f79c`
- `0x1800163f4`
- `0x180018284`
- `0x18001b9d8`
- `0x18001bf04`
- `0x18001bf98`
- `0x18001c02c`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000cc3b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cc3b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce1a`
- `OLEAUT32!__imp_VariantInit` at `0x18000cd27`
- `OLEAUT32!__imp_VariantInit` at `0x18000cd40`
- `OLEAUT32!__imp_VariantInit` at `0x18000cd27`
- `OLEAUT32!__imp_VariantInit` at `0x18000cd40`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ceec`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000cf17`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ceec`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000cf17`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000ced9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000cf04`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000ced9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000cf04`
- `RPCRT4!UuidFromStringW` at `0x18000cab4`
- `RPCRT4!UuidFromStringW` at `0x18000cab4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000cec1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000cec1`

## string_xrefs

- `0x18000ca92`: `/s "%s" /c /OsEditionUpgradeAlert /SID "%s"`
- `0x18000ca7b`: `/s "%s" /c /Win10SModeAlert /SID "%s"`
- `0x18000ca99`: `OS Edition Upgrade event listener created by enrollment client`
- `0x18000ca82`: `Win10 S Mode event listener created by enrollment client`
- `0x18000ca61`: `Wsc Startup event listener created by enrollment client`
- `0x18000cb9e`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
__int64 __fastcall ScheduleAlertTask(unsigned __int16 *a1, int a2)
{
  int v4; // edi
  const unsigned __int16 *v5; // r15
  unsigned int v6; // edx
  void *v7; // rax
  const unsigned __int16 *v8; // rbx
  RPC_STATUS v9; // edi
  int EnrollmentString; // eax
  unsigned __int16 *v11; // rax
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, __int64); // rdi
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  __int64 v18; // rbx
  void *v19; // rcx
  unsigned int i; // ebx
  struct IUnknown *v21; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // r12
  __int128 v23; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v25; // xmm8
  IRecordInfo *v26; // xmm9_8
  _variant_t *v27; // rax
  __int64 v28; // rdi
  __int128 v29; // xmm10
  __int64 v30; // xmm11_8
  _bstr_t *v31; // rax
  __int64 v32; // rdx
  int v33; // eax
  const struct std::nothrow_t *v34; // rdx
  BSTR *v35; // rbx
  BSTR v36; // rcx
  const unsigned __int16 *v37; // rcx
  const unsigned __int16 *v38; // r8
  int v39; // esi
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v41; // rax
  CEnrollmentLogger *v42; // rax
  SAFEARRAY *v43; // rbx
  SAFEARRAY *v44; // rbx
  __int64 v46; // [rsp+48h] [rbp-C0h]
  unsigned __int16 *v47; // [rsp+78h] [rbp-90h] BYREF
  void *v48; // [rsp+80h] [rbp-88h] BYREF
  int v49; // [rsp+88h] [rbp-80h] BYREF
  __int64 v50; // [rsp+90h] [rbp-78h] BYREF
  __int64 v51; // [rsp+98h] [rbp-70h] BYREF
  SAFEARRAY *v52; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-58h] BYREF
  struct IUnknown *v55; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-48h] BYREF
  LPVOID v57[2]; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v58; // [rsp+D8h] [rbp-30h] BYREF
  SAFEARRAY *psa; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v60; // [rsp+100h] [rbp-8h] BYREF
  __int64 v61; // [rsp+108h] [rbp+0h] BYREF
  VARIANTARG pvarg; // [rsp+110h] [rbp+8h] BYREF
  __int128 v63; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v64; // [rsp+138h] [rbp+30h]
  __int128 v65; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v66; // [rsp+158h] [rbp+50h]
  __int128 v67; // [rsp+168h] [rbp+60h] BYREF
  __int64 v68; // [rsp+178h] [rbp+70h]
  _BYTE v69[32]; // [rsp+188h] [rbp+80h] BYREF
  UUID Uuid; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v71[264]; // [rsp+1B8h] [rbp+B0h] BYREF

  v57[0] = 0;
  v55 = 0;
  v50 = 0;
  v54 = 0;
  v56 = 0;
  v51 = 0;
  v53 = 0;
  v61 = 0;
  v60 = 0;
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&v52, 8);
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&psa, 0);
  v49 = 0;
  Uuid = 0;
  switch ( a2 )
  {
    case 0:
      v7 = (void *)WNF_OLIC_OS_EDITION_CHANGE;
      v8 = L"/s \"%s\" /c /OsEditionUpgradeAlert /SID \"%s\"";
      v5 = L"OS Edition Upgrade event listener created by enrollment client";
LABEL_8:
      v48 = v7;
      v47 = 0;
      v9 = UuidFromStringW(a1, &Uuid);
      if ( v9 )
      {
        v4 = v9 | 0x80010000;
        CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v47);
        goto LABEL_54;
      }
      *(UUID *)&v58.vt = Uuid;
      EnrollmentString = EEDBManager::GetEnrollmentString((struct _GUID *)&v58, L"SID", &v47);
      v4 = EnrollmentString;
      if ( EnrollmentString < 0 )
      {
        if ( EnrollmentString != -2147024894 )
        {
LABEL_15:
          CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v47);
LABEL_16:
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v49, v6);
          if ( v4 < 0 )
            goto LABEL_55;
          LODWORD(v46) = 0;
          v4 = CreateTask(
                 v57,
                 &v55,
                 &v50,
                 &v54,
                 a1,
                 L"%windir%\\system32\\deviceenroller.exe",
                 v71,
                 L"S-1-5-18",
                 v46,
                 1,
                 0,
                 0,
                 0);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 120LL))(v50, &v51);
          if ( v4 < 0 )
            goto LABEL_55;
          v12 = v51;
          v13 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 64LL);
          v14 = _bstr_t::_bstr_t((_bstr_t *)&v58, L"LocalSystem");
          if ( *(_QWORD *)v14 )
            v15 = **(_QWORD **)v14;
          else
            v15 = 0;
          v16 = v13(v12, v15);
          v18 = *(_QWORD *)&v58.vt;
          v4 = v16;
          if ( *(_QWORD *)&v58.vt
            && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v58.vt + 16LL), 0xFFFFFFFF) == 1
            && v18 )
          {
            if ( *(_QWORD *)v18 )
            {
              SysFreeString(*(BSTR *)v18);
              *(_QWORD *)v18 = 0;
            }
            v19 = *(void **)(v18 + 8);
            if ( v19 )
            {
              operator delete(v19, v17);
              *(_QWORD *)(v18 + 8) = 0;
            }
            operator delete((void *)v18, (const struct std::nothrow_t *)0x18);
          }
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 144LL))(v51, 1);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 208LL))(v54, 0xFFFFFFFFLL);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 72LL))(v50, &v53);
          if ( v4 < 0 )
            goto LABEL_55;
          for ( i = 0; (unsigned __int64)(int)i < 8; ++i )
          {
            v4 = ATL::CComSafeArray<unsigned char,17>::SetAt(&v52, i, (char *)&v48 + (int)i);
            if ( v4 < 0 )
              goto LABEL_55;
          }
          v4 = AddTaskWNFTrigger(v53, &v52);
          if ( v4 < 0 )
            goto LABEL_55;
          v21 = v55;
          Release = v55->lpVtbl[5].Release;
          VariantInit(&pvarg);
          v23 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v58);
          v25 = *(_OWORD *)&v58.vt;
          v26 = v58.pRecInfo;
          v27 = _variant_t::_variant_t((_variant_t *)v69, L"S-1-5-18");
          v28 = v50;
          v29 = *(_OWORD *)v27;
          v30 = *((_QWORD *)v27 + 2);
          v31 = _bstr_t::_bstr_t((_bstr_t *)&v48, v5);
          if ( *(_QWORD *)v31 )
            v32 = **(_QWORD **)v31;
          else
            v32 = 0;
          v63 = v23;
          v64 = pRecInfo;
          v65 = v25;
          v66 = v26;
          v67 = v29;
          v68 = v30;
          v33 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                  v21,
                  v32,
                  v28,
                  6,
                  &v67,
                  &v65,
                  3,
                  &v63,
                  &v56);
          v35 = (BSTR *)v48;
          v4 = v33;
          if ( v48 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v48 + 4, 0xFFFFFFFF) == 1 && v35 )
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
            v48 = 0;
          }
          _variant_t::~_variant_t((_variant_t *)v69);
          _variant_t::~_variant_t((_variant_t *)&v58);
          _variant_t::~_variant_t((_variant_t *)&pvarg);
          if ( a2 == 2 )
            DmDisableTask(v37, a1, v38);
LABEL_54:
          if ( v4 >= 0 )
            goto LABEL_61;
          goto LABEL_55;
        }
        v11 = L"S-1-1-0";
      }
      else
      {
        v11 = v47;
      }
      v4 = StringCchPrintfW(v71, 0x104u, v8, a1, v11);
      goto LABEL_15;
    case 1:
      v7 = (void *)WNF_CI_SMODE_CHANGE;
      v8 = L"/s \"%s\" /c /Win10SModeAlert /SID \"%s\"";
      v5 = L"Win10 S Mode event listener created by enrollment client";
      goto LABEL_8;
    case 2:
      v48 = (void *)WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION;
      v5 = L"Wsc Startup event listener created by enrollment client";
      v4 = StringCchPrintfW(v71, 0x104u, L"/s \"%s\" /c /WscStartupAlert", a1);
      goto LABEL_16;
  }
  v4 = -2147418113;
LABEL_55:
  if ( a2 )
  {
    v39 = a2 - 1;
    if ( v39 )
    {
      if ( v39 == 1 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogWscStartupAlertScheduleSetupFail(Logger, v4);
      }
    }
    else
    {
      v41 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogWin10SModeScheduleSetupFail(v41, v4);
    }
  }
  else
  {
    v42 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogOsEditionUpgradeScheduleSetupFail(v42, v4);
  }
LABEL_61:
  if ( v49 )
    CoUninitialize();
  v43 = psa;
  if ( psa && SafeArrayUnlock(psa) >= 0 )
    SafeArrayDestroy(v43);
  v44 = v52;
  if ( v52 && SafeArrayUnlock(v52) >= 0 )
    SafeArrayDestroy(v44);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v60);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v61);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v53);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v54);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v55);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v57);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c980  mov     rax, rsp
0x18000c983  push    rbp
0x18000c984  push    rbx
0x18000c985  push    rsi
0x18000c986  push    rdi
0x18000c987  push    r12
0x18000c989  push    r13
0x18000c98b  push    r14
0x18000c98d  push    r15
0x18000c98f  lea     rbp, [rax-378h]
0x18000c996  sub     rsp, 438h
0x18000c99d  movaps  xmmword ptr [rax-58h], xmm6
0x18000c9a1  movaps  xmmword ptr [rax-68h], xmm7
0x18000c9a5  movaps  xmmword ptr [rax-78h], xmm8
0x18000c9aa  movaps  xmmword ptr [rax-88h], xmm9
0x18000c9b2  movaps  xmmword ptr [rax-98h], xmm10
0x18000c9ba  movaps  xmmword ptr [rax-0A8h], xmm11
0x18000c9c2  mov     rax, cs:__security_cookie
0x18000c9c9  xor     rax, rsp
0x18000c9cc  mov     [rbp+370h+var_B0], rax
0x18000c9d3  xor     r13d, r13d
0x18000c9d6  mov     esi, edx
0x18000c9d8  mov     r14, rcx
0x18000c9db  mov     [rbp+370h+var_3B0], r13
0x18000c9df  lea     rcx, [rbp+370h+var_3D8]
0x18000c9e3  mov     [rbp+370h+var_3C0], r13
0x18000c9e7  mov     [rbp+370h+var_3E8], r13
0x18000c9eb  lea     edx, [r13+8]
0x18000c9ef  mov     [rbp+370h+var_3C8], r13
0x18000c9f3  mov     [rbp+370h+var_3B8], r13
0x18000c9f7  mov     [rbp+370h+var_3E0], r13
0x18000c9fb  mov     [rbp+370h+var_3D0], r13
0x18000c9ff  mov     [rbp+370h+var_370], r13
0x18000ca03  mov     [rbp+370h+var_378], r13
0x18000ca07  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x18000ca0c  xor     edx, edx
0x18000ca0e  lea     rcx, [rbp+370h+psa]
0x18000ca12  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x18000ca17  mov     [rbp+370h+var_3F0], r13d
0x18000ca1b  xorps   xmm0, xmm0
0x18000ca1e  mov     ecx, esi
0x18000ca20  movups  xmmword ptr [rbp+370h+Uuid.Data1], xmm0
0x18000ca27  test    esi, esi
0x18000ca29  jz      short loc_18000CA8B
0x18000ca2b  sub     ecx, 1
0x18000ca2e  jz      short loc_18000CA74
0x18000ca30  cmp     ecx, 1
0x18000ca33  jz      short loc_18000CA3F
0x18000ca35  mov     edi, 8000FFFFh
0x18000ca3a  jmp     loc_18000CE7C
0x18000ca3f  mov     rax, cs:WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION
0x18000ca46  lea     r8, aSSCWscstartupa; "/s \"%s\" /c /WscStartupAlert"
0x18000ca4d  mov     r9, r14
0x18000ca50  mov     [rsp+470h+var_3F8], rax
0x18000ca55  mov     edx, 104h; unsigned __int64
0x18000ca5a  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x18000ca61  lea     r15, aWscStartupEven; "Wsc Startup event listener created by e"...
0x18000ca68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ca6d  mov     edi, eax
0x18000ca6f  jmp     loc_18000CB3F
0x18000ca74  mov     rax, cs:WNF_CI_SMODE_CHANGE
0x18000ca7b  lea     rbx, aSSCWin10smodea; "/s \"%s\" /c /Win10SModeAlert /SID \"%s"...
0x18000ca82  lea     r15, aWin10SModeEven; "Win10 S Mode event listener created by "...
0x18000ca89  jmp     short loc_18000CAA0
0x18000ca8b  mov     rax, cs:WNF_OLIC_OS_EDITION_CHANGE
0x18000ca92  lea     rbx, aSSCOseditionup; "/s \"%s\" /c /OsEditionUpgradeAlert /SI"...
0x18000ca99  lea     r15, aOsEditionUpgra; "OS Edition Upgrade event listener creat"...
0x18000caa0  lea     rdx, [rbp+370h+Uuid]; Uuid
0x18000caa7  mov     [rsp+470h+var_3F8], rax
0x18000caac  mov     rcx, r14; StringUuid
0x18000caaf  mov     [rsp+470h+var_400], r13
0x18000cab4  call    cs:__imp_UuidFromStringW
0x18000cabb  nop     dword ptr [rax+rax+00h]
0x18000cac0  mov     edi, eax
0x18000cac2  test    eax, eax
0x18000cac4  jz      short loc_18000CADB
0x18000cac6  or      edi, 80010000h
0x18000cacc  lea     rcx, [rsp+470h+var_400]
0x18000cad1  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18000cad6  jmp     loc_18000CE78
0x18000cadb  movaps  xmm0, xmmword ptr [rbp+370h+Uuid.Data1]
0x18000cae2  lea     r8, [rsp+470h+var_400]; unsigned __int16 **
0x18000cae7  lea     rdx, aSid; "SID"
0x18000caee  movdqa  xmmword ptr [rbp+370h+var_3A0], xmm0
0x18000caf3  lea     rcx, [rbp+370h+var_3A0]; struct _GUID
0x18000caf7  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18000cafc  mov     edi, eax
0x18000cafe  test    eax, eax
0x18000cb00  js      short loc_18000CB09
0x18000cb02  mov     rax, [rsp+470h+var_400]
0x18000cb07  jmp     short loc_18000CB17
0x18000cb09  cmp     eax, 80070002h
0x18000cb0e  jnz     short loc_18000CB35
0x18000cb10  lea     rax, aS110; "S-1-1-0"
0x18000cb17  mov     r9, r14
0x18000cb1a  mov     [rsp+470h+var_450], rax
0x18000cb1f  mov     r8, rbx; unsigned __int16 *
0x18000cb22  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x18000cb29  mov     edx, 104h; unsigned __int64
0x18000cb2e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cb33  mov     edi, eax
0x18000cb35  lea     rcx, [rsp+470h+var_400]
0x18000cb3a  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18000cb3f  test    edi, edi
0x18000cb41  js      loc_18000CE7C
0x18000cb47  lea     rcx, [rbp+370h+var_3F0]; this
0x18000cb4b  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x18000cb50  mov     edi, eax
0x18000cb52  test    eax, eax
0x18000cb54  js      loc_18000CE7C
0x18000cb5a  mov     [rsp+470h+var_410], r13d
0x18000cb5f  lea     rax, aS1518; "S-1-5-18"
0x18000cb66  mov     [rsp+470h+var_418], r13d
0x18000cb6b  lea     r9, [rbp+370h+var_3C8]
0x18000cb6f  mov     [rsp+470h+var_420], r13d
0x18000cb74  lea     r8, [rbp+370h+var_3E8]
0x18000cb78  mov     [rsp+470h+var_428], 1
0x18000cb80  lea     rdx, [rbp+370h+var_3C0]
0x18000cb84  mov     dword ptr [rsp+470h+var_430], r13d
0x18000cb89  lea     rcx, [rbp+370h+var_3B0]
0x18000cb8d  mov     [rsp+470h+var_438], rax
0x18000cb92  lea     rax, [rbp+370h+var_2C0]
0x18000cb99  mov     [rsp+470h+var_440], rax
0x18000cb9e  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x18000cba5  mov     [rsp+470h+var_448], rax
0x18000cbaa  mov     [rsp+470h+var_450], r14
0x18000cbaf  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18000cbb4  mov     edi, eax
0x18000cbb6  test    eax, eax
0x18000cbb8  js      loc_18000CE7C
0x18000cbbe  mov     rcx, [rbp+370h+var_3E8]
0x18000cbc2  lea     rdx, [rbp+370h+var_3E0]
0x18000cbc6  mov     rax, [rcx]
0x18000cbc9  mov     rax, [rax+78h]
0x18000cbcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbd2  mov     edi, eax
0x18000cbd4  test    eax, eax
0x18000cbd6  js      loc_18000CE7C
0x18000cbdc  mov     rbx, [rbp+370h+var_3E0]
0x18000cbe0  lea     rdx, aLocalsystem; "LocalSystem"
0x18000cbe7  lea     rcx, [rbp+370h+var_3A0]; this
0x18000cbeb  mov     rax, [rbx]
0x18000cbee  mov     rdi, [rax+40h]
0x18000cbf2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000cbf7  mov     rcx, [rax]
0x18000cbfa  test    rcx, rcx
0x18000cbfd  jz      short loc_18000CC04
0x18000cbff  mov     rdx, [rcx]
0x18000cc02  jmp     short loc_18000CC07
0x18000cc04  mov     rdx, r13
0x18000cc07  mov     rcx, rbx
0x18000cc0a  mov     rax, rdi
0x18000cc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc12  mov     rbx, qword ptr [rbp+370h+var_3A0]
0x18000cc16  or      r12d, 0FFFFFFFFh
0x18000cc1a  mov     edi, eax
0x18000cc1c  test    rbx, rbx
0x18000cc1f  jz      short loc_18000CC69
0x18000cc21  mov     eax, r12d
0x18000cc24  lock xadd [rbx+10h], eax
0x18000cc29  add     eax, r12d
0x18000cc2c  jnz     short loc_18000CC69
0x18000cc2e  test    rbx, rbx
0x18000cc31  jz      short loc_18000CC69
0x18000cc33  mov     rcx, [rbx]; bstrString
0x18000cc36  test    rcx, rcx
0x18000cc39  jz      short loc_18000CC4A
0x18000cc3b  call    cs:__imp_SysFreeString
0x18000cc42  nop     dword ptr [rax+rax+00h]
0x18000cc47  mov     [rbx], r13
0x18000cc4a  mov     rcx, [rbx+8]; void *
0x18000cc4e  test    rcx, rcx
0x18000cc51  jz      short loc_18000CC5C
0x18000cc53  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cc58  mov     [rbx+8], r13
0x18000cc5c  mov     edx, 18h; struct std::nothrow_t *
0x18000cc61  mov     rcx, rbx; void *
0x18000cc64  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cc69  test    edi, edi
0x18000cc6b  js      loc_18000CE7C
0x18000cc71  mov     rcx, [rbp+370h+var_3E0]
0x18000cc75  mov     edx, 1
0x18000cc7a  mov     rax, [rcx]
0x18000cc7d  mov     rax, [rax+90h]
0x18000cc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc89  mov     edi, eax
0x18000cc8b  test    eax, eax
0x18000cc8d  js      loc_18000CE7C
0x18000cc93  mov     rcx, [rbp+370h+var_3C8]
0x18000cc97  mov     edx, r12d
0x18000cc9a  mov     rax, [rcx]
0x18000cc9d  mov     rax, [rax+0D0h]
0x18000cca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca9  mov     edi, eax
0x18000ccab  test    eax, eax
0x18000ccad  js      loc_18000CE7C
0x18000ccb3  mov     rcx, [rbp+370h+var_3E8]
0x18000ccb7  lea     rdx, [rbp+370h+var_3D0]
0x18000ccbb  mov     rax, [rcx]
0x18000ccbe  mov     rax, [rax+48h]
0x18000ccc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccc7  mov     edi, eax
0x18000ccc9  test    eax, eax
0x18000cccb  js      loc_18000CE7C
0x18000ccd1  mov     ebx, r13d
0x18000ccd4  movsxd  rax, ebx
0x18000ccd7  cmp     rax, 8
0x18000ccdb  jnb     short loc_18000CCFE
0x18000ccdd  lea     r8, [rsp+470h+var_3F8]
0x18000cce2  mov     edx, ebx
0x18000cce4  add     r8, rax
0x18000cce7  lea     rcx, [rbp+370h+var_3D8]
0x18000cceb  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x18000ccf0  mov     edi, eax
0x18000ccf2  test    eax, eax
0x18000ccf4  js      loc_18000CE7C
0x18000ccfa  inc     ebx
0x18000ccfc  jmp     short loc_18000CCD4
0x18000ccfe  mov     rcx, [rbp+370h+var_3D0]
0x18000cd02  lea     rdx, [rbp+370h+var_3D8]
0x18000cd06  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x18000cd0b  mov     edi, eax
0x18000cd0d  test    eax, eax
0x18000cd0f  js      loc_18000CE7C
0x18000cd15  mov     rbx, [rbp+370h+var_3C0]
0x18000cd19  lea     rcx, [rbp+370h+pvarg]; pvarg
0x18000cd1d  mov     rax, [rbx]
0x18000cd20  mov     r12, [rax+88h]
0x18000cd27  call    cs:__imp_VariantInit
0x18000cd2e  nop     dword ptr [rax+rax+00h]
0x18000cd33  movups  xmm6, xmmword ptr [rbp+370h+pvarg]
0x18000cd37  lea     rcx, [rbp+370h+var_3A0]; pvarg
0x18000cd3b  movsd   xmm7, qword ptr [rbp+370h+pvarg+10h]
0x18000cd40  call    cs:__imp_VariantInit
0x18000cd47  nop     dword ptr [rax+rax+00h]
0x18000cd4c  movups  xmm8, xmmword ptr [rbp+370h+var_3A0]
0x18000cd51  lea     rdx, aS1518; "S-1-5-18"
0x18000cd58  movsd   xmm9, qword ptr [rbp+370h+var_3A0+10h]
0x18000cd5e  lea     rcx, [rbp+370h+var_2F0]; this
0x18000cd65  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18000cd6a  mov     rdi, [rbp+370h+var_3E8]
0x18000cd6e  lea     rcx, [rsp+470h+var_3F8]; this
0x18000cd73  mov     rdx, r15; unsigned __int16 *
0x18000cd76  movups  xmm10, xmmword ptr [rax]
0x18000cd7a  movsd   xmm11, qword ptr [rax+10h]
0x18000cd80  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000cd85  mov     rdx, [rax]
0x18000cd88  test    rdx, rdx
0x18000cd8b  jz      short loc_18000CD92
0x18000cd8d  mov     rdx, [rdx]
0x18000cd90  jmp     short loc_18000CD95
0x18000cd92  mov     rdx, r13
0x18000cd95  lea     rax, [rbp+370h+var_3B8]
0x18000cd99  movaps  [rbp+370h+var_350], xmm6
0x18000cd9d  mov     [rsp+470h+var_430], rax
0x18000cda2  mov     r9d, 6
0x18000cda8  lea     rax, [rbp+370h+var_350]
0x18000cdac  movsd   [rbp+370h+var_340], xmm7
0x18000cdb1  mov     [rsp+470h+var_438], rax
0x18000cdb6  mov     r8, rdi
0x18000cdb9  lea     rax, [rbp+370h+var_330]
0x18000cdbd  mov     dword ptr [rsp+470h+var_440], 3
0x18000cdc5  mov     [rsp+470h+var_448], rax
0x18000cdca  mov     rcx, rbx
0x18000cdcd  lea     rax, [rbp+370h+var_310]
0x18000cdd1  movaps  [rbp+370h+var_330], xmm8
0x18000cdd6  mov     [rsp+470h+var_450], rax
0x18000cddb  mov     rax, r12
0x18000cdde  movsd   [rbp+370h+var_320], xmm9
0x18000cde4  movaps  [rbp+370h+var_310], xmm10
0x18000cde9  movsd   [rbp+370h+var_300], xmm11
0x18000cdef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdf4  mov     rbx, [rsp+470h+var_3F8]
0x18000cdf9  mov     edi, eax
0x18000cdfb  test    rbx, rbx
0x18000cdfe  jz      short loc_18000CE4D
0x18000ce00  or      eax, 0FFFFFFFFh
0x18000ce03  lock xadd [rbx+10h], eax
0x18000ce08  cmp     eax, 1
0x18000ce0b  jnz     short loc_18000CE48
0x18000ce0d  test    rbx, rbx
0x18000ce10  jz      short loc_18000CE48
0x18000ce12  mov     rcx, [rbx]; bstrString
0x18000ce15  test    rcx, rcx
0x18000ce18  jz      short loc_18000CE29
0x18000ce1a  call    cs:__imp_SysFreeString
0x18000ce21  nop     dword ptr [rax+rax+00h]
0x18000ce26  mov     [rbx], r13
0x18000ce29  mov     rcx, [rbx+8]; void *
0x18000ce2d  test    rcx, rcx
0x18000ce30  jz      short loc_18000CE3B
0x18000ce32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ce37  mov     [rbx+8], r13
0x18000ce3b  mov     edx, 18h; struct std::nothrow_t *
0x18000ce40  mov     rcx, rbx; void *
0x18000ce43  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ce48  mov     [rsp+470h+var_3F8], r13
0x18000ce4d  lea     rcx, [rbp+370h+var_2F0]; this
0x18000ce54  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000ce59  lea     rcx, [rbp+370h+var_3A0]; this
  ... truncated ...
```
