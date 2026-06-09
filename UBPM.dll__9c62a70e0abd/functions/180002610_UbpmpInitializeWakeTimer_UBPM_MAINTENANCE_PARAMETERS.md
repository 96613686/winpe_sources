# UbpmpInitializeWakeTimer(_UBPM_MAINTENANCE_PARAMETERS *)

- ea: `0x180002610`
- end: `0x180002c67`
- name: `?UbpmpInitializeWakeTimer@@YAKPEAU_UBPM_MAINTENANCE_PARAMETERS@@@Z`
- size: `1623`
- prototype: `unsigned int __fastcall(struct _UBPM_MAINTENANCE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800390b0`

## callees

- `0x180002610`
- `0x180002c70`
- `0x180002cc4`
- `0x1800191a0`
- `0x180019220`
- `0x18002ba28`
- `0x1800351ec`
- `0x180036d44`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `ntdll!RtlRandomEx` at `0x180002a83`
- `ntdll!RtlRandomEx` at `0x180002a83`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002891`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800028ea`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002891`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800028ea`
- `ntdll!RtlAcquireSRWLockShared` at `0x180002878`
- `ntdll!RtlAcquireSRWLockShared` at `0x180002878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000299f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000299f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002adc`
- `EventAggregation!EACreateAggregateEvent` at `0x180002821`
- `EventAggregation!EACreateAggregateEvent` at `0x180002821`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800029fc`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800029fc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002acc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002acc`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000298f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000298f`
- `DABAPI!DabRegisterTriggerConsumer` at `0x1800027c0`
- `DABAPI!DabRegisterTriggerConsumer` at `0x1800027c0`
- `TimeBrokerClient!TbCreateCEvent` at `0x180002bce`
- `TimeBrokerClient!TbCreateCEvent` at `0x180002bce`

## pseudocode

```c
__int64 __fastcall UbpmpInitializeWakeTimer(struct _UBPM_MAINTENANCE_PARAMETERS *a1)
{
  char v2; // r15
  bool v3; // r12
  unsigned int v4; // esi
  unsigned int v5; // eax
  DWORD LastError; // ebx
  _UNKNOWN **i; // rbx
  void *v9; // rcx
  _BYTE *v10; // rdx
  void *v11; // rcx
  __int128 v12; // xmm0
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  DWORD dwLowDateTime; // ecx
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // eax
  PVOID v19; // rcx
  struct _FILETIME v20; // [rsp+30h] [rbp-D0h]
  _FILETIME FileTime; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v25; // [rsp+68h] [rbp-98h]
  __int128 v26; // [rsp+78h] [rbp-88h]
  __m256i v27; // [rsp+90h] [rbp-70h] BYREF
  SYSTEMTIME v28; // [rsp+B0h] [rbp-50h]
  __int128 v29; // [rsp+C0h] [rbp-40h]
  __int128 v30; // [rsp+D0h] [rbp-30h]
  __int128 v31; // [rsp+E0h] [rbp-20h]
  __int128 v32; // [rsp+F0h] [rbp-10h]
  __int128 v33; // [rsp+100h] [rbp+0h]
  __int128 v34; // [rsp+110h] [rbp+10h]
  __int128 v35; // [rsp+120h] [rbp+20h]
  __int128 v36; // [rsp+130h] [rbp+30h]
  __int128 v37; // [rsp+140h] [rbp+40h]
  __int128 v38; // [rsp+150h] [rbp+50h]
  __int128 v39; // [rsp+160h] [rbp+60h]
  __int128 v40; // [rsp+170h] [rbp+70h]
  __int64 v41; // [rsp+180h] [rbp+80h]
  __int128 v42; // [rsp+190h] [rbp+90h] BYREF
  __int128 v43; // [rsp+1A0h] [rbp+A0h]
  __int128 v44; // [rsp+1B0h] [rbp+B0h]
  __int64 v45; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v46; // [rsp+1D0h] [rbp+D0h] BYREF
  int v47; // [rsp+1D8h] [rbp+D8h]
  unsigned int v48; // [rsp+1DCh] [rbp+DCh]
  int v49; // [rsp+1E0h] [rbp+E0h]
  int v50; // [rsp+1E4h] [rbp+E4h]
  __int128 v51; // [rsp+1E8h] [rbp+E8h]
  int v52; // [rsp+208h] [rbp+108h]
  __int128 *v53; // [rsp+210h] [rbp+110h]
  SYSTEMTIME SystemTime[3]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v55; // [rsp+250h] [rbp+150h]
  __int128 v56; // [rsp+260h] [rbp+160h]
  __int128 v57; // [rsp+270h] [rbp+170h]
  __int128 v58; // [rsp+280h] [rbp+180h]
  _OWORD v59[8]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v60; // [rsp+310h] [rbp+210h]

  memset_0(SystemTime, 0, 0xF8u);
  v23 = 0;
  memset_0(&v46, 0, 0x48u);
  v2 = 0;
  v45 = 0;
  v3 = 0;
  FileTime = 0;
  LocalFileTime = 0;
  v4 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( *((_BYTE *)a1 + 38) )
  {
    UbpmpAcquireListLockShared();
    for ( i = (_UNKNOWN **)g_leConsumerListHead; i != &g_leConsumerListHead; i = (_UNKNOWN **)*i )
    {
      RtlAcquireSRWLockShared(i + 5);
      v9 = i[2];
      if ( *((_QWORD *)v9 + 6) )
      {
        if ( (*((_BYTE *)v9 + 16) & 1) == 0 )
        {
          v10 = *(_BYTE **)(*((_QWORD *)v9 + 5) + 32LL);
          if ( v10 )
          {
            if ( (*v10 & 0x10) != 0 )
            {
              v2 = 1;
              v3 = UbpmUtilsSearchMultiString(*((PCNZWCH *)v9 + 1), g_CriticalTasks) != 0;
              ReportTaskEvent(v11, &MSCHED_TASK_WAKEUP_REQUESTED, *((const unsigned __int16 **)i[2] + 1));
              RtlReleaseSRWLockShared(i + 5);
              break;
            }
          }
        }
      }
      RtlReleaseSRWLockShared(i + 5);
    }
    UbpmpReleaseListLockShared();
  }
  if ( *((_BYTE *)a1 + 39) )
    v4 = *((unsigned __int16 *)a1 + 18) + 60 * (*((unsigned __int16 *)a1 + 17) + 60 * *((unsigned __int16 *)a1 + 16));
  if ( !v2 && g_pCriticalActions.Data4[0] )
  {
    memset_0(SystemTime, 0, 0xF8u);
    *(_DWORD *)&SystemTime[0].wYear = 4;
    DWORD2(v57) = 1;
    StringCbCopyW((unsigned __int16 *)v59 + 2, 0x80u, L"TsMaintWakeTimer");
    v12 = *(_OWORD *)a1;
    *(_DWORD *)&SystemTime[1].wHour = *((_DWORD *)a1 + 4);
    *(_OWORD *)&SystemTime[0].wHour = v12;
    *(_DWORD *)&SystemTime[1].wSecond = 60;
    BYTE5(v55) = 1;
    if ( SystemTimeToFileTime((const SYSTEMTIME *)&SystemTime[0].wHour, &FileTime) )
    {
      if ( FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
      {
        dwLowDateTime = LocalFileTime.dwLowDateTime;
        v20 = LocalFileTime;
        if ( v4 )
        {
          if ( !Seed )
            Seed = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
          v16 = 10000000LL * (RtlRandomEx(&Seed) % v4) + *(_QWORD *)&v20;
          dwLowDateTime = v16;
        }
        else
        {
          HIDWORD(v16) = LocalFileTime.dwHighDateTime;
        }
        FileTime.dwLowDateTime = dwLowDateTime;
        FileTime.dwHighDateTime = HIDWORD(v16);
        if ( FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)&SystemTime[0].wHour) )
        {
          v27 = *(__m256i *)&SystemTime[0].wYear;
          v41 = v60;
          v28 = SystemTime[2];
          v30 = v56;
          v29 = v55;
          v32 = v58;
          v31 = v57;
          v34 = v59[1];
          v33 = v59[0];
          v36 = v59[3];
          v35 = v59[2];
          v38 = v59[5];
          v37 = v59[4];
          v40 = v59[7];
          v39 = v59[6];
          v17 = TbCreateCEvent(&v27, &g_MaintenancePilot);
          if ( !v17 )
          {
LABEL_8:
            v42 = g_MaintenancePilot;
            *(_QWORD *)&v44 = &UbpmpMaintenanceRetriggerTasksCallback;
            v43 = 0u;
            *((_QWORD *)&v44 + 1) = 0;
            v45 = 0;
            return (unsigned int)EACreateAggregateEvent(&v42, &qword_18004FC10);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, v17);
          goto LABEL_6;
        }
        LastError = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return LastError;
        v14 = 15;
      }
      else
      {
        LastError = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return LastError;
        v14 = 14;
      }
    }
    else
    {
      LastError = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LastError;
      v14 = 13;
    }
    WPP_SF_d(v13[2], v14, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, LastError);
    return LastError;
  }
LABEL_6:
  v23 = 0;
  memset_0(&v46, 0, 0x48u);
  LODWORD(v26) = 0;
  v46 = L"Maintenance Timer";
  v53 = &v23;
  v49 = *((_DWORD *)a1 + 4);
  *(_QWORD *)&v24 = qword_18004F430;
  *((_QWORD *)&v24 + 1) = L"Maintenance Activator";
  LODWORD(v23) = 5;
  v52 = 4;
  v50 = -1;
  v47 = 16;
  v48 = v4;
  v25 = 0;
  v51 = *(_OWORD *)a1;
  if ( v2 )
  {
    v18 = 2;
    if ( v3 )
      v18 = 34;
    LODWORD(v25) = v18;
  }
  DWORD1(v26) = 1;
  *((_QWORD *)&v26 + 1) = &v46;
  v5 = DabRegisterTriggerConsumer(0xFFFF, 1, &v24, &g_MaintenancePilot, &qword_18004FC08);
  if ( !v5 )
    goto LABEL_8;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, v5);
  MicrosoftTelemetryAssertTriggeredNoArgs(v19);
  return 0;
}

```

## disassembly

```asm
0x180002610  push    rbp
0x180002612  push    rbx
0x180002613  push    rsi
0x180002614  push    rdi
0x180002615  push    r12
0x180002617  push    r13
0x180002619  push    r14
0x18000261b  push    r15
0x18000261d  lea     rbp, [rsp-238h]
0x180002625  sub     rsp, 338h
0x18000262c  mov     rax, cs:__security_cookie
0x180002633  xor     rax, rsp
0x180002636  mov     [rbp+270h+var_50], rax
0x18000263d  mov     rdi, rcx
0x180002640  xor     edx, edx; Val
0x180002642  lea     rcx, [rbp+270h+SystemTime]; void *
0x180002649  mov     r8d, 0F8h; Size
0x18000264f  call    memset_0
0x180002654  xor     edx, edx; Val
0x180002656  lea     rcx, [rbp+270h+var_1A0]; void *
0x18000265d  xorps   xmm0, xmm0
0x180002660  movups  [rsp+370h+var_328], xmm0
0x180002665  lea     r8d, [rdx+48h]; Size
0x180002669  call    memset_0
0x18000266e  xor     r13d, r13d
0x180002671  xor     eax, eax
0x180002673  xorps   xmm0, xmm0
0x180002676  xorps   xmm1, xmm1
0x180002679  mov     r15b, r13b
0x18000267c  mov     [rbp+270h+var_1B0], rax
0x180002683  mov     r12b, r13b
0x180002686  mov     qword ptr [rsp+370h+FileTime.dwLowDateTime], r13
0x18000268b  lea     r14d, [rax+1]
0x18000268f  mov     qword ptr [rsp+370h+LocalFileTime.dwLowDateTime], r13
0x180002694  mov     esi, r13d
0x180002697  mov     [rsp+370h+var_340], r13
0x18000269c  movups  [rsp+370h+var_318], xmm0
0x1800026a1  movups  [rsp+370h+var_308], xmm0
0x1800026a6  movups  [rsp+370h+var_2F8], xmm0
0x1800026ab  movups  [rbp+270h+var_1E0], xmm1
0x1800026b2  movups  [rbp+270h+var_1D0], xmm1
0x1800026b9  movups  [rbp+270h+var_1C0], xmm1
0x1800026c0  cmp     [rdi+26h], r13b
0x1800026c4  jnz     loc_180002855
0x1800026ca  cmp     [rdi+27h], r13b
0x1800026ce  jnz     loc_180002906
0x1800026d4  lea     rbx, WPP_GLOBAL_Control
0x1800026db  test    r15b, r15b
0x1800026de  jnz     short loc_1800026ED
0x1800026e0  cmp     cs:?g_pCriticalActions@@3PEAU_GUID@@EA.Data4, r13b; _GUID * g_pCriticalActions ...
0x1800026e7  jnz     loc_180002921
0x1800026ed  xor     edx, edx; Val
0x1800026ef  lea     rcx, [rbp+270h+var_1A0]; void *
0x1800026f6  xorps   xmm0, xmm0
0x1800026f9  movups  [rsp+370h+var_328], xmm0
0x1800026fe  lea     r8d, [rdx+48h]; Size
0x180002702  call    memset_0
0x180002707  mov     dword ptr [rsp+370h+var_2F8], r13d
0x18000270c  lea     rax, aMaintenanceTim; "Maintenance Timer"
0x180002713  mov     [rbp+270h+var_1A0], rax
0x18000271a  lea     rax, [rsp+370h+var_328]
0x18000271f  mov     [rbp+270h+var_160], rax
0x180002726  xorps   xmm0, xmm0
0x180002729  mov     eax, [rdi+10h]
0x18000272c  mov     [rbp+270h+var_190], eax
0x180002732  lea     rax, qword_18004F430
0x180002739  mov     qword ptr [rsp+370h+var_318], rax
0x18000273e  lea     rax, aMaintenanceAct; "Maintenance Activator"
0x180002745  mov     qword ptr [rsp+370h+var_318+8], rax
0x18000274a  mov     dword ptr [rsp+370h+var_328], 5
0x180002752  mov     [rbp+270h+var_168], 4
0x18000275c  mov     [rbp+270h+var_18C], 0FFFFFFFFh
0x180002766  mov     [rbp+270h+var_198], 10h
0x180002770  mov     [rbp+270h+var_194], esi
0x180002776  movdqu  [rsp+370h+var_308], xmm0
0x18000277c  movups  xmm0, xmmword ptr [rdi]
0x18000277f  movdqu  [rbp+270h+var_188], xmm0
0x180002787  test    r15b, r15b
0x18000278a  jnz     loc_180002C19
0x180002790  lea     rax, [rbp+270h+var_1A0]
0x180002797  mov     dword ptr [rsp+370h+var_2F8+4], r14d
0x18000279c  mov     qword ptr [rbp+270h+var_2F8+8], rax
0x1800027a0  lea     r9, ?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x1800027a7  lea     rax, qword_18004FC08
0x1800027ae  mov     edx, r14d
0x1800027b1  lea     r8, [rsp+370h+var_318]
0x1800027b6  mov     [rsp+370h+var_350], rax
0x1800027bb  mov     ecx, 0FFFFh
0x1800027c0  call    cs:__imp_DabRegisterTriggerConsumer
0x1800027c7  nop     dword ptr [rax+rax+00h]
0x1800027cc  test    eax, eax
0x1800027ce  jnz     loc_180002C30
0x1800027d4  mov     rax, cs:?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x1800027db  lea     rdx, qword_18004FC10
0x1800027e2  mov     qword ptr [rbp+270h+var_1E0], rax
0x1800027e9  lea     rcx, [rbp+270h+var_1E0]
0x1800027f0  lea     rax, ?UbpmpMaintenanceRetriggerTasksCallback@@YAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; UbpmpMaintenanceRetriggerTasksCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x1800027f7  mov     qword ptr [rbp+270h+var_1E0+8], r13
0x1800027fe  mov     qword ptr [rbp+270h+var_1C0], rax
0x180002805  mov     qword ptr [rbp+270h+var_1D0+8], r13
0x18000280c  mov     qword ptr [rbp+270h+var_1D0], r13
0x180002813  mov     qword ptr [rbp+270h+var_1C0+8], r13
0x18000281a  mov     [rbp+270h+var_1B0], r13
0x180002821  call    cs:__imp_EACreateAggregateEvent
0x180002828  nop     dword ptr [rax+rax+00h]
0x18000282d  mov     ebx, eax
0x18000282f  mov     eax, ebx
0x180002831  mov     rcx, [rbp+270h+var_50]
0x180002838  xor     rcx, rsp; StackCookie
0x18000283b  call    __security_check_cookie
0x180002840  add     rsp, 338h
0x180002847  pop     r15
0x180002849  pop     r14
0x18000284b  pop     r13
0x18000284d  pop     r12
0x18000284f  pop     rdi
0x180002850  pop     rsi
0x180002851  pop     rbx
0x180002852  pop     rbp
0x180002853  retn
0x180002855  call    UbpmpAcquireListLockShared
0x18000285a  mov     rbx, cs:g_leConsumerListHead
0x180002861  lea     rax, g_leConsumerListHead
0x180002868  cmp     rbx, rax
0x18000286b  jz      loc_1800028F6
0x180002871  lea     r14, [rbx+28h]
0x180002875  mov     rcx, r14
0x180002878  call    cs:__imp_RtlAcquireSRWLockShared
0x18000287f  nop     dword ptr [rax+rax+00h]
0x180002884  mov     rcx, [rbx+10h]
0x180002888  cmp     [rcx+30h], r13
0x18000288c  jnz     short loc_1800028A2
0x18000288e  mov     rcx, r14
0x180002891  call    cs:__imp_RtlReleaseSRWLockShared
0x180002898  nop     dword ptr [rax+rax+00h]
0x18000289d  mov     rbx, [rbx]
0x1800028a0  jmp     short loc_180002861
0x1800028a2  test    byte ptr [rcx+10h], 1
0x1800028a6  jnz     short loc_18000288E
0x1800028a8  mov     rax, [rcx+28h]
0x1800028ac  mov     rdx, [rax+20h]
0x1800028b0  test    rdx, rdx
0x1800028b3  jz      short loc_18000288E
0x1800028b5  test    byte ptr [rdx], 10h
0x1800028b8  jz      short loc_18000288E
0x1800028ba  mov     rdx, cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; lpString1
0x1800028c1  mov     r15b, 1
0x1800028c4  mov     rcx, [rcx+8]; lpString2
0x1800028c8  call    ?UbpmUtilsSearchMultiString@@YAEPEBG0@Z; UbpmUtilsSearchMultiString(ushort const *,ushort const *)
0x1800028cd  mov     r8, [rbx+10h]
0x1800028d1  lea     rdx, MSCHED_TASK_WAKEUP_REQUESTED; struct _EVENT_DESCRIPTOR *
0x1800028d8  test    al, al
0x1800028da  setnz   r12b
0x1800028de  mov     r8, [r8+8]; unsigned __int16 *
0x1800028e2  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800028e7  mov     rcx, r14
0x1800028ea  call    cs:__imp_RtlReleaseSRWLockShared
0x1800028f1  nop     dword ptr [rax+rax+00h]
0x1800028f6  call    UbpmpReleaseListLockShared
0x1800028fb  mov     r14d, 1
0x180002901  jmp     loc_1800026CA
0x180002906  movzx   eax, word ptr [rdi+20h]
0x18000290a  imul    ecx, eax, 3Ch ; '<'
0x18000290d  movzx   eax, word ptr [rdi+22h]
0x180002911  add     ecx, eax
0x180002913  movzx   eax, word ptr [rdi+24h]
0x180002917  imul    esi, ecx, 3Ch ; '<'
0x18000291a  add     esi, eax
0x18000291c  jmp     loc_1800026D4
0x180002921  xor     edx, edx; Val
0x180002923  lea     rcx, [rbp+270h+SystemTime]; void *
0x18000292a  mov     r8d, 0F8h; Size
0x180002930  call    memset_0
0x180002935  lea     r8, aTsmaintwaketim; "TsMaintWakeTimer"
0x18000293c  mov     dword ptr [rbp+270h+SystemTime.wYear], 4
0x180002946  mov     edx, 80h; unsigned __int64
0x18000294b  mov     [rbp+270h+var_F8], r14d
0x180002952  lea     rcx, [rbp+270h+var_DC]; unsigned __int16 *
0x180002959  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000295e  movups  xmm0, xmmword ptr [rdi]
0x180002961  mov     eax, [rdi+10h]
0x180002964  lea     rdx, [rsp+370h+FileTime]; lpFileTime
0x180002969  lea     rcx, [rbp+270h+SystemTime.wHour]; lpSystemTime
0x180002970  mov     [rbp+270h+var_138], eax
0x180002976  movdqu  xmmword ptr [rbp+270h+SystemTime.wHour], xmm0
0x18000297e  mov     [rbp+270h+var_134], 3Ch ; '<'
0x180002988  mov     [rbp+270h+var_11B], r14b
0x18000298f  call    cs:__imp_SystemTimeToFileTime
0x180002996  nop     dword ptr [rax+rax+00h]
0x18000299b  test    eax, eax
0x18000299d  jnz     short loc_1800029F2
0x18000299f  call    cs:__imp_GetLastError
0x1800029a6  nop     dword ptr [rax+rax+00h]
0x1800029ab  mov     ebx, eax
0x1800029ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029b4  lea     rax, WPP_GLOBAL_Control
0x1800029bb  cmp     rcx, rax
0x1800029be  jz      loc_18000282F
0x1800029c4  test    [rcx+1Ch], r14b
0x1800029c8  jz      loc_18000282F
0x1800029ce  mov     edx, 0Dh
0x1800029d3  jmp     short loc_1800029DA
0x1800029d5  mov     edx, 0Fh
0x1800029da  mov     rcx, [rcx+10h]
0x1800029de  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x1800029e5  mov     r9d, ebx
0x1800029e8  call    WPP_SF_d
0x1800029ed  jmp     loc_18000282F
0x1800029f2  lea     rdx, [rsp+370h+LocalFileTime]; lpLocalFileTime
0x1800029f7  lea     rcx, [rsp+370h+FileTime]; lpFileTime
0x1800029fc  call    cs:__imp_FileTimeToLocalFileTime
0x180002a03  nop     dword ptr [rax+rax+00h]
0x180002a08  test    eax, eax
0x180002a0a  jnz     short loc_180002A42
0x180002a0c  call    cs:__imp_GetLastError
0x180002a13  nop     dword ptr [rax+rax+00h]
0x180002a18  mov     ebx, eax
0x180002a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a21  lea     rax, WPP_GLOBAL_Control
0x180002a28  cmp     rcx, rax
0x180002a2b  jz      loc_18000282F
0x180002a31  test    [rcx+1Ch], r14b
0x180002a35  jz      loc_18000282F
0x180002a3b  mov     edx, 0Eh
0x180002a40  jmp     short loc_1800029DA
0x180002a42  mov     eax, [rsp+370h+LocalFileTime.dwHighDateTime]
0x180002a46  mov     ecx, [rsp+370h+LocalFileTime.dwLowDateTime]
0x180002a4a  mov     dword ptr [rsp+370h+var_340+4], eax
0x180002a4e  mov     dword ptr [rsp+370h+var_340], ecx
0x180002a52  test    esi, esi
0x180002a54  jz      short loc_180002AAF
0x180002a56  cmp     cs:Seed, r13d
0x180002a5d  jnz     short loc_180002A7C
0x180002a5f  mov     eax, 7FFE0320h
0x180002a64  mov     rax, [rax]
0x180002a67  mov     ecx, ds:7FFE0004h
0x180002a6e  imul    rcx, rax
0x180002a72  shr     rcx, 18h
0x180002a76  mov     cs:Seed, ecx
0x180002a7c  lea     rcx, Seed; Seed
0x180002a83  call    cs:__imp_RtlRandomEx
0x180002a8a  nop     dword ptr [rax+rax+00h]
0x180002a8f  xor     edx, edx
0x180002a91  div     esi
0x180002a93  mov     rax, [rsp+370h+var_340]
0x180002a98  mov     ecx, edx
0x180002a9a  imul    rdx, rcx, 989680h
0x180002aa1  add     rax, rdx
0x180002aa4  mov     [rsp+370h+var_340], rax
0x180002aa9  mov     ecx, dword ptr [rsp+370h+var_340]
0x180002aad  jmp     short loc_180002AB4
0x180002aaf  mov     rax, [rsp+370h+var_340]
0x180002ab4  shr     rax, 20h
0x180002ab8  lea     rdx, [rbp+270h+SystemTime.wHour]; lpSystemTime
0x180002abf  mov     [rsp+370h+FileTime.dwLowDateTime], ecx
0x180002ac3  lea     rcx, [rsp+370h+FileTime]; lpFileTime
0x180002ac8  mov     [rsp+370h+FileTime.dwHighDateTime], eax
0x180002acc  call    cs:__imp_FileTimeToSystemTime
0x180002ad3  nop     dword ptr [rax+rax+00h]
0x180002ad8  test    eax, eax
0x180002ada  jnz     short loc_180002B10
0x180002adc  call    cs:__imp_GetLastError
0x180002ae3  nop     dword ptr [rax+rax+00h]
0x180002ae8  mov     ebx, eax
0x180002aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180002af1  lea     rax, WPP_GLOBAL_Control
0x180002af8  cmp     rcx, rax
0x180002afb  jz      loc_18000282F
0x180002b01  test    [rcx+1Ch], r14b
0x180002b05  jz      loc_18000282F
0x180002b0b  jmp     loc_1800029D5
0x180002b10  movaps  xmm0, xmmword ptr [rbp+270h+SystemTime.wYear]
0x180002b17  lea     rdx, ?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x180002b1e  movaps  xmm1, xmmword ptr [rbp+130h]
0x180002b25  lea     rcx, [rbp+270h+var_2E0]
0x180002b29  mov     rax, [rbp+270h+var_60]
0x180002b30  movups  [rbp+270h+var_2E0], xmm0
0x180002b34  mov     [rbp+270h+var_1F0], rax
0x180002b3b  movaps  xmm0, [rbp+270h+var_130]
0x180002b42  movups  [rbp+270h+var_2C0], xmm0
0x180002b46  movaps  xmm0, [rbp+270h+var_110]
0x180002b4d  movups  [rbp+270h+var_2D0], xmm1
0x180002b51  movaps  xmm1, xmmword ptr [rbp+150h]
0x180002b58  movups  [rbp+270h+var_2A0], xmm0
0x180002b5c  movaps  xmm0, [rbp+270h+var_F0]
0x180002b63  movups  [rbp+270h+var_2B0], xmm1
0x180002b67  movaps  xmm1, xmmword ptr [rbp+170h]
0x180002b6e  movups  [rbp+270h+var_280], xmm0
0x180002b72  movaps  xmm0, [rbp+270h+var_D0]
0x180002b79  movups  [rbp+270h+var_290], xmm1
0x180002b7d  movaps  xmm1, xmmword ptr [rbp+190h]
0x180002b84  movups  [rbp+270h+var_260], xmm0
0x180002b88  movaps  xmm0, [rbp+270h+var_B0]
0x180002b8f  movups  [rbp+270h+var_270], xmm1
0x180002b93  movaps  xmm1, [rbp+270h+var_C0]
0x180002b9a  movups  [rbp+270h+var_240], xmm0
0x180002b9e  movaps  xmm0, [rbp+270h+var_90]
0x180002ba5  movups  [rbp+270h+var_250], xmm1
0x180002ba9  movaps  xmm1, [rbp+270h+var_A0]
0x180002bb0  movups  [rbp+270h+var_220], xmm0
  ... truncated ...
```
