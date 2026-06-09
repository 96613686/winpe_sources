# ScheduleAlertTask(ushort const *,DMAlertType)

- ea: `0x14000d780`
- end: `0x14000ddd1`
- name: `?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z`
- size: `1617`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140010818`

## callees

- `0x1400029c0`
- `0x1400029e4`
- `0x14000476c`
- `0x140004cd0`
- `0x140007628`
- `0x140008f4c`
- `0x1400091e0`
- `0x140009268`
- `0x1400092d4`
- `0x1400099c8`
- `0x14000a134`
- `0x14000a51c`
- `0x14000d780`
- `0x140010468`
- `0x14001848c`
- `0x1400189b4`
- `0x140018aec`
- `0x140018b80`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000da3b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000dc1a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000da3b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000dc1a`
- `OLEAUT32!__imp_VariantInit` at `0x14000db27`
- `OLEAUT32!__imp_VariantInit` at `0x14000db40`
- `OLEAUT32!__imp_VariantInit` at `0x14000db27`
- `OLEAUT32!__imp_VariantInit` at `0x14000db40`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000dd01`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000dd2c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000dd01`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000dd2c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000dcee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000dd19`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000dcee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000dd19`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000dcd6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000dcd6`
- `DMCmnUtils!DmDisableTask` at `0x14000dc81`
- `DMCmnUtils!DmDisableTask` at `0x14000dc81`
- `dmEnrollEngine!GetEnrollmentSID` at `0x14000d8f0`
- `dmEnrollEngine!GetEnrollmentSID` at `0x14000d8f0`
- `RPCRT4!UuidFromStringW` at `0x14000d8b4`
- `RPCRT4!UuidFromStringW` at `0x14000d8b4`

## string_xrefs

- `0x14000d892`: `/s "%s" /c /OsEditionUpgradeAlert /SID "%s"`
- `0x14000d87b`: `/s "%s" /c /Win10SModeAlert /SID "%s"`
- `0x14000d899`: `OS Edition Upgrade event listener created by enrollment client`
- `0x14000d882`: `Win10 S Mode event listener created by enrollment client`
- `0x14000d861`: `Wsc Startup event listener created by enrollment client`
- `0x14000dc70`: `Wsc Startup event listener created by enrollment client`
- `0x14000d99e`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
__int64 __fastcall ScheduleAlertTask(unsigned __int16 *a1, int a2)
{
  signed int Task; // edi
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
                   (int)v52,
                   (int)v50,
                   (int)v45,
                   (int)v49,
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
0x14000d780  mov     rax, rsp
0x14000d783  push    rbp
0x14000d784  push    rbx
0x14000d785  push    rsi
0x14000d786  push    rdi
0x14000d787  push    r12
0x14000d789  push    r13
0x14000d78b  push    r14
0x14000d78d  push    r15
0x14000d78f  lea     rbp, [rax-378h]
0x14000d796  sub     rsp, 438h
0x14000d79d  movaps  xmmword ptr [rax-58h], xmm6
0x14000d7a1  movaps  xmmword ptr [rax-68h], xmm7
0x14000d7a5  movaps  xmmword ptr [rax-78h], xmm8
0x14000d7aa  movaps  xmmword ptr [rax-88h], xmm9
0x14000d7b2  movaps  xmmword ptr [rax-98h], xmm10
0x14000d7ba  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000d7c2  mov     rax, cs:__security_cookie
0x14000d7c9  xor     rax, rsp
0x14000d7cc  mov     [rbp+370h+var_B0], rax
0x14000d7d3  xor     r13d, r13d
0x14000d7d6  mov     esi, edx
0x14000d7d8  mov     r14, rcx
0x14000d7db  mov     qword ptr [rbp+370h+var_3B0], r13
0x14000d7df  lea     rcx, [rbp+370h+var_3D8]
0x14000d7e3  mov     qword ptr [rbp+370h+var_3C0], r13
0x14000d7e7  mov     qword ptr [rbp+370h+var_3E8], r13
0x14000d7eb  lea     edx, [r13+8]
0x14000d7ef  mov     qword ptr [rbp+370h+var_3C8], r13
0x14000d7f3  mov     [rbp+370h+var_3B8], r13
0x14000d7f7  mov     [rbp+370h+var_3E0], r13
0x14000d7fb  mov     [rbp+370h+var_3D0], r13
0x14000d7ff  mov     [rbp+370h+var_370], r13
0x14000d803  mov     [rbp+370h+var_378], r13
0x14000d807  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x14000d80c  xor     edx, edx
0x14000d80e  lea     rcx, [rbp+370h+psa]
0x14000d812  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x14000d817  mov     [rbp+370h+var_3F0], r13d
0x14000d81b  xorps   xmm0, xmm0
0x14000d81e  mov     ecx, esi
0x14000d820  movups  xmmword ptr [rbp+370h+Uuid.Data1], xmm0
0x14000d827  test    esi, esi
0x14000d829  jz      short loc_14000D88B
0x14000d82b  sub     ecx, 1
0x14000d82e  jz      short loc_14000D874
0x14000d830  cmp     ecx, 1
0x14000d833  jz      short loc_14000D83F
0x14000d835  mov     edi, 8000FFFFh
0x14000d83a  jmp     loc_14000DC91
0x14000d83f  mov     rax, cs:WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION
0x14000d846  lea     r8, aSSCWscstartupa; "/s \"%s\" /c /WscStartupAlert"
0x14000d84d  mov     r9, r14
0x14000d850  mov     [rsp+470h+var_3F8], rax
0x14000d855  mov     edx, 104h; unsigned __int64
0x14000d85a  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x14000d861  lea     r15, aWscStartupEven; "Wsc Startup event listener created by e"...
0x14000d868  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d86d  mov     edi, eax
0x14000d86f  jmp     loc_14000D93F
0x14000d874  mov     rax, cs:WNF_CI_SMODE_CHANGE
0x14000d87b  lea     rbx, aSSCWin10smodea; "/s \"%s\" /c /Win10SModeAlert /SID \"%s"...
0x14000d882  lea     r15, aWin10SModeEven; "Win10 S Mode event listener created by "...
0x14000d889  jmp     short loc_14000D8A0
0x14000d88b  mov     rax, cs:WNF_OLIC_OS_EDITION_CHANGE
0x14000d892  lea     rbx, aSSCOseditionup; "/s \"%s\" /c /OsEditionUpgradeAlert /SI"...
0x14000d899  lea     r15, aOsEditionUpgra; "OS Edition Upgrade event listener creat"...
0x14000d8a0  lea     rdx, [rbp+370h+Uuid]; Uuid
0x14000d8a7  mov     [rsp+470h+var_3F8], rax
0x14000d8ac  mov     rcx, r14; StringUuid
0x14000d8af  mov     [rsp+470h+var_400], r13
0x14000d8b4  call    cs:__imp_UuidFromStringW
0x14000d8bb  nop     dword ptr [rax+rax+00h]
0x14000d8c0  mov     edi, eax
0x14000d8c2  test    eax, eax
0x14000d8c4  jz      short loc_14000D8DB
0x14000d8c6  or      edi, 80010000h
0x14000d8cc  lea     rcx, [rsp+470h+var_400]
0x14000d8d1  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x14000d8d6  jmp     loc_14000DC8D
0x14000d8db  movaps  xmm0, xmmword ptr [rbp+370h+Uuid.Data1]
0x14000d8e2  lea     rdx, [rsp+470h+var_400]
0x14000d8e7  lea     rcx, [rbp+370h+Block]
0x14000d8eb  movdqa  xmmword ptr [rbp+370h+Block], xmm0
0x14000d8f0  call    cs:__imp_GetEnrollmentSID
0x14000d8f7  nop     dword ptr [rax+rax+00h]
0x14000d8fc  mov     edi, eax
0x14000d8fe  test    eax, eax
0x14000d900  js      short loc_14000D909
0x14000d902  mov     rax, [rsp+470h+var_400]
0x14000d907  jmp     short loc_14000D917
0x14000d909  cmp     eax, 80070002h
0x14000d90e  jnz     short loc_14000D935
0x14000d910  lea     rax, aS110; "S-1-1-0"
0x14000d917  mov     r9, r14
0x14000d91a  mov     [rsp+470h+var_450], rax
0x14000d91f  mov     r8, rbx; unsigned __int16 *
0x14000d922  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x14000d929  mov     edx, 104h; unsigned __int64
0x14000d92e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d933  mov     edi, eax
0x14000d935  lea     rcx, [rsp+470h+var_400]
0x14000d93a  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x14000d93f  test    edi, edi
0x14000d941  js      loc_14000DC91
0x14000d947  lea     rcx, [rbp+370h+var_3F0]; this
0x14000d94b  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000d950  mov     edi, eax
0x14000d952  test    eax, eax
0x14000d954  js      loc_14000DC91
0x14000d95a  mov     [rsp+470h+Data], r13d; Data
0x14000d95f  lea     rax, aS1518; "S-1-5-18"
0x14000d966  mov     [rsp+470h+var_418], r13d; int
0x14000d96b  lea     r9, [rbp+370h+var_3C8]; int
0x14000d96f  mov     [rsp+470h+var_420], r13d; int
0x14000d974  lea     r8, [rbp+370h+var_3E8]; int
0x14000d978  mov     [rsp+470h+var_428], 1; int
0x14000d980  lea     rdx, [rbp+370h+var_3C0]; int
0x14000d984  mov     [rsp+470h+var_430], r13d; int
0x14000d989  lea     rcx, [rbp+370h+var_3B0]; int
0x14000d98d  mov     [rsp+470h+var_438], rax; unsigned __int16 *
0x14000d992  lea     rax, [rbp+370h+var_2C0]
0x14000d999  mov     [rsp+470h+var_440], rax; unsigned __int16 *
0x14000d99e  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x14000d9a5  mov     [rsp+470h+var_448], rax; unsigned __int16 *
0x14000d9aa  mov     [rsp+470h+var_450], r14; unsigned __int16 *
0x14000d9af  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000d9b4  mov     edi, eax
0x14000d9b6  test    eax, eax
0x14000d9b8  js      loc_14000DC91
0x14000d9be  mov     rcx, qword ptr [rbp+370h+var_3E8]
0x14000d9c2  lea     rdx, [rbp+370h+var_3E0]
0x14000d9c6  mov     rax, [rcx]
0x14000d9c9  mov     rax, [rax+78h]
0x14000d9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9d2  mov     edi, eax
0x14000d9d4  test    eax, eax
0x14000d9d6  js      loc_14000DC91
0x14000d9dc  mov     rbx, [rbp+370h+var_3E0]
0x14000d9e0  lea     rdx, aLocalsystem; "LocalSystem"
0x14000d9e7  lea     rcx, [rbp+370h+Block]; this
0x14000d9eb  mov     rax, [rbx]
0x14000d9ee  mov     rdi, [rax+40h]
0x14000d9f2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000d9f7  mov     rcx, [rax]
0x14000d9fa  test    rcx, rcx
0x14000d9fd  jz      short loc_14000DA04
0x14000d9ff  mov     rdx, [rcx]
0x14000da02  jmp     short loc_14000DA07
0x14000da04  mov     rdx, r13
0x14000da07  mov     rcx, rbx
0x14000da0a  mov     rax, rdi
0x14000da0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da12  mov     rbx, [rbp+370h+Block]
0x14000da16  or      r12d, 0FFFFFFFFh
0x14000da1a  mov     edi, eax
0x14000da1c  test    rbx, rbx
0x14000da1f  jz      short loc_14000DA69
0x14000da21  mov     eax, r12d
0x14000da24  lock xadd [rbx+10h], eax
0x14000da29  add     eax, r12d
0x14000da2c  jnz     short loc_14000DA69
0x14000da2e  test    rbx, rbx
0x14000da31  jz      short loc_14000DA69
0x14000da33  mov     rcx, [rbx]; bstrString
0x14000da36  test    rcx, rcx
0x14000da39  jz      short loc_14000DA4A
0x14000da3b  call    cs:__imp_SysFreeString
0x14000da42  nop     dword ptr [rax+rax+00h]
0x14000da47  mov     [rbx], r13
0x14000da4a  mov     rcx, [rbx+8]; Block
0x14000da4e  test    rcx, rcx
0x14000da51  jz      short loc_14000DA5C
0x14000da53  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000da58  mov     [rbx+8], r13
0x14000da5c  mov     edx, 18h
0x14000da61  mov     rcx, rbx; Block
0x14000da64  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000da69  test    edi, edi
0x14000da6b  js      loc_14000DC91
0x14000da71  mov     rcx, [rbp+370h+var_3E0]
0x14000da75  mov     edx, 1
0x14000da7a  mov     rax, [rcx]
0x14000da7d  mov     rax, [rax+90h]
0x14000da84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da89  mov     edi, eax
0x14000da8b  test    eax, eax
0x14000da8d  js      loc_14000DC91
0x14000da93  mov     rcx, qword ptr [rbp+370h+var_3C8]
0x14000da97  mov     edx, r12d
0x14000da9a  mov     rax, [rcx]
0x14000da9d  mov     rax, [rax+0D0h]
0x14000daa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000daa9  mov     edi, eax
0x14000daab  test    eax, eax
0x14000daad  js      loc_14000DC91
0x14000dab3  mov     rcx, qword ptr [rbp+370h+var_3E8]
0x14000dab7  lea     rdx, [rbp+370h+var_3D0]
0x14000dabb  mov     rax, [rcx]
0x14000dabe  mov     rax, [rax+48h]
0x14000dac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dac7  mov     edi, eax
0x14000dac9  test    eax, eax
0x14000dacb  js      loc_14000DC91
0x14000dad1  mov     ebx, r13d
0x14000dad4  movsxd  rax, ebx
0x14000dad7  cmp     rax, 8
0x14000dadb  jnb     short loc_14000DAFE
0x14000dadd  lea     r8, [rsp+470h+var_3F8]
0x14000dae2  mov     edx, ebx
0x14000dae4  add     r8, rax
0x14000dae7  lea     rcx, [rbp+370h+var_3D8]
0x14000daeb  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x14000daf0  mov     edi, eax
0x14000daf2  test    eax, eax
0x14000daf4  js      loc_14000DC91
0x14000dafa  inc     ebx
0x14000dafc  jmp     short loc_14000DAD4
0x14000dafe  mov     rcx, [rbp+370h+var_3D0]
0x14000db02  lea     rdx, [rbp+370h+var_3D8]
0x14000db06  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x14000db0b  mov     edi, eax
0x14000db0d  test    eax, eax
0x14000db0f  js      loc_14000DC91
0x14000db15  mov     rbx, qword ptr [rbp+370h+var_3C0]
0x14000db19  lea     rcx, [rbp+370h+pvarg]; pvarg
0x14000db1d  mov     rax, [rbx]
0x14000db20  mov     r12, [rax+88h]
0x14000db27  call    cs:__imp_VariantInit
0x14000db2e  nop     dword ptr [rax+rax+00h]
0x14000db33  movups  xmm6, xmmword ptr [rbp+370h+pvarg]
0x14000db37  lea     rcx, [rbp+370h+Block]; pvarg
0x14000db3b  movsd   xmm7, qword ptr [rbp+370h+pvarg+10h]
0x14000db40  call    cs:__imp_VariantInit
0x14000db47  nop     dword ptr [rax+rax+00h]
0x14000db4c  movups  xmm8, xmmword ptr [rbp+370h+Block]
0x14000db51  lea     rdx, aS1518; "S-1-5-18"
0x14000db58  movsd   xmm9, [rbp+370h+var_390]
0x14000db5e  lea     rcx, [rbp+370h+var_2F0]; this
0x14000db65  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000db6a  mov     rdi, qword ptr [rbp+370h+var_3E8]
0x14000db6e  lea     rcx, [rsp+470h+var_3F8]; this
0x14000db73  mov     rdx, r15; unsigned __int16 *
0x14000db76  movups  xmm10, xmmword ptr [rax]
0x14000db7a  movsd   xmm11, qword ptr [rax+10h]
0x14000db80  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000db85  mov     rdx, [rax]
0x14000db88  test    rdx, rdx
0x14000db8b  jz      short loc_14000DB92
0x14000db8d  mov     rdx, [rdx]
0x14000db90  jmp     short loc_14000DB95
0x14000db92  mov     rdx, r13
0x14000db95  lea     rax, [rbp+370h+var_3B8]
0x14000db99  movaps  [rbp+370h+var_350], xmm6
0x14000db9d  mov     qword ptr [rsp+470h+var_430], rax
0x14000dba2  mov     r9d, 6
0x14000dba8  lea     rax, [rbp+370h+var_350]
0x14000dbac  movsd   [rbp+370h+var_340], xmm7
0x14000dbb1  mov     [rsp+470h+var_438], rax
0x14000dbb6  mov     r8, rdi
0x14000dbb9  lea     rax, [rbp+370h+var_330]
0x14000dbbd  mov     dword ptr [rsp+470h+var_440], 3
0x14000dbc5  mov     [rsp+470h+var_448], rax
0x14000dbca  mov     rcx, rbx
0x14000dbcd  lea     rax, [rbp+370h+var_310]
0x14000dbd1  movaps  [rbp+370h+var_330], xmm8
0x14000dbd6  mov     [rsp+470h+var_450], rax
0x14000dbdb  mov     rax, r12
0x14000dbde  movsd   [rbp+370h+var_320], xmm9
0x14000dbe4  movaps  [rbp+370h+var_310], xmm10
0x14000dbe9  movsd   [rbp+370h+var_300], xmm11
0x14000dbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbf4  mov     rbx, [rsp+470h+var_3F8]
0x14000dbf9  mov     edi, eax
0x14000dbfb  test    rbx, rbx
0x14000dbfe  jz      short loc_14000DC4D
0x14000dc00  or      eax, 0FFFFFFFFh
0x14000dc03  lock xadd [rbx+10h], eax
0x14000dc08  cmp     eax, 1
0x14000dc0b  jnz     short loc_14000DC48
0x14000dc0d  test    rbx, rbx
0x14000dc10  jz      short loc_14000DC48
0x14000dc12  mov     rcx, [rbx]; bstrString
0x14000dc15  test    rcx, rcx
0x14000dc18  jz      short loc_14000DC29
0x14000dc1a  call    cs:__imp_SysFreeString
0x14000dc21  nop     dword ptr [rax+rax+00h]
0x14000dc26  mov     [rbx], r13
0x14000dc29  mov     rcx, [rbx+8]; Block
0x14000dc2d  test    rcx, rcx
0x14000dc30  jz      short loc_14000DC3B
0x14000dc32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dc37  mov     [rbx+8], r13
0x14000dc3b  mov     edx, 18h
0x14000dc40  mov     rcx, rbx; Block
0x14000dc43  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dc48  mov     [rsp+470h+var_3F8], r13
0x14000dc4d  lea     rcx, [rbp+370h+var_2F0]; pvarg
0x14000dc54  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000dc59  lea     rcx, [rbp+370h+Block]; pvarg
  ... truncated ...
```
