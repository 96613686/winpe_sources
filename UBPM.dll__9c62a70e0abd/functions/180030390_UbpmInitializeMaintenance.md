# UbpmInitializeMaintenance

- ea: `0x180030390`
- end: `0x18003090b`
- name: `UbpmInitializeMaintenance`
- size: `1403`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bb88`

## callees

- `0x1800103c0`
- `0x1800191a0`
- `0x18001b74c`
- `0x180025d50`
- `0x180029de0`
- `0x18002a444`
- `0x18002b5bc`
- `0x18002b784`
- `0x18002c0b4`
- `0x18002d620`
- `0x180030390`
- `0x180031770`
- `0x180033114`
- `0x180038be8`
- `0x180038ea8`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800304b4`
- `ntdll!RtlNtStatusToDosError` at `0x1800304b4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180030468`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180030543`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800307f1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180030468`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180030543`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800307f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800305e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800305e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800307b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800307b6`
- `EventAggregation!EACreateAggregateEvent` at `0x18003070e`
- `EventAggregation!EACreateAggregateEvent` at `0x18003076f`
- `EventAggregation!EACreateAggregateEvent` at `0x18003070e`
- `EventAggregation!EACreateAggregateEvent` at `0x18003076f`
- `UMPDC!SleepstudyHelperCreateLibrary` at `0x1800304a4`
- `UMPDC!SleepstudyHelperCreateLibrary` at `0x1800304a4`
- `TimeBrokerClient!TbCreateCEvent` at `0x1800306a7`
- `TimeBrokerClient!TbCreateCEvent` at `0x1800306a7`

## pseudocode

```c
__int64 UbpmInitializeMaintenance()
{
  NTSTATUS v0; // esi
  int v1; // r14d
  unsigned int MaintenanceSettings; // ebx
  int v3; // edi
  __int64 v4; // rcx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  NTSTATUS v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-CCh] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME v17; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v18[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME v19; // [rsp+80h] [rbp-80h] BYREF
  __m256i v20; // [rsp+90h] [rbp-70h]
  __int128 v21; // [rsp+B0h] [rbp-50h]
  __int128 v22; // [rsp+C0h] [rbp-40h]
  __int128 v23; // [rsp+D0h] [rbp-30h]
  __int128 v24; // [rsp+E0h] [rbp-20h]
  __int128 v25; // [rsp+F0h] [rbp-10h]
  __int128 v26; // [rsp+100h] [rbp+0h]
  __int128 v27; // [rsp+110h] [rbp+10h]
  __int128 v28; // [rsp+120h] [rbp+20h]
  __int128 v29; // [rsp+130h] [rbp+30h]
  __int128 v30; // [rsp+140h] [rbp+40h]
  __int128 v31; // [rsp+150h] [rbp+50h]
  __int128 v32; // [rsp+160h] [rbp+60h]
  __int64 v33; // [rsp+170h] [rbp+70h]
  __int128 v34; // [rsp+180h] [rbp+80h] BYREF
  __int128 v35; // [rsp+190h] [rbp+90h]
  __int128 v36; // [rsp+1A0h] [rbp+A0h]
  __int64 v37; // [rsp+1B0h] [rbp+B0h]
  SYSTEMTIME Time; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1D0h] [rbp+D0h] BYREF
  __m256i v40; // [rsp+1E0h] [rbp+E0h]
  __int128 v41; // [rsp+200h] [rbp+100h]
  __int128 v42; // [rsp+210h] [rbp+110h]
  __int128 v43; // [rsp+220h] [rbp+120h]
  __int128 v44; // [rsp+230h] [rbp+130h]
  _OWORD v45[8]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v46; // [rsp+2C0h] [rbp+1C0h]
  char v47[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  SYSTEMTIME *p_Time; // [rsp+2F0h] [rbp+1F0h]
  __int64 v49; // [rsp+2F8h] [rbp+1F8h]
  unsigned int *v50; // [rsp+300h] [rbp+200h]
  __int64 v51; // [rsp+308h] [rbp+208h]
  int *v52; // [rsp+310h] [rbp+210h]
  __int64 v53; // [rsp+318h] [rbp+218h]
  NTSTATUS *v54; // [rsp+320h] [rbp+220h]
  __int64 v55; // [rsp+328h] [rbp+228h]

  memset_0(&SystemTime, 0, 0xF8u);
  v16 = 0;
  *(_QWORD *)&Time.wYear = 0;
  v14 = 0;
  memset(v18, 0, 28);
  v37 = 0;
  v0 = 0;
  v1 = 0;
  v17 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  UbpmpInitializeMaintenanceParameters(&v17);
  MaintenanceSettings = UbpmpReadMaintenanceSettings(
                          (struct _UBPM_MAINTENANCE_PARAMETERS *)&v17,
                          (const unsigned __int16 **)&Time);
  if ( MaintenanceSettings )
  {
    v3 = 10;
    goto LABEL_29;
  }
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenancePilotLock);
  byte_18004FC32 = BYTE8(v18[1]);
  dword_180050000 = 0;
  RtlReleaseSRWLockExclusive(&g_MaintenancePilotLock);
  MaintenanceSettings = UbpmMaintenanceInitializeTaskTriggers();
  if ( MaintenanceSettings )
  {
    v3 = 20;
    goto LABEL_29;
  }
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenanceLaunchLock);
  UbpmpRegisterPdcClient();
  v0 = SleepstudyHelperCreateLibrary(1936944500, &v16);
  RtlNtStatusToDosError(v0);
  if ( v0 == -1073741637 )
  {
    v1 = 10;
  }
  else if ( v0 >= 0 )
  {
    qword_18004FC48 = v16;
    v16 = 0;
  }
  else
  {
    v1 = 20;
    if ( (unsigned int)dword_18004F0F0 > 2 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL) )
    {
      v15 = 20;
      v13 = v0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (unsigned int)byte_180046E35,
        v6,
        v7,
        (__int64)&v13,
        (__int64)&v15);
    }
  }
  dword_18004FFE8 = 0;
  RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
  if ( g_CrmRegistrationHandle )
  {
    MaintenanceSettings = UbpmpInitializeCrmMaintenanceLevels();
    if ( MaintenanceSettings )
    {
      v3 = 30;
      goto LABEL_29;
    }
  }
  else
  {
    MaintenanceSettings = UbpmpInitializeLegacyMaintenanceLevels();
    if ( MaintenanceSettings )
    {
      v3 = 40;
      goto LABEL_29;
    }
  }
  memset_0(&SystemTime, 0, 0xF8u);
  *(_DWORD *)&SystemTime.wYear = 2;
  DWORD2(v43) = 0;
  StringCbCopyW((unsigned __int16 *)v45 + 2, 0x80u, L"TsMaintPeriodRetrigger");
  *(__int64 *)((char *)&v40.m256i_i64[1] + 4) = 60;
  v40.m256i_i32[2] = 120;
  v3 = 60;
  GetSystemTime((LPSYSTEMTIME)&SystemTime.wHour);
  v19 = SystemTime;
  v33 = v46;
  v20 = v40;
  v22 = v42;
  v21 = v41;
  v24 = v44;
  v23 = v43;
  v26 = v45[1];
  v25 = v45[0];
  v28 = v45[3];
  v27 = v45[2];
  v30 = v45[5];
  v29 = v45[4];
  v32 = v45[7];
  v31 = v45[6];
  MaintenanceSettings = TbCreateCEvent(&v19, &qword_18004FC20);
  if ( MaintenanceSettings )
  {
    v3 = 50;
  }
  else
  {
    v37 = 0;
    v34 = (unsigned __int64)qword_18004FC20;
    *((_QWORD *)&v36 + 1) = 0;
    *(_QWORD *)&v36 = &UbpmpMaintenanceTelemetryCallback;
    v35 = 0;
    MaintenanceSettings = EACreateAggregateEvent(&v34, &qword_18004FC18);
    if ( !MaintenanceSettings )
    {
      v37 = 0;
      v34 = (unsigned __int64)qword_18004FC20;
      *((_QWORD *)&v36 + 1) = 0;
      *(_QWORD *)&v36 = &UbpmpMaintenanceEvalAllTriggersCallback;
      v35 = 0;
      MaintenanceSettings = EACreateAggregateEvent(&v34, &qword_18004FC28);
      if ( MaintenanceSettings )
      {
        v3 = 70;
      }
      else
      {
        if ( !UbpmpMaintenanceStateReported(&v14) && v14 - 2 <= 2 )
        {
          Time = 0;
          GetLocalTime(&Time);
          UbpmpReportMaintenanceState(&Time, 0);
        }
        UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenancePilotLock);
        byte_18004FC30 = 1;
        dword_180050000 = 0;
        RtlReleaseSRWLockExclusive(&g_MaintenancePilotLock);
        if ( (unsigned int)dword_18004F0F0 > 4 && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
        {
          v13 = v1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v9,
            (unsigned int)&word_180046DFE,
            v10,
            v11,
            (__int64)&v13);
        }
        v3 = 0;
        MaintenanceSettings = 0;
      }
    }
  }
LABEL_29:
  if ( (unsigned int)dword_18004F0F0 > 4 )
  {
    v54 = &v13;
    v52 = &v15;
    v50 = &v14;
    *(_DWORD *)&Time.wYear = MaintenanceSettings;
    p_Time = &Time;
    v55 = 4;
    v53 = 4;
    v51 = 4;
    v49 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18004F0F0, byte_1800471F3, 0, 0, 6, v47, __PAIR64__(v3, v1), v0);
  }
  return MaintenanceSettings;
}

```

## disassembly

```asm
0x180030390  push    rbp
0x180030392  push    rbx
0x180030393  push    rsi
0x180030394  push    rdi
0x180030395  push    r14
0x180030397  push    r15
0x180030399  lea     rbp, [rsp-248h]
0x1800303a1  sub     rsp, 348h
0x1800303a8  mov     rax, cs:__security_cookie
0x1800303af  xor     rax, rsp
0x1800303b2  mov     [rbp+270h+var_40], rax
0x1800303b9  xor     edx, edx; Val
0x1800303bb  lea     rcx, [rbp+270h+SystemTime]; void *
0x1800303c2  mov     r8d, 0F8h; Size
0x1800303c8  call    memset_0
0x1800303cd  xor     r15d, r15d
0x1800303d0  lea     rcx, [rsp+370h+var_328]; struct _SYSTEMTIME *
0x1800303d5  xorps   xmm0, xmm0
0x1800303d8  mov     [rsp+370h+var_330], r15
0x1800303dd  xorps   xmm1, xmm1
0x1800303e0  mov     qword ptr [rbp+270h+Time.wYear], r15
0x1800303e7  xor     eax, eax
0x1800303e9  mov     dword ptr [rsp+370h+var_340+4], r15d
0x1800303ee  movups  [rsp+370h+var_318], xmm0
0x1800303f3  mov     [rbp+270h+var_1C0], rax
0x1800303fa  mov     esi, r15d
0x1800303fd  movups  [rsp+370h+var_318+0Ch], xmm0
0x180030402  mov     r14d, r15d
0x180030405  movups  xmmword ptr [rsp+370h+var_328.wYear], xmm0
0x18003040a  movups  [rbp+270h+var_1F0], xmm1
0x180030411  movups  [rbp+270h+var_1E0], xmm1
0x180030418  movups  [rbp+270h+var_1D0], xmm1
0x18003041f  call    ?UbpmpInitializeMaintenanceParameters@@YAXPEAU_UBPM_MAINTENANCE_PARAMETERS@@@Z; UbpmpInitializeMaintenanceParameters(_UBPM_MAINTENANCE_PARAMETERS *)
0x180030424  lea     rdx, [rbp+270h+Time]; unsigned __int16 **
0x18003042b  lea     rcx, [rsp+370h+var_328]; struct _UBPM_MAINTENANCE_PARAMETERS *
0x180030430  call    ?UbpmpReadMaintenanceSettings@@YAKPEAU_UBPM_MAINTENANCE_PARAMETERS@@PEAPEBG@Z; UbpmpReadMaintenanceSettings(_UBPM_MAINTENANCE_PARAMETERS *,ushort const * *)
0x180030435  mov     ebx, eax
0x180030437  test    eax, eax
0x180030439  jz      short loc_180030444
0x18003043b  lea     edi, [r15+0Ah]
0x18003043f  jmp     loc_18003083C
0x180030444  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x18003044b  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180030450  mov     al, [rsp+370h+var_300]
0x180030454  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_MaintenancePilotLock
0x18003045b  mov     cs:byte_18004FC32, al
0x180030461  mov     cs:dword_180050000, r15d
0x180030468  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003046f  nop     dword ptr [rax+rax+00h]
0x180030474  call    UbpmMaintenanceInitializeTaskTriggers
0x180030479  mov     ebx, eax
0x18003047b  test    eax, eax
0x18003047d  jz      short loc_180030489
0x18003047f  mov     edi, 14h
0x180030484  jmp     loc_18003083C
0x180030489  lea     rcx, g_MaintenanceLaunchLock; struct _UBPM_SRWLOCK *
0x180030490  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180030495  call    ?UbpmpRegisterPdcClient@@YAXXZ; UbpmpRegisterPdcClient(void)
0x18003049a  lea     rdx, [rsp+370h+var_330]
0x18003049f  mov     ecx, 73736D74h
0x1800304a4  call    cs:__imp_SleepstudyHelperCreateLibrary
0x1800304ab  nop     dword ptr [rax+rax+00h]
0x1800304b0  mov     ecx, eax; Status
0x1800304b2  mov     esi, eax
0x1800304b4  call    cs:__imp_RtlNtStatusToDosError
0x1800304bb  nop     dword ptr [rax+rax+00h]
0x1800304c0  cmp     esi, 0C00000BBh
0x1800304c6  jnz     short loc_1800304D0
0x1800304c8  mov     r14d, 0Ah
0x1800304ce  jmp     short loc_180030535
0x1800304d0  test    esi, esi
0x1800304d2  jns     short loc_180030524
0x1800304d4  mov     eax, cs:dword_18004F0F0
0x1800304da  mov     edi, 14h
0x1800304df  mov     r14d, edi
0x1800304e2  cmp     eax, 2
0x1800304e5  jbe     short loc_180030535
0x1800304e7  mov     rdx, 200000000000h
0x1800304f1  call    _tlgKeywordOn
0x1800304f6  test    al, al
0x1800304f8  jz      short loc_180030535
0x1800304fa  lea     rax, [rsp+370h+var_338]
0x1800304ff  mov     [rsp+370h+var_338], edi
0x180030503  mov     [rsp+370h+var_348], rax
0x180030508  lea     rdx, byte_180046E35
0x18003050f  lea     rax, [rsp+370h+var_340]
0x180030514  mov     dword ptr [rsp+370h+var_340], esi
0x180030518  mov     [rsp+370h+var_350], rax
0x18003051d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180030522  jmp     short loc_180030535
0x180030524  mov     rax, [rsp+370h+var_330]
0x180030529  mov     cs:qword_18004FC48, rax
0x180030530  mov     [rsp+370h+var_330], r15
0x180030535  lea     rcx, g_MaintenanceLaunchLock
0x18003053c  mov     cs:dword_18004FFE8, r15d
0x180030543  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003054a  nop     dword ptr [rax+rax+00h]
0x18003054f  cmp     cs:g_CrmRegistrationHandle, r15
0x180030556  jz      short loc_18003056D
0x180030558  call    ?UbpmpInitializeCrmMaintenanceLevels@@YAKXZ; UbpmpInitializeCrmMaintenanceLevels(void)
0x18003055d  mov     ebx, eax
0x18003055f  test    eax, eax
0x180030561  jz      short loc_180030582
0x180030563  mov     edi, 1Eh
0x180030568  jmp     loc_18003083C
0x18003056d  call    ?UbpmpInitializeLegacyMaintenanceLevels@@YAKXZ; UbpmpInitializeLegacyMaintenanceLevels(void)
0x180030572  mov     ebx, eax
0x180030574  test    eax, eax
0x180030576  jz      short loc_180030582
0x180030578  mov     edi, 28h ; '('
0x18003057d  jmp     loc_18003083C
0x180030582  xor     edx, edx; Val
0x180030584  lea     rcx, [rbp+270h+SystemTime]; void *
0x18003058b  mov     r8d, 0F8h; Size
0x180030591  call    memset_0
0x180030596  lea     r8, aTsmaintperiodr; "TsMaintPeriodRetrigger"
0x18003059d  mov     dword ptr [rbp+270h+SystemTime.wYear], 2
0x1800305a7  mov     edx, 80h; unsigned __int64
0x1800305ac  mov     [rbp+270h+var_148], r15d
0x1800305b3  lea     rcx, [rbp+270h+var_12C]; unsigned __int16 *
0x1800305ba  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800305bf  lea     rcx, [rbp+270h+SystemTime.wHour]; lpSystemTime
0x1800305c6  mov     qword ptr [rbp+270h+var_184], 3Ch ; '<'
0x1800305d1  mov     [rbp+270h+var_188], 78h ; 'x'
0x1800305db  mov     edi, 3Ch ; '<'
0x1800305e0  call    cs:__imp_GetSystemTime
0x1800305e7  nop     dword ptr [rax+rax+00h]
0x1800305ec  movaps  xmm0, xmmword ptr [rbp+270h+SystemTime.wYear]
0x1800305f3  lea     rdx, qword_18004FC20
0x1800305fa  movaps  xmm1, xmmword ptr [rbp+0E0h]
0x180030601  lea     rcx, [rbp+270h+var_2F0]
0x180030605  mov     rax, [rbp+270h+var_B0]
0x18003060c  movups  [rbp+270h+var_2F0], xmm0
0x180030610  mov     [rbp+270h+var_200], rax
0x180030614  movaps  xmm0, [rbp+270h+var_184+4]
0x18003061b  movups  [rbp+270h+var_2D0], xmm0
0x18003061f  movaps  xmm0, [rbp+270h+var_160]
0x180030626  movups  [rbp+270h+var_2E0], xmm1
0x18003062a  movaps  xmm1, [rbp+270h+var_170]
0x180030631  movups  [rbp+270h+var_2B0], xmm0
0x180030635  movaps  xmm0, [rbp+270h+var_140]
0x18003063c  movups  [rbp+270h+var_2C0], xmm1
0x180030640  movaps  xmm1, xmmword ptr [rbp+120h]
0x180030647  movups  [rbp+270h+var_290], xmm0
0x18003064b  movaps  xmm0, [rbp+270h+var_120]
0x180030652  movups  [rbp+270h+var_2A0], xmm1
0x180030656  movaps  xmm1, xmmword ptr [rbp+140h]
0x18003065d  movups  [rbp+270h+var_270], xmm0
0x180030661  movaps  xmm0, [rbp+270h+var_100]
0x180030668  movups  [rbp+270h+var_280], xmm1
0x18003066c  movaps  xmm1, [rbp+270h+var_110]
0x180030673  movups  [rbp+270h+var_250], xmm0
0x180030677  movaps  xmm0, [rbp+270h+var_E0]
0x18003067e  movups  [rbp+270h+var_260], xmm1
0x180030682  movaps  xmm1, [rbp+270h+var_F0]
0x180030689  movups  [rbp+270h+var_230], xmm0
0x18003068d  movaps  xmm0, [rbp+270h+var_C0]
0x180030694  movups  [rbp+270h+var_240], xmm1
0x180030698  movaps  xmm1, [rbp+270h+var_D0]
0x18003069f  movups  [rbp+270h+var_210], xmm0
0x1800306a3  movups  [rbp+270h+var_220], xmm1
0x1800306a7  call    cs:__imp_TbCreateCEvent
0x1800306ae  nop     dword ptr [rax+rax+00h]
0x1800306b3  mov     ebx, eax
0x1800306b5  test    eax, eax
0x1800306b7  jz      short loc_1800306C3
0x1800306b9  mov     edi, 32h ; '2'
0x1800306be  jmp     loc_18003083C
0x1800306c3  xor     eax, eax
0x1800306c5  lea     rdx, qword_18004FC18
0x1800306cc  xorps   xmm0, xmm0
0x1800306cf  mov     [rbp+270h+var_1C0], rax
0x1800306d6  mov     rax, cs:qword_18004FC20
0x1800306dd  lea     rcx, [rbp+270h+var_1F0]
0x1800306e4  movups  [rbp+270h+var_1F0], xmm0
0x1800306eb  mov     qword ptr [rbp+270h+var_1F0], rax
0x1800306f2  lea     rax, ?UbpmpMaintenanceTelemetryCallback@@YAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; UbpmpMaintenanceTelemetryCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x1800306f9  movups  [rbp+270h+var_1D0], xmm0
0x180030700  mov     qword ptr [rbp+270h+var_1D0], rax
0x180030707  movups  [rbp+270h+var_1E0], xmm0
0x18003070e  call    cs:__imp_EACreateAggregateEvent
0x180030715  nop     dword ptr [rax+rax+00h]
0x18003071a  mov     ebx, eax
0x18003071c  test    eax, eax
0x18003071e  jnz     loc_18003083C
0x180030724  xor     eax, eax
0x180030726  lea     rdx, qword_18004FC28
0x18003072d  xorps   xmm0, xmm0
0x180030730  mov     [rbp+270h+var_1C0], rax
0x180030737  mov     rax, cs:qword_18004FC20
0x18003073e  lea     rcx, [rbp+270h+var_1F0]
0x180030745  movups  [rbp+270h+var_1F0], xmm0
0x18003074c  mov     qword ptr [rbp+270h+var_1F0], rax
0x180030753  lea     rax, ?UbpmpMaintenanceEvalAllTriggersCallback@@YAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; UbpmpMaintenanceEvalAllTriggersCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x18003075a  movups  [rbp+270h+var_1D0], xmm0
0x180030761  mov     qword ptr [rbp+270h+var_1D0], rax
0x180030768  movups  [rbp+270h+var_1E0], xmm0
0x18003076f  call    cs:__imp_EACreateAggregateEvent
0x180030776  nop     dword ptr [rax+rax+00h]
0x18003077b  mov     ebx, eax
0x18003077d  test    eax, eax
0x18003077f  jz      short loc_18003078B
0x180030781  mov     edi, 46h ; 'F'
0x180030786  jmp     loc_18003083C
0x18003078b  lea     rcx, [rsp+370h+var_340+4]; unsigned int *
0x180030790  call    ?UbpmpMaintenanceStateReported@@YAKPEAK@Z; UbpmpMaintenanceStateReported(ulong *)
0x180030795  test    eax, eax
0x180030797  jnz     short loc_1800307D0
0x180030799  mov     eax, dword ptr [rsp+370h+var_340+4]
0x18003079d  add     eax, 0FFFFFFFEh
0x1800307a0  cmp     eax, 2
0x1800307a3  ja      short loc_1800307D0
0x1800307a5  xorps   xmm0, xmm0
0x1800307a8  lea     rcx, [rbp+270h+Time]; lpSystemTime
0x1800307af  movups  xmmword ptr [rbp+270h+Time.wYear], xmm0
0x1800307b6  call    cs:__imp_GetLocalTime
0x1800307bd  nop     dword ptr [rax+rax+00h]
0x1800307c2  xor     edx, edx; unsigned int
0x1800307c4  lea     rcx, [rbp+270h+Time]; lpTime
0x1800307cb  call    ?UbpmpReportMaintenanceState@@YAXPEAU_SYSTEMTIME@@K@Z; UbpmpReportMaintenanceState(_SYSTEMTIME *,ulong)
0x1800307d0  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x1800307d7  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x1800307dc  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_MaintenancePilotLock
0x1800307e3  mov     cs:byte_18004FC30, 1
0x1800307ea  mov     cs:dword_180050000, r15d
0x1800307f1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800307f8  nop     dword ptr [rax+rax+00h]
0x1800307fd  mov     eax, cs:dword_18004F0F0
0x180030803  cmp     eax, 4
0x180030806  jbe     short loc_180030836
0x180030808  mov     rdx, 400000000000h
0x180030812  call    _tlgKeywordOn
0x180030817  test    al, al
0x180030819  jz      short loc_180030836
0x18003081b  lea     rax, [rsp+370h+var_340]
0x180030820  mov     dword ptr [rsp+370h+var_340], r14d
0x180030825  lea     rdx, word_180046DFE
0x18003082c  mov     [rsp+370h+var_350], rax
0x180030831  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180030836  mov     edi, r15d
0x180030839  mov     ebx, r15d
0x18003083c  mov     eax, cs:dword_18004F0F0
0x180030842  cmp     eax, 4
0x180030845  jbe     loc_1800308E9
0x18003084b  lea     rax, [rsp+370h+var_340]
0x180030850  mov     dword ptr [rsp+370h+var_340], r14d
0x180030855  mov     [rbp+270h+var_50], rax
0x18003085c  lea     rdx, byte_1800471F3
0x180030863  lea     rax, [rsp+370h+var_338]
0x180030868  mov     [rsp+370h+var_338], esi
0x18003086c  mov     [rbp+270h+var_60], rax
0x180030873  lea     rcx, dword_18004F0F0
0x18003087a  lea     rax, [rsp+370h+var_340+4]
0x18003087f  mov     dword ptr [rsp+370h+var_340+4], edi
0x180030883  mov     [rbp+270h+var_70], rax
0x18003088a  xor     r9d, r9d
0x18003088d  lea     rax, [rbp+270h+Time]
0x180030894  mov     dword ptr [rbp+270h+Time.wYear], ebx
0x18003089a  mov     [rbp+270h+var_80], rax
0x1800308a1  xor     r8d, r8d
0x1800308a4  lea     rax, [rbp+270h+var_A0]
0x1800308ab  mov     [rbp+270h+var_48], 4
0x1800308b6  mov     [rsp+370h+var_348], rax
0x1800308bb  mov     dword ptr [rsp+370h+var_350], 6
0x1800308c3  mov     [rbp+270h+var_58], 4
0x1800308ce  mov     [rbp+270h+var_68], 4
0x1800308d9  mov     [rbp+270h+var_78], 4
0x1800308e4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800308e9  mov     eax, ebx
0x1800308eb  mov     rcx, [rbp+270h+var_40]
0x1800308f2  xor     rcx, rsp; StackCookie
0x1800308f5  call    __security_check_cookie
0x1800308fa  add     rsp, 348h
0x180030901  pop     r15
0x180030903  pop     r14
0x180030905  pop     rdi
0x180030906  pop     rsi
0x180030907  pop     rbx
0x180030908  pop     rbp
0x180030909  retn
```
