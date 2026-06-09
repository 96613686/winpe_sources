# UbpmpHostLaunchTaskExe(_UBPM_TASK_LAUNCH_INPUT_PARAMS *,void * *,_UBPM_TASK_HOST_CONTEXT_BLOCK * *,_UBPM_TASK_HOST_TASK_CONTEXT * *)

- ea: `0x18001da20`
- end: `0x18001eaed`
- name: `?UbpmpHostLaunchTaskExe@@YAKPEAU_UBPM_TASK_LAUNCH_INPUT_PARAMS@@PEAPEAXPEAPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_UBPM_TASK_HOST_TASK_CONTEXT@@@Z`
- size: `4301`
- prototype: `unsigned int __fastcall(struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *, void **, struct _UBPM_TASK_HOST_CONTEXT_BLOCK **, struct _UBPM_TASK_HOST_TASK_CONTEXT **)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007000`
- `0x18000d9bc`

## callees

- `0x180003da0`
- `0x18000467c`
- `0x180004c30`
- `0x1800053a0`
- `0x180007e9c`
- `0x18001131c`
- `0x180012b1c`
- `0x180013c90`
- `0x18001af64`
- `0x18001ca84`
- `0x18001cb40`
- `0x18001cd98`
- `0x18001d0ec`
- `0x18001d1d8`
- `0x18001d230`
- `0x18001d620`
- `0x18001d820`
- `0x18001da20`
- `0x18001eaf4`
- `0x18001ff30`
- `0x180032f78`
- `0x1800351ec`
- `0x180036c60`
- `0x18003e8b0`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e972`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e972`
- `ntdll!NtQueryInformationProcess` at `0x18001dbe1`
- `ntdll!NtQueryInformationProcess` at `0x18001dbe1`
- `ntdll!EtwEventWrite` at `0x18001e15a`
- `ntdll!EtwEventWrite` at `0x18001e15a`
- `ntdll!EtwEventEnabled` at `0x18001e09a`
- `ntdll!EtwEventEnabled` at `0x18001e09a`
- `ntdll!RtlFreeHeap` at `0x18001dd4c`
- `ntdll!RtlFreeHeap` at `0x18001dd70`
- `ntdll!RtlFreeHeap` at `0x18001ddec`
- `ntdll!RtlFreeHeap` at `0x18001dd4c`
- `ntdll!RtlFreeHeap` at `0x18001dd70`
- `ntdll!RtlFreeHeap` at `0x18001ddec`
- `ntdll!RtlNtStatusToDosError` at `0x18001e3c9`
- `ntdll!RtlNtStatusToDosError` at `0x18001e3c9`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001e34a`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001e34a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001e329`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001e329`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001de84`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001df6b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001e237`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001e73e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001de84`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001df6b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001e237`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001e73e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001df3d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e045`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e29c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e792`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e9b9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001df3d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e045`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e29c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e792`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e9b9`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001e6ca`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001e6ca`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e4ad`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e887`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e4ad`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e887`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001e1c6`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001e1c6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001ea3d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001ea3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001de90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001df77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e243`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e74a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001de90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001df77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e243`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e74a`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x18001e05e`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x18001e05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001de07`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001de07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea89`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18001e019`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18001e019`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18001e272`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18001e272`
- `profapi!__imp_UnloadProfileBasic` at `0x18001eaaf`
- `profapi!__imp_UnloadProfileBasic` at `0x18001eaaf`

## string_xrefs

- `0x18001e19a`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18001e173`: `EventWrite error`
- `0x18001e51e`: `taskhostw.exe`

## pseudocode

```c
__int64 __fastcall UbpmpHostLaunchTaskExe(
        struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *a1,
        void **a2,
        struct _UBPM_TASK_HOST_CONTEXT_BLOCK **a3,
        struct _UBPM_TASK_HOST_TASK_CONTEXT **a4)
{
  __int64 v4; // rax
  _DWORD *v6; // r12
  _DWORD *v7; // rcx
  bool v8; // zf
  int v9; // r14d
  int v10; // esi
  bool v11; // r13
  __int16 v12; // r15
  unsigned int v13; // r9d
  unsigned __int16 *v14; // r8
  wchar_t *v15; // r15
  struct _UBPM_ACTION_EXE_LAUNCH_PARAMS *v16; // rdx
  const unsigned __int16 *v17; // rcx
  int v18; // esi
  void *v19; // r9
  unsigned int Host; // edi
  int v21; // eax
  int v22; // edi
  DWORD *v23; // rdx
  _QWORD *v24; // rcx
  void **v25; // rsi
  __int64 v27; // rax
  unsigned int v28; // r13d
  PVOID v29; // r12
  PVOID v30; // r15
  HANDLE v31; // r14
  unsigned int v32; // esi
  HANDLE v33; // rdi
  DWORD CurrentThreadId; // eax
  _QWORD *v35; // rcx
  char *v36; // rdx
  unsigned __int64 v37; // rax
  void **v38; // rsi
  unsigned int *v39; // rsi
  DWORD v40; // eax
  struct _LIST_ENTRY *Flink; // rcx
  unsigned int v42; // eax
  struct _LIST_ENTRY **p_Blink; // rdi
  __int64 v44; // rcx
  int v45; // eax
  DWORD PriorityClass; // eax
  __int64 *v47; // rdi
  EventManager *v48; // rsi
  __int64 v49; // rcx
  __int64 v50; // rax
  unsigned int v51; // eax
  EventManager *v52; // rcx
  signed int v53; // edi
  __int64 v54; // r8
  HINSTANCE v55; // rdx
  void *v56; // rax
  void *v57; // rsi
  int v58; // r12d
  _DWORD *v59; // rdi
  __int64 v60; // rax
  char *v61; // rcx
  void *v62; // rcx
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v63; // rax
  __int64 v64; // r9
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v65; // rcx
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v66; // rax
  int v67; // edx
  __int64 v68; // r9
  int v69; // ecx
  char v70; // al
  _QWORD *v71; // rcx
  __int64 v72; // rdx
  int v73; // edx
  DWORD v74; // eax
  struct _LIST_ENTRY *v75; // rdi
  _QWORD *v76; // rcx
  __int64 v77; // rdx
  char *v78; // rcx
  void *v79; // rcx
  unsigned int v80; // [rsp+30h] [rbp-108h]
  int v81; // [rsp+40h] [rbp-F8h]
  size_t Size; // [rsp+50h] [rbp-E8h]
  char Sizea; // [rsp+50h] [rbp-E8h]
  const unsigned __int16 *Src; // [rsp+58h] [rbp-E0h]
  void *v85; // [rsp+B8h] [rbp-80h] BYREF
  __int64 v86; // [rsp+C0h] [rbp-78h] BYREF
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v87; // [rsp+C8h] [rbp-70h] BYREF
  unsigned int v88; // [rsp+D0h] [rbp-68h] BYREF
  int v89; // [rsp+D8h] [rbp-60h] BYREF
  HANDLE ProcessHandle; // [rsp+E0h] [rbp-58h] BYREF
  struct _LIST_ENTRY **v91; // [rsp+E8h] [rbp-50h] BYREF
  unsigned int v92; // [rsp+F0h] [rbp-48h] BYREF
  struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT *v93; // [rsp+F8h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+100h] [rbp-38h] BYREF
  int ProcessInformation; // [rsp+108h] [rbp-30h] BYREF
  int v96; // [rsp+10Ch] [rbp-2Ch]
  int v97; // [rsp+110h] [rbp-28h]
  void **v98; // [rsp+118h] [rbp-20h]
  HKEY v99; // [rsp+120h] [rbp-18h] BYREF
  PVOID v100; // [rsp+128h] [rbp-10h] BYREF
  PVOID P; // [rsp+130h] [rbp-8h] BYREF
  PVOID v102; // [rsp+138h] [rbp+0h] BYREF
  char *v103; // [rsp+140h] [rbp+8h]
  unsigned __int64 v104; // [rsp+148h] [rbp+10h] BYREF
  HANDLE hThread; // [rsp+150h] [rbp+18h] BYREF
  wchar_t *v106; // [rsp+158h] [rbp+20h]
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK **v107; // [rsp+160h] [rbp+28h]
  struct _UBPM_TASK_HOST_TASK_CONTEXT **v108; // [rsp+168h] [rbp+30h]
  char *v109; // [rsp+170h] [rbp+38h]
  _QWORD *v110; // [rsp+178h] [rbp+40h]
  HANDLE EventW; // [rsp+180h] [rbp+48h]
  PVOID v112; // [rsp+188h] [rbp+50h]
  unsigned __int64 v113; // [rsp+190h] [rbp+58h]
  struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT *v114; // [rsp+198h] [rbp+60h]
  HKEY v115; // [rsp+1A0h] [rbp+68h]
  __int64 *v116; // [rsp+1A8h] [rbp+70h] BYREF
  __int64 v117; // [rsp+1B0h] [rbp+78h]
  __int64 *v118; // [rsp+1B8h] [rbp+80h]
  __int64 v119; // [rsp+1C0h] [rbp+88h]
  struct _LIST_ENTRY ***v120; // [rsp+1C8h] [rbp+90h]
  __int64 v121; // [rsp+1D0h] [rbp+98h]
  int *v122; // [rsp+1D8h] [rbp+A0h]
  __int64 v123; // [rsp+1E0h] [rbp+A8h]

  v4 = *(_QWORD *)a1;
  v98 = a2;
  v6 = (_DWORD *)((char *)a1 + 80);
  v85 = 0;
  ProcessHandle = 0;
  v88 = 0;
  hObject = 0;
  hThread = 0;
  v100 = 0;
  v7 = *(_DWORD **)(v4 + 24);
  v108 = a4;
  v107 = a3;
  v8 = *v7 == 2;
  v103 = (char *)a1 + 80;
  if ( v8 || *v6 )
  {
    v103 = (char *)a1 + 80;
    v9 = 1;
  }
  else
  {
    v9 = 0;
  }
  v10 = v7[12];
  v11 = 0;
  v89 = v9;
  v12 = 0;
  v87 = 0;
  LODWORD(v86) = 0;
  v99 = 0;
  P = 0;
  v92 = 0;
  v102 = 0;
  v93 = 0;
  v104 = 0;
  ProcessInformation = 0;
  if ( v9 )
  {
    while ( 1 )
    {
      LOBYTE(a4) = *v6 == 0;
      Host = UbpmpFindHost(
               *((_QWORD *)a1 + 3),
               *(_QWORD *)(*(_QWORD *)a1 + 24LL),
               *((_DWORD *)a1 + 14),
               (int)a4,
               *((PSID *)a1 + 8),
               (__int64)&v85,
               (__int64)&v86);
      if ( Host )
        break;
      RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
      while ( (*((_BYTE *)v85 + 104) & 0x20) != 0 )
        SleepConditionVariableSRW(&g_cvHostStartedup, &g_TaskHostContextListLock, 0xFFFFFFFF, 1u);
      RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
      if ( (_DWORD)v86 )
      {
        UbpmpDecrementRefAndDelete(&v85, 1);
        v85 = 0;
        Sleep(0x64u);
        if ( (unsigned __int16)++v12 >= 0x2BCu )
        {
          Host = 1235;
          v76 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_13;
          v77 = 34;
          goto LABEL_150;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids);
      }
      else
      {
        v64 = 2;
        if ( *v6 )
          LOWORD(v64) = 4;
        Host = UbpmpSendCommandGetResponse(v85, a1, &v87, v64);
        if ( !Host )
        {
          v65 = v87;
          v66 = (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)v85;
          *v108 = v87;
          *v107 = v66;
          if ( !*v6 )
            v11 = v65 == 0;
          v85 = 0;
          v87 = 0;
          goto LABEL_13;
        }
        if ( Host != 1237 )
        {
          v71 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_13;
          v72 = 36;
LABEL_128:
          WPP_SF_dd(v71[2], v72, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, *((unsigned int *)v85 + 8));
          goto LABEL_13;
        }
        UbpmpDecrementRefAndDelete(&v85, 1);
        v85 = 0;
        Sleep(0x64u);
        if ( (unsigned __int16)++v12 >= 0x2BCu )
        {
          Host = 1235;
          v76 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_13;
          v77 = 37;
          goto LABEL_150;
        }
      }
    }
    if ( Host != 1168 )
    {
      v76 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v77 = 38;
LABEL_150:
      WPP_SF_d(v76[2], v77, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, Host);
      goto LABEL_13;
    }
    v14 = L"{222A245B-E637-4AE9-A93F-A59CA119A75E}";
    v15 = L"taskhostw.exe";
    v13 = *((unsigned __int8 *)v85 + 432);
    if ( !*((_BYTE *)v85 + 432) )
      v14 = 0;
  }
  else
  {
    v13 = 0;
    v14 = (unsigned __int16 *)*((_QWORD *)a1 + 12);
    v15 = *(wchar_t **)(*(_QWORD *)(v4 + 24) + 8LL);
  }
  v16 = *(struct _UBPM_ACTION_EXE_LAUNCH_PARAMS **)(*(_QWORD *)a1 + 24LL);
  Src = (const unsigned __int16 *)*((_QWORD *)a1 + 18);
  Sizea = *((_DWORD *)a1 + 34);
  v17 = (const unsigned __int16 *)*((_QWORD *)a1 + 3);
  v81 = v10;
  v18 = (int)v98;
  v80 = v13;
  v19 = (void *)*((_QWORD *)a1 + 9);
  v106 = v15;
  LODWORD(v86) = UbpmpLaunchAction(
                   v17,
                   v16,
                   v98,
                   v19,
                   v15,
                   v80,
                   0,
                   v81,
                   v14,
                   Sizea,
                   Src,
                   &ProcessHandle,
                   &v88,
                   &hObject,
                   &hThread,
                   &v100,
                   &v99,
                   &P,
                   &v92,
                   (void ***)&v102,
                   &v104,
                   &v93);
  Host = v86;
  if ( (_DWORD)v86 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v67 = 39;
    goto LABEL_164;
  }
  v21 = NtQueryInformationProcess(ProcessHandle, ProcessSessionInformation, &ProcessInformation, 4u, 0);
  if ( v21 < 0 )
  {
    Host = RtlNtStatusToDosError(v21);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v67 = 40;
    goto LABEL_164;
  }
  v22 = ProcessInformation;
  LODWORD(v91) = ProcessInformation;
  if ( v9 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      Host = GetLastError();
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v67 = 41;
      goto LABEL_164;
    }
    v27 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 32LL);
    if ( v27 )
    {
      v69 = *(_DWORD *)(v27 + 32);
      LODWORD(v27) = *(_DWORD *)(v27 + 36);
      v97 = v69;
    }
    else
    {
      v97 = 0;
    }
    v28 = v92;
    v29 = P;
    v30 = v100;
    v31 = hObject;
    v32 = v88;
    v33 = ProcessHandle;
    v96 = v27;
    v114 = v93;
    v113 = v104;
    v112 = v102;
    v115 = v99;
    v110 = v85;
    v109 = (char *)v85 + 64;
    RtlAcquireSRWLockExclusive((char *)v85 + 64);
    CurrentThreadId = GetCurrentThreadId();
    v35 = v110;
    v36 = v109;
    *((_DWORD *)v109 + 2) = CurrentThreadId;
    v35[6] = EventW;
    *((_DWORD *)v35 + 66) = v96;
    *((_DWORD *)v35 + 67) = v97;
    *((_DWORD *)v35 + 48) = (_DWORD)v91;
    v35[50] = v112;
    v37 = v113;
    *((_DWORD *)v35 + 8) = v32;
    v38 = v98;
    v35[48] = v37;
    v35[53] = v114;
    v35[3] = v33;
    v35[32] = v31;
    v35[22] = v30;
    v35[23] = v29;
    *((_DWORD *)v35 + 98) = v28;
    if ( v38 )
    {
      v35[30] = v115;
      v35[31] = *v38;
      *v38 = 0;
    }
    *((_DWORD *)v36 + 2) = 0;
    RtlReleaseSRWLockExclusive(v36);
    v9 = v89;
    v11 = 0;
    v15 = v106;
    v6 = v103;
  }
  else
  {
    v23 = *(DWORD **)(*(_QWORD *)a1 + 32LL);
    if ( v23 )
      UbpmpSetProcessPriorities(ProcessHandle, v23[4], v23[6], v23[7]);
    LODWORD(v86) = UbpmpCreateTaskHostContextBlock(
                     0,
                     v18,
                     (_DWORD)a1,
                     (_DWORD)ProcessHandle,
                     v88,
                     v22,
                     (__int64)hObject,
                     (__int64)v100,
                     (__int64)P,
                     (__int64)v99,
                     v92,
                     (__int64)v102,
                     v104,
                     (__int64)v93,
                     (__int64)&v85);
    Host = v86;
    if ( (_DWORD)v86 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v67 = 42;
      goto LABEL_164;
    }
  }
  v39 = (unsigned int *)v85;
  v91 = 0;
  RtlAcquireSRWLockExclusive(&g_TaskHostJobObjectLock);
  v40 = GetCurrentThreadId();
  Flink = g_leJobObjectContextsHead.Flink;
  dword_180050080 = v40;
  while ( Flink != &g_leJobObjectContextsHead )
  {
    v42 = v39[48];
    p_Blink = &Flink[-1].Blink;
    v91 = &Flink[-1].Blink;
    if ( LODWORD(Flink[1].Blink) == v42 )
    {
      if ( v9 )
      {
        if ( v9 == 1 )
        {
          v70 = *((_BYTE *)v39 + 432);
          if ( v70 == 1 && *((_DWORD *)p_Blink + 9) == 1 )
            goto LABEL_57;
          if ( !v70 && *((_DWORD *)p_Blink + 9) == 2 )
            goto LABEL_57;
        }
      }
      else if ( !*((_DWORD *)p_Blink + 9) )
      {
        goto LABEL_57;
      }
    }
    Flink = Flink->Flink;
  }
  if ( v9 )
    v44 = 2 - (unsigned int)(*((_BYTE *)v39 + 432) != 0);
  else
    v44 = 0;
  v45 = CreateJobObjectContext(v44, v39[48], &v91);
  p_Blink = v91;
  if ( v45 )
    goto LABEL_52;
LABEL_57:
  if ( AssignProcessToJobObject(p_Blink[3], *((HANDLE *)v39 + 3)) )
  {
    *((_QWORD *)v39 + 52) = p_Blink;
    ++*(_DWORD *)p_Blink;
    goto LABEL_59;
  }
  GetLastError();
LABEL_52:
  if ( p_Blink && !*(_DWORD *)p_Blink && !*((_DWORD *)p_Blink + 1) )
    DestroyJobObjectContext(p_Blink);
LABEL_59:
  dword_180050080 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostJobObjectLock);
  if ( ProcessHandle )
  {
    PriorityClass = GetPriorityClass(ProcessHandle);
    v47 = (__int64 *)*((_QWORD *)a1 + 2);
    if ( !v47 )
      v47 = (__int64 *)*((_QWORD *)a1 + 3);
    v48 = g_hTaskEventManager;
    v89 = PriorityClass;
    LODWORD(v91) = v88;
    if ( *(_QWORD *)g_hTaskEventManager )
    {
      if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_hTaskEventManager, CREATED_TASK_PROCESS) )
        goto LABEL_120;
      v49 = -1;
      if ( v47 )
      {
        v116 = v47;
        v50 = -1;
        do
          v8 = *((_WORD *)v47 + ++v50) == 0;
        while ( !v8 );
        v117 = (unsigned int)(2 * v50 + 2);
      }
      else
      {
        v116 = &qword_1800439C0;
        v117 = 2;
      }
      if ( v15 )
      {
        v118 = (__int64 *)v15;
        do
          v8 = v15[++v49] == 0;
        while ( !v8 );
        v119 = (unsigned int)(2 * v49 + 2);
      }
      else
      {
        v118 = &qword_1800439C0;
        v119 = 2;
      }
      v120 = &v91;
      v121 = 4;
      v123 = 4;
      v122 = &v89;
      v51 = EtwEventWrite(*(_QWORD *)v48, CREATED_TASK_PROCESS, 4, &v116);
      v53 = v51;
      if ( v51 )
      {
        EventManager::LogIt(v52, L"EventWrite error", v51);
        if ( v53 > 0 )
          v53 = (unsigned __int16)v53 | 0x80070000;
      }
      else
      {
LABEL_120:
        v53 = 0;
      }
    }
    else
    {
      v53 = 1;
    }
    v54 = (unsigned __int16)v53;
    if ( v53 >= 0 )
      v54 = 0;
    TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", CREATED_TASK_PROCESS, v54);
  }
  ProcessHandle = 0;
  v100 = 0;
  P = 0;
  v99 = 0;
  v102 = 0;
  hObject = 0;
  v93 = 0;
  ResumeThread(hThread);
  if ( v9 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)v85 + 12);
    Host = UbpmUtilsSubmitThreadPoolWork(
             (void (*)(void *, unsigned __int8, void *))UbpmpConsumeHostCommandActionCallback,
             v85,
             1,
             0,
             0);
    if ( !Host )
    {
      v68 = 2;
      if ( *v6 )
        LOWORD(v68) = 4;
      LODWORD(v86) = UbpmpSendCommandGetResponse(v85, a1, &v87, v68);
      Host = v86;
      if ( (_DWORD)v86 )
      {
        v71 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_13;
        v72 = 44;
        goto LABEL_128;
      }
      if ( !*v6 )
        v11 = v87 == 0;
      goto LABEL_79;
    }
    UbpmpDecrementRefAndDelete(&v85, 1);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v67 = 43;
LABEL_164:
    WPP_SF_Sd(v24[2], v67, (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, (_DWORD)v15, Host);
    goto LABEL_13;
  }
LABEL_79:
  if ( **(_DWORD **)(*(_QWORD *)a1 + 24LL) != 2 )
    goto LABEL_82;
  v56 = v85;
  v57 = (void *)*((_QWORD *)v85 + 23);
  if ( !v57 )
    goto LABEL_83;
  v58 = *((_DWORD *)v85 + 8);
  if ( UbpmUtilsSidSupportsHardening(*((PSID *)v85 + 23)) )
  {
    RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
    v74 = GetCurrentThreadId();
    v75 = g_leTaskHostHardeningListHead.Flink;
    for ( dword_180050018 = v74; v75 != &g_leTaskHostHardeningListHead; v75 = v75->Flink )
    {
      if ( !v75[3].Flink && EqualSid(v57, v75[1].Blink) && !LODWORD(v75[3].Blink) )
        LODWORD(v75[3].Blink) = v58;
    }
    dword_180050018 = 0;
    RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
    v56 = v85;
  }
  else
  {
LABEL_82:
    v56 = v85;
  }
LABEL_83:
  if ( !v9 && (*((_DWORD *)a1 + 34) & 0x200000) != 0 )
  {
    UbpmUtilsSystemPowerOn(*((const unsigned __int16 **)a1 + 2), v55, (void **)v56 + 51);
    v56 = v85;
  }
  _InterlockedIncrement64((volatile signed __int64 *)v56 + 12);
  v59 = v85;
  RtlAcquireSRWLockExclusive((char *)v85 + 64);
  v59[18] = GetCurrentThreadId();
  v60 = RegisterWaitForSingleObjectEx(*((_QWORD *)v85 + 3), UbpmpTaskHostDead, v85, 0xFFFFFFFFLL, 8);
  *((_QWORD *)v85 + 5) = v60;
  if ( *((_QWORD *)v85 + 5) )
  {
    v61 = (char *)v85 + 64;
    *((_DWORD *)v85 + 18) = 0;
    RtlReleaseSRWLockExclusive(v61);
    v62 = v85;
    v63 = v87;
    *v107 = (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)v85;
    *v108 = v63;
    UbpmpHostStartStateActions(v62, 1);
    Host = v86;
    v85 = 0;
    v87 = 0;
    goto LABEL_13;
  }
  Host = GetLastError();
  v78 = (char *)v85 + 64;
  *((_DWORD *)v85 + 18) = 0;
  RtlReleaseSRWLockExclusive(v78);
  if ( **(_DWORD **)(*(_QWORD *)a1 + 24LL) == 2 )
    UbpmpInitPidInHardeningList(*((PSID *)v85 + 23));
  v79 = (void *)*((_QWORD *)v85 + 51);
  if ( v79 )
  {
    UbpmUtilsSystemPowerOff(v79);
    *((_QWORD *)v85 + 51) = 0;
  }
  v87 = 0;
  UbpmpDecrementRefAndDelete(&v85, 1);
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v67 = 45;
    goto LABEL_164;
  }
LABEL_13:
  if ( ProcessHandle )
  {
    TerminateProcess(ProcessHandle, Host);
    CloseHandle(ProcessHandle);
  }
  v25 = v98;
  if ( v93 )
    UbpmpDecrementAppContainerRefAndDelete(&v93);
  if ( hObject )
    CloseHandle(hObject);
  if ( hThread )
    CloseHandle(hThread);
  if ( v99 && v25 && *v25 )
    UnloadProfileBasic(*v25);
  if ( v85 )
  {
    UbpmpHostStartStateActions(v85, Host == 0);
    UbpmpDecrementRefAndDelete(&v85, 1);
  }
  if ( v100 != pSid && v100 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v102 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v102);
  if ( v87 )
    UbpmpDecrementTaskRefAndDelete(&v87);
  if ( v11 || Host )
  {
    v73 = *((unsigned __int16 *)a1 + 22);
    if ( (_WORD)v73 )
    {
      LODWORD(Size) = *((_DWORD *)a1 + 27);
      UbpmRunNextSerializedAction(
        *((_QWORD *)a1 + 1),
        v73,
        *((_QWORD *)a1 + 4),
        *((_DWORD *)a1 + 10),
        *((_QWORD *)a1 + 6),
        *((_DWORD *)a1 + 14),
        *((PSID *)a1 + 8),
        *((_QWORD *)a1 + 11),
        *((_DWORD *)a1 + 26),
        Size,
        *((void **)a1 + 14),
        *((_BYTE *)a1 + 120),
        *((unsigned __int16 ***)a1 + 16),
        *((_DWORD *)a1 + 34),
        *((_BYTE *)a1 + 152),
        *((unsigned __int16 ***)a1 + 20));
    }
  }
  return Host;
}

```

## disassembly

```asm
0x18001da20  mov     r11, rsp
0x18001da23  push    rbp
0x18001da24  push    rbx
0x18001da25  lea     rbp, [r11-108h]
0x18001da2c  sub     rsp, 228h
0x18001da33  mov     rax, cs:__security_cookie
0x18001da3a  xor     rax, rsp
0x18001da3d  mov     [rbp+100h+var_50], rax
0x18001da44  mov     rax, [rcx]
0x18001da47  mov     rbx, rcx
0x18001da4a  mov     [r11-18h], rsi
0x18001da4e  mov     [r11-28h], r12
0x18001da52  mov     [r11-30h], r13
0x18001da56  mov     [rbp+100h+var_120], rdx
0x18001da5a  lea     r12, [rbx+50h]
0x18001da5e  xor     edx, edx
0x18001da60  mov     [r11-38h], r14
0x18001da64  mov     [rbp+100h+var_180], rdx
0x18001da68  mov     [rbp+100h+ProcessHandle], rdx
0x18001da6c  mov     [rbp+100h+var_168], edx
0x18001da6f  mov     [rbp+100h+hObject], rdx
0x18001da73  mov     [rbp+100h+hThread], rdx
0x18001da77  mov     [rbp+100h+var_110], rdx
0x18001da7b  mov     rcx, [rax+18h]
0x18001da7f  mov     [r11-40h], r15
0x18001da83  mov     [rbp+100h+var_D0], r9
0x18001da87  mov     [rbp+100h+var_D8], r8
0x18001da8b  cmp     dword ptr [rcx], 2
0x18001da8e  mov     [rbp+100h+var_F8], r12
0x18001da92  jz      loc_18001DDC5
0x18001da98  cmp     [r12], edx
0x18001da9c  jnz     loc_18001DDC5
0x18001daa2  mov     r14d, edx
0x18001daa5  mov     esi, [rcx+30h]
0x18001daa8  xor     r13b, r13b
0x18001daab  mov     [rbp+100h+var_160], r14d
0x18001daaf  mov     r15d, edx
0x18001dab2  mov     [rsp+230h+var_18], rdi
0x18001daba  mov     [rbp+100h+var_170], rdx
0x18001dabe  mov     dword ptr [rbp+100h+var_178], edx
0x18001dac1  mov     [rbp+100h+var_118], rdx
0x18001dac5  mov     [rbp+100h+P], rdx
0x18001dac9  mov     [rbp+100h+var_148], edx
0x18001dacc  mov     [rbp+100h+var_100], rdx
0x18001dad0  mov     [rbp+100h+var_140], rdx
0x18001dad4  mov     [rbp+100h+var_F0], rdx
0x18001dad8  mov     [rbp+100h+ProcessInformation], edx
0x18001dadb  test    r14d, r14d
0x18001dade  jnz     loc_18001E2E0
0x18001dae4  mov     rcx, [rax+18h]
0x18001dae8  mov     r9d, edx
0x18001daeb  mov     r8, [rbx+60h]
0x18001daef  mov     r15, [rcx+8]
0x18001daf3  mov     ecx, [rbx+88h]
0x18001daf9  lea     r10, [rbp+100h+var_140]
0x18001dafd  mov     rax, [rbx+90h]
0x18001db04  mov     rdx, [rbx]
0x18001db07  mov     [rsp+0A8h], r10; struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT **
0x18001db0f  lea     r10, [rbp+100h+var_F0]
0x18001db13  mov     [rsp+230h+var_190], r10; unsigned __int64 *
0x18001db1b  lea     r10, [rbp+100h+var_100]
0x18001db1f  mov     [rsp+230h+var_198], r10; void ***
0x18001db27  lea     r10, [rbp+100h+var_148]
0x18001db2b  mov     rdx, [rdx+18h]; struct _UBPM_ACTION_EXE_LAUNCH_PARAMS *
0x18001db2f  mov     [rsp+230h+var_1A0], r10; unsigned int *
0x18001db37  lea     r10, [rbp+100h+P]
0x18001db3b  mov     [rsp+230h+var_1A8], r10; void **
0x18001db43  lea     r10, [rbp+100h+var_118]
0x18001db47  mov     [rsp+230h+var_1B0], r10; HKEY *
0x18001db4f  lea     r10, [rbp+100h+var_110]
0x18001db53  mov     [rsp+230h+var_1B8], r10; void **
0x18001db58  lea     r10, [rbp+100h+hThread]
0x18001db5c  mov     [rsp+230h+var_1C0], r10; void **
0x18001db61  lea     r10, [rbp+100h+hObject]
0x18001db65  mov     [rsp+230h+var_1C8], r10; void **
0x18001db6a  lea     r10, [rbp+100h+var_168]
0x18001db6e  mov     [rsp+230h+var_1D0], r10; unsigned int *
0x18001db73  lea     r10, [rbp+100h+ProcessHandle]
0x18001db77  mov     [rsp+230h+var_1D8], r10; void **
0x18001db7c  mov     [rsp+230h+Src], rax; unsigned __int16 *
0x18001db81  mov     dword ptr [rsp+230h+Size], ecx; unsigned int
0x18001db85  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18001db89  mov     [rsp+230h+var_1F0], r8; unsigned __int16 *
0x18001db8e  mov     dword ptr [rsp+230h+var_1F8], esi; int
0x18001db92  mov     rsi, [rbp+100h+var_120]
0x18001db96  mov     dword ptr [rsp+230h+pSid], 0; int
0x18001db9e  mov     r8, rsi; void **
0x18001dba1  mov     dword ptr [rsp+230h+var_208], r9d; int
0x18001dba6  mov     r9, [rbx+48h]; void *
0x18001dbaa  mov     [rbp+100h+var_E0], r15
0x18001dbae  mov     [rsp+230h+ReturnLength], r15; Str
0x18001dbb3  call    ?UbpmpLaunchAction@@YAKPEBGPEAU_UBPM_ACTION_EXE_LAUNCH_PARAMS@@PEAPEAXPEAX0HHH0K02PEAK222PEAPEAUHKEY__@@24PEAPEAPEAXPEA_KPEAPEAU_UBPM_TASK_HOST_APPCONTAINER_CONTEXT@@@Z; UbpmpLaunchAction(ushort const *,_UBPM_ACTION_EXE_LAUNCH_PARAMS *,void * *,void *,ushort const *,int,int,int,ushort const *,ulong,ushort const *,void * *,ulong *,void * *,void * *,void * *,HKEY__ * *,void * *,ulong *,void * * *,unsigned __int64 *,_UBPM_TASK_HOST_APPCONTAINER_CONTEXT * *)
0x18001dbb8  mov     dword ptr [rbp+100h+var_178], eax
0x18001dbbb  mov     edi, eax
0x18001dbbd  test    eax, eax
0x18001dbbf  jnz     loc_18001E541
0x18001dbc5  mov     rcx, [rbp+100h+ProcessHandle]; ProcessHandle
0x18001dbc9  lea     r8, [rbp+100h+ProcessInformation]; ProcessInformation
0x18001dbcd  mov     r9d, 4; ProcessInformationLength
0x18001dbd3  mov     [rsp+230h+ReturnLength], 0; ReturnLength
0x18001dbdc  mov     edx, 18h; ProcessInformationClass
0x18001dbe1  call    cs:__imp_NtQueryInformationProcess
0x18001dbe8  nop     dword ptr [rax+rax+00h]
0x18001dbed  test    eax, eax
0x18001dbef  js      loc_18001E3C7
0x18001dbf5  mov     edi, [rbp+100h+ProcessInformation]
0x18001dbf8  mov     dword ptr [rbp+100h+var_150], edi
0x18001dbfb  test    r14d, r14d
0x18001dbfe  jnz     loc_18001DDFD
0x18001dc04  mov     rax, [rbx]
0x18001dc07  mov     rdx, [rax+20h]
0x18001dc0b  test    rdx, rdx
0x18001dc0e  jz      short loc_18001DC24
0x18001dc10  mov     r9d, [rdx+1Ch]; unsigned int
0x18001dc14  mov     r8d, [rdx+18h]; unsigned int
0x18001dc18  mov     edx, [rdx+10h]; dwPriorityClass
0x18001dc1b  mov     rcx, [rbp+100h+ProcessHandle]; Process
0x18001dc1f  call    ?UbpmpSetProcessPriorities@@YAXPEAXKKK@Z; UbpmpSetProcessPriorities(void *,ulong,ulong,ulong)
0x18001dc24  mov     r9, [rbp+100h+ProcessHandle]
0x18001dc28  lea     rax, [rbp+100h+var_180]
0x18001dc2c  mov     [rsp+230h+var_1C0], rax
0x18001dc31  mov     r8, rbx
0x18001dc34  mov     rax, [rbp+100h+var_140]
0x18001dc38  mov     rdx, rsi
0x18001dc3b  mov     [rsp+230h+var_1C8], rax
0x18001dc40  xor     ecx, ecx
0x18001dc42  mov     rax, [rbp+100h+var_F0]
0x18001dc46  mov     [rsp+230h+var_1D0], rax
0x18001dc4b  mov     rax, [rbp+100h+var_100]
0x18001dc4f  mov     [rsp+230h+var_1D8], rax
0x18001dc54  mov     eax, [rbp+100h+var_148]
0x18001dc57  mov     dword ptr [rsp+230h+Src], eax
0x18001dc5b  mov     rax, [rbp+100h+var_118]
0x18001dc5f  mov     [rsp+230h+Size], rax
0x18001dc64  mov     rax, [rbp+100h+P]
0x18001dc68  mov     [rsp+230h+var_1F0], rax
0x18001dc6d  mov     rax, [rbp+100h+var_110]
0x18001dc71  mov     [rsp+230h+var_1F8], rax
0x18001dc76  mov     rax, [rbp+100h+hObject]
0x18001dc7a  mov     [rsp+230h+pSid], rax
0x18001dc7f  mov     eax, [rbp+100h+var_168]
0x18001dc82  mov     dword ptr [rsp+230h+var_208], edi
0x18001dc86  mov     dword ptr [rsp+230h+ReturnLength], eax
0x18001dc8a  call    UbpmpCreateTaskHostContextBlock
0x18001dc8f  mov     dword ptr [rbp+100h+var_178], eax
0x18001dc92  mov     edi, eax
0x18001dc94  test    eax, eax
0x18001dc96  jz      loc_18001DF58
0x18001dc9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dca3  lea     rax, WPP_GLOBAL_Control
0x18001dcaa  cmp     rcx, rax
0x18001dcad  jnz     loc_18001E952
0x18001dcb3  mov     rcx, [rbp+100h+ProcessHandle]; hProcess
0x18001dcb7  mov     r15, [rsp+230h+var_38]
0x18001dcbf  mov     r14, [rsp+230h+var_30]
0x18001dcc7  mov     r12, [rsp+230h+var_20]
0x18001dccf  test    rcx, rcx
0x18001dcd2  jnz     loc_18001EA3B
0x18001dcd8  cmp     [rbp+100h+var_140], 0
0x18001dcdd  mov     rsi, [rbp+100h+var_120]
0x18001dce1  jnz     loc_18001EA5E
0x18001dce7  mov     rcx, [rbp+100h+hObject]; hObject
0x18001dceb  test    rcx, rcx
0x18001dcee  jnz     loc_18001EA78
0x18001dcf4  mov     rcx, [rbp+100h+hThread]; hObject
0x18001dcf8  test    rcx, rcx
0x18001dcfb  jnz     loc_18001EA89
0x18001dd01  mov     rdx, [rbp+100h+var_118]
0x18001dd05  test    rdx, rdx
0x18001dd08  jnz     loc_18001EA9A
0x18001dd0e  mov     rcx, [rbp+100h+var_180]
0x18001dd12  mov     rsi, [rsp+220h]
0x18001dd1a  test    rcx, rcx
0x18001dd1d  jnz     loc_18001EAC0
0x18001dd23  mov     r8, [rbp+100h+var_110]; P
0x18001dd27  cmp     r8, cs:pSid
0x18001dd2e  jnz     loc_18001DDD4
0x18001dd34  mov     r8, [rbp+100h+P]; P
0x18001dd38  test    r8, r8
0x18001dd3b  jz      short loc_18001DD58
0x18001dd3d  mov     rcx, gs:60h
0x18001dd46  xor     edx, edx; Flags
0x18001dd48  mov     rcx, [rcx+30h]; HeapHandle
0x18001dd4c  call    cs:__imp_RtlFreeHeap
0x18001dd53  nop     dword ptr [rax+rax+00h]
0x18001dd58  mov     r8, [rbp+100h+var_100]; P
0x18001dd5c  test    r8, r8
0x18001dd5f  jz      short loc_18001DD7C
0x18001dd61  mov     rcx, gs:60h
0x18001dd6a  xor     edx, edx; Flags
0x18001dd6c  mov     rcx, [rcx+30h]; HeapHandle
0x18001dd70  call    cs:__imp_RtlFreeHeap
0x18001dd77  nop     dword ptr [rax+rax+00h]
0x18001dd7c  cmp     [rbp+100h+var_170], 0
0x18001dd81  jnz     loc_18001EADF
0x18001dd87  cmp     r13b, 1
0x18001dd8b  mov     r13, [rsp+230h+var_28]
0x18001dd93  jz      loc_18001E5FE
0x18001dd99  test    edi, edi
0x18001dd9b  jnz     loc_18001E5FE
0x18001dda1  mov     eax, edi
0x18001dda3  mov     rdi, [rsp+230h+var_18]
0x18001ddab  mov     rcx, [rbp+100h+var_50]
0x18001ddb2  xor     rcx, rsp; StackCookie
0x18001ddb5  call    __security_check_cookie
0x18001ddba  add     rsp, 228h
0x18001ddc1  pop     rbx
0x18001ddc2  pop     rbp
0x18001ddc3  retn
0x18001ddc5  mov     [rbp+100h+var_F8], r12
0x18001ddc9  mov     r14d, 1
0x18001ddcf  jmp     loc_18001DAA5
0x18001ddd4  test    r8, r8
0x18001ddd7  jz      loc_18001DD34
0x18001dddd  mov     rcx, gs:60h
0x18001dde6  xor     edx, edx; Flags
0x18001dde8  mov     rcx, [rcx+30h]; HeapHandle
0x18001ddec  call    cs:__imp_RtlFreeHeap
0x18001ddf3  nop     dword ptr [rax+rax+00h]
0x18001ddf8  jmp     loc_18001DD34
0x18001ddfd  xor     r9d, r9d; lpName
0x18001de00  xor     r8d, r8d; bInitialState
0x18001de03  xor     edx, edx; bManualReset
0x18001de05  xor     ecx, ecx; lpEventAttributes
0x18001de07  call    cs:__imp_CreateEventW
0x18001de0e  nop     dword ptr [rax+rax+00h]
0x18001de13  mov     [rbp+100h+var_B8], rax
0x18001de17  test    rax, rax
0x18001de1a  jz      loc_18001E7A7
0x18001de20  mov     rax, [rbx]
0x18001de23  mov     rcx, [rax+18h]
0x18001de27  mov     rax, [rcx+20h]
0x18001de2b  test    rax, rax
0x18001de2e  jnz     loc_18001E56C
0x18001de34  mov     [rbp+100h+var_128], eax
0x18001de37  mov     r13d, [rbp+100h+var_148]
0x18001de3b  mov     r12, [rbp+100h+P]
0x18001de3f  mov     r15, [rbp+100h+var_110]
0x18001de43  mov     r14, [rbp+100h+hObject]
0x18001de47  mov     esi, [rbp+100h+var_168]
0x18001de4a  mov     rdi, [rbp+100h+ProcessHandle]
0x18001de4e  mov     [rbp+100h+var_12C], eax
0x18001de51  mov     rax, [rbp+100h+var_140]
0x18001de55  mov     [rbp+100h+var_A0], rax
0x18001de59  mov     rax, [rbp+100h+var_F0]
0x18001de5d  mov     [rbp+100h+var_A8], rax
0x18001de61  mov     rax, [rbp+100h+var_100]
0x18001de65  mov     [rbp+100h+var_B0], rax
0x18001de69  mov     rax, [rbp+100h+var_118]
0x18001de6d  mov     [rbp+100h+var_98], rax
0x18001de71  mov     rax, [rbp+100h+var_180]
0x18001de75  mov     [rbp+100h+var_C0], rax
0x18001de79  add     rax, 40h ; '@'
0x18001de7d  mov     rcx, rax
0x18001de80  mov     [rbp+100h+var_C8], rax
0x18001de84  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001de8b  nop     dword ptr [rax+rax+00h]
0x18001de90  call    cs:__imp_GetCurrentThreadId
0x18001de97  nop     dword ptr [rax+rax+00h]
0x18001de9c  mov     rcx, [rbp+100h+var_C0]
0x18001dea0  mov     rdx, [rbp+100h+var_C8]
0x18001dea4  mov     [rdx+8], eax
0x18001dea7  mov     rax, [rbp+100h+var_B8]
0x18001deab  mov     [rcx+30h], rax
0x18001deaf  mov     eax, [rbp+100h+var_12C]
0x18001deb2  mov     [rcx+108h], eax
0x18001deb8  mov     eax, [rbp+100h+var_128]
0x18001debb  mov     [rcx+10Ch], eax
0x18001dec1  mov     eax, dword ptr [rbp+100h+var_150]
0x18001dec4  mov     [rcx+0C0h], eax
0x18001deca  mov     rax, [rbp+100h+var_B0]
0x18001dece  mov     [rcx+190h], rax
0x18001ded5  mov     rax, [rbp+100h+var_A8]
0x18001ded9  mov     [rcx+20h], esi
0x18001dedc  mov     rsi, [rbp+100h+var_120]
0x18001dee0  mov     [rcx+180h], rax
0x18001dee7  mov     rax, [rbp+100h+var_A0]
0x18001deeb  mov     [rcx+1A8h], rax
0x18001def2  mov     [rcx+18h], rdi
0x18001def6  mov     [rcx+100h], r14
0x18001defd  mov     [rcx+0B0h], r15
0x18001df04  mov     [rcx+0B8h], r12
0x18001df0b  mov     [rcx+188h], r13d
0x18001df12  test    rsi, rsi
0x18001df15  jz      short loc_18001DF33
0x18001df17  mov     rax, [rbp+100h+var_98]
0x18001df1b  mov     [rcx+0F0h], rax
0x18001df22  mov     rax, [rsi]
0x18001df25  mov     [rcx+0F8h], rax
0x18001df2c  mov     qword ptr [rsi], 0
0x18001df33  mov     rcx, rdx
0x18001df36  mov     dword ptr [rdx+8], 0
0x18001df3d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001df44  nop     dword ptr [rax+rax+00h]
0x18001df49  mov     r14d, [rbp+100h+var_160]
0x18001df4d  xor     r13b, r13b
0x18001df50  mov     r15, [rbp+100h+var_E0]
0x18001df54  mov     r12, [rbp+100h+var_F8]
0x18001df58  mov     rsi, [rbp+100h+var_180]
0x18001df5c  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
  ... truncated ...
```
