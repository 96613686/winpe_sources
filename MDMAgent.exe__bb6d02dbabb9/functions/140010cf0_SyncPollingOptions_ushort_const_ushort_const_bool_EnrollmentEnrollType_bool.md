# SyncPollingOptions(ushort const *,ushort const *,bool,EnrollmentEnrollType,bool)

- ea: `0x140010cf0`
- end: `0x1400112a8`
- name: `?SyncPollingOptions@@YAJPEBG0_NW4EnrollmentEnrollType@@1@Z`
- size: `1464`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000829c`

## callees

- `0x1400029c0`
- `0x140004b94`
- `0x140006bf4`
- `0x1400079f8`
- `0x140007e3c`
- `0x140009004`
- `0x1400094bc`
- `0x140009ffc`
- `0x14000bac4`
- `0x14000bdd4`
- `0x14000ec7c`
- `0x14000f604`
- `0x140010718`
- `0x140010cf0`
- `0x1400122b4`
- `0x14001848c`
- `0x1400184e8`
- `0x140018560`
- `0x1400185c8`
- `0x14001865c`
- `0x1400186d4`
- `0x140018768`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400111e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400111e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011229`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011229`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140011155`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140011155`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140010e8a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140010e8a`

## string_xrefs

- `0x140010e4b`: `Schedule #1 created by enrollment client`
- `0x140010f2b`: `Schedule #2 created by enrollment client`
- `0x140010fe4`: `Schedule #3 created by enrollment client`
- `0x14001106d`: `Maintenance Schedule created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SyncPollingOptions(const unsigned __int16 *a1, __int64 a2, __int64 a3, int a4)
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
  int DeviceEnrollerKey; // eax
  LSTATUS ValueW; // eax
  CEnrollmentLogger *v33; // rax
  int lpData; // [rsp+20h] [rbp-91h]
  int pcbData; // [rsp+30h] [rbp-81h]
  int pcbDataa; // [rsp+30h] [rbp-81h]
  int pcbDatab; // [rsp+30h] [rbp-81h]
  int pcbDatac; // [rsp+30h] [rbp-81h]
  int v39; // [rsp+38h] [rbp-79h]
  int v40; // [rsp+38h] [rbp-79h]
  int v41; // [rsp+38h] [rbp-79h]
  int v42; // [rsp+38h] [rbp-79h]
  int Data; // [rsp+50h] [rbp-61h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-59h] BYREF
  _BYTE v45[8]; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v46; // [rsp+68h] [rbp-49h] BYREF
  unsigned int v47; // [rsp+6Ch] [rbp-45h] BYREF
  int v48; // [rsp+70h] [rbp-41h]
  DWORD v49; // [rsp+74h] [rbp-3Dh] BYREF
  __int64 v50; // [rsp+78h] [rbp-39h]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-31h] BYREF
  __int128 pvData; // [rsp+90h] [rbp-21h] BYREF
  unsigned int v53[4]; // [rsp+A0h] [rbp-11h] BYREF
  unsigned int v54[4]; // [rsp+B0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v48 = a4;
  v50 = a2;
  *(_OWORD *)v53 = 0;
  *(_OWORD *)v54 = 0;
  Data = 0;
  v46 = 0;
  v47 = 0;
  v5 = 0;
  hkey = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v45, "SyncPollingOptions");
  for ( i = 0; i < 8; ++i )
  {
    PollValueFromRegistry = GetPollValueFromRegistry(a1, (LPCWSTR)(&g_RegistryKeyNames)[i], &v53[i]);
    Data = PollValueFromRegistry;
    if ( (int)(PollValueFromRegistry + 0x80000000) >= 0 && PollValueFromRegistry != -2147024894 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v45);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return PollValueFromRegistry;
    }
    if ( PollValueFromRegistry != -2147024894 )
      v5 = 1;
  }
  if ( !v5 )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v45);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 1;
  }
  ClearSchedulesAfterInfinite(v53, v6, v7, &g_RegistryKeyNames);
  for ( j = 0; j != 8; ++j )
  {
    SetPollValueToRegistry(a1, (LPCWSTR)v11[j], v53[j]);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v14, v13, (&g_RegistryKeyNames)[j], v53[j]);
    v11 = &g_RegistryKeyNames;
  }
  v15 = v53[0];
  v16 = v53[1];
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #1 created by enrollment client",
           v53[1],
           v53[0],
           v53[0],
           0,
           pcbData,
           v39,
           1,
           0);
  if ( Data >= 0 )
  {
    Data = ULongLongToULong(v15 * (v16 + 1), &v46);
    if ( Data < 0
      || (v19 = v46,
          v20 = v53[2],
          v21 = v53[3],
          Data = ScheduleOneOmaDmSession(
                   a1,
                   L"Schedule #2 created by enrollment client",
                   v53[3],
                   v53[2],
                   v46,
                   0,
                   pcbDataa,
                   v40,
                   1,
                   0),
          Data < 0) )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(Logger, Data);
      PollValueFromRegistry = Data;
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v45);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
    else
    {
      Data = ULongLongToULong(v21 * v20, &v47);
      if ( Data >= 0 )
      {
        v23 = v47 + v19;
        if ( v47 + v19 < v47 )
        {
          v33 = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v33, -2147024362);
          PollValueFromRegistry = -2147024362;
          EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v45);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          return PollValueFromRegistry;
        }
        v24 = v54[0];
        v25 = v54[1];
        Data = ScheduleOneOmaDmSession(
                 a1,
                 L"Schedule #3 created by enrollment client",
                 v54[1],
                 v54[0],
                 v23,
                 0,
                 pcbDatab,
                 v41,
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
                     v42,
                     1,
                     0);
          v26 = (1LL << v48) & 0x9402021;
          v27 = v50;
          if ( v54[2] )
          {
            Data = ScheduleOneOmaDmSessionOnLogin(
                     a1,
                     (const unsigned __int16 *)(v50 & ((unsigned __int128)-(__int128)(unsigned int)v26 >> 64)),
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
          if ( v54[3] )
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
          DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hkey);
          PollValueFromRegistry = DeviceEnrollerKey;
          if ( DeviceEnrollerKey >= 0 )
          {
            pvData = 0;
            v49 = 16;
            ValueW = RegGetValueW(hkey, 0, L"FirstScheduleTimestamp", 8u, 0, &pvData, &v49);
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
            EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v45);
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
            EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v45);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          }
          return PollValueFromRegistry;
        }
      }
      v22 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v22, Data);
      PollValueFromRegistry = Data;
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v45);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"ScheduleOneOmaDmSession", 4u, &Data, 4u);
    v17 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollScheduleSetupFail(v17, Data);
    PollValueFromRegistry = Data;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v45);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  return PollValueFromRegistry;
}

```

## disassembly

```asm
0x140010cf0  mov     [rsp-8+arg_10], rbx
0x140010cf5  push    rbp
0x140010cf6  push    rsi
0x140010cf7  push    rdi
0x140010cf8  push    r12
0x140010cfa  push    r13
0x140010cfc  push    r14
0x140010cfe  push    r15
0x140010d00  lea     rbp, [rsp-1Fh]
0x140010d05  sub     rsp, 0D0h
0x140010d0c  mov     rax, cs:__security_cookie
0x140010d13  xor     rax, rsp
0x140010d16  mov     [rbp+4Fh+var_40], rax
0x140010d1a  mov     [rbp+4Fh+var_90], r9d
0x140010d1e  mov     [rbp+4Fh+var_88], rdx
0x140010d22  mov     rdi, rcx
0x140010d25  xorps   xmm0, xmm0
0x140010d28  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x140010d2c  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x140010d30  xor     r13d, r13d
0x140010d33  mov     [rbp+4Fh+Data], r13d
0x140010d37  mov     [rbp+4Fh+var_98], r13d
0x140010d3b  mov     [rbp+4Fh+var_94], r13d
0x140010d3f  mov     esi, r13d
0x140010d42  mov     [rbp+4Fh+hkey], r13
0x140010d46  lea     rdx, aSyncpollingopt_0; "SyncPollingOptions"
0x140010d4d  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010d51  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x140010d56  mov     r14d, r13d
0x140010d59  mov     r12d, 80070002h
0x140010d5f  lea     r15d, [r13+1]
0x140010d63  lea     r9, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x140010d6a  cmp     r14d, 8
0x140010d6e  jge     short loc_140010DC1
0x140010d70  movsxd  rdx, r14d
0x140010d73  lea     r8, [rbp+4Fh+var_60]
0x140010d77  lea     r8, [r8+rdx*4]; unsigned int *
0x140010d7b  mov     rdx, [r9+rdx*8]; lpValue
0x140010d7f  mov     rcx, rdi; unsigned __int16 *
0x140010d82  call    ?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z; GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)
0x140010d87  mov     ebx, eax
0x140010d89  mov     [rbp+4Fh+Data], eax
0x140010d8c  mov     ecx, 80000000h
0x140010d91  add     eax, ecx
0x140010d93  test    ecx, eax
0x140010d95  jnz     short loc_140010D9C
0x140010d97  cmp     ebx, r12d
0x140010d9a  jnz     short loc_140010DA8
0x140010d9c  cmp     ebx, r12d
0x140010d9f  cmovnz  esi, r15d
0x140010da3  add     r14d, r15d
0x140010da6  jmp     short loc_140010D63
0x140010da8  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010dac  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010db1  nop
0x140010db2  lea     rcx, [rbp+4Fh+hkey]
0x140010db6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010dbb  nop
0x140010dbc  jmp     loc_14001127E
0x140010dc1  test    esi, esi
0x140010dc3  jnz     short loc_140010DE1
0x140010dc5  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010dc9  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010dce  nop
0x140010dcf  lea     rcx, [rbp+4Fh+hkey]
0x140010dd3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010dd8  nop
0x140010dd9  mov     eax, r15d
0x140010ddc  jmp     loc_140011280
0x140010de1  lea     rcx, [rbp+4Fh+var_60]
0x140010de5  call    ClearSchedulesAfterInfinite
0x140010dea  mov     rbx, r13
0x140010ded  mov     r8d, [rbp+rbx*4+4Fh+var_60]; unsigned int
0x140010df2  mov     rdx, [r9+rbx*8]; lpValueName
0x140010df6  mov     rcx, rdi; unsigned __int16 *
0x140010df9  call    ?SetPollValueToRegistry@@YAJPEBG0K@Z; SetPollValueToRegistry(ushort const *,ushort const *,ulong)
0x140010dfe  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x140010e05  jz      short loc_140010E1C
0x140010e07  mov     r9d, [rbp+rbx*4+4Fh+var_60]
0x140010e0c  lea     r8, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x140010e13  mov     r8, [r8+rbx*8]
0x140010e17  call    McTemplateU0zq_EventWriteTransfer
0x140010e1c  add     rbx, r15
0x140010e1f  cmp     rbx, 8
0x140010e23  lea     r9, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x140010e2a  jnz     short loc_140010DED
0x140010e2c  mov     [rsp+100h+var_B8], r13d; int
0x140010e31  mov     [rsp+100h+var_C0], r15d; int
0x140010e36  mov     [rsp+100h+cbData], r13d; int
0x140010e3b  mov     ebx, [rbp+4Fh+var_60]
0x140010e3e  mov     dword ptr [rsp+100h+lpData], ebx; unsigned int
0x140010e42  mov     r9d, ebx; unsigned int
0x140010e45  mov     esi, [rbp+4Fh+var_60+4]
0x140010e48  mov     r8d, esi; unsigned int
0x140010e4b  lea     rdx, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x140010e52  mov     rcx, rdi; unsigned __int16 *
0x140010e55  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x140010e5a  mov     [rbp+4Fh+Data], eax
0x140010e5d  test    eax, eax
0x140010e5f  jns     short loc_140010EC2
0x140010e61  mov     r9d, 4; dwType
0x140010e67  mov     [rsp+100h+cbData], r9d; cbData
0x140010e6c  lea     rax, [rbp+4Fh+Data]
0x140010e70  mov     [rsp+100h+lpData], rax; lpData
0x140010e75  lea     r8, aScheduleoneoma; "ScheduleOneOmaDmSession"
0x140010e7c  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x140010e83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010e8a  call    cs:__imp_RegSetKeyValueW
0x140010e91  nop     dword ptr [rax+rax+00h]
0x140010e96  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010e9b  mov     edx, [rbp+4Fh+Data]; int
0x140010e9e  mov     rcx, rax; this
0x140010ea1  call    ?LogDMPollScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollScheduleSetupFail(long)
0x140010ea6  mov     ebx, [rbp+4Fh+Data]
0x140010ea9  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010ead  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010eb2  nop
0x140010eb3  lea     rcx, [rbp+4Fh+hkey]
0x140010eb7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010ebc  nop
0x140010ebd  jmp     loc_14001127E
0x140010ec2  lea     ecx, [rsi+1]
0x140010ec5  imul    rcx, rbx; unsigned __int64
0x140010ec9  lea     rdx, [rbp+4Fh+var_98]; unsigned int *
0x140010ecd  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140010ed2  mov     [rbp+4Fh+Data], eax
0x140010ed5  test    eax, eax
0x140010ed7  jns     short loc_140010F05
0x140010ed9  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010ede  mov     edx, [rbp+4Fh+Data]; int
0x140010ee1  mov     rcx, rax; this
0x140010ee4  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x140010ee9  mov     ebx, [rbp+4Fh+Data]
0x140010eec  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010ef0  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010ef5  nop
0x140010ef6  lea     rcx, [rbp+4Fh+hkey]
0x140010efa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010eff  nop
0x140010f00  jmp     loc_14001127E
0x140010f05  mov     [rsp+100h+var_B8], r13d; int
0x140010f0a  mov     [rsp+100h+var_C0], r15d; int
0x140010f0f  mov     [rsp+100h+cbData], r13d; int
0x140010f14  mov     r12d, [rbp+4Fh+var_98]
0x140010f18  mov     dword ptr [rsp+100h+lpData], r12d; unsigned int
0x140010f1d  mov     r15d, [rbp+4Fh+var_60+8]
0x140010f21  mov     r9d, r15d; unsigned int
0x140010f24  mov     r14d, [rbp+4Fh+var_60+0Ch]
0x140010f28  mov     r8d, r14d; unsigned int
0x140010f2b  lea     rdx, aSchedule2Creat; "Schedule #2 created by enrollment clien"...
0x140010f32  mov     rcx, rdi; unsigned __int16 *
0x140010f35  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x140010f3a  mov     [rbp+4Fh+Data], eax
0x140010f3d  test    eax, eax
0x140010f3f  jns     short loc_140010F6D
0x140010f41  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010f46  mov     edx, [rbp+4Fh+Data]; int
0x140010f49  mov     rcx, rax; this
0x140010f4c  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x140010f51  mov     ebx, [rbp+4Fh+Data]
0x140010f54  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010f58  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010f5d  nop
0x140010f5e  lea     rcx, [rbp+4Fh+hkey]
0x140010f62  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010f67  nop
0x140010f68  jmp     loc_14001127E
0x140010f6d  mov     rcx, r15
0x140010f70  imul    rcx, r14; unsigned __int64
0x140010f74  lea     rdx, [rbp+4Fh+var_94]; unsigned int *
0x140010f78  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140010f7d  mov     [rbp+4Fh+Data], eax
0x140010f80  test    eax, eax
0x140010f82  jns     short loc_140010FB0
0x140010f84  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010f89  mov     edx, [rbp+4Fh+Data]; int
0x140010f8c  mov     rcx, rax; this
0x140010f8f  call    ?LogDMPollSecondAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(long)
0x140010f94  mov     ebx, [rbp+4Fh+Data]
0x140010f97  lea     rcx, [rbp+4Fh+var_A0]; this
0x140010f9b  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010fa0  nop
0x140010fa1  lea     rcx, [rbp+4Fh+hkey]
0x140010fa5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010faa  nop
0x140010fab  jmp     loc_14001127E
0x140010fb0  mov     eax, [rbp+4Fh+var_94]
0x140010fb3  lea     ecx, [rax+r12]
0x140010fb7  cmp     ecx, eax
0x140010fb9  jb      loc_140011250
0x140010fbf  mov     [rbp+4Fh+Data], r13d
0x140010fc3  mov     [rsp+100h+var_B8], r13d; int
0x140010fc8  mov     [rsp+100h+var_C0], r13d; int
0x140010fcd  mov     [rsp+100h+cbData], r13d; int
0x140010fd2  mov     dword ptr [rsp+100h+lpData], ecx; unsigned int
0x140010fd6  mov     r13d, [rbp+4Fh+var_50]
0x140010fda  mov     r9d, r13d; unsigned int
0x140010fdd  mov     r12d, [rbp+4Fh+var_50+4]
0x140010fe1  mov     r8d, r12d; unsigned int
0x140010fe4  lea     rdx, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x140010feb  mov     rcx, rdi; unsigned __int16 *
0x140010fee  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x140010ff3  mov     [rbp+4Fh+Data], eax
0x140010ff6  test    eax, eax
0x140010ff8  jns     short loc_140011026
0x140010ffa  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010fff  mov     edx, [rbp+4Fh+Data]; int
0x140011002  mov     rcx, rax; this
0x140011005  call    ?LogDMPollSecondAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(long)
0x14001100a  mov     ebx, [rbp+4Fh+Data]
0x14001100d  lea     rcx, [rbp+4Fh+var_A0]; this
0x140011011  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140011016  nop
0x140011017  lea     rcx, [rbp+4Fh+hkey]
0x14001101b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140011020  nop
0x140011021  jmp     loc_14001127E
0x140011026  test    r12d, r12d
0x140011029  jnz     short loc_140011035
0x14001102b  xor     r12d, r12d
0x14001102e  test    r13d, r13d
0x140011031  jnz     short loc_14001107F
0x140011033  jmp     short loc_140011038
0x140011035  xor     r12d, r12d
0x140011038  test    r14d, r14d
0x14001103b  jnz     short loc_140011042
0x14001103d  test    r15d, r15d
0x140011040  jnz     short loc_14001107F
0x140011042  test    esi, esi
0x140011044  jnz     short loc_14001104A
0x140011046  test    ebx, ebx
0x140011048  jnz     short loc_14001107F
0x14001104a  mov     [rsp+100h+var_B8], r12d; int
0x14001104f  mov     [rsp+100h+var_C0], 1; int
0x140011057  mov     [rsp+100h+cbData], 1; int
0x14001105f  mov     dword ptr [rsp+100h+lpData], r12d; int
0x140011064  mov     r9d, 1; unsigned int
0x14001106a  mov     r8d, r9d; unsigned int
0x14001106d  lea     rdx, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x140011074  mov     rcx, rdi; unsigned __int16 *
0x140011077  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x14001107c  mov     [rbp+4Fh+Data], eax
0x14001107f  mov     ecx, [rbp+4Fh+var_90]
0x140011082  mov     ebx, 1
0x140011087  shl     rbx, cl
0x14001108a  and     ebx, 9402021h
0x140011090  mov     rsi, [rbp+4Fh+var_88]
0x140011094  cmp     [rbp+4Fh+var_50+8], r12d
0x140011098  jz      short loc_1400110E5
0x14001109a  mov     eax, ebx
0x14001109c  neg     rax
0x14001109f  sbb     rdx, rdx
0x1400110a2  and     rdx, rsi; unsigned __int16 *
0x1400110a5  xor     r8d, r8d; int
0x1400110a8  mov     rcx, rdi; unsigned __int16 *
0x1400110ab  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x1400110b0  mov     [rbp+4Fh+Data], eax
0x1400110b3  test    eax, eax
0x1400110b5  jns     short loc_1400110E5
0x1400110b7  test    rbx, rbx
0x1400110ba  jz      short loc_1400110D5
0x1400110bc  test    rsi, rsi
0x1400110bf  jz      short loc_1400110D5
0x1400110c1  xor     r8d, r8d; int
0x1400110c4  xor     edx, edx; unsigned __int16 *
0x1400110c6  mov     rcx, rdi; unsigned __int16 *
0x1400110c9  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x1400110ce  mov     [rbp+4Fh+Data], eax
0x1400110d1  test    eax, eax
0x1400110d3  jns     short loc_1400110E5
0x1400110d5  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1400110da  mov     edx, [rbp+4Fh+Data]; int
0x1400110dd  mov     rcx, rax; this
0x1400110e0  call    ?LogDMPollLoginSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollLoginSetupFail(long)
0x1400110e5  cmp     [rbp+4Fh+var_50+0Ch], r12d
0x1400110e9  jz      short loc_14001114A
0x1400110eb  mov     rax, rbx
0x1400110ee  neg     rax
0x1400110f1  sbb     rdx, rdx
0x1400110f4  and     rdx, rsi; unsigned __int16 *
0x1400110f7  mov     r8d, 1; int
0x1400110fd  mov     rcx, rdi; unsigned __int16 *
0x140011100  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x140011105  mov     [rbp+4Fh+Data], eax
0x140011108  test    eax, eax
0x14001110a  jns     short loc_14001113D
0x14001110c  test    rbx, rbx
0x14001110f  jz      short loc_14001112B
0x140011111  test    rsi, rsi
0x140011114  jz      short loc_14001112B
0x140011116  xor     edx, edx; unsigned __int16 *
0x140011118  lea     r8d, [rdx+1]; int
0x14001111c  mov     rcx, rdi; unsigned __int16 *
0x14001111f  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x140011124  mov     [rbp+4Fh+Data], eax
0x140011127  test    eax, eax
0x140011129  jns     short loc_14001113D
0x14001112b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140011130  mov     edx, [rbp+4Fh+Data]; int
0x140011133  mov     rcx, rax; this
  ... truncated ...
```
