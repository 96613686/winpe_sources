# ScheduleAlertTask(ushort const *,DMAlertType)

- ea: `0x14000d0fc`
- end: `0x14000d704`
- name: `?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z`
- size: `1544`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140010000`

## callees

- `0x140002930`
- `0x140002954`
- `0x1400046a4`
- `0x140004c34`
- `0x140007368`
- `0x140008b48`
- `0x140008dc8`
- `0x140008e48`
- `0x140008ea8`
- `0x1400095cc`
- `0x140009cd8`
- `0x14000a0b8`
- `0x14000d0fc`
- `0x14000fc70`
- `0x1400177b0`
- `0x140017cbc`
- `0x140017dec`
- `0x140017e7c`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000d3ab`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d578`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d3ab`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d578`
- `OLEAUT32!__imp_VariantInit` at `0x14000d491`
- `OLEAUT32!__imp_VariantInit` at `0x14000d4a4`
- `OLEAUT32!__imp_VariantInit` at `0x14000d491`
- `OLEAUT32!__imp_VariantInit` at `0x14000d4a4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000d647`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000d666`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000d647`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000d666`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000d63a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000d659`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000d63a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000d659`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000d628`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000d628`
- `DMCmnUtils!DmDisableTask` at `0x14000d5d9`
- `DMCmnUtils!DmDisableTask` at `0x14000d5d9`
- `dmEnrollEngine!GetEnrollmentSID` at `0x14000d266`
- `dmEnrollEngine!GetEnrollmentSID` at `0x14000d266`
- `RPCRT4!UuidFromStringW` at `0x14000d230`
- `RPCRT4!UuidFromStringW` at `0x14000d230`

## string_xrefs

- `0x14000d20e`: `/s "%s" /c /OsEditionUpgradeAlert /SID "%s"`
- `0x14000d1f7`: `/s "%s" /c /Win10SModeAlert /SID "%s"`
- `0x14000d215`: `OS Edition Upgrade event listener created by enrollment client`
- `0x14000d1fe`: `Win10 S Mode event listener created by enrollment client`
- `0x14000d1dd`: `Wsc Startup event listener created by enrollment client`
- `0x14000d5c8`: `Wsc Startup event listener created by enrollment client`
- `0x14000d30e`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
__int64 __fastcall ScheduleAlertTask(unsigned __int16 *a1, int a2)
{
  int Task; // edi
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
  int v16; // eax
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
  int v32; // eax
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
  int v45[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v46; // [rsp+98h] [rbp-70h] BYREF
  SAFEARRAY *v47; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-60h] BYREF
  int v49[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v50[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-48h] BYREF
  int v52[2]; // [rsp+C8h] [rbp-40h] BYREF
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
  VARIANTARG v64; // [rsp+188h] [rbp+80h] BYREF
  UUID Uuid; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v66[264]; // [rsp+1B8h] [rbp+B0h] BYREF

  *(_QWORD *)v52 = 0;
  *(_QWORD *)v50 = 0;
  *(_QWORD *)v45 = 0;
  *(_QWORD *)v49 = 0;
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
        Task = v9 | 0x80010000;
        CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v42);
        goto LABEL_54;
      }
      *(UUID *)&Block.vt = Uuid;
      EnrollmentSID = GetEnrollmentSID(&Block, &v42);
      Task = EnrollmentSID;
      if ( EnrollmentSID < 0 )
      {
        if ( EnrollmentSID != -2147024894 )
        {
LABEL_15:
          CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v42);
LABEL_16:
          if ( Task < 0 )
            goto LABEL_55;
          Task = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v44, v6);
          if ( Task < 0 )
            goto LABEL_55;
          Task = CreateTask(
                   v52,
                   (__int64)v50,
                   v45,
                   v49,
                   a1,
                   L"%windir%\\system32\\deviceenroller.exe",
                   v66,
                   L"S-1-5-18",
                   0,
                   1,
                   0,
                   0,
                   0);
          if ( Task < 0 )
            goto LABEL_55;
          Task = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v45 + 120LL))(*(_QWORD *)v45, &v46);
          if ( Task < 0 )
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
          Task = v16;
          if ( *(_QWORD *)&Block.vt
            && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&Block.vt + 16LL), 0xFFFFFFFF) == 1
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
          if ( Task < 0 )
            goto LABEL_55;
          Task = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 144LL))(v46, 1);
          if ( Task < 0 )
            goto LABEL_55;
          Task = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v49 + 208LL))(*(_QWORD *)v49, 0xFFFFFFFFLL);
          if ( Task < 0 )
            goto LABEL_55;
          Task = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v45 + 72LL))(*(_QWORD *)v45, &v48);
          if ( Task < 0 )
            goto LABEL_55;
          for ( i = 0; (unsigned __int64)(int)i < 8; ++i )
          {
            Task = ATL::CComSafeArray<unsigned char,17>::SetAt(&v47, i, (char *)&v43 + (int)i);
            if ( Task < 0 )
              goto LABEL_55;
          }
          Task = AddTaskWNFTrigger(v48, &v47);
          if ( Task < 0 )
            goto LABEL_55;
          v20 = *(_QWORD *)v50;
          v21 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v50 + 136LL);
          VariantInit(&pvarg);
          v22 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&Block);
          v24 = *(_OWORD *)&Block.vt;
          v25 = Block.pRecInfo;
          v26 = _variant_t::_variant_t((_variant_t *)&v64, L"S-1-5-18");
          v27 = *(_QWORD *)v45;
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
          Task = v32;
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
          ATL::CComVariant::~CComVariant(&v64);
          ATL::CComVariant::~CComVariant(&Block);
          ATL::CComVariant::~CComVariant(&pvarg);
          if ( a2 == 2 )
            DmDisableTask(
              L"\\Microsoft\\Windows\\EnterpriseMgmt",
              a1,
              L"Wsc Startup event listener created by enrollment client");
LABEL_54:
          if ( Task >= 0 )
            goto LABEL_61;
          goto LABEL_55;
        }
        v11 = L"S-1-1-0";
      }
      else
      {
        v11 = v42;
      }
      Task = StringCchPrintfW(v66, 0x104u, v8, a1, v11);
      goto LABEL_15;
    case 1:
      v7 = (void *)WNF_CI_SMODE_CHANGE;
      v8 = L"/s \"%s\" /c /Win10SModeAlert /SID \"%s\"";
      v5 = L"Win10 S Mode event listener created by enrollment client";
      goto LABEL_8;
    case 2:
      v43 = (void *)WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION;
      v5 = L"Wsc Startup event listener created by enrollment client";
      Task = StringCchPrintfW(v66, 0x104u, L"/s \"%s\" /c /WscStartupAlert", a1);
      goto LABEL_16;
  }
  Task = -2147418113;
LABEL_55:
  if ( a2 )
  {
    v35 = a2 - 1;
    if ( v35 )
    {
      if ( v35 == 1 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogWscStartupAlertScheduleSetupFail(Logger, Task);
      }
    }
    else
    {
      v37 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogWin10SModeScheduleSetupFail(v37, Task);
    }
  }
  else
  {
    v38 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogOsEditionUpgradeScheduleSetupFail(v38, Task);
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
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v49);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v45);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v50);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v52);
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x14000d0fc  mov     rax, rsp
0x14000d0ff  push    rbp
0x14000d100  push    rbx
0x14000d101  push    rsi
0x14000d102  push    rdi
0x14000d103  push    r12
0x14000d105  push    r13
0x14000d107  push    r14
0x14000d109  push    r15
0x14000d10b  lea     rbp, [rax-378h]
0x14000d112  sub     rsp, 438h
0x14000d119  movaps  xmmword ptr [rax-58h], xmm6
0x14000d11d  movaps  xmmword ptr [rax-68h], xmm7
0x14000d121  movaps  xmmword ptr [rax-78h], xmm8
0x14000d126  movaps  xmmword ptr [rax-88h], xmm9
0x14000d12e  movaps  xmmword ptr [rax-98h], xmm10
0x14000d136  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000d13e  mov     rax, cs:__security_cookie
0x14000d145  xor     rax, rsp
0x14000d148  mov     [rbp+370h+var_B0], rax
0x14000d14f  xor     r13d, r13d
0x14000d152  mov     esi, edx
0x14000d154  mov     r14, rcx
0x14000d157  mov     qword ptr [rbp+370h+var_3B0], r13
0x14000d15b  lea     rcx, [rbp+370h+var_3D8]
0x14000d15f  mov     qword ptr [rbp+370h+var_3C0], r13
0x14000d163  mov     qword ptr [rbp+370h+var_3E8], r13
0x14000d167  lea     edx, [r13+8]
0x14000d16b  mov     qword ptr [rbp+370h+var_3C8], r13
0x14000d16f  mov     [rbp+370h+var_3B8], r13
0x14000d173  mov     [rbp+370h+var_3E0], r13
0x14000d177  mov     [rbp+370h+var_3D0], r13
0x14000d17b  mov     [rbp+370h+var_370], r13
0x14000d17f  mov     [rbp+370h+var_378], r13
0x14000d183  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x14000d188  xor     edx, edx
0x14000d18a  lea     rcx, [rbp+370h+psa]
0x14000d18e  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x14000d193  mov     [rbp+370h+var_3F0], r13d
0x14000d197  xorps   xmm0, xmm0
0x14000d19a  mov     ecx, esi
0x14000d19c  movups  xmmword ptr [rbp+370h+Uuid.Data1], xmm0
0x14000d1a3  test    esi, esi
0x14000d1a5  jz      short loc_14000D207
0x14000d1a7  sub     ecx, 1
0x14000d1aa  jz      short loc_14000D1F0
0x14000d1ac  cmp     ecx, 1
0x14000d1af  jz      short loc_14000D1BB
0x14000d1b1  mov     edi, 8000FFFFh
0x14000d1b6  jmp     loc_14000D5E3
0x14000d1bb  mov     rax, cs:WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION
0x14000d1c2  lea     r8, aSSCWscstartupa; "/s \"%s\" /c /WscStartupAlert"
0x14000d1c9  mov     r9, r14
0x14000d1cc  mov     [rsp+470h+var_3F8], rax
0x14000d1d1  mov     edx, 104h; unsigned __int64
0x14000d1d6  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x14000d1dd  lea     r15, aWscStartupEven; "Wsc Startup event listener created by e"...
0x14000d1e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d1e9  mov     edi, eax
0x14000d1eb  jmp     loc_14000D2AF
0x14000d1f0  mov     rax, cs:WNF_CI_SMODE_CHANGE
0x14000d1f7  lea     rbx, aSSCWin10smodea; "/s \"%s\" /c /Win10SModeAlert /SID \"%s"...
0x14000d1fe  lea     r15, aWin10SModeEven; "Win10 S Mode event listener created by "...
0x14000d205  jmp     short loc_14000D21C
0x14000d207  mov     rax, cs:WNF_OLIC_OS_EDITION_CHANGE
0x14000d20e  lea     rbx, aSSCOseditionup; "/s \"%s\" /c /OsEditionUpgradeAlert /SI"...
0x14000d215  lea     r15, aOsEditionUpgra; "OS Edition Upgrade event listener creat"...
0x14000d21c  lea     rdx, [rbp+370h+Uuid]; Uuid
0x14000d223  mov     [rsp+470h+var_3F8], rax
0x14000d228  mov     rcx, r14; StringUuid
0x14000d22b  mov     [rsp+470h+var_400], r13
0x14000d230  call    cs:__imp_UuidFromStringW
0x14000d236  mov     edi, eax
0x14000d238  test    eax, eax
0x14000d23a  jz      short loc_14000D251
0x14000d23c  or      edi, 80010000h
0x14000d242  lea     rcx, [rsp+470h+var_400]
0x14000d247  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x14000d24c  jmp     loc_14000D5DF
0x14000d251  movaps  xmm0, xmmword ptr [rbp+370h+Uuid.Data1]
0x14000d258  lea     rdx, [rsp+470h+var_400]
0x14000d25d  lea     rcx, [rbp+370h+Block]
0x14000d261  movdqa  xmmword ptr [rbp+370h+Block], xmm0
0x14000d266  call    cs:__imp_GetEnrollmentSID
0x14000d26c  mov     edi, eax
0x14000d26e  test    eax, eax
0x14000d270  js      short loc_14000D279
0x14000d272  mov     rax, [rsp+470h+var_400]
0x14000d277  jmp     short loc_14000D287
0x14000d279  cmp     eax, 80070002h
0x14000d27e  jnz     short loc_14000D2A5
0x14000d280  lea     rax, aS110; "S-1-1-0"
0x14000d287  mov     r9, r14
0x14000d28a  mov     [rsp+470h+var_450], rax
0x14000d28f  mov     r8, rbx; unsigned __int16 *
0x14000d292  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x14000d299  mov     edx, 104h; unsigned __int64
0x14000d29e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d2a3  mov     edi, eax
0x14000d2a5  lea     rcx, [rsp+470h+var_400]
0x14000d2aa  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x14000d2af  test    edi, edi
0x14000d2b1  js      loc_14000D5E3
0x14000d2b7  lea     rcx, [rbp+370h+var_3F0]; this
0x14000d2bb  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000d2c0  mov     edi, eax
0x14000d2c2  test    eax, eax
0x14000d2c4  js      loc_14000D5E3
0x14000d2ca  mov     [rsp+470h+Data], r13d; Data
0x14000d2cf  lea     rax, aS1518; "S-1-5-18"
0x14000d2d6  mov     [rsp+470h+var_418], r13d; int
0x14000d2db  lea     r9, [rbp+370h+var_3C8]; int
0x14000d2df  mov     [rsp+470h+var_420], r13d; int
0x14000d2e4  lea     r8, [rbp+370h+var_3E8]; int
0x14000d2e8  mov     [rsp+470h+var_428], 1; int
0x14000d2f0  lea     rdx, [rbp+370h+var_3C0]; int
0x14000d2f4  mov     [rsp+470h+var_430], r13d; int
0x14000d2f9  lea     rcx, [rbp+370h+var_3B0]; int
0x14000d2fd  mov     [rsp+470h+var_438], rax; unsigned __int16 *
0x14000d302  lea     rax, [rbp+370h+var_2C0]
0x14000d309  mov     [rsp+470h+var_440], rax; unsigned __int16 *
0x14000d30e  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x14000d315  mov     [rsp+470h+var_448], rax; unsigned __int16 *
0x14000d31a  mov     [rsp+470h+var_450], r14; unsigned __int16 *
0x14000d31f  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000d324  mov     edi, eax
0x14000d326  test    eax, eax
0x14000d328  js      loc_14000D5E3
0x14000d32e  mov     rcx, qword ptr [rbp+370h+var_3E8]
0x14000d332  lea     rdx, [rbp+370h+var_3E0]
0x14000d336  mov     rax, [rcx]
0x14000d339  mov     rax, [rax+78h]
0x14000d33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d342  mov     edi, eax
0x14000d344  test    eax, eax
0x14000d346  js      loc_14000D5E3
0x14000d34c  mov     rbx, [rbp+370h+var_3E0]
0x14000d350  lea     rdx, aLocalsystem; "LocalSystem"
0x14000d357  lea     rcx, [rbp+370h+Block]; this
0x14000d35b  mov     rax, [rbx]
0x14000d35e  mov     rdi, [rax+40h]
0x14000d362  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000d367  mov     rcx, [rax]
0x14000d36a  test    rcx, rcx
0x14000d36d  jz      short loc_14000D374
0x14000d36f  mov     rdx, [rcx]
0x14000d372  jmp     short loc_14000D377
0x14000d374  mov     rdx, r13
0x14000d377  mov     rcx, rbx
0x14000d37a  mov     rax, rdi
0x14000d37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d382  mov     rbx, [rbp+370h+Block]
0x14000d386  or      r12d, 0FFFFFFFFh
0x14000d38a  mov     edi, eax
0x14000d38c  test    rbx, rbx
0x14000d38f  jz      short loc_14000D3D3
0x14000d391  mov     eax, r12d
0x14000d394  lock xadd [rbx+10h], eax
0x14000d399  add     eax, r12d
0x14000d39c  jnz     short loc_14000D3D3
0x14000d39e  test    rbx, rbx
0x14000d3a1  jz      short loc_14000D3D3
0x14000d3a3  mov     rcx, [rbx]; bstrString
0x14000d3a6  test    rcx, rcx
0x14000d3a9  jz      short loc_14000D3B4
0x14000d3ab  call    cs:__imp_SysFreeString
0x14000d3b1  mov     [rbx], r13
0x14000d3b4  mov     rcx, [rbx+8]; Block
0x14000d3b8  test    rcx, rcx
0x14000d3bb  jz      short loc_14000D3C6
0x14000d3bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d3c2  mov     [rbx+8], r13
0x14000d3c6  mov     edx, 18h
0x14000d3cb  mov     rcx, rbx; Block
0x14000d3ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d3d3  test    edi, edi
0x14000d3d5  js      loc_14000D5E3
0x14000d3db  mov     rcx, [rbp+370h+var_3E0]
0x14000d3df  mov     edx, 1
0x14000d3e4  mov     rax, [rcx]
0x14000d3e7  mov     rax, [rax+90h]
0x14000d3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3f3  mov     edi, eax
0x14000d3f5  test    eax, eax
0x14000d3f7  js      loc_14000D5E3
0x14000d3fd  mov     rcx, qword ptr [rbp+370h+var_3C8]
0x14000d401  mov     edx, r12d
0x14000d404  mov     rax, [rcx]
0x14000d407  mov     rax, [rax+0D0h]
0x14000d40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d413  mov     edi, eax
0x14000d415  test    eax, eax
0x14000d417  js      loc_14000D5E3
0x14000d41d  mov     rcx, qword ptr [rbp+370h+var_3E8]
0x14000d421  lea     rdx, [rbp+370h+var_3D0]
0x14000d425  mov     rax, [rcx]
0x14000d428  mov     rax, [rax+48h]
0x14000d42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d431  mov     edi, eax
0x14000d433  test    eax, eax
0x14000d435  js      loc_14000D5E3
0x14000d43b  mov     ebx, r13d
0x14000d43e  movsxd  rax, ebx
0x14000d441  cmp     rax, 8
0x14000d445  jnb     short loc_14000D468
0x14000d447  lea     r8, [rsp+470h+var_3F8]
0x14000d44c  mov     edx, ebx
0x14000d44e  add     r8, rax
0x14000d451  lea     rcx, [rbp+370h+var_3D8]
0x14000d455  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x14000d45a  mov     edi, eax
0x14000d45c  test    eax, eax
0x14000d45e  js      loc_14000D5E3
0x14000d464  inc     ebx
0x14000d466  jmp     short loc_14000D43E
0x14000d468  mov     rcx, [rbp+370h+var_3D0]
0x14000d46c  lea     rdx, [rbp+370h+var_3D8]
0x14000d470  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x14000d475  mov     edi, eax
0x14000d477  test    eax, eax
0x14000d479  js      loc_14000D5E3
0x14000d47f  mov     rbx, qword ptr [rbp+370h+var_3C0]
0x14000d483  lea     rcx, [rbp+370h+pvarg]; pvarg
0x14000d487  mov     rax, [rbx]
0x14000d48a  mov     r12, [rax+88h]
0x14000d491  call    cs:__imp_VariantInit
0x14000d497  movups  xmm6, xmmword ptr [rbp+370h+pvarg]
0x14000d49b  lea     rcx, [rbp+370h+Block]; pvarg
0x14000d49f  movsd   xmm7, qword ptr [rbp+370h+pvarg+10h]
0x14000d4a4  call    cs:__imp_VariantInit
0x14000d4aa  movups  xmm8, xmmword ptr [rbp+370h+Block]
0x14000d4af  lea     rdx, aS1518; "S-1-5-18"
0x14000d4b6  movsd   xmm9, [rbp+370h+var_390]
0x14000d4bc  lea     rcx, [rbp+370h+var_2F0]; this
0x14000d4c3  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000d4c8  mov     rdi, qword ptr [rbp+370h+var_3E8]
0x14000d4cc  lea     rcx, [rsp+470h+var_3F8]; this
0x14000d4d1  mov     rdx, r15; unsigned __int16 *
0x14000d4d4  movups  xmm10, xmmword ptr [rax]
0x14000d4d8  movsd   xmm11, qword ptr [rax+10h]
0x14000d4de  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000d4e3  mov     rdx, [rax]
0x14000d4e6  test    rdx, rdx
0x14000d4e9  jz      short loc_14000D4F0
0x14000d4eb  mov     rdx, [rdx]
0x14000d4ee  jmp     short loc_14000D4F3
0x14000d4f0  mov     rdx, r13
0x14000d4f3  lea     rax, [rbp+370h+var_3B8]
0x14000d4f7  movaps  [rbp+370h+var_350], xmm6
0x14000d4fb  mov     qword ptr [rsp+470h+var_430], rax
0x14000d500  mov     r9d, 6
0x14000d506  lea     rax, [rbp+370h+var_350]
0x14000d50a  movsd   [rbp+370h+var_340], xmm7
0x14000d50f  mov     [rsp+470h+var_438], rax
0x14000d514  mov     r8, rdi
0x14000d517  lea     rax, [rbp+370h+var_330]
0x14000d51b  mov     dword ptr [rsp+470h+var_440], 3
0x14000d523  mov     [rsp+470h+var_448], rax
0x14000d528  mov     rcx, rbx
0x14000d52b  lea     rax, [rbp+370h+var_310]
0x14000d52f  movaps  [rbp+370h+var_330], xmm8
0x14000d534  mov     [rsp+470h+var_450], rax
0x14000d539  mov     rax, r12
0x14000d53c  movsd   [rbp+370h+var_320], xmm9
0x14000d542  movaps  [rbp+370h+var_310], xmm10
0x14000d547  movsd   [rbp+370h+var_300], xmm11
0x14000d54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d552  mov     rbx, [rsp+470h+var_3F8]
0x14000d557  mov     edi, eax
0x14000d559  test    rbx, rbx
0x14000d55c  jz      short loc_14000D5A5
0x14000d55e  or      eax, 0FFFFFFFFh
0x14000d561  lock xadd [rbx+10h], eax
0x14000d566  cmp     eax, 1
0x14000d569  jnz     short loc_14000D5A0
0x14000d56b  test    rbx, rbx
0x14000d56e  jz      short loc_14000D5A0
0x14000d570  mov     rcx, [rbx]; bstrString
0x14000d573  test    rcx, rcx
0x14000d576  jz      short loc_14000D581
0x14000d578  call    cs:__imp_SysFreeString
0x14000d57e  mov     [rbx], r13
0x14000d581  mov     rcx, [rbx+8]; Block
0x14000d585  test    rcx, rcx
0x14000d588  jz      short loc_14000D593
0x14000d58a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d58f  mov     [rbx+8], r13
0x14000d593  mov     edx, 18h
0x14000d598  mov     rcx, rbx; Block
0x14000d59b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d5a0  mov     [rsp+470h+var_3F8], r13
0x14000d5a5  lea     rcx, [rbp+370h+var_2F0]; pvarg
0x14000d5ac  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000d5b1  lea     rcx, [rbp+370h+Block]; pvarg
0x14000d5b5  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000d5ba  lea     rcx, [rbp+370h+pvarg]; pvarg
0x14000d5be  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000d5c3  cmp     esi, 2
0x14000d5c6  jnz     short loc_14000D5DF
0x14000d5c8  lea     r8, aWscStartupEven; "Wsc Startup event listener created by e"...
  ... truncated ...
```
