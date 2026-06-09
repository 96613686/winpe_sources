# SyncPollingOptions(ushort const *,ushort const *,bool,EnrollmentEnrollType,bool)

- ea: `0x180010340`
- end: `0x1800107fb`
- name: `?SyncPollingOptions@@YAJPEBG0_NW4EnrollmentEnrollType@@1@Z`
- size: `1211`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004168`

## callees

- `0x180001c60`
- `0x180006574`
- `0x18000707c`
- `0x1800075e8`
- `0x180007778`
- `0x180008558`
- `0x18000a464`
- `0x18000a864`
- `0x18000c938`
- `0x18000de68`
- `0x18000e7f0`
- `0x18000fb24`
- `0x180010340`
- `0x180011828`
- `0x180011e0c`
- `0x18001b9d8`
- `0x18001ba38`
- `0x18001bab0`
- `0x18001bb18`
- `0x18001bbac`
- `0x18001bc24`
- `0x18001bcb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800104b1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800104b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001074f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001074f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010792`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010792`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800106d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800106d2`

## string_xrefs

- `0x180010456`: `Schedule #1 created by enrollment client`
- `0x180010502`: `Schedule #2 created by enrollment client`
- `0x180010568`: `Schedule #3 created by enrollment client`
- `0x1800105cc`: `Maintenance Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall SyncPollingOptions(const unsigned __int16 *a1, __int64 a2, __int64 a3, int a4)
{
  int v5; // esi
  __int64 v6; // rdx
  __int64 v7; // r8
  int i; // r14d
  int v9; // ebx
  const unsigned __int16 * near **v10; // r9
  __int64 j; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rbx
  unsigned int v15; // esi
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v17; // rax
  __int64 v18; // r14
  unsigned int v19; // r12d
  unsigned int v20; // r15d
  unsigned int v21; // ecx
  unsigned int v22; // r12d
  unsigned int v23; // r13d
  __int64 v24; // rsi
  __int64 v25; // rbx
  CEnrollmentLogger *v26; // rax
  CEnrollmentLogger *v27; // rax
  CEnrollmentLogger *v28; // rax
  int DeviceEnrollerKey; // eax
  LSTATUS ValueW; // eax
  CEnrollmentLogger *v31; // rax
  int lpData; // [rsp+20h] [rbp-91h]
  int pcbData; // [rsp+30h] [rbp-81h]
  int pcbDataa; // [rsp+30h] [rbp-81h]
  int pcbDatab; // [rsp+30h] [rbp-81h]
  int pcbDatac; // [rsp+30h] [rbp-81h]
  int v38; // [rsp+38h] [rbp-79h]
  int v39; // [rsp+38h] [rbp-79h]
  int v40; // [rsp+38h] [rbp-79h]
  int v41; // [rsp+38h] [rbp-79h]
  int Data; // [rsp+50h] [rbp-61h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-59h] BYREF
  unsigned int v44; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v45; // [rsp+64h] [rbp-4Dh] BYREF
  int v46; // [rsp+68h] [rbp-49h]
  DWORD v47; // [rsp+6Ch] [rbp-45h] BYREF
  _BYTE v48[8]; // [rsp+70h] [rbp-41h] BYREF
  __int64 v49; // [rsp+78h] [rbp-39h]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-31h] BYREF
  __int128 pvData; // [rsp+90h] [rbp-21h] BYREF
  unsigned int v52[4]; // [rsp+A0h] [rbp-11h] BYREF
  unsigned int v53[4]; // [rsp+B0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v49 = a2;
  Data = 0;
  v44 = 0;
  v45 = 0;
  hkey = 0;
  *(_OWORD *)v52 = 0;
  v5 = 0;
  v46 = a4;
  *(_OWORD *)v53 = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v48, "SyncPollingOptions");
  for ( i = 0; i < 8; ++i )
  {
    Data = GetPollValueFromRegistry(a1, (LPCWSTR)(&g_RegistryKeyNames)[i], &v52[i]);
    v9 = Data;
    if ( (int)(Data + 0x80000000) >= 0 && Data != -2147024894 )
      goto LABEL_51;
    if ( Data != -2147024894 )
      v5 = 1;
  }
  if ( !v5 )
  {
    v9 = 1;
    goto LABEL_51;
  }
  ClearSchedulesAfterInfinite(v52, v6, v7, &g_RegistryKeyNames);
  for ( j = 0; j != 8; ++j )
  {
    SetPollValueToRegistry(a1, (LPCWSTR)v10[j], v52[j]);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v13, v12, (&g_RegistryKeyNames)[j], v52[j]);
    v10 = &g_RegistryKeyNames;
  }
  v14 = v52[0];
  v15 = v52[1];
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #1 created by enrollment client",
           v52[1],
           v52[0],
           v52[0],
           0,
           pcbData,
           v38,
           1,
           0);
  if ( Data < 0 )
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"ScheduleOneOmaDmSession", 4u, &Data, 4u);
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollScheduleSetupFail(Logger, Data);
LABEL_50:
    v9 = Data;
    goto LABEL_51;
  }
  Data = ULongLongToULong(v14 * (v15 + 1), &v44);
  if ( Data < 0
    || (v18 = v52[3],
        v19 = v44,
        v20 = v52[2],
        Data = ScheduleOneOmaDmSession(
                 a1,
                 L"Schedule #2 created by enrollment client",
                 v52[3],
                 v52[2],
                 v44,
                 0,
                 pcbDataa,
                 v39,
                 1,
                 0),
        Data < 0) )
  {
    v17 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(v17, Data);
    goto LABEL_50;
  }
  Data = ULongLongToULong(v18 * v20, &v45);
  if ( Data < 0 )
    goto LABEL_49;
  v21 = v45 + v19;
  if ( v45 + v19 < v45 )
  {
    Data = -2147024362;
    goto LABEL_49;
  }
  v22 = v53[1];
  v23 = v53[0];
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #3 created by enrollment client",
           v53[1],
           v53[0],
           v21,
           0,
           pcbDatab,
           v40,
           0,
           0);
  if ( Data < 0 )
  {
LABEL_49:
    v31 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v31, Data);
    goto LABEL_50;
  }
  if ( (v22 || !v23) && ((_DWORD)v18 || !v20) && (v15 || !(_DWORD)v14) )
    Data = ScheduleOneOmaDmSession(
             a1,
             L"Maintenance Schedule created by enrollment client",
             1u,
             1u,
             0,
             1,
             pcbDatac,
             v41,
             1,
             0);
  v24 = v49;
  v25 = (1LL << v46) & 0x9402021;
  if ( v53[2] )
  {
    Data = ScheduleOneOmaDmSessionOnLogin(
             a1,
             (const unsigned __int16 *)(v49 & ((unsigned __int128)-(__int128)(unsigned int)v25 >> 64)),
             0);
    if ( Data < 0 )
    {
      if ( !v25 || !v24 || (Data = ScheduleOneOmaDmSessionOnLogin(a1, 0, 0), Data < 0) )
      {
        v26 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogDMPollLoginSetupFail(v26, Data);
      }
    }
  }
  if ( v53[3] )
  {
    Data = ScheduleOneOmaDmSessionOnLogin(
             a1,
             (const unsigned __int16 *)(v24 & ((unsigned __int128)-(__int128)(unsigned __int64)v25 >> 64)),
             1);
    if ( Data >= 0 || v25 && v24 && (Data = ScheduleOneOmaDmSessionOnLogin(a1, 0, 1), Data >= 0) )
    {
      v28 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupSuccess(v28);
    }
    else
    {
      v27 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupFail(v27, Data);
    }
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hkey);
  v9 = DeviceEnrollerKey;
  if ( DeviceEnrollerKey >= 0 )
  {
    pvData = 0;
    v47 = 16;
    ValueW = RegGetValueW(hkey, 0, L"FirstScheduleTimestamp", 8u, 0, &pvData, &v47);
    v9 = ValueW;
    if ( ValueW > 0 )
      v9 = (unsigned __int16)ValueW | 0x80070000;
    Data = v9;
    if ( v9 < 0 )
    {
      v9 = RegSetValueExW(hkey, L"FirstScheduleTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
      Data = v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)DeviceEnrollerKey,
      lpData);
  }
LABEL_51:
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v48);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180010340  mov     [rsp-8+arg_10], rbx
0x180010345  push    rbp
0x180010346  push    rsi
0x180010347  push    rdi
0x180010348  push    r12
0x18001034a  push    r13
0x18001034c  push    r14
0x18001034e  push    r15
0x180010350  lea     rbp, [rsp-1Fh]
0x180010355  sub     rsp, 0D0h
0x18001035c  mov     rax, cs:__security_cookie
0x180010363  xor     rax, rsp
0x180010366  mov     [rbp+4Fh+var_40], rax
0x18001036a  xor     r13d, r13d
0x18001036d  mov     [rbp+4Fh+var_88], rdx
0x180010371  xorps   xmm0, xmm0
0x180010374  mov     [rbp+4Fh+Data], r13d
0x180010378  mov     rdi, rcx
0x18001037b  mov     [rbp+4Fh+var_A0], r13d
0x18001037f  lea     rdx, aSyncpollingopt_2; "SyncPollingOptions"
0x180010386  mov     [rbp+4Fh+var_9C], r13d
0x18001038a  lea     rcx, [rbp+4Fh+var_90]; this
0x18001038e  mov     [rbp+4Fh+hkey], r13
0x180010392  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x180010396  mov     esi, r13d
0x180010399  mov     [rbp+4Fh+var_98], r9d
0x18001039d  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x1800103a1  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x1800103a6  mov     r14d, r13d
0x1800103a9  lea     r15d, [r13+1]
0x1800103ad  mov     r12d, 80070002h
0x1800103b3  lea     r9, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x1800103ba  cmp     r14d, 8
0x1800103be  jge     short loc_1800103FC
0x1800103c0  movsxd  rdx, r14d
0x1800103c3  lea     r8, [rbp+4Fh+var_60]
0x1800103c7  mov     rcx, rdi; unsigned __int16 *
0x1800103ca  lea     r8, [r8+rdx*4]; unsigned int *
0x1800103ce  mov     rdx, [r9+rdx*8]; lpValue
0x1800103d2  call    ?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z; GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)
0x1800103d7  mov     ecx, 80000000h
0x1800103dc  mov     [rbp+4Fh+Data], eax
0x1800103df  mov     ebx, eax
0x1800103e1  add     eax, ecx
0x1800103e3  test    ecx, eax
0x1800103e5  jnz     short loc_1800103F0
0x1800103e7  cmp     ebx, r12d
0x1800103ea  jnz     loc_1800107BF
0x1800103f0  cmp     ebx, r12d
0x1800103f3  cmovnz  esi, r15d
0x1800103f7  add     r14d, r15d
0x1800103fa  jmp     short loc_1800103B3
0x1800103fc  test    esi, esi
0x1800103fe  jnz     short loc_180010408
0x180010400  mov     ebx, r15d
0x180010403  jmp     loc_1800107BF
0x180010408  lea     rcx, [rbp+4Fh+var_60]
0x18001040c  call    ClearSchedulesAfterInfinite
0x180010411  mov     rbx, r13
0x180010414  mov     r8d, [rbp+rbx*4+4Fh+var_60]; unsigned int
0x180010419  mov     rcx, rdi; unsigned __int16 *
0x18001041c  mov     rdx, [r9+rbx*8]; lpValueName
0x180010420  call    ?SetPollValueToRegistry@@YAJPEBG0K@Z; SetPollValueToRegistry(ushort const *,ushort const *,ulong)
0x180010425  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18001042c  jz      short loc_180010443
0x18001042e  mov     r9d, [rbp+rbx*4+4Fh+var_60]
0x180010433  lea     r8, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x18001043a  mov     r8, [r8+rbx*8]
0x18001043e  call    McTemplateU0zq_EventWriteTransfer
0x180010443  add     rbx, r15
0x180010446  lea     r9, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x18001044d  cmp     rbx, 8
0x180010451  jnz     short loc_180010414
0x180010453  mov     ebx, [rbp+4Fh+var_60]
0x180010456  lea     rdx, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x18001045d  mov     esi, [rbp+4Fh+var_60+4]
0x180010460  mov     r9d, ebx; unsigned int
0x180010463  mov     [rsp+100h+var_B8], r13d; int
0x180010468  mov     r8d, esi; unsigned int
0x18001046b  mov     [rsp+100h+var_C0], r15d; int
0x180010470  mov     rcx, rdi; unsigned __int16 *
0x180010473  mov     [rsp+100h+cbData], r13d; int
0x180010478  mov     dword ptr [rsp+100h+lpData], ebx; unsigned int
0x18001047c  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x180010481  mov     [rbp+4Fh+Data], eax
0x180010484  test    eax, eax
0x180010486  jns     short loc_1800104D2
0x180010488  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18001048f  lea     rax, [rbp+4Fh+Data]
0x180010493  mov     r9d, 4; dwType
0x180010499  lea     r8, aScheduleoneoma; "ScheduleOneOmaDmSession"
0x1800104a0  mov     [rsp+100h+cbData], r9d; cbData
0x1800104a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800104ac  mov     [rsp+100h+lpData], rax; lpData
0x1800104b1  call    cs:__imp_RegSetKeyValueW
0x1800104b8  nop     dword ptr [rax+rax+00h]
0x1800104bd  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800104c2  mov     edx, [rbp+4Fh+Data]; int
0x1800104c5  mov     rcx, rax; this
0x1800104c8  call    ?LogDMPollScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollScheduleSetupFail(long)
0x1800104cd  jmp     loc_1800107BC
0x1800104d2  lea     ecx, [rsi+1]
0x1800104d5  imul    rcx, rbx; unsigned __int64
0x1800104d9  lea     rdx, [rbp+4Fh+var_A0]; unsigned int *
0x1800104dd  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800104e2  mov     [rbp+4Fh+Data], eax
0x1800104e5  test    eax, eax
0x1800104e7  jns     short loc_1800104FE
0x1800104e9  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800104ee  mov     edx, [rbp+4Fh+Data]; int
0x1800104f1  mov     rcx, rax; this
0x1800104f4  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x1800104f9  jmp     loc_1800107BC
0x1800104fe  mov     r14d, [rbp+4Fh+var_60+0Ch]
0x180010502  lea     rdx, aSchedule2Creat; "Schedule #2 created by enrollment clien"...
0x180010509  mov     r12d, [rbp+4Fh+var_A0]
0x18001050d  mov     r8d, r14d; unsigned int
0x180010510  mov     [rsp+100h+var_B8], r13d; int
0x180010515  mov     rcx, rdi; unsigned __int16 *
0x180010518  mov     [rsp+100h+var_C0], r15d; int
0x18001051d  mov     r15d, [rbp+4Fh+var_60+8]
0x180010521  mov     r9d, r15d; unsigned int
0x180010524  mov     [rsp+100h+cbData], r13d; int
0x180010529  mov     dword ptr [rsp+100h+lpData], r12d; unsigned int
0x18001052e  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x180010533  mov     [rbp+4Fh+Data], eax
0x180010536  test    eax, eax
0x180010538  js      short loc_1800104E9
0x18001053a  mov     ecx, r15d
0x18001053d  lea     rdx, [rbp+4Fh+var_9C]; unsigned int *
0x180010541  imul    rcx, r14; unsigned __int64
0x180010545  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001054a  mov     [rbp+4Fh+Data], eax
0x18001054d  test    eax, eax
0x18001054f  js      loc_1800107AC
0x180010555  mov     eax, [rbp+4Fh+var_9C]
0x180010558  lea     ecx, [rax+r12]
0x18001055c  cmp     ecx, eax
0x18001055e  jb      loc_1800107A5
0x180010564  mov     r12d, [rbp+4Fh+var_50+4]
0x180010568  lea     rdx, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x18001056f  mov     [rsp+100h+var_B8], r13d; int
0x180010574  mov     r8d, r12d; unsigned int
0x180010577  mov     [rsp+100h+var_C0], r13d; int
0x18001057c  mov     [rsp+100h+cbData], r13d; int
0x180010581  mov     [rbp+4Fh+Data], r13d
0x180010585  mov     r13d, [rbp+4Fh+var_50]
0x180010589  mov     r9d, r13d; unsigned int
0x18001058c  mov     dword ptr [rsp+100h+lpData], ecx; unsigned int
0x180010590  mov     rcx, rdi; unsigned __int16 *
0x180010593  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x180010598  mov     [rbp+4Fh+Data], eax
0x18001059b  test    eax, eax
0x18001059d  js      loc_1800107AC
0x1800105a3  test    r12d, r12d
0x1800105a6  jnz     short loc_1800105B2
0x1800105a8  xor     r12d, r12d
0x1800105ab  test    r13d, r13d
0x1800105ae  jnz     short loc_1800105FC
0x1800105b0  jmp     short loc_1800105B5
0x1800105b2  xor     r12d, r12d
0x1800105b5  test    r14d, r14d
0x1800105b8  jnz     short loc_1800105BF
0x1800105ba  test    r15d, r15d
0x1800105bd  jnz     short loc_1800105FC
0x1800105bf  test    esi, esi
0x1800105c1  jnz     short loc_1800105C7
0x1800105c3  test    ebx, ebx
0x1800105c5  jnz     short loc_1800105FC
0x1800105c7  mov     [rsp+100h+var_B8], r12d; int
0x1800105cc  lea     rdx, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x1800105d3  mov     r9d, 1; unsigned int
0x1800105d9  mov     [rsp+100h+var_C0], 1; int
0x1800105e1  mov     [rsp+100h+cbData], 1; int
0x1800105e9  mov     r8d, r9d; unsigned int
0x1800105ec  mov     rcx, rdi; unsigned __int16 *
0x1800105ef  mov     dword ptr [rsp+100h+lpData], r12d; int
0x1800105f4  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800105f9  mov     [rbp+4Fh+Data], eax
0x1800105fc  mov     ecx, [rbp+4Fh+var_98]
0x1800105ff  mov     ebx, 1
0x180010604  mov     rsi, [rbp+4Fh+var_88]
0x180010608  shl     rbx, cl
0x18001060b  and     ebx, 9402021h
0x180010611  cmp     [rbp+4Fh+var_50+8], r12d
0x180010615  jz      short loc_180010662
0x180010617  mov     eax, ebx
0x180010619  mov     rcx, rdi; unsigned __int16 *
0x18001061c  neg     rax
0x18001061f  sbb     rdx, rdx
0x180010622  xor     r8d, r8d; int
0x180010625  and     rdx, rsi; unsigned __int16 *
0x180010628  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x18001062d  mov     [rbp+4Fh+Data], eax
0x180010630  test    eax, eax
0x180010632  jns     short loc_180010662
0x180010634  test    rbx, rbx
0x180010637  jz      short loc_180010652
0x180010639  test    rsi, rsi
0x18001063c  jz      short loc_180010652
0x18001063e  xor     r8d, r8d; int
0x180010641  xor     edx, edx; unsigned __int16 *
0x180010643  mov     rcx, rdi; unsigned __int16 *
0x180010646  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x18001064b  mov     [rbp+4Fh+Data], eax
0x18001064e  test    eax, eax
0x180010650  jns     short loc_180010662
0x180010652  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180010657  mov     edx, [rbp+4Fh+Data]; int
0x18001065a  mov     rcx, rax; this
0x18001065d  call    ?LogDMPollLoginSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollLoginSetupFail(long)
0x180010662  cmp     [rbp+4Fh+var_50+0Ch], r12d
0x180010666  jz      short loc_1800106C7
0x180010668  mov     rax, rbx
0x18001066b  mov     r8d, 1; int
0x180010671  neg     rax
0x180010674  mov     rcx, rdi; unsigned __int16 *
0x180010677  sbb     rdx, rdx
0x18001067a  and     rdx, rsi; unsigned __int16 *
0x18001067d  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x180010682  mov     [rbp+4Fh+Data], eax
0x180010685  test    eax, eax
0x180010687  jns     short loc_1800106BA
0x180010689  test    rbx, rbx
0x18001068c  jz      short loc_1800106A8
0x18001068e  test    rsi, rsi
0x180010691  jz      short loc_1800106A8
0x180010693  xor     edx, edx; unsigned __int16 *
0x180010695  mov     rcx, rdi; unsigned __int16 *
0x180010698  lea     r8d, [rdx+1]; int
0x18001069c  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x1800106a1  mov     [rbp+4Fh+Data], eax
0x1800106a4  test    eax, eax
0x1800106a6  jns     short loc_1800106BA
0x1800106a8  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800106ad  mov     edx, [rbp+4Fh+Data]; int
0x1800106b0  mov     rcx, rax; this
0x1800106b3  call    ?LogDMAllUsersPollOnFirstLoginSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupFail(long)
0x1800106b8  jmp     short loc_1800106C7
0x1800106ba  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800106bf  mov     rcx, rax; this
0x1800106c2  call    ?LogDMAllUsersPollOnFirstLoginSetupSuccess@CEnrollmentLogger@@QEAAXXZ; CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupSuccess(void)
0x1800106c7  xorps   xmm0, xmm0
0x1800106ca  lea     rcx, [rbp+4Fh+SystemTime]; lpSystemTime
0x1800106ce  movups  xmmword ptr [rbp+4Fh+SystemTime.wYear], xmm0
0x1800106d2  call    cs:__imp_GetSystemTime
0x1800106d9  nop     dword ptr [rax+rax+00h]
0x1800106de  xor     edx, edx
0x1800106e0  lea     rcx, [rbp+4Fh+hkey]
0x1800106e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800106e9  lea     rdx, [rbp+4Fh+hkey]; HKEY *
0x1800106ed  mov     rcx, rdi; pszMore
0x1800106f0  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x1800106f5  mov     ebx, eax
0x1800106f7  test    eax, eax
0x1800106f9  jns     short loc_180010718
0x1800106fb  mov     rcx, [rbp+57h]; this
0x1800106ff  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180010706  mov     r9d, eax; char *
0x180010709  mov     edx, 0C9Fh; void *
0x18001070e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010713  jmp     loc_1800107BF
0x180010718  mov     rcx, [rbp+4Fh+hkey]; hkey
0x18001071c  lea     rax, [rbp+4Fh+var_94]
0x180010720  mov     [rsp+100h+pcbData], rax; pcbData
0x180010725  lea     r8, Value; "FirstScheduleTimestamp"
0x18001072c  mov     edi, 10h
0x180010731  lea     rax, [rbp+4Fh+pvData]
0x180010735  xorps   xmm0, xmm0
0x180010738  mov     qword ptr [rsp+100h+cbData], rax; pvData
0x18001073d  xor     edx, edx; lpSubKey
0x18001073f  mov     [rsp+100h+lpData], r12; pdwType
0x180010744  movups  [rbp+4Fh+pvData], xmm0
0x180010748  lea     r9d, [rdi-8]; dwFlags
0x18001074c  mov     [rbp+4Fh+var_94], edi
0x18001074f  call    cs:__imp_RegGetValueW
0x180010756  nop     dword ptr [rax+rax+00h]
0x18001075b  mov     ebx, eax
0x18001075d  test    eax, eax
0x18001075f  jle     short loc_18001076A
0x180010761  movzx   ebx, ax
0x180010764  or      ebx, 80070000h
0x18001076a  mov     [rbp+4Fh+Data], ebx
0x18001076d  test    ebx, ebx
0x18001076f  jns     short loc_1800107BF
0x180010771  mov     rcx, [rbp+4Fh+hkey]; hKey
0x180010775  lea     rax, [rbp+4Fh+SystemTime]
0x180010779  mov     [rsp+100h+cbData], edi; cbData
0x18001077d  lea     rdx, Value; "FirstScheduleTimestamp"
0x180010784  mov     r9d, 3; dwType
0x18001078a  mov     [rsp+100h+lpData], rax; lpData
0x18001078f  xor     r8d, r8d; Reserved
0x180010792  call    cs:__imp_RegSetValueExW
0x180010799  nop     dword ptr [rax+rax+00h]
0x18001079e  mov     ebx, eax
0x1800107a0  mov     [rbp+4Fh+Data], eax
0x1800107a3  jmp     short loc_1800107BF
0x1800107a5  mov     [rbp+4Fh+Data], 80070216h
0x1800107ac  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800107b1  mov     edx, [rbp+4Fh+Data]; int
  ... truncated ...
```
