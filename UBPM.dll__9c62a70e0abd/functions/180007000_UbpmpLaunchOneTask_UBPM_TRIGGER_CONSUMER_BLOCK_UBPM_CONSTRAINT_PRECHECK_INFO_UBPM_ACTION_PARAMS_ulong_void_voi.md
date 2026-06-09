# UbpmpLaunchOneTask(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_ACTION_PARAMS *,ulong,void *,void * *,void *,_GUID *,ulong,unsigned __int64,ulong,unsigned __int64,uchar,ushort const * *,ulong,uchar *,ulong,void *,uchar,ushort const * *,uchar *)

- ea: `0x180007000`
- end: `0x180007e96`
- name: `?UbpmpLaunchOneTask@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAU_UBPM_ACTION_PARAMS@@KPEAXPEAPEAX3PEAU_GUID@@K_KK6EPEAPEBGKPEAEK3E78@Z`
- size: `3734`
- prototype: `unsigned int __usercall@<eax>(struct _UBPM_TRIGGER_CONSUMER_BLOCK *@<rcx>, struct _UBPM_CONSTRAINT_PRECHECK_INFO *@<rdx>, struct _UBPM_ACTION_PARAMS *@<r8>, unsigned int@<r9d>, PSID pSid, void **, void *, struct _GUID *, unsigned int, unsigned __int64, unsigned int, unsigned __int64, char, const unsigned __int16 **, unsigned int, unsigned __int8 *, unsigned int, void *, unsigned __int8, const unsigned __int16 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000aff0`
- `0x18000b938`
- `0x18000bd60`

## callees

- `0x180003790`
- `0x1800057e0`
- `0x180005a60`
- `0x180006820`
- `0x180007000`
- `0x180007e9c`
- `0x180008430`
- `0x180008b30`
- `0x18000ad48`
- `0x18000fbf0`
- `0x18001af64`
- `0x18001b07c`
- `0x18001bb54`
- `0x18001bcdc`
- `0x18001bf54`
- `0x18001cbe0`
- `0x18001da20`
- `0x180024740`
- `0x180026e7c`
- `0x18002ce98`
- `0x18002e1d8`
- `0x180030bb4`
- `0x180035184`
- `0x1800385c8`
- `0x18004022e`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007080`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007080`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007901`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007901`
- `ntdll!RtlFreeHeap` at `0x1800072e5`
- `ntdll!RtlFreeHeap` at `0x18000762c`
- `ntdll!RtlFreeHeap` at `0x18000772c`
- `ntdll!RtlFreeHeap` at `0x180007750`
- `ntdll!RtlFreeHeap` at `0x180007773`
- `ntdll!RtlFreeHeap` at `0x1800072e5`
- `ntdll!RtlFreeHeap` at `0x18000762c`
- `ntdll!RtlFreeHeap` at `0x18000772c`
- `ntdll!RtlFreeHeap` at `0x180007750`
- `ntdll!RtlFreeHeap` at `0x180007773`
- `ntdll!RtlAllocateHeap` at `0x1800070f9`
- `ntdll!RtlAllocateHeap` at `0x1800070f9`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007673`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007673`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000764e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000764e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007159`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007159`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007708`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007708`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007915`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007789`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007789`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007d26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007d26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800072a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800072a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007d99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007d99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007533`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007533`
- `RPCRT4!UuidEqual` at `0x1800079c7`
- `RPCRT4!UuidEqual` at `0x1800079c7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800078d5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800078d5`

## string_xrefs

- `0x1800078ae`: `NT TASK`
- `0x180007609`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x1800076c9`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18000783e`: `ReportTaskEvent(0x%x) --> ret=%d`

## pseudocode

```c
__int64 __fastcall UbpmpLaunchOneTask(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        struct _UBPM_CONSTRAINT_PRECHECK_INFO *a2,
        struct _UBPM_ACTION_PARAMS *a3,
        unsigned int a4,
        PSID pSid,
        void **a6,
        void *a7,
        struct _GUID *a8,
        unsigned int a9,
        unsigned __int64 a10,
        unsigned int a11,
        unsigned __int64 a12,
        unsigned __int8 a13,
        const unsigned __int16 **a14,
        unsigned int a15,
        unsigned __int8 *a16,
        unsigned int a17,
        void *a18,
        unsigned __int8 a19,
        const unsigned __int16 **a20,
        unsigned __int8 *a21)
{
  PSID v23; // rbx
  DWORD LengthSid; // r14d
  __int64 v25; // rax
  __int64 v26; // r13
  const WCHAR *v27; // rdi
  __int64 v28; // rax
  char *Heap; // rax
  char *v30; // rsi
  unsigned __int8 *v31; // r12
  __int64 v32; // r8
  void *v33; // r9
  int v34; // r14d
  bool v35; // r12
  unsigned int ConsumerUserPropertiesKeyName; // eax
  WCHAR *v37; // r14
  LSTATUS v38; // eax
  __int64 v39; // r12
  __int64 v40; // r8
  __int64 v41; // rax
  unsigned __int8 v42; // cl
  unsigned __int8 *v43; // r14
  __int64 v44; // rcx
  __int64 v45; // rcx
  struct _UBPM_ACTION_PARAMS *v46; // r13
  int v47; // edx
  int v48; // eax
  struct _GUID *v49; // r13
  struct _GUID v50; // xmm0
  unsigned int v51; // eax
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v52; // rcx
  const struct _EVENT_DESCRIPTOR *v53; // rdx
  int v54; // r8d
  PVOID v55; // rbx
  const unsigned __int16 *v56; // r9
  int v57; // eax
  __int64 v58; // r8
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v59; // rbx
  int v60; // r13d
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v61; // rsi
  const unsigned __int16 *v62; // rcx
  int v63; // eax
  __int64 v64; // r8
  __int64 v65; // rdx
  DWORD v67; // ebx
  __int64 v68; // rdx
  __int64 v69; // rax
  int v70; // eax
  __int64 v71; // r8
  __int64 v72; // rdx
  DWORD LastError; // ebx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // r13
  bool v77; // zf
  unsigned __int16 *v78; // r12
  const unsigned __int16 *v79; // rdx
  __int64 v80; // rax
  unsigned int v81; // edx
  const unsigned __int16 *v82; // rcx
  unsigned int v83; // r12d
  PVOID v84; // rbx
  const unsigned __int16 *v85; // r9
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // r9
  _DWORD *v89; // rax
  LSTATUS v90; // eax
  const unsigned __int16 *v91; // rdx
  const struct _GUID *phkResult; // [rsp+20h] [rbp-E0h]
  void *cchCount2; // [rsp+28h] [rbp-D8h]
  struct _GUID *v94; // [rsp+30h] [rbp-D0h]
  const struct _GUID *v95; // [rsp+38h] [rbp-C8h]
  __int16 v96; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  RPC_STATUS Status; // [rsp+60h] [rbp-A0h] BYREF
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v101; // [rsp+68h] [rbp-98h] BYREF
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v102; // [rsp+70h] [rbp-90h] BYREF
  PVOID P; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  PVOID v105; // [rsp+88h] [rbp-78h] BYREF
  PVOID v106; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp-68h] BYREF
  __int128 v108; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v109; // [rsp+B0h] [rbp-50h]
  PSID Sid[2]; // [rsp+C0h] [rbp-40h]
  __int128 v111; // [rsp+D0h] [rbp-30h]
  __int128 v112; // [rsp+E0h] [rbp-20h]
  __int128 v113; // [rsp+F0h] [rbp-10h]
  __int128 v114; // [rsp+100h] [rbp+0h]
  const unsigned __int16 **v115; // [rsp+110h] [rbp+10h]
  _QWORD v116[5]; // [rsp+120h] [rbp+20h] BYREF
  int v117; // [rsp+148h] [rbp+48h]
  __int16 v118; // [rsp+14Ch] [rbp+4Ch]
  unsigned __int64 v119; // [rsp+150h] [rbp+50h]
  unsigned int v120; // [rsp+158h] [rbp+58h]
  PSID v121; // [rsp+160h] [rbp+60h]
  void *v122; // [rsp+168h] [rbp+68h]
  int v123; // [rsp+174h] [rbp+74h]
  unsigned __int64 v124; // [rsp+178h] [rbp+78h]
  const unsigned __int16 *v125; // [rsp+180h] [rbp+80h]
  unsigned int v126; // [rsp+188h] [rbp+88h]
  unsigned int v127; // [rsp+18Ch] [rbp+8Ch]
  unsigned __int8 *v128; // [rsp+190h] [rbp+90h]
  unsigned __int8 v129; // [rsp+198h] [rbp+98h]
  const unsigned __int16 **v130; // [rsp+1A0h] [rbp+A0h]
  unsigned int v131; // [rsp+1A8h] [rbp+A8h]
  const unsigned __int16 *v132; // [rsp+1B0h] [rbp+B0h]
  unsigned __int8 v133; // [rsp+1B8h] [rbp+B8h]
  const unsigned __int16 **v134; // [rsp+1C0h] [rbp+C0h]
  unsigned __int16 v135; // [rsp+220h] [rbp+120h] BYREF
  struct _UBPM_CONSTRAINT_PRECHECK_INFO *v136; // [rsp+228h] [rbp+128h]
  struct _UBPM_ACTION_PARAMS *v137; // [rsp+230h] [rbp+130h]
  unsigned int v138; // [rsp+238h] [rbp+138h]

  v138 = a4;
  v137 = a3;
  v136 = a2;
  v96 = 0;
  memset_0(v116, 0, 0xA8u);
  v23 = pSid;
  v115 = 0;
  v108 = 0;
  v109 = 0;
  *(_OWORD *)Sid = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  if ( pSid )
    LengthSid = GetLengthSid(pSid);
  else
    LengthSid = 0;
  v25 = *((_QWORD *)a1 + 3);
  v26 = -1;
  P = 0;
  v105 = 0;
  v106 = 0;
  v101 = 0;
  v102 = 0;
  v135 = 0;
  Status = 0;
  v27 = *(const WCHAR **)(v25 + 8);
  if ( v27 )
  {
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    if ( (unsigned int)v28 > 8 && CompareStringW(0x7Fu, 1u, v27, 7, L"NT TASK", 7) == 2 )
      v27 += 7;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, LengthSid + 120);
  v30 = Heap;
  if ( Heap )
  {
    if ( v23 )
    {
      *((_QWORD *)Heap + 11) = Heap + 120;
      if ( !CopySid(LengthSid, Heap + 120, v23) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
            LastError);
        UBPM_MIDL_user_free(v30, v72, v74, v75);
        return LastError;
      }
    }
    LOBYTE(pSid) = 0;
    *((_QWORD *)v30 + 1) = v30;
    *(_QWORD *)v30 = v30;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
        *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
    UbpmpActionContextCleanup(a1);
    if ( *(_QWORD *)(*((_QWORD *)a1 + 3) + 48LL) )
    {
      RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
      dword_18004FFE8 = GetCurrentThreadId();
      LOBYTE(pSid) = 1;
    }
    *(_QWORD *)&v112 = a10;
    DWORD2(v112) = a11;
    *(_QWORD *)&v113 = a12;
    BYTE8(v113) = a13;
    *(_QWORD *)&v114 = a14;
    BYTE12(v114) = a19;
    v115 = a20;
    DWORD2(v114) = a17;
    DWORD2(v111) = a9;
    Sid[0] = (PSID)__PAIR64__(v138, a15);
    *((_QWORD *)&v108 + 1) = a3;
    v31 = a21;
    *(_QWORD *)&v111 = a8;
    *((_QWORD *)&v109 + 1) = a16;
    *(_QWORD *)&v108 = a1;
    Sid[1] = v23;
    v34 = UbpmConstraintsCheck((unsigned int)&v108, (_DWORD)v136, (unsigned int)&v96, (unsigned int)&v135, (__int64)a21);
    if ( v34 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
          v34);
    }
    else
    {
      if ( *v31 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
        goto LABEL_66;
      }
      if ( Sid[1] )
      {
        hKey = 0;
        v35 = 0;
        lpSubKey = 0;
        *(_DWORD *)Data = 0;
        Type = 0;
        cbData = 0;
        ConsumerUserPropertiesKeyName = UbpmpGetConsumerUserPropertiesKeyName(
                                          *(PCNZWCH *)(*(_QWORD *)(v108 + 24) + 8LL),
                                          Sid[1],
                                          (unsigned __int16 **)&lpSubKey);
        v37 = (WCHAR *)lpSubKey;
        if ( !ConsumerUserPropertiesKeyName )
        {
          v38 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 1u, &hKey);
          if ( (unsigned int)(v38 - 2) > 1 && !v38 )
          {
            cbData = 4;
            v90 = RegQueryValueExW(hKey, L"Disabled", 0, &Type, Data, &cbData);
            if ( (unsigned int)(v90 - 2) > 1 && !v90 && Type == 4 && cbData == 4 )
              v35 = *(_DWORD *)Data != 0;
          }
        }
        if ( hKey )
          RegCloseKey(hKey);
        if ( v37 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
        if ( v35 )
        {
          v34 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              73,
              (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
              *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
              0);
          goto LABEL_66;
        }
      }
      v39 = a17;
      if ( a17 != 0xFFFF )
      {
        v68 = *((_QWORD *)a1 + 3);
        v69 = *(_QWORD *)(v68 + 24);
        if ( *(_DWORD *)(v69 + 48LL * a17) == 1
          && *(_DWORD *)(*(_QWORD *)(v69 + 48LL * a17 + 8) + 56LL) == 4
          && (a9 & 0x20) != 0
          && *(char *)(v68 + 16) >= 0 )
        {
          v70 = EventManager::EvtReport(g_hTaskEventManager, &MISSED_TASK_REJECTED, v27, v33, phkResult);
          v71 = (unsigned __int16)v70;
          if ( v70 >= 0 )
            v71 = 0;
          TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &MISSED_TASK_REJECTED, v71);
          v34 = 4320;
          goto LABEL_86;
        }
      }
      v40 = *((_QWORD *)a1 + 3);
      v117 = *((_DWORD *)a1 + 11);
      v116[0] = v137;
      v116[4] = a8;
      v116[1] = *(_QWORD *)v40;
      v116[2] = v27;
      v116[3] = *(_QWORD *)(v40 + 8);
      v119 = a10;
      v120 = v138;
      v118 = v96;
      v122 = a7;
      v41 = *((_QWORD *)v137 + 4);
      v121 = v23;
      if ( v41 )
        v123 = *(_DWORD *)(v41 + 20);
      else
        v123 = 0;
      v124 = a12;
      if ( v135 >= a13 )
        v125 = 0;
      else
        v125 = a14[v135];
      v42 = a19;
      v131 = a9;
      if ( v135 < a19 )
      {
        v132 = a20[v135];
        v42 = a19;
      }
      else
      {
        v132 = 0;
      }
      v43 = a16;
      v126 = a17;
      if ( (*(_BYTE *)(v40 + 16) & 2) != 0 )
      {
        v127 = a15;
        v129 = a13;
        v130 = a14;
        v133 = v42;
        v134 = a20;
        v128 = a16;
      }
      if ( !v23 )
      {
        v80 = *(_QWORD *)(*((_QWORD *)v137 + 3) + 32LL);
        if ( v80 )
          v23 = *(PSID *)(*(_QWORD *)(v80 + 8) + 8LL);
        else
          LODWORD(v23) = (_DWORD)::pSid;
      }
      UbpmpActionLogTriggered(a1, a17, a9, a18, a8);
      if ( (_DWORD)v39 == 0xFFFF )
        goto LABEL_35;
      v44 = *(_QWORD *)(*((_QWORD *)a1 + 3) + 24LL);
      if ( *(_DWORD *)(v44 + 48 * v39) != 1 )
        goto LABEL_35;
      v45 = *(_QWORD *)(v44 + 48 * v39 + 8);
      if ( *(_DWORD *)(v45 + 56) != 1 )
        goto LABEL_35;
      if ( !UuidEqual(**(UUID ***)(v45 + 64), (UUID *)&TRIGGER_EMULATOR_PROVIDER_GUID, &Status) )
        goto LABEL_35;
      if ( Status )
        goto LABEL_35;
      v32 = a15 >> 1;
      if ( !(a15 >> 1) || !v43 || *(_WORD *)&v43[2 * (unsigned int)(v32 - 1)] )
        goto LABEL_35;
      do
        ++v26;
      while ( *(_WORD *)&v43[2 * v26] );
      v76 = (unsigned int)(v26 + 1);
      if ( (unsigned int)v76 < (unsigned int)v32 && (v32 = (unsigned int)(v32 - v76), (a15 = v32) != 0) )
      {
        v77 = *(_WORD *)&v43[2 * v76] == 0;
        v78 = (unsigned __int16 *)&v43[2 * v76];
        v46 = v137;
        if ( !v77 )
        {
          if ( !v125 )
          {
            v79 = *(const unsigned __int16 **)(*((_QWORD *)v137 + 3) + 16LL);
            if ( v79 )
            {
              v34 = UbpmpExpandString((unsigned __int16 **)&v105, v79, v78, v32);
              if ( v34 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    74,
                    (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                    *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
                    v34);
                goto LABEL_65;
              }
              v32 = a15;
              v125 = (const unsigned __int16 *)v105;
            }
          }
          if ( !v132 )
          {
            v91 = *(const unsigned __int16 **)(*((_QWORD *)v46 + 3) + 24LL);
            if ( v91 )
            {
              v34 = UbpmpExpandString((unsigned __int16 **)&v106, v91, v78, v32);
              if ( v34 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    75,
                    (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                    *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
                    v34);
                goto LABEL_65;
              }
              v132 = (const unsigned __int16 *)v106;
            }
          }
        }
        LODWORD(v39) = a17;
      }
      else
      {
LABEL_35:
        v46 = v137;
      }
      v47 = **(_DWORD **)(v116[0] + 24LL);
      v101 = 0;
      v102 = 0;
      if ( (unsigned int)(v47 - 1) > 1 )
      {
        if ( v47 == 3 )
          v48 = UbpmLaunchTaskSignal(v116, a6, v32);
        else
          v48 = UbpmLaunchTaskPublish(v116, a6, v32);
      }
      else
      {
        v48 = UbpmpHostLaunchTaskExe((struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *)v116, a6, &v101, &v102);
      }
      v34 = v48;
      if ( !v135 && (DWORD2(v111) & 0x80000) != 0 )
      {
        v89 = *(_DWORD **)(*((_QWORD *)&v108 + 1) + 32LL);
        if ( v89 )
        {
          if ( (*v89 & 0x1C0) == 0x1C0 )
            *((_BYTE *)a1 + 304) = 0;
        }
      }
      if ( v34 )
      {
        if ( v34 > 0 )
          v81 = (unsigned __int16)v34 | 0x80070000;
        else
          v81 = v34;
        v82 = L"NULL";
        if ( *((_QWORD *)v46 + 1) )
          v82 = (const unsigned __int16 *)*((_QWORD *)v46 + 1);
        ReportTaskEvent(g_hTaskEventManager, &ACTION_LAUNCH_FAILURE, v27, a8, v82, v81);
        if ( !v135 )
        {
          UbpmUtilsGetAccountNamesFromSid((_DWORD)v23, 1, 0, 0, (__int64)&P);
          if ( v34 > 0 )
            v83 = (unsigned __int16)v34 | 0x80070000;
          else
            v83 = v34;
          v84 = P;
          v85 = L"(NONE)";
          if ( P )
            v85 = (const unsigned __int16 *)P;
          ReportTaskEvent(g_hTaskEventManager, &JOB_START_FAILED, v27, v85, v83);
          UBPM_MIDL_user_free(v84, v86, v87, v88);
        }
        UbpmScheduleRestartOnFailure(a1, 1);
      }
      else
      {
        *((_QWORD *)v30 + 3) = v46;
        v49 = a8;
        *((_QWORD *)v30 + 4) = v101;
        *((_QWORD *)v30 + 5) = v102;
        *((_DWORD *)v30 + 12) = v138;
        v50 = *v49;
        *((_QWORD *)v30 + 10) = a12;
        v51 = a9;
        *(struct _GUID *)(v30 + 52) = v50;
        *((_DWORD *)v30 + 25) = v51;
        *((_QWORD *)v30 + 13) = a1;
        *((_DWORD *)v30 + 24) = v39;
        GetSystemTimeAsFileTime((LPFILETIME)v30 + 14);
        _InterlockedIncrement64((volatile signed __int64 *)a1 + 8);
        v52 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)*((_QWORD *)a1 + 29);
        if ( *v52 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)a1 + 224) )
          __fastfail(3u);
        *(_QWORD *)v30 = (char *)a1 + 224;
        *((_QWORD *)v30 + 1) = v52;
        *v52 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v30;
        *((_QWORD *)a1 + 29) = v30;
        if ( *(_QWORD *)(*((_QWORD *)a1 + 3) + 48LL) )
          UbpmpMaintenanceTaskStartedCallout(a1, v30);
        UbpmTriggerConsumerPublishStateChange(a1);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_SqqddL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v138,
            v54,
            *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
            (char)v30,
            (char)v101,
            v96,
            v138,
            a9);
        if ( !v135 )
        {
          UbpmUtilsGetAccountNamesFromSid((_DWORD)v23, 1, 0, 0, (__int64)&P);
          v55 = P;
          v56 = L"(NONE)";
          if ( P )
            v56 = (const unsigned __int16 *)P;
          v57 = EventManager::EvtReport(g_hTaskEventManager, &JOB_START, v27, v56, v49, cchCount2, v94);
          v58 = (unsigned __int16)v57;
          if ( v57 >= 0 )
            v58 = 0;
          TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &JOB_START, v58);
          if ( v55 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v55);
        }
        v59 = v101;
        LOBYTE(v60) = 0;
        if ( v101 )
        {
          v61 = v102;
          RtlAcquireSRWLockShared((char *)v101 + 64);
          if ( (!v61 || (*((_BYTE *)v61 + 104) & 1) == 0) && (*((_BYTE *)v59 + 104) & 4) == 0 )
            v60 = *((_DWORD *)v59 + 8);
          RtlReleaseSRWLockShared((char *)v59 + 64);
        }
        v62 = (const unsigned __int16 *)*((_QWORD *)v137 + 1);
        if ( !v62 )
          v62 = L"NULL";
        v63 = EventManager::EvtReport(g_hTaskEventManager, v53, v27, v62, a8, v60, v94, v95);
        v64 = (unsigned __int16)v63;
        if ( v63 >= 0 )
          v64 = 0;
        TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", ACTION_START, v64);
        v30 = 0;
      }
    }
LABEL_65:
    if ( v34 > 0 )
    {
LABEL_86:
      v65 = (unsigned __int16)v34 | 0x80070000;
      goto LABEL_67;
    }
LABEL_66:
    v65 = (unsigned int)v34;
LABEL_67:
    LOBYTE(v32) = 1;
    UbpmpTriggerConsumerReportResult(a1, v65, v32);
    if ( (_BYTE)pSid )
    {
      dword_18004FFE8 = 0;
      RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
    }
    if ( v105 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v105);
    if ( v106 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v106);
    if ( v30 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
    return (unsigned int)v34;
  }
  SetLastError(8u);
  v67 = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
      v67);
  return v67;
}

```

## disassembly

```asm
0x180007000  mov     [rsp-8+arg_18], r9d
0x180007005  mov     [rsp-8+arg_10], r8
0x18000700a  mov     [rsp-8+arg_8], rdx
0x18000700f  push    rbp
0x180007010  push    rbx
0x180007011  push    rsi
0x180007012  push    rdi
0x180007013  push    r12
0x180007015  push    r13
0x180007017  push    r14
0x180007019  push    r15
0x18000701b  lea     rbp, [rsp-0D8h]
0x180007023  sub     rsp, 1D8h
0x18000702a  mov     r12, r8
0x18000702d  mov     r15, rcx
0x180007030  xor     edi, edi
0x180007032  lea     rcx, [rbp+110h+var_F0]; void *
0x180007036  mov     r8d, 0A8h; Size
0x18000703c  mov     [rsp+210h+var_1C0], di
0x180007041  xor     edx, edx; Val
0x180007043  call    memset_0
0x180007048  mov     rbx, [rbp+110h+pSid]
0x18000704f  xorps   xmm0, xmm0
0x180007052  xor     eax, eax
0x180007054  mov     [rbp+110h+var_100], rax
0x180007058  movups  [rbp+110h+var_170], xmm0
0x18000705c  movups  [rbp+110h+var_160], xmm0
0x180007060  movups  xmmword ptr [rbp+110h+Sid], xmm0
0x180007064  movups  [rbp+110h+var_140], xmm0
0x180007068  movups  [rbp+110h+var_130], xmm0
0x18000706c  movups  [rbp+110h+var_120], xmm0
0x180007070  movups  [rbp+110h+var_110], xmm0
0x180007074  test    rbx, rbx
0x180007077  jz      loc_1800077D1
0x18000707d  mov     rcx, rbx; pSid
0x180007080  call    cs:__imp_GetLengthSid
0x180007087  nop     dword ptr [rax+rax+00h]
0x18000708c  mov     r14d, eax
0x18000708f  mov     rax, [r15+18h]
0x180007093  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000709a  mov     [rsp+210h+P], rdi
0x18000709f  mov     [rbp+110h+var_188], rdi
0x1800070a3  mov     [rbp+110h+var_180], rdi
0x1800070a7  mov     [rsp+210h+var_1A8], rdi
0x1800070ac  mov     [rsp+210h+var_1A0], rdi
0x1800070b1  mov     [rbp+110h+arg_0], di
0x1800070b8  mov     [rsp+210h+Status], edi
0x1800070bc  mov     rdi, [rax+8]
0x1800070c0  test    rdi, rdi
0x1800070c3  jz      short loc_1800070E3
0x1800070c5  mov     rax, r13
0x1800070c8  nop     dword ptr [rax+rax+00000000h]
0x1800070d0  inc     rax
0x1800070d3  cmp     word ptr [rdi+rax*2], 0
0x1800070d8  jnz     short loc_1800070D0
0x1800070da  cmp     eax, 8
0x1800070dd  ja      loc_1800078AE
0x1800070e3  mov     rcx, gs:60h
0x1800070ec  lea     r8d, [r14+78h]; Size
0x1800070f0  mov     edx, 8; Flags
0x1800070f5  mov     rcx, [rcx+30h]; HeapHandle
0x1800070f9  call    cs:__imp_RtlAllocateHeap
0x180007100  nop     dword ptr [rax+rax+00h]
0x180007105  mov     rsi, rax
0x180007108  test    rax, rax
0x18000710b  jz      loc_180007784
0x180007111  test    rbx, rbx
0x180007114  jnz     loc_1800078F3
0x18000711a  mov     byte ptr [rbp+110h+pSid], 0
0x180007121  mov     [rsi+8], rsi
0x180007125  mov     [rsi], rsi
0x180007128  mov     rcx, cs:WPP_GLOBAL_Control
0x18000712f  lea     rax, WPP_GLOBAL_Control
0x180007136  cmp     rcx, rax
0x180007139  jnz     loc_18000785F
0x18000713f  mov     rcx, r15
0x180007142  call    UbpmpActionContextCleanup
0x180007147  mov     rax, [r15+18h]
0x18000714b  cmp     qword ptr [rax+30h], 0
0x180007150  jz      short loc_18000717E
0x180007152  lea     rcx, g_MaintenanceLaunchLock
0x180007159  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007160  nop     dword ptr [rax+rax+00h]
0x180007165  call    cs:__imp_GetCurrentThreadId
0x18000716c  nop     dword ptr [rax+rax+00h]
0x180007171  mov     cs:dword_18004FFE8, eax
0x180007177  mov     byte ptr [rbp+110h+pSid], 1
0x18000717e  mov     rax, [rbp+110h+arg_48]
0x180007185  lea     r8, [rsp+210h+var_1C0]
0x18000718a  mov     edx, [rbp+110h+arg_40]
0x180007190  lea     rcx, [rbp+110h+var_170]
0x180007194  mov     r9, [rbp+110h+arg_38]
0x18000719b  mov     qword ptr [rbp+110h+var_130], rax
0x18000719f  mov     eax, [rbp+110h+arg_50]
0x1800071a5  mov     dword ptr [rbp+110h+var_130+8], eax
0x1800071a8  mov     rax, [rbp+110h+arg_58]
0x1800071af  mov     qword ptr [rbp+110h+var_120], rax
0x1800071b3  movzx   eax, [rbp+110h+arg_60]
0x1800071ba  mov     byte ptr [rbp+110h+var_120+8], al
0x1800071bd  mov     rax, [rbp+110h+arg_68]
0x1800071c4  mov     qword ptr [rbp+110h+var_110], rax
0x1800071c8  movzx   eax, [rbp+110h+arg_90]
0x1800071cf  mov     byte ptr [rbp+110h+var_110+0Ch], al
0x1800071d2  mov     rax, [rbp+110h+arg_98]
0x1800071d9  mov     [rbp+110h+var_100], rax
0x1800071dd  mov     eax, [rbp+110h+arg_80]
0x1800071e3  mov     dword ptr [rbp+110h+var_110+8], eax
0x1800071e6  mov     eax, [rbp+110h+arg_70]
0x1800071ec  mov     dword ptr [rbp+110h+var_140+8], edx
0x1800071ef  mov     edx, [rbp+110h+arg_18]
0x1800071f5  mov     dword ptr [rbp+110h+Sid], eax
0x1800071f8  mov     rax, [rbp+110h+arg_78]
0x1800071ff  mov     qword ptr [rbp+110h+var_170+8], r12
0x180007203  mov     r12, [rbp+110h+arg_A0]
0x18000720a  mov     qword ptr [rbp+110h+var_140], r9
0x18000720e  lea     r9, [rbp+110h+arg_0]
0x180007215  mov     dword ptr [rbp+110h+Sid+4], edx
0x180007218  mov     rdx, [rbp+110h+arg_8]
0x18000721f  mov     qword ptr [rbp+110h+var_160+8], rax
0x180007223  mov     qword ptr [rbp+110h+var_170], r15
0x180007227  mov     [rbp+110h+Sid+8], rbx
0x18000722b  mov     [rsp+210h+phkResult], r12
0x180007230  call    UbpmConstraintsCheck
0x180007235  mov     r14d, eax
0x180007238  test    eax, eax
0x18000723a  jnz     loc_18000796C
0x180007240  cmp     [r12], al
0x180007244  jnz     loc_180007BD8
0x18000724a  mov     rdx, [rbp+110h+Sid+8]; Sid
0x18000724e  test    rdx, rdx
0x180007251  jz      loc_1800072FA
0x180007257  xor     eax, eax
0x180007259  lea     r8, [rbp+110h+lpSubKey]; unsigned __int16 **
0x18000725d  mov     [rbp+110h+hKey], rax
0x180007261  xor     r12b, r12b
0x180007264  mov     [rbp+110h+lpSubKey], rax
0x180007268  mov     dword ptr [rsp+210h+Data], eax
0x18000726c  mov     [rsp+210h+Type], eax
0x180007270  mov     [rsp+210h+cbData], eax
0x180007274  mov     rax, qword ptr [rbp+110h+var_170]
0x180007278  mov     rcx, [rax+18h]
0x18000727c  mov     rcx, [rcx+8]; lpString1
0x180007280  call    ?UbpmpGetConsumerUserPropertiesKeyName@@YAKPEBGPEAXPEAPEAG@Z; UbpmpGetConsumerUserPropertiesKeyName(ushort const *,void *,ushort * *)
0x180007285  mov     r14, [rbp+110h+lpSubKey]
0x180007289  test    eax, eax
0x18000728b  jnz     short loc_1800072C1
0x18000728d  lea     rax, [rbp+110h+hKey]
0x180007291  mov     r9d, 1; samDesired
0x180007297  xor     r8d, r8d; ulOptions
0x18000729a  mov     [rsp+210h+phkResult], rax; struct _GUID *
0x18000729f  mov     rdx, r14; lpSubKey
0x1800072a2  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800072a9  call    cs:__imp_RegOpenKeyExW
0x1800072b0  nop     dword ptr [rax+rax+00h]
0x1800072b5  lea     ecx, [rax-2]
0x1800072b8  cmp     ecx, 1
0x1800072bb  ja      loc_180007CEF
0x1800072c1  mov     rcx, [rbp+110h+hKey]; hKey
0x1800072c5  test    rcx, rcx
0x1800072c8  jnz     loc_180007D99
0x1800072ce  test    r14, r14
0x1800072d1  jz      short loc_1800072F1
0x1800072d3  mov     rcx, gs:60h
0x1800072dc  mov     r8, r14; P
0x1800072df  xor     edx, edx; Flags
0x1800072e1  mov     rcx, [rcx+30h]; HeapHandle
0x1800072e5  call    cs:__imp_RtlFreeHeap
0x1800072ec  nop     dword ptr [rax+rax+00h]
0x1800072f1  test    r12b, r12b
0x1800072f4  jnz     loc_180007CA4
0x1800072fa  mov     r12d, [rbp+110h+arg_80]
0x180007301  mov     r14d, [rbp+110h+arg_40]
0x180007308  cmp     r12d, 0FFFFh
0x18000730f  jnz     loc_1800077D9
0x180007315  mov     eax, [r15+2Ch]
0x180007319  mov     r8, [r15+18h]
0x18000731d  mov     rcx, [rbp+110h+arg_10]
0x180007324  mov     r11, [rbp+110h+arg_38]
0x18000732b  mov     [rbp+110h+var_C8], eax
0x18000732e  mov     [rbp+110h+var_F0], rcx
0x180007332  mov     [rbp+110h+var_D0], r11
0x180007336  mov     rax, [r8]
0x180007339  mov     [rbp+110h+var_E8], rax
0x18000733d  mov     [rbp+110h+var_E0], rdi
0x180007341  mov     rax, [r8+8]
0x180007345  mov     [rbp+110h+var_D8], rax
0x180007349  mov     rax, [rbp+110h+arg_48]
0x180007350  mov     [rbp+110h+var_C0], rax
0x180007354  mov     eax, [rbp+110h+arg_18]
0x18000735a  mov     [rbp+110h+var_B8], eax
0x18000735d  movzx   eax, [rsp+210h+var_1C0]
0x180007362  mov     [rbp+110h+var_C4], ax
0x180007366  mov     rax, [rbp+110h+arg_30]
0x18000736d  mov     [rbp+110h+var_A8], rax
0x180007371  mov     rax, [rcx+20h]
0x180007375  mov     [rbp+110h+var_B0], rbx
0x180007379  test    rax, rax
0x18000737c  jz      loc_180007C1B
0x180007382  mov     eax, [rax+14h]
0x180007385  mov     [rbp+110h+var_9C], eax
0x180007388  movzx   r9d, [rbp+110h+arg_60]
0x180007390  movzx   edx, [rbp+110h+arg_0]
0x180007397  mov     rax, [rbp+110h+arg_58]
0x18000739e  mov     r10, [rbp+110h+arg_68]
0x1800073a5  mov     [rbp+110h+var_98], rax
0x1800073a9  cmp     dx, r9w
0x1800073ad  jnb     loc_18000788E
0x1800073b3  mov     rcx, [r10+rdx*8]
0x1800073b7  mov     [rbp+110h+var_90], rcx
0x1800073be  movzx   ecx, [rbp+110h+arg_90]
0x1800073c5  mov     [rbp+110h+var_68], r14d
0x1800073cc  cmp     dx, cx
0x1800073cf  jb      loc_180007ACF
0x1800073d5  mov     rdx, [rbp+110h+arg_98]
0x1800073dc  mov     [rbp+110h+var_60], 0
0x1800073e7  mov     r14, [rbp+110h+arg_78]
0x1800073ee  mov     [rbp+110h+var_88], r12d
0x1800073f5  test    byte ptr [r8+10h], 2
0x1800073fa  jz      short loc_18000742A
0x1800073fc  mov     eax, [rbp+110h+arg_70]
0x180007402  mov     [rbp+110h+var_84], eax
0x180007408  mov     [rbp+110h+var_78], r9b
0x18000740f  mov     [rbp+110h+var_70], r10
0x180007416  mov     [rbp+110h+var_58], cl
0x18000741c  mov     [rbp+110h+var_50], rdx
0x180007423  mov     [rbp+110h+var_80], r14
0x18000742a  test    rbx, rbx
0x18000742d  jz      loc_180007AF0
0x180007433  mov     r9, [rbp+110h+arg_88]; void *
0x18000743a  mov     edx, r12d; unsigned int
0x18000743d  mov     r8d, [rbp+110h+arg_40]; unsigned int
0x180007444  mov     rcx, r15; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180007447  mov     [rsp+210h+phkResult], r11; struct _GUID *
0x18000744c  call    ?UbpmpActionLogTriggered@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@KKPEAXPEAU_GUID@@@Z; UbpmpActionLogTriggered(_UBPM_TRIGGER_CONSUMER_BLOCK *,ulong,ulong,void *,_GUID *)
0x180007451  cmp     r12d, 0FFFFh
0x180007458  jz      short loc_18000747E
0x18000745a  mov     rax, [r15+18h]
0x18000745e  lea     rdx, [r12+r12*2]
0x180007462  add     rdx, rdx
0x180007465  mov     rcx, [rax+18h]
0x180007469  cmp     dword ptr [rcx+rdx*8], 1
0x18000746d  jnz     short loc_18000747E
0x18000746f  mov     rcx, [rcx+rdx*8+8]
0x180007474  cmp     dword ptr [rcx+38h], 1
0x180007478  jz      loc_1800079B4
0x18000747e  mov     r13, [rbp+110h+arg_10]
0x180007485  mov     rax, [rbp+110h+var_F0]
0x180007489  mov     rcx, [rax+18h]
0x18000748d  xor     eax, eax
0x18000748f  mov     edx, [rcx]
0x180007491  lea     rcx, [rbp+110h+var_F0]; struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *
0x180007495  mov     [rsp+210h+var_1A8], rax
0x18000749a  mov     [rsp+210h+var_1A0], rax
0x18000749f  lea     eax, [rdx-1]
0x1800074a2  cmp     eax, 1
0x1800074a5  ja      loc_180007C33
0x1800074ab  mov     rdx, [rbp+110h+arg_28]; void **
0x1800074b2  lea     r9, [rsp+210h+var_1A0]; struct _UBPM_TASK_HOST_TASK_CONTEXT **
0x1800074b7  lea     r8, [rsp+210h+var_1A8]; struct _UBPM_TASK_HOST_CONTEXT_BLOCK **
0x1800074bc  call    ?UbpmpHostLaunchTaskExe@@YAKPEAU_UBPM_TASK_LAUNCH_INPUT_PARAMS@@PEAPEAXPEAPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_UBPM_TASK_HOST_TASK_CONTEXT@@@Z; UbpmpHostLaunchTaskExe(_UBPM_TASK_LAUNCH_INPUT_PARAMS *,void * *,_UBPM_TASK_HOST_CONTEXT_BLOCK * *,_UBPM_TASK_HOST_TASK_CONTEXT * *)
0x1800074c1  cmp     [rbp+110h+arg_0], 0
0x1800074c9  mov     r14d, eax
0x1800074cc  jnz     short loc_1800074DB
0x1800074ce  test    dword ptr [rbp+110h+var_140+8], 80000h
0x1800074d5  jnz     loc_180007C6A
0x1800074db  test    r14d, r14d
0x1800074de  jnz     loc_180007B15
0x1800074e4  mov     [rsi+18h], r13
0x1800074e8  lea     rcx, [rsi+70h]; lpSystemTimeAsFileTime
0x1800074ec  mov     rax, [rsp+210h+var_1A8]
0x1800074f1  mov     r13, [rbp+110h+arg_38]
0x1800074f8  mov     [rsi+20h], rax
0x1800074fc  mov     rax, [rsp+210h+var_1A0]
0x180007501  mov     [rsi+28h], rax
0x180007505  mov     eax, [rbp+110h+arg_18]
0x18000750b  mov     [rsi+30h], eax
0x18000750e  movups  xmm0, xmmword ptr [r13+0]
0x180007513  mov     rax, [rbp+110h+arg_58]
0x18000751a  mov     [rsi+50h], rax
0x18000751e  mov     eax, [rbp+110h+arg_40]
0x180007524  movups  xmmword ptr [rsi+34h], xmm0
0x180007528  mov     [rsi+64h], eax
0x18000752b  mov     [rsi+68h], r15
0x18000752f  mov     [rsi+60h], r12d
0x180007533  call    cs:__imp_GetSystemTimeAsFileTime
0x18000753a  nop     dword ptr [rax+rax+00h]
0x18000753f  lock inc qword ptr [r15+40h]
0x180007544  lea     rax, [r15+0E0h]
0x18000754b  mov     rcx, [rax+8]
0x18000754f  cmp     [rcx], rax
0x180007552  jnz     loc_180007C57
0x180007558  mov     [rsi], rax
0x18000755b  mov     [rsi+8], rcx
0x18000755f  mov     [rcx], rsi
0x180007562  mov     [rax+8], rsi
0x180007566  mov     rax, [r15+18h]
0x18000756a  cmp     qword ptr [rax+30h], 0
0x18000756f  jnz     loc_18000789E
0x180007575  mov     rcx, r15
0x180007578  call    UbpmTriggerConsumerPublishStateChange
  ... truncated ...
```
