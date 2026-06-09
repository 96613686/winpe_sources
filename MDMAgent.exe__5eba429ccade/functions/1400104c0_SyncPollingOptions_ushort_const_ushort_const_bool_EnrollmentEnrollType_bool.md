# SyncPollingOptions(ushort const *,ushort const *,bool,EnrollmentEnrollType,bool)

- ea: `0x1400104c0`
- end: `0x140010a5f`
- name: `?SyncPollingOptions@@YAJPEBG0_NW4EnrollmentEnrollType@@1@Z`
- size: `1439`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140007f34`

## callees

- `0x140002930`
- `0x140004b0c`
- `0x140006984`
- `0x140007724`
- `0x140007b34`
- `0x140008bf4`
- `0x1400090d4`
- `0x140009bc0`
- `0x14000b5a0`
- `0x14000b894`
- `0x14000e530`
- `0x14000ee6c`
- `0x14000ff08`
- `0x1400104c0`
- `0x140011aa8`
- `0x1400177b0`
- `0x140017808`
- `0x140017880`
- `0x1400178e8`
- `0x140017978`
- `0x1400179f0`
- `0x140017a80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400109aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400109aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400109e7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400109e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001091f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001091f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001065a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001065a`

## string_xrefs

- `0x14001061b`: `Schedule #1 created by enrollment client`
- `0x1400106f5`: `Schedule #2 created by enrollment client`
- `0x1400107ae`: `Schedule #3 created by enrollment client`
- `0x140010837`: `Maintenance Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall SyncPollingOptions(unsigned __int16 *a1, __int64 a2, __int64 a3, int a4)
{
  int v5; // esi
  __int64 v6; // rdx
  __int64 v7; // r8
  int i; // r14d
  unsigned int PollValueFromRegistry; // ebx
  const unsigned __int16 * near **v11; // r9
  __int64 j; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rbx
  unsigned int v16; // esi
  CEnrollmentLogger *v17; // rax
  CEnrollmentLogger *Logger; // rax
  unsigned int v19; // r12d
  __int64 v20; // r15
  __int64 v21; // r14
  CEnrollmentLogger *v22; // rax
  unsigned int v23; // ecx
  unsigned int v24; // r13d
  unsigned int v25; // r12d
  __int64 v26; // rbx
  __int64 v27; // rsi
  CEnrollmentLogger *v28; // rax
  CEnrollmentLogger *v29; // rax
  CEnrollmentLogger *v30; // rax
  int v31; // r8d
  int DeviceEnrollerKey; // eax
  LSTATUS ValueW; // eax
  CEnrollmentLogger *v34; // rax
  int lpData; // [rsp+20h] [rbp-91h]
  int pcbData; // [rsp+30h] [rbp-81h]
  int pcbDataa; // [rsp+30h] [rbp-81h]
  int pcbDatab; // [rsp+30h] [rbp-81h]
  int pcbDatac; // [rsp+30h] [rbp-81h]
  int v40; // [rsp+38h] [rbp-79h]
  int v41; // [rsp+38h] [rbp-79h]
  int v42; // [rsp+38h] [rbp-79h]
  int v43; // [rsp+38h] [rbp-79h]
  int Data; // [rsp+50h] [rbp-61h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-59h] BYREF
  _BYTE v46[8]; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v47; // [rsp+68h] [rbp-49h] BYREF
  unsigned int v48; // [rsp+6Ch] [rbp-45h] BYREF
  int v49; // [rsp+70h] [rbp-41h]
  DWORD v50; // [rsp+74h] [rbp-3Dh] BYREF
  __int64 v51; // [rsp+78h] [rbp-39h]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-31h] BYREF
  __int128 pvData; // [rsp+90h] [rbp-21h] BYREF
  unsigned int v54[4]; // [rsp+A0h] [rbp-11h] BYREF
  unsigned int v55[4]; // [rsp+B0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v49 = a4;
  v51 = a2;
  *(_OWORD *)v54 = 0;
  *(_OWORD *)v55 = 0;
  Data = 0;
  v47 = 0;
  v48 = 0;
  v5 = 0;
  hkey = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v46, "SyncPollingOptions");
  for ( i = 0; i < 8; ++i )
  {
    PollValueFromRegistry = GetPollValueFromRegistry(a1, (LPCWSTR)(&g_RegistryKeyNames)[i], &v54[i]);
    Data = PollValueFromRegistry;
    if ( (int)(PollValueFromRegistry + 0x80000000) >= 0 && PollValueFromRegistry != -2147024894 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return PollValueFromRegistry;
    }
    if ( PollValueFromRegistry != -2147024894 )
      v5 = 1;
  }
  if ( !v5 )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 1;
  }
  ClearSchedulesAfterInfinite(v54, v6, v7, &g_RegistryKeyNames);
  for ( j = 0; j != 8; ++j )
  {
    SetPollValueToRegistry(a1, (LPCWSTR)v11[j], v54[j]);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v14, v13, (&g_RegistryKeyNames)[j], v54[j]);
    v11 = &g_RegistryKeyNames;
  }
  v15 = v54[0];
  v16 = v54[1];
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #1 created by enrollment client",
           v54[1],
           v54[0],
           v54[0],
           0,
           pcbData,
           v40,
           1,
           0);
  if ( Data >= 0 )
  {
    Data = ULongLongToULong(v15 * (v16 + 1), &v47);
    if ( Data < 0
      || (v19 = v47,
          v20 = v54[2],
          v21 = v54[3],
          Data = ScheduleOneOmaDmSession(
                   a1,
                   L"Schedule #2 created by enrollment client",
                   v54[3],
                   v54[2],
                   v47,
                   0,
                   pcbDataa,
                   v41,
                   1,
                   0),
          Data < 0) )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(Logger, Data);
      PollValueFromRegistry = Data;
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
    else
    {
      Data = ULongLongToULong(v21 * v20, &v48);
      if ( Data >= 0 )
      {
        v23 = v48 + v19;
        if ( v48 + v19 < v48 )
        {
          v34 = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v34, -2147024362);
          PollValueFromRegistry = -2147024362;
          EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          return PollValueFromRegistry;
        }
        v24 = v55[0];
        v25 = v55[1];
        Data = ScheduleOneOmaDmSession(
                 a1,
                 L"Schedule #3 created by enrollment client",
                 v55[1],
                 v55[0],
                 v23,
                 0,
                 pcbDatab,
                 v42,
                 0,
                 0);
        if ( Data >= 0 )
        {
          if ( (v25 || !v24) && ((_DWORD)v21 || !(_DWORD)v20) && (v16 || !(_DWORD)v15) )
            Data = ScheduleOneOmaDmSession(
                     a1,
                     L"Maintenance Schedule created by enrollment client",
                     1u,
                     1u,
                     0,
                     1,
                     pcbDatac,
                     v43,
                     1,
                     0);
          v26 = (1LL << v49) & 0x9402021;
          v27 = v51;
          if ( v55[2] )
          {
            Data = ScheduleOneOmaDmSessionOnLogin(
                     a1,
                     (const unsigned __int16 *)(v51 & ((unsigned __int128)-(__int128)(unsigned int)v26 >> 64)),
                     0);
            if ( Data < 0 )
            {
              if ( !v26 || !v27 || (Data = ScheduleOneOmaDmSessionOnLogin(a1, 0, 0), Data < 0) )
              {
                v28 = CEnrollmentLogger::GetLogger();
                CEnrollmentLogger::LogDMPollLoginSetupFail(v28, Data);
              }
            }
          }
          if ( v55[3] )
          {
            Data = ScheduleOneOmaDmSessionOnLogin(
                     a1,
                     (const unsigned __int16 *)(v27 & ((unsigned __int128)-(__int128)(unsigned __int64)v26 >> 64)),
                     1);
            if ( Data >= 0 || v26 && v27 && (Data = ScheduleOneOmaDmSessionOnLogin(a1, 0, 1), Data >= 0) )
            {
              v30 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupSuccess(v30);
            }
            else
            {
              v29 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupFail(v29, Data);
            }
          }
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hkey,
            0);
          DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hkey, v31);
          PollValueFromRegistry = DeviceEnrollerKey;
          if ( DeviceEnrollerKey >= 0 )
          {
            pvData = 0;
            v50 = 16;
            ValueW = RegGetValueW(hkey, 0, L"FirstScheduleTimestamp", 8u, 0, &pvData, &v50);
            PollValueFromRegistry = ValueW;
            if ( ValueW > 0 )
              PollValueFromRegistry = (unsigned __int16)ValueW | 0x80070000;
            Data = PollValueFromRegistry;
            if ( (PollValueFromRegistry & 0x80000000) != 0 )
            {
              PollValueFromRegistry = RegSetValueExW(
                                        hkey,
                                        L"FirstScheduleTimestamp",
                                        0,
                                        3u,
                                        (const BYTE *)&SystemTime,
                                        0x10u);
              Data = PollValueFromRegistry;
            }
            EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC9F,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
              (const char *)(unsigned int)DeviceEnrollerKey,
              lpData);
            EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          }
          return PollValueFromRegistry;
        }
      }
      v22 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v22, Data);
      PollValueFromRegistry = Data;
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"ScheduleOneOmaDmSession", 4u, &Data, 4u);
    v17 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollScheduleSetupFail(v17, Data);
    PollValueFromRegistry = Data;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  return PollValueFromRegistry;
}

```

## disassembly

```asm
0x1400104c0  mov     [rsp-8+arg_10], rbx
0x1400104c5  push    rbp
0x1400104c6  push    rsi
0x1400104c7  push    rdi
0x1400104c8  push    r12
0x1400104ca  push    r13
0x1400104cc  push    r14
0x1400104ce  push    r15
0x1400104d0  lea     rbp, [rsp-1Fh]
0x1400104d5  sub     rsp, 0D0h
0x1400104dc  mov     rax, cs:__security_cookie
0x1400104e3  xor     rax, rsp
0x1400104e6  mov     [rbp+4Fh+var_40], rax
0x1400104ea  mov     [rbp+4Fh+var_90], r9d
0x1400104ee  mov     [rbp+4Fh+var_88], rdx
0x1400104f2  mov     rdi, rcx
0x1400104f5  xorps   xmm0, xmm0
0x1400104f8  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x1400104fc  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x140010500  xor     r13d, r13d
0x140010503  mov     [rbp+4Fh+Data], r13d
0x140010507  mov     [rbp+4Fh+var_98], r13d
0x14001050b  mov     [rbp+4Fh+var_94], r13d
0x14001050f  mov     esi, r13d
0x140010512  mov     [rbp+4Fh+hkey], r13
0x140010516  lea     rdx, aSyncpollingopt_0; "SyncPollingOptions"
0x14001051d  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010521  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x140010526  mov     r14d, r13d
0x140010529  mov     r12d, 80070002h
0x14001052f  lea     r15d, [r13+1]
0x140010533  lea     r9, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x14001053a  cmp     r14d, 8
0x14001053e  jge     short loc_140010591
0x140010540  movsxd  rdx, r14d
0x140010543  lea     r8, [rbp+4Fh+var_60]
0x140010547  lea     r8, [r8+rdx*4]; unsigned int *
0x14001054b  mov     rdx, [r9+rdx*8]; lpValue
0x14001054f  mov     rcx, rdi; unsigned __int16 *
0x140010552  call    ?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z; GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)
0x140010557  mov     ebx, eax
0x140010559  mov     [rbp+4Fh+Data], eax
0x14001055c  mov     ecx, 80000000h
0x140010561  add     eax, ecx
0x140010563  test    ecx, eax
0x140010565  jnz     short loc_14001056C
0x140010567  cmp     ebx, r12d
0x14001056a  jnz     short loc_140010578
0x14001056c  cmp     ebx, r12d
0x14001056f  cmovnz  esi, r15d
0x140010573  add     r14d, r15d
0x140010576  jmp     short loc_140010533
0x140010578  lea     rcx, [rbp+4Fh+var_A0]; this
0x14001057c  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010581  nop
0x140010582  lea     rcx, [rbp+4Fh+hkey]
0x140010586  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001058b  nop
0x14001058c  jmp     loc_140010A36
0x140010591  test    esi, esi
0x140010593  jnz     short loc_1400105B1
0x140010595  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010599  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x14001059e  nop
0x14001059f  lea     rcx, [rbp+4Fh+hkey]
0x1400105a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400105a8  nop
0x1400105a9  mov     eax, r15d
0x1400105ac  jmp     loc_140010A38
0x1400105b1  lea     rcx, [rbp+4Fh+var_60]
0x1400105b5  call    ClearSchedulesAfterInfinite
0x1400105ba  mov     rbx, r13
0x1400105bd  mov     r8d, [rbp+rbx*4+4Fh+var_60]; unsigned int
0x1400105c2  mov     rdx, [r9+rbx*8]; lpValueName
0x1400105c6  mov     rcx, rdi; unsigned __int16 *
0x1400105c9  call    ?SetPollValueToRegistry@@YAJPEBG0K@Z; SetPollValueToRegistry(ushort const *,ushort const *,ulong)
0x1400105ce  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x1400105d5  jz      short loc_1400105EC
0x1400105d7  mov     r9d, [rbp+rbx*4+4Fh+var_60]
0x1400105dc  lea     r8, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x1400105e3  mov     r8, [r8+rbx*8]
0x1400105e7  call    McTemplateU0zq_EventWriteTransfer
0x1400105ec  add     rbx, r15
0x1400105ef  cmp     rbx, 8
0x1400105f3  lea     r9, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x1400105fa  jnz     short loc_1400105BD
0x1400105fc  mov     [rsp+100h+var_B8], r13d; int
0x140010601  mov     [rsp+100h+var_C0], r15d; int
0x140010606  mov     [rsp+100h+cbData], r13d; int
0x14001060b  mov     ebx, [rbp+4Fh+var_60]
0x14001060e  mov     dword ptr [rsp+100h+lpData], ebx; unsigned int
0x140010612  mov     r9d, ebx; unsigned int
0x140010615  mov     esi, [rbp+4Fh+var_60+4]
0x140010618  mov     r8d, esi; unsigned int
0x14001061b  lea     rdx, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x140010622  mov     rcx, rdi; unsigned __int16 *
0x140010625  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x14001062a  mov     [rbp+4Fh+Data], eax
0x14001062d  test    eax, eax
0x14001062f  jns     short loc_14001068C
0x140010631  mov     r9d, 4; dwType
0x140010637  mov     [rsp+100h+cbData], r9d; cbData
0x14001063c  lea     rax, [rbp+4Fh+Data]
0x140010640  mov     [rsp+100h+lpData], rax; lpData
0x140010645  lea     r8, aScheduleoneoma; "ScheduleOneOmaDmSession"
0x14001064c  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x140010653  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001065a  call    cs:__imp_RegSetKeyValueW
0x140010660  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010665  mov     edx, [rbp+4Fh+Data]; int
0x140010668  mov     rcx, rax; this
0x14001066b  call    ?LogDMPollScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollScheduleSetupFail(long)
0x140010670  mov     ebx, [rbp+4Fh+Data]
0x140010673  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010677  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x14001067c  nop
0x14001067d  lea     rcx, [rbp+4Fh+hkey]
0x140010681  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010686  nop
0x140010687  jmp     loc_140010A36
0x14001068c  lea     ecx, [rsi+1]
0x14001068f  imul    rcx, rbx; unsigned __int64
0x140010693  lea     rdx, [rbp+4Fh+var_98]; unsigned int *
0x140010697  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14001069c  mov     [rbp+4Fh+Data], eax
0x14001069f  test    eax, eax
0x1400106a1  jns     short loc_1400106CF
0x1400106a3  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1400106a8  mov     edx, [rbp+4Fh+Data]; int
0x1400106ab  mov     rcx, rax; this
0x1400106ae  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x1400106b3  mov     ebx, [rbp+4Fh+Data]
0x1400106b6  lea     rcx, [rbp+4Fh+var_A0]; this
0x1400106ba  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1400106bf  nop
0x1400106c0  lea     rcx, [rbp+4Fh+hkey]
0x1400106c4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400106c9  nop
0x1400106ca  jmp     loc_140010A36
0x1400106cf  mov     [rsp+100h+var_B8], r13d; int
0x1400106d4  mov     [rsp+100h+var_C0], r15d; int
0x1400106d9  mov     [rsp+100h+cbData], r13d; int
0x1400106de  mov     r12d, [rbp+4Fh+var_98]
0x1400106e2  mov     dword ptr [rsp+100h+lpData], r12d; unsigned int
0x1400106e7  mov     r15d, [rbp+4Fh+var_60+8]
0x1400106eb  mov     r9d, r15d; unsigned int
0x1400106ee  mov     r14d, [rbp+4Fh+var_60+0Ch]
0x1400106f2  mov     r8d, r14d; unsigned int
0x1400106f5  lea     rdx, aSchedule2Creat; "Schedule #2 created by enrollment clien"...
0x1400106fc  mov     rcx, rdi; unsigned __int16 *
0x1400106ff  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x140010704  mov     [rbp+4Fh+Data], eax
0x140010707  test    eax, eax
0x140010709  jns     short loc_140010737
0x14001070b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010710  mov     edx, [rbp+4Fh+Data]; int
0x140010713  mov     rcx, rax; this
0x140010716  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x14001071b  mov     ebx, [rbp+4Fh+Data]
0x14001071e  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010722  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010727  nop
0x140010728  lea     rcx, [rbp+4Fh+hkey]
0x14001072c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010731  nop
0x140010732  jmp     loc_140010A36
0x140010737  mov     rcx, r15
0x14001073a  imul    rcx, r14; unsigned __int64
0x14001073e  lea     rdx, [rbp+4Fh+var_94]; unsigned int *
0x140010742  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140010747  mov     [rbp+4Fh+Data], eax
0x14001074a  test    eax, eax
0x14001074c  jns     short loc_14001077A
0x14001074e  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010753  mov     edx, [rbp+4Fh+Data]; int
0x140010756  mov     rcx, rax; this
0x140010759  call    ?LogDMPollSecondAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(long)
0x14001075e  mov     ebx, [rbp+4Fh+Data]
0x140010761  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010765  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x14001076a  nop
0x14001076b  lea     rcx, [rbp+4Fh+hkey]
0x14001076f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010774  nop
0x140010775  jmp     loc_140010A36
0x14001077a  mov     eax, [rbp+4Fh+var_94]
0x14001077d  lea     ecx, [rax+r12]
0x140010781  cmp     ecx, eax
0x140010783  jb      loc_140010A08
0x140010789  mov     [rbp+4Fh+Data], r13d
0x14001078d  mov     [rsp+100h+var_B8], r13d; int
0x140010792  mov     [rsp+100h+var_C0], r13d; int
0x140010797  mov     [rsp+100h+cbData], r13d; int
0x14001079c  mov     dword ptr [rsp+100h+lpData], ecx; unsigned int
0x1400107a0  mov     r13d, [rbp+4Fh+var_50]
0x1400107a4  mov     r9d, r13d; unsigned int
0x1400107a7  mov     r12d, [rbp+4Fh+var_50+4]
0x1400107ab  mov     r8d, r12d; unsigned int
0x1400107ae  lea     rdx, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x1400107b5  mov     rcx, rdi; unsigned __int16 *
0x1400107b8  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1400107bd  mov     [rbp+4Fh+Data], eax
0x1400107c0  test    eax, eax
0x1400107c2  jns     short loc_1400107F0
0x1400107c4  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1400107c9  mov     edx, [rbp+4Fh+Data]; int
0x1400107cc  mov     rcx, rax; this
0x1400107cf  call    ?LogDMPollSecondAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(long)
0x1400107d4  mov     ebx, [rbp+4Fh+Data]
0x1400107d7  lea     rcx, [rbp+4Fh+var_A0]; this
0x1400107db  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1400107e0  nop
0x1400107e1  lea     rcx, [rbp+4Fh+hkey]
0x1400107e5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400107ea  nop
0x1400107eb  jmp     loc_140010A36
0x1400107f0  test    r12d, r12d
0x1400107f3  jnz     short loc_1400107FF
0x1400107f5  xor     r12d, r12d
0x1400107f8  test    r13d, r13d
0x1400107fb  jnz     short loc_140010849
0x1400107fd  jmp     short loc_140010802
0x1400107ff  xor     r12d, r12d
0x140010802  test    r14d, r14d
0x140010805  jnz     short loc_14001080C
0x140010807  test    r15d, r15d
0x14001080a  jnz     short loc_140010849
0x14001080c  test    esi, esi
0x14001080e  jnz     short loc_140010814
0x140010810  test    ebx, ebx
0x140010812  jnz     short loc_140010849
0x140010814  mov     [rsp+100h+var_B8], r12d; int
0x140010819  mov     [rsp+100h+var_C0], 1; int
0x140010821  mov     [rsp+100h+cbData], 1; int
0x140010829  mov     dword ptr [rsp+100h+lpData], r12d; int
0x14001082e  mov     r9d, 1; unsigned int
0x140010834  mov     r8d, r9d; unsigned int
0x140010837  lea     rdx, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x14001083e  mov     rcx, rdi; unsigned __int16 *
0x140010841  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x140010846  mov     [rbp+4Fh+Data], eax
0x140010849  mov     ecx, [rbp+4Fh+var_90]
0x14001084c  mov     ebx, 1
0x140010851  shl     rbx, cl
0x140010854  and     ebx, 9402021h
0x14001085a  mov     rsi, [rbp+4Fh+var_88]
0x14001085e  cmp     [rbp+4Fh+var_50+8], r12d
0x140010862  jz      short loc_1400108AF
0x140010864  mov     eax, ebx
0x140010866  neg     rax
0x140010869  sbb     rdx, rdx
0x14001086c  and     rdx, rsi; unsigned __int16 *
0x14001086f  xor     r8d, r8d; int
0x140010872  mov     rcx, rdi; unsigned __int16 *
0x140010875  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x14001087a  mov     [rbp+4Fh+Data], eax
0x14001087d  test    eax, eax
0x14001087f  jns     short loc_1400108AF
0x140010881  test    rbx, rbx
0x140010884  jz      short loc_14001089F
0x140010886  test    rsi, rsi
0x140010889  jz      short loc_14001089F
0x14001088b  xor     r8d, r8d; int
0x14001088e  xor     edx, edx; unsigned __int16 *
0x140010890  mov     rcx, rdi; unsigned __int16 *
0x140010893  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x140010898  mov     [rbp+4Fh+Data], eax
0x14001089b  test    eax, eax
0x14001089d  jns     short loc_1400108AF
0x14001089f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1400108a4  mov     edx, [rbp+4Fh+Data]; int
0x1400108a7  mov     rcx, rax; this
0x1400108aa  call    ?LogDMPollLoginSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollLoginSetupFail(long)
0x1400108af  cmp     [rbp+4Fh+var_50+0Ch], r12d
0x1400108b3  jz      short loc_140010914
0x1400108b5  mov     rax, rbx
0x1400108b8  neg     rax
0x1400108bb  sbb     rdx, rdx
0x1400108be  and     rdx, rsi; unsigned __int16 *
0x1400108c1  mov     r8d, 1; int
0x1400108c7  mov     rcx, rdi; unsigned __int16 *
0x1400108ca  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x1400108cf  mov     [rbp+4Fh+Data], eax
0x1400108d2  test    eax, eax
0x1400108d4  jns     short loc_140010907
0x1400108d6  test    rbx, rbx
0x1400108d9  jz      short loc_1400108F5
0x1400108db  test    rsi, rsi
0x1400108de  jz      short loc_1400108F5
0x1400108e0  xor     edx, edx; unsigned __int16 *
0x1400108e2  lea     r8d, [rdx+1]; int
0x1400108e6  mov     rcx, rdi; unsigned __int16 *
0x1400108e9  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x1400108ee  mov     [rbp+4Fh+Data], eax
0x1400108f1  test    eax, eax
0x1400108f3  jns     short loc_140010907
0x1400108f5  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1400108fa  mov     edx, [rbp+4Fh+Data]; int
0x1400108fd  mov     rcx, rax; this
0x140010900  call    ?LogDMAllUsersPollOnFirstLoginSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupFail(long)
  ... truncated ...
```
