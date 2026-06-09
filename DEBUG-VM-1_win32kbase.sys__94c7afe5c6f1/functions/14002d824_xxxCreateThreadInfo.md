# xxxCreateThreadInfo

- ea: `0x14002d824`
- end: `0x14002edc6`
- name: `xxxCreateThreadInfo`
- size: `5538`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `2`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14002cf40`
- `0x14009961c`

## callees

- `0x140012c80`
- `0x140029f00`
- `0x140029fe8`
- `0x14002a0e4`
- `0x14002ab14`
- `0x14002d76c`
- `0x14002d798`
- `0x14002d824`
- `0x14002edcc`
- `0x14005c210`
- `0x14005f5b0`
- `0x140073980`
- `0x140073a50`
- `0x140075700`
- `0x1400757c8`
- `0x1400759e0`
- `0x140076ef0`
- `0x14008deb0`
- `0x1400a15c0`
- `0x1400a1690`
- `0x1400aacac`
- `0x1400e0460`
- `0x1400e1970`
- `0x1400f7aa0`
- `0x140111308`
- `0x140111f70`
- `0x14011c664`
- `0x140127ce0`
- `0x14012bdb0`
- `0x14012ff50`
- `0x140133a8c`
- `0x140133bac`
- `0x140133c0c`
- `0x14013981c`
- `0x140148380`
- `0x14014d388`
- `0x140156708`
- `0x140171b74`
- `0x140177bc0`
- `0x140193f58`
- `0x1401aa4fc`
- `0x1401bb040`
- `0x1401c71a4`
- `0x140238bf0`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x14002d976`
- `ntoskrnl!PsGetProcessPeb` at `0x14002ea7e`
- `ntoskrnl!PsGetProcessPeb` at `0x14002d976`
- `ntoskrnl!PsGetProcessPeb` at `0x14002ea7e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002e3ca`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002e3ca`
- `ntoskrnl!ProbeForRead` at `0x14002d9ab`
- `ntoskrnl!ProbeForRead` at `0x14002da01`
- `ntoskrnl!ProbeForRead` at `0x14002d9ab`
- `ntoskrnl!ProbeForRead` at `0x14002da01`
- `ntoskrnl!KeBugCheckEx` at `0x14002dbf6`
- `ntoskrnl!KeBugCheckEx` at `0x14002dc2d`
- `ntoskrnl!KeBugCheckEx` at `0x14002e711`
- `ntoskrnl!KeBugCheckEx` at `0x14002dbf6`
- `ntoskrnl!KeBugCheckEx` at `0x14002dc2d`
- `ntoskrnl!KeBugCheckEx` at `0x14002e711`
- `ntoskrnl!PsGetThreadProcess` at `0x14002d83a`
- `ntoskrnl!PsGetThreadProcess` at `0x14002d83a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002d8f5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002dc48`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002e8c5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002d8f5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002dc48`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002e8c5`
- `ntoskrnl!ExRaiseStatus` at `0x14002dbcb`
- `ntoskrnl!ExRaiseStatus` at `0x14002dc05`
- `ntoskrnl!ExRaiseStatus` at `0x14002dbcb`
- `ntoskrnl!ExRaiseStatus` at `0x14002dc05`
- `ntoskrnl!PsGetThreadProcessId` at `0x14002dc7b`
- `ntoskrnl!PsGetThreadProcessId` at `0x14002dc7b`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14002ea92`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14002ea92`
- `ntoskrnl!ZwCreateEvent` at `0x14002df33`
- `ntoskrnl!ZwCreateEvent` at `0x14002df33`
- `ntoskrnl!ExEventObjectType` at `0x14002e274`
- `ntoskrnl!ExEventObjectType` at `0x14002e2ac`
- `ntoskrnl!ZwTerminateProcess` at `0x14002e86a`
- `ntoskrnl!ZwTerminateProcess` at `0x14002e86a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e1cf`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e1cf`
- `ntoskrnl!ExDesktopObjectType` at `0x14002e371`
- `ntoskrnl!PsGetProcessId` at `0x14002e454`
- `ntoskrnl!PsGetProcessId` at `0x14002e454`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14002ec74`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14002ec74`
- `ntoskrnl!ObCloseHandle` at `0x14002eadb`
- `ntoskrnl!ObCloseHandle` at `0x14002eadb`
- `ntoskrnl!ObDuplicateObject` at `0x14002df7f`
- `ntoskrnl!ObDuplicateObject` at `0x14002df7f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e284`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e385`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e284`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e385`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e3b3`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e3b3`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14002e943`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14002e943`
- `ntoskrnl!PsGetThreadId` at `0x14002de3a`
- `ntoskrnl!PsGetThreadId` at `0x14002de3a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002decd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e05f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e121`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e173`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e2c5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e2f2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e3f8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e48c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e5f7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e690`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e6bf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e71e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e74b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e90f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002decd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e05f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e121`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e173`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e2c5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e2f2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e3f8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e48c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e5f7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e690`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e6bf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e71e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e74b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e90f`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002d946`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002e00e`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002d946`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002e00e`
- `WIN32K!W32GetUserSessionState` at `0x14002d8dd`
- `WIN32K!W32GetUserSessionState` at `0x14002d92f`
- `WIN32K!W32GetUserSessionState` at `0x14002dc8a`
- `WIN32K!W32GetUserSessionState` at `0x14002dcb5`
- `WIN32K!W32GetUserSessionState` at `0x14002dccf`
- `WIN32K!W32GetUserSessionState` at `0x14002dce8`
- `WIN32K!W32GetUserSessionState` at `0x14002dcfd`
- `WIN32K!W32GetUserSessionState` at `0x14002dd2b`
- `WIN32K!W32GetUserSessionState` at `0x14002de5b`
- `WIN32K!W32GetUserSessionState` at `0x14002de70`
- `WIN32K!W32GetUserSessionState` at `0x14002de9e`
- `WIN32K!W32GetUserSessionState` at `0x14002e0fb`
- `WIN32K!W32GetUserSessionState` at `0x14002e43c`
- `WIN32K!W32GetUserSessionState` at `0x14002e50f`
- `WIN32K!W32GetUserSessionState` at `0x14002e589`
- `WIN32K!W32GetUserSessionState` at `0x14002e5c1`
- `WIN32K!W32GetUserSessionState` at `0x14002e77f`
- `WIN32K!W32GetUserSessionState` at `0x14002e79e`
- `WIN32K!W32GetUserSessionState` at `0x14002e7b6`
- `WIN32K!W32GetUserSessionState` at `0x14002e7c8`
- `WIN32K!W32GetUserSessionState` at `0x14002e876`
- `WIN32K!W32GetUserSessionState` at `0x14002e99b`
- `WIN32K!W32GetUserSessionState` at `0x14002e9b0`
- `WIN32K!W32GetUserSessionState` at `0x14002e9c3`
- `WIN32K!W32GetUserSessionState` at `0x14002e9d6`
- `WIN32K!W32GetUserSessionState` at `0x14002e9ef`
- `WIN32K!W32GetUserSessionState` at `0x14002ea02`
- `WIN32K!W32GetUserSessionState` at `0x14002ec43`
- `WIN32K!W32GetUserSessionState` at `0x14002ec5c`
- `WIN32K!W32GetUserSessionState` at `0x14002ec85`
- `WIN32K!W32GetUserSessionState` at `0x14002ec98`
- `WIN32K!W32GetUserSessionState` at `0x14002ecb2`
- `WIN32K!W32GetUserSessionState` at `0x14002d8dd`
- `WIN32K!W32GetUserSessionState` at `0x14002d92f`
- `WIN32K!W32GetUserSessionState` at `0x14002dc8a`
- `WIN32K!W32GetUserSessionState` at `0x14002dcb5`
- `WIN32K!W32GetUserSessionState` at `0x14002dccf`
- `WIN32K!W32GetUserSessionState` at `0x14002dce8`
- `WIN32K!W32GetUserSessionState` at `0x14002dcfd`
- `WIN32K!W32GetUserSessionState` at `0x14002dd2b`
- `WIN32K!W32GetUserSessionState` at `0x14002de5b`
- `WIN32K!W32GetUserSessionState` at `0x14002de70`
- `WIN32K!W32GetUserSessionState` at `0x14002de9e`
- `WIN32K!W32GetUserSessionState` at `0x14002e0fb`
- `WIN32K!W32GetUserSessionState` at `0x14002e43c`
- `WIN32K!W32GetUserSessionState` at `0x14002e50f`
- `WIN32K!W32GetUserSessionState` at `0x14002e589`
- `WIN32K!W32GetUserSessionState` at `0x14002e5c1`
- `WIN32K!W32GetUserSessionState` at `0x14002e77f`
- `WIN32K!W32GetUserSessionState` at `0x14002e79e`
- `WIN32K!W32GetUserSessionState` at `0x14002e7b6`
- `WIN32K!W32GetUserSessionState` at `0x14002e7c8`
- `WIN32K!W32GetUserSessionState` at `0x14002e876`
- `WIN32K!W32GetUserSessionState` at `0x14002e99b`
- `WIN32K!W32GetUserSessionState` at `0x14002e9b0`
- `WIN32K!W32GetUserSessionState` at `0x14002e9c3`
- `WIN32K!W32GetUserSessionState` at `0x14002e9d6`
- `WIN32K!W32GetUserSessionState` at `0x14002e9ef`
- `WIN32K!W32GetUserSessionState` at `0x14002ea02`
- `WIN32K!W32GetUserSessionState` at `0x14002ec43`
- `WIN32K!W32GetUserSessionState` at `0x14002ec5c`
- `WIN32K!W32GetUserSessionState` at `0x14002ec85`
- `WIN32K!W32GetUserSessionState` at `0x14002ec98`
- `WIN32K!W32GetUserSessionState` at `0x14002ecb2`

## pseudocode

```c
__int64 __fastcall xxxCreateThreadInfo(PETHREAD Thread)
{
  struct _KPROCESS *ThreadProcess; // rbx
  __int64 v3; // rcx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v5; // rcx
  __int64 UserSessionState; // rax
  int v7; // r12d
  __int64 ThreadWin32Thread; // r14
  __int64 v9; // rdx
  NTSTATUS v10; // eax
  __int64 v11; // rdx
  ULONG_PTR v12; // rbx
  NTSTATUS v13; // eax
  ULONG_PTR v14; // rbx
  struct tagTHREADINFO *v15; // rax
  struct tagTHREADINFO *v16; // rax
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v18; // rax
  __int64 v19; // rax
  __int64 v20; // r15
  int v21; // edi
  HANDLE ThreadProcessId; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  unsigned int v25; // r13d
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  struct _NT_TIB *v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 (*v34)(void); // rax
  int v35; // eax
  int v36; // r12d
  HANDLE *v37; // rbx
  NTSTATUS Event; // edi
  PEPROCESS v39; // r13
  int v40; // eax
  struct tagQ *v41; // rax
  struct tagQ *v42; // rbx
  __int64 v43; // rcx
  _DWORD *v44; // r13
  __int64 (*v45)(void); // rax
  _QWORD *v46; // rdi
  int v47; // ebx
  __int64 (__fastcall *v48)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *); // rax
  __int64 (*v49)(void); // rax
  unsigned int CurrentProcessId; // eax
  __int64 v51; // r8
  __int64 v53; // rdx
  __int64 v54; // r9
  __int64 (*v55)(void); // rax
  int v56; // eax
  __int64 (__fastcall *v57)(__int64); // rax
  __int64 v59; // rcx
  __int64 (__fastcall *v60)(__int128 *); // rax
  HANDLE v61; // rbx
  void (*v62)(void); // rax
  __int64 v63; // rcx
  __int64 v64; // rcx
  char v65; // al
  int v66; // ebx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 (*v69)(void); // rax
  __int64 v70; // rax
  __int64 (*v71)(void); // rax
  __int64 (*v72)(void); // rax
  struct tagTHREADINFO *v73; // rax
  __int64 (*v74)(void); // rax
  int v75; // eax
  void (__fastcall *v76)(_QWORD); // rax
  __int64 v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 v81; // rcx
  _QWORD *v82; // rbx
  __int64 v83; // rcx
  __int64 v84; // r14
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  char v88; // al
  void (__fastcall *v89)(__int64); // rax
  __int64 ProcessWin32Process; // rax
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // rbx
  __int64 v94; // rcx
  __int64 v95; // rax
  __int64 v96; // rdx
  __int64 v97; // rcx
  PEPROCESS v98; // rbx
  __int64 ProcessSectionBaseAddress; // rax
  unsigned int v100; // eax
  __int64 v101; // rbx
  __int64 v102; // rbx
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rbx
  char *v106; // [rsp+40h] [rbp-188h] BYREF
  __int64 v107; // [rsp+48h] [rbp-180h]
  PEPROCESS Process; // [rsp+50h] [rbp-178h]
  PVOID Object; // [rsp+58h] [rbp-170h] BYREF
  HANDLE v110; // [rsp+60h] [rbp-168h] BYREF
  _QWORD *v111; // [rsp+68h] [rbp-160h]
  ULONG_PTR v112[2]; // [rsp+70h] [rbp-158h] BYREF
  __int64 (__fastcall *v113)(PVOID); // [rsp+80h] [rbp-148h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+88h] [rbp-140h] BYREF
  __int64 (__fastcall *v115)(PVOID); // [rsp+98h] [rbp-130h]
  ULONG_PTR v116[2]; // [rsp+A0h] [rbp-128h] BYREF
  __int64 v117; // [rsp+B0h] [rbp-118h]
  __int64 v118; // [rsp+B8h] [rbp-110h]
  __int64 v119; // [rsp+C0h] [rbp-108h]
  _QWORD v120[12]; // [rsp+D0h] [rbp-F8h] BYREF
  __int128 v121; // [rsp+130h] [rbp-98h] BYREF
  __int128 v122; // [rsp+140h] [rbp-88h]
  __int128 v123; // [rsp+150h] [rbp-78h]
  _QWORD *v124; // [rsp+160h] [rbp-68h]
  char *v125; // [rsp+168h] [rbp-60h]
  volatile void *Address; // [rsp+1D8h] [rbp+10h] BYREF
  struct _NT_TIB *Self; // [rsp+1E0h] [rbp+18h]
  HANDLE Handle; // [rsp+1E8h] [rbp+20h] BYREF

  ThreadProcess = PsGetThreadProcess(Thread);
  Process = ThreadProcess;
  memset(v120, 0, 0x48u);
  Handle = 0;
  v110 = 0;
  Self = KeGetPcr()->NtTib.Self;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v112);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v116);
  v121 = 0;
  v122 = 0;
  v123 = 0;
  if ( (Microsoft_Windows_Win32kEnableBits & 0x8000) != 0 )
    McTemplateK0_EtwWriteTransfer(v3, &InitiateGuiThreadExecution, &W32kControlGuid);
  if ( !*(_DWORD *)(((__int64 (*)(void))W32GetUserSessionState)() + 36232) )
  {
    CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
    if ( CurrentProcessWin32Process )
    {
      v5 = -*(_QWORD *)CurrentProcessWin32Process;
      if ( (-(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process) != 0 )
      {
        v119 = 0;
        v118 = 0;
        UserSessionState = W32GetUserSessionState(v5);
        ++*(_DWORD *)(UserSessionState + 36240);
        v7 = 33554504;
        if ( ThreadProcess != *(struct _KPROCESS **)(W32GetUserGdiSessionState() + 40) )
          v7 = 0;
        ThreadWin32Thread = W32GetThreadWin32Thread(Thread);
        v120[6] = 0;
        Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
        v120[10] = 1;
        ProbeForRead(Address, 1u, 1u);
        Address = (volatile void *)*((_QWORD *)Address + 4);
        v111 = v120;
        v124 = v120;
        v120[11] = 1;
        ProbeForRead(Address, 1u, 1u);
        v120[0] = *((_QWORD *)Address + 4);
        v120[1] = *((_QWORD *)Address + 5);
        v120[2] = *((_QWORD *)Address + 17);
        v120[3] = *((_QWORD *)Address + 18);
        v120[4] = *(_QWORD *)((char *)Address + 164);
        v125 = (char *)Address + 192;
        v10 = DuplicateUnicodeStringFromUser<0>((char *)Address + 192, v9, &v120[5]);
        if ( v10 < 0 )
          ExRaiseStatus(v10);
        v12 = v120[6];
        if ( v120[6] )
        {
          v119 = v120[6];
          if ( v115 != (__int64 (__fastcall *)(PVOID))-1LL )
          {
            BugCheckParameter4 = PtiCurrent();
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, v12, (ULONG_PTR)BugCheckParameter4);
          }
          v16 = PtiCurrent();
          BugCheckParameter2[0] = *((_QWORD *)v16 + 47);
          *((_QWORD *)v16 + 47) = BugCheckParameter2;
          BugCheckParameter2[1] = v12;
          v115 = GreDeleteFastMutex;
        }
        v106 = (char *)Address + 208;
        v13 = DuplicateUnicodeStringFromUser<0>((char *)Address + 208, v11, &v120[7]);
        if ( v13 < 0 )
          ExRaiseStatus(v13);
        v14 = v120[8];
        if ( v120[8] )
        {
          v118 = v120[8];
          if ( v113 != (__int64 (__fastcall *)(PVOID))-1LL )
          {
            v18 = PtiCurrent();
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v112, v14, (ULONG_PTR)v18);
          }
          v15 = PtiCurrent();
          v112[0] = *((_QWORD *)v15 + 47);
          *((_QWORD *)v15 + 47) = v112;
          v112[1] = v14;
          v113 = GreDeleteFastMutex;
        }
        v19 = PsGetCurrentProcessWin32Process();
        v20 = v19;
        if ( v19 )
          v20 = -(__int64)(*(_QWORD *)v19 != 0) & v19;
        v21 = v7 | 0x100;
        if ( *(char *)(v20 + 12) >= 0 )
          v21 = v7;
        ThreadProcessId = PsGetThreadProcessId(Thread);
        v25 = v21 | 0x2000000;
        if ( *(HANDLE *)(W32GetUserSessionState(v23) + 63312) != ThreadProcessId )
          v25 = v21;
        _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), v25);
        v26 = *(unsigned int *)(W32GetUserSessionState(v24) + 66792);
        if ( (v26 & 0x80u) != 0LL )
        {
          if ( *(_QWORD *)(W32GetUserSessionState(v26) + 14216) )
          {
            v33 = W32GetUserSessionState(v32);
            if ( (*(_BYTE *)(HMPheFromObject(*(_QWORD *)(v33 + 14216)) + 25) & 1) != 0 )
            {
              LODWORD(Address) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1338);
            }
          }
          v106 = (char *)(ThreadWin32Thread + 472);
          v30 = *(_QWORD *)(W32GetUserSessionState(v32) + 14216);
LABEL_32:
          v107 = v30;
          HMAssignmentLock(&v106, 0);
          *(_QWORD *)(ThreadWin32Thread + 480) = ThreadWin32Thread + 1088;
          if ( (*(_DWORD *)(v20 + 12) & 0x800000) != 0 )
            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
          *(_QWORD *)(ThreadWin32Thread + 456) = v20;
          *(_QWORD *)(ThreadWin32Thread + 696) = *(_QWORD *)(v20 + 328);
          *(_QWORD *)(v20 + 328) = ThreadWin32Thread;
          ++*(_DWORD *)(v20 + 376);
          if ( Self )
          {
            v31 = Self;
            v31[2].StackBase = PsGetThreadId(*(PETHREAD *)ThreadWin32Thread);
          }
          *(_QWORD *)(ThreadWin32Thread + 512) = (char *)Self + 2048;
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 232LL) = *(_DWORD *)(ThreadWin32Thread + 392);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 236LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 400) = *(_QWORD *)(ThreadWin32Thread + 512) + 232LL;
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 240LL) = *(_DWORD *)(ThreadWin32Thread + 396);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 244LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 408) = *(_QWORD *)(ThreadWin32Thread + 512) + 240LL;
          if ( (*(_DWORD *)(v20 + 12) & 0x2000000) != 0 )
            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x20000000u);
          if ( !*(_DWORD *)(ThreadWin32Thread + 664) )
          {
            v98 = Process;
            if ( PsGetProcessPeb(Process) )
            {
              ProcessSectionBaseAddress = PsGetProcessSectionBaseAddress(v98);
              *(_DWORD *)(ThreadWin32Thread + 664) = RtlGetExpWinVer(ProcessSectionBaseAddress);
            }
            else
            {
              *(_DWORD *)(ThreadWin32Thread + 664) = 1536;
            }
          }
          v34 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 896LL);
          if ( v34 )
          {
            v35 = v34();
            v36 = -1073741637;
          }
          else
          {
            v36 = -1073741637;
            v35 = -1073741637;
          }
          if ( v35 >= 0 )
          {
            v62 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 904LL);
            if ( v62 )
              v62();
          }
          LODWORD(Self) = v25 & 0xC;
          if ( (v25 & 0xC) == 0 )
          {
            v55 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 912LL);
            v56 = v55 ? v55() : -1073741637;
            if ( v56 >= 0 )
            {
              v57 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 920LL);
              if ( v57 ? v57(ThreadWin32Thread) : 0 )
                *(_DWORD *)(v20 + 12) |= 0x1000000u;
            }
          }
          v37 = (HANDLE *)(ThreadWin32Thread + 752);
          Event = ZwCreateEvent((PHANDLE)(ThreadWin32Thread + 752), 0x1F0003u, 0, SynchronizationEvent, 0);
          if ( Event >= 0 )
          {
            Address = 0;
            Event = ObReferenceObjectByHandle(*v37, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 1, (PVOID *)&Address, 0);
            *(_QWORD *)(ThreadWin32Thread + 760) = Address;
            if ( Event < 0 )
            {
              if ( Event != -1073741816 )
                ObCloseHandle(*v37, 1);
            }
            else
            {
              LOBYTE(v54) = 1;
              Event = ProtectHandle(*v37, v53, ExEventObjectType, v54);
            }
          }
          if ( Event < 0 )
          {
            *v37 = 0;
          }
          else
          {
            Event = ObDuplicateObject(Process, *v37, Process, ThreadWin32Thread + 1632, 0, 512, 2, 0);
            if ( Event < 0 )
            {
              *(_QWORD *)(ThreadWin32Thread + 1632) = 0;
            }
            else
            {
              v39 = Process;
              Event = InitializeThreadInfoIocp(Process, (struct tagTHREADINFO *)ThreadWin32Thread);
              if ( Event >= 0 )
              {
                v40 = *(_DWORD *)(v20 + 12);
                LODWORD(Address) = v40 & 0x4000;
                *(_DWORD *)(v20 + 12) = v40 | 0x4000;
                if ( !*(_DWORD *)(v20 + 772) && LODWORD(v120[4]) )
                {
                  *(_DWORD *)(v20 + 772) = 28;
                  *(_QWORD *)(v20 + 776) = v120[2];
                  *(_QWORD *)(v20 + 784) = v120[3];
                  *(_DWORD *)(v20 + 792) = v120[4];
                  *(_WORD *)(v20 + 796) = WORD2(v120[4]);
                }
                if ( (v40 & 0x4000) == 0 )
                {
                  if ( (v120[4] & 0x200) != 0 )
                    v100 = v120[0];
                  else
                    v100 = LOWORD(v120[7])
                         ? ParseReserved((const unsigned __int16 *volatile)v120[8], (const unsigned __int16 *)0x4000)
                         : 0;
                  *(_DWORD *)(v20 + 676) = v100;
                  if ( (v111[4] & 0x400) != 0 )
                  {
                    v101 = v111[1];
                    if ( HMValidateSharedHandle(v101) )
                      *(_QWORD *)(v20 + 680) = v101;
                  }
                }
                v41 = (struct tagQ *)AllocQueue(0, 0);
                v42 = v41;
                if ( v41 )
                {
                  tagTHREADINFO::AssignQueue((tagTHREADINFO *)ThreadWin32Thread, v41);
                  *((_QWORD *)v42 + 13) = ThreadWin32Thread;
                  *((_QWORD *)v42 + 12) = ThreadWin32Thread;
                  ApiSetEditionUpdateRawMouseMode(v42);
                  if ( v39 == *(PEPROCESS *)(W32GetUserGdiSessionState() + 40) )
                  {
                    *((_QWORD *)v42 + 68) = 0x2000;
                  }
                  else
                  {
                    *((_DWORD *)v42 + 136) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 864LL);
                    *((_DWORD *)v42 + 137) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 868LL);
                    v43 = *(unsigned int *)(*(_QWORD *)(ThreadWin32Thread + 456) + 872LL);
                    *((_DWORD *)v42 + 138) = v43;
                  }
                  if ( (_InterlockedCompareExchange((volatile signed __int32 *)(ThreadWin32Thread + 520), 0, 0) & 0xC) != 0
                    || !*(_QWORD *)(W32GetUserSessionState(v43) + 63288) )
                  {
                    v44 = 0;
                    goto LABEL_59;
                  }
                  v110 = 0;
                  v46 = v111;
                  v47 = *((_DWORD *)v111 + 8);
                  v48 = *(__int64 (__fastcall **)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48)
                                                                                                + 944LL);
                  if ( v48 )
                    Event = v48(-1, v46 + 5, &v110, v47 & 0x40000000, &Handle);
                  else
                    Event = -1073741637;
                  if ( Event < 0 )
                  {
                    if ( Event != -1073741205 )
                    {
                      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
                      if ( (Microsoft_Windows_Win32kEnableBits & 1) != 0 )
                        McTemplateK0dq_EtwWriteTransfer(
                          Microsoft_Windows_Win32kEnableBits,
                          &DesktopResolutionFailure,
                          v51,
                          CurrentProcessId,
                          Event);
                      Event = -1073741502;
                      goto LABEL_78;
                    }
                    UserSessionSwitchLeaveCritWithNonPaged();
                    ZwTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073741205);
                    v84 = W32GetUserSessionState(v83);
                    v85 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
                            v84,
                            1,
                            0,
                            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
                    *(_QWORD *)(v84 + 16) = v85;
                    if ( v85 )
                    {
                      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v85 + 520), 0, 0) & 0x1000000) != 0
                        && *(char *)(v85 + 1360) >= 0 )
                      {
                        v86 = PsGetCurrentProcessWin32Process();
                        if ( !v86 )
                          goto LABEL_78;
                        v87 = -(__int64)(*(_QWORD *)v86 != 0) & v86;
                        if ( !v87 )
                          goto LABEL_78;
                        v88 = *(_BYTE *)(v87 + 1200);
                        if ( v88 != 1 )
                          goto LABEL_78;
                      }
                      else
                      {
                        v88 = 0;
                      }
                      if ( v88 )
                      {
                        while ( 1 )
                        {
                          v82 = *(_QWORD **)(v84 + 19544);
                          if ( !v82 )
                            break;
                          *(_QWORD *)(v84 + 19544) = v82[2];
                          v82[2] = 0;
                          if ( !*(_DWORD *)(*v82 + 8LL) )
                          {
                            LODWORD(Address) = 0x20000;
                            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                          }
                          HMUnlockObject(*v82);
                        }
                        DestroyDeferredUnlockObjectAssignmentList(v84 + 19576);
                        DestroyDeferredUnlockObjectAssignmentList(v84 + 19560);
                      }
                    }
                  }
                  else
                  {
                    v49 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 952LL);
                    if ( v49 )
                      Event = v49();
                    else
                      Event = -1073741637;
                    if ( Event >= 0 )
                    {
                      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v106);
                      Event = xxxSetProcessWindowStation(v110);
                      if ( (_BYTE)v106 )
                        --*(_DWORD *)(v107 + 28);
                      if ( Event >= 0 )
                      {
                        Object = 0;
                        Event = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)ExDesktopObjectType, 1, &Object, 0);
                        v44 = Object;
                        if ( Event < 0 )
                          goto LABEL_79;
                        Win32RawLockedNtObject<tagDESKTOP>::ManualLock((ULONG_PTR)v116, (ULONG_PTR)Object);
                        ObfDereferenceObject(v44);
                        LODWORD(v122) = 1;
                        *((_QWORD *)&v122 + 1) = PsGetCurrentProcess();
                        *(_QWORD *)&v123 = v44;
                        *((_QWORD *)&v123 + 1) = 0x100000000LL;
                        v59 = *(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48);
                        v60 = *(__int64 (__fastcall **)(__int128 *))(v59 + 968);
                        Event = v60 ? v60(&v121) : -1073741637;
                        if ( Event < 0 )
                          goto LABEL_79;
                        if ( !*(_QWORD *)(v20 + 384) )
                        {
                          v61 = *(HANDLE *)(W32GetUserSessionState(v59) + 63312);
                          if ( PsGetProcessId(Process) != v61 )
                          {
                            LockObjectAssignment(v20 + 344, v44);
                            *(_QWORD *)(v20 + 384) = Handle;
                          }
                        }
LABEL_59:
                        if ( (unsigned int)InitClientInfo(ThreadWin32Thread) )
                        {
                          AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v106);
                          v45 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 976LL);
                          if ( v45 )
                            Event = v45();
                          else
                            Event = -1073741637;
                          if ( Event < 0 || (Event = zzzSetDesktop(ThreadWin32Thread, v44, Handle), Event < 0) )
                          {
                            if ( (_BYTE)v106 )
                            {
                              --*(_DWORD *)(v107 + 28);
                              v107 = 0;
                            }
                            goto LABEL_79;
                          }
                          if ( (_BYTE)v106 )
                            --*(_DWORD *)(v107 + 28);
                          W32GetUserSessionState(v63);
                          if ( *((int *)v111 + 8) >= 0 )
                          {
LABEL_117:
                            v65 = _InterlockedCompareExchange(
                                    (volatile signed __int32 *)(ThreadWin32Thread + 520),
                                    0,
                                    0);
                            v66 = (int)Address;
                            if ( (v65 & 0xC) == 0 && !(_DWORD)Address )
                            {
                              v77 = W32GetUserSessionState(v64);
                              ++*(_DWORD *)(v77 + 70592);
                              if ( (int)IszzzCalcStartCursorHideSupported() >= 0 )
                              {
                                ProcessWin32Process = PsGetProcessWin32Process(Process);
                                v91 = ProcessWin32Process;
                                if ( ProcessWin32Process )
                                  v91 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)ProcessWin32Process >> 64)
                                      & ProcessWin32Process;
                                zzzCalcStartCursorHide(v91, 5000);
                              }
                              if ( !*(_DWORD *)(W32GetUserSessionState(v78) + 70592) )
                              {
                                LODWORD(Address) = 0x20000;
                                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1780);
                              }
                              v80 = W32GetUserSessionState(v79);
                              --*(_DWORD *)(v80 + 70592);
                              if ( *(_QWORD *)(W32GetUserSessionState(v81) + 63288) )
                              {
                                if ( !*(_QWORD *)(v20 + 656) )
                                {
                                  UserSetLastError(1003);
                                  goto LABEL_161;
                                }
                              }
                            }
                            ApiSetEditionInitInputHangInfo();
                            v67 = *(_QWORD *)(ThreadWin32Thread + 464);
                            if ( v67 )
                              SetUnavailableInputSource(v67 + 532);
                            if ( (*(_DWORD *)(v20 + 12) & 0x20000) != 0 )
                              _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x4000u);
                            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x1000000u);
                            if ( (*(_DWORD *)(v20 + 12) & 0x140) == 0
                              && (*(_BYTE *)(v20 + 808) & 0x30) != 0x10
                              && ((v68 = *(_QWORD *)(W32GetUserSessionState(v67) + 18984)) != 0
                               && *(_QWORD *)(v68 + 456) == v20
                               || (unsigned int)LastWokenThread::Test(v20, 0) == 3) )
                            {
                              tagTHREADINFO::SetForegroundActivate(ThreadWin32Thread, 1);
                            }
                            if ( (**(_DWORD **)(W32GetUserSessionState(v67) + 19704) & 4) != 0 )
                            {
                              v74 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 1032LL);
                              v75 = v74 ? v74() : -1073741637;
                              if ( v75 >= 0 )
                              {
                                v76 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48)
                                                                    + 1040LL);
                                if ( v76 )
                                  v76(0);
                              }
                            }
                            if ( !(_DWORD)Self )
                            {
                              v71 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 1048LL);
                              Event = v71 ? v71() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                              v72 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 1056LL);
                              Event = v72 ? v72() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                            }
                            if ( !v66 && (*(_DWORD *)(v20 + 12) & 1) == 0 )
                            {
                              v69 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 1064LL);
                              if ( v69 )
                                v36 = v69();
                              if ( v36 >= 0 )
                              {
                                v89 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48)
                                                                     + 1072LL);
                                if ( v89 )
                                  v89(7);
                              }
                            }
                            if ( v44 )
                            {
                              if ( (v44[12] & 8) != 0 )
                              {
LABEL_161:
                                Event = -1073741823;
                                goto LABEL_79;
                              }
                              if ( v117 == -1 )
                              {
                                v73 = PtiCurrent();
                                KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v116, 0, (ULONG_PTR)v73);
                              }
                              PopAndFreeW32ThreadLock(v116);
                              v117 = -1;
                            }
                            v70 = *(_QWORD *)(ThreadWin32Thread + 1360);
                            if ( (v70 & 1) != 0 )
                              *(_QWORD *)(ThreadWin32Thread + 1360) = v70 & 0xFFFFFFFFFFFFFFFEuLL;
                            goto LABEL_86;
                          }
                          if ( !(_DWORD)Address )
                          {
                            if ( !*(_QWORD *)(W32GetUserSessionState(v64) + 63312)
                              || (v102 = *(_QWORD *)(W32GetUserSessionState(v64) + 63312),
                                  PsGetProcessInheritedFromUniqueProcessId(Process) != v102) )
                            {
                              *((_DWORD *)v111 + 8) &= ~0x80000000;
                              goto LABEL_117;
                            }
                            *(_QWORD *)(W32GetUserSessionState(v64) + 62592) = v20;
                            v104 = *(_QWORD *)(W32GetUserSessionState(v103) + 19704);
                            v105 = *(_QWORD *)(v104 + 4960);
                            *(_QWORD *)(W32GetUserSessionState(v104) + 36056) = v105;
                            *(_DWORD *)(v20 + 12) |= 0x200000u;
                            EtwTraceScreenSaverProcessEvent(1);
                            ForegroundBoost::SetForegroundPriority(ThreadWin32Thread, 1, 8);
                            *(_DWORD *)(v20 + 12) |= 0x400000u;
                          }
                          _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
                          goto LABEL_117;
                        }
LABEL_79:
                        if ( v44 )
                          Win32RawLockedItemBase<tagDESKTOP,&void UserDereferenceObject(void *),1,1,1>::UnlockWorker((ULONG_PTR)v116);
                        if ( v118 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)v112);
                        if ( v119 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                        xxxDestroyThreadInfo();
LABEL_86:
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v116);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v112);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                        return (unsigned int)Event;
                      }
                    }
                    CloseProtectedHandle(Handle);
                    CloseProtectedHandle(v110);
                    Handle = 0;
                    v110 = 0;
                  }
                }
                else
                {
                  Event = -1073741801;
                }
              }
            }
          }
LABEL_78:
          v44 = 0;
          goto LABEL_79;
        }
        if ( !*(_QWORD *)(W32GetUserSessionState(v26) + 14184) )
        {
          if ( *(_QWORD *)(W32GetUserSessionState(v27) + 14216) )
          {
            v93 = *(_QWORD *)(W32GetUserSessionState(v92) + 14216);
            v95 = W32GetUserSessionState(v94);
            v96 = 1;
          }
          else
          {
            if ( !*(_QWORD *)(W32GetUserSessionState(v92) + 14656) )
              goto LABEL_28;
            v93 = *(_QWORD *)(W32GetUserSessionState(v27) + 14656);
            v95 = W32GetUserSessionState(v97);
            v96 = 0;
          }
          v106 = (char *)(v95 + 14184);
          v107 = v93;
          HMAssignmentLock(&v106, v96);
        }
LABEL_28:
        if ( *(_QWORD *)(W32GetUserSessionState(v27) + 14184) )
        {
          v29 = W32GetUserSessionState(v28);
          if ( (*(_BYTE *)(HMPheFromObject(*(_QWORD *)(v29 + 14184)) + 25) & 1) != 0 )
          {
            LODWORD(Address) = 0x20000;
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1356);
          }
        }
        v106 = (char *)(ThreadWin32Thread + 472);
        v30 = *(_QWORD *)(W32GetUserSessionState(v28) + 14184);
        goto LABEL_32;
      }
    }
  }
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v116);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v112);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return 3221225738LL;
}

```

## disassembly

```asm
0x14002d824  push    rbx
0x14002d826  push    rsi
0x14002d827  push    rdi
0x14002d828  push    r12
0x14002d82a  push    r13
0x14002d82c  push    r14
0x14002d82e  push    r15
0x14002d830  sub     rsp, 190h
0x14002d837  mov     r13, rcx
0x14002d83a  call    cs:__imp_PsGetThreadProcess
0x14002d841  nop     dword ptr [rax+rax+00h]
0x14002d846  mov     rbx, rax
0x14002d849  mov     [rsp+1C8h+Process], rax
0x14002d84e  xor     edx, edx; Val
0x14002d850  lea     r8d, [rdx+48h]; Size
0x14002d854  lea     rcx, [rsp+1C8h+var_F8]; void *
0x14002d85c  call    memset
0x14002d861  xor     esi, esi
0x14002d863  mov     [rsp+1C8h+Handle], rsi
0x14002d86b  mov     [rsp+1C8h+var_168], rsi
0x14002d870  mov     rax, gs:30h
0x14002d879  mov     [rsp+1C8h+arg_10], rax
0x14002d881  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x14002d889  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14002d88e  lea     rcx, [rsp+1C8h+var_158]
0x14002d893  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14002d898  lea     rcx, [rsp+1C8h+var_128]
0x14002d8a0  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14002d8a5  xorps   xmm1, xmm1
0x14002d8a8  movups  [rsp+1C8h+var_98], xmm1
0x14002d8b0  movups  [rsp+1C8h+var_88], xmm1
0x14002d8b8  movups  [rsp+1C8h+var_78], xmm1
0x14002d8c0  mov     al, byte ptr cs:Microsoft_Windows_Win32kEnableBits+1
0x14002d8c6  test    al, al
0x14002d8c8  jns     short loc_14002D8DD
0x14002d8ca  lea     r8, W32kControlGuid
0x14002d8d1  lea     rdx, InitiateGuiThreadExecution
0x14002d8d8  call    McTemplateK0_EtwWriteTransfer
0x14002d8dd  call    cs:__imp_W32GetUserSessionState
0x14002d8e4  nop     dword ptr [rax+rax+00h]
0x14002d8e9  cmp     [rax+8D88h], esi
0x14002d8ef  jnz     loc_14002ED98
0x14002d8f5  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14002d8fc  nop     dword ptr [rax+rax+00h]
0x14002d901  test    rax, rax
0x14002d904  jz      loc_14002ED98
0x14002d90a  mov     rcx, [rax]
0x14002d90d  neg     rcx
0x14002d910  sbb     rdx, rdx
0x14002d913  and     rax, rdx
0x14002d916  test    rax, rax
0x14002d919  jz      loc_14002ED98
0x14002d91f  mov     [rsp+1C8h+var_108], rsi
0x14002d927  mov     [rsp+1C8h+var_110], rsi
0x14002d92f  call    cs:__imp_W32GetUserSessionState
0x14002d936  nop     dword ptr [rax+rax+00h]
0x14002d93b  mov     edi, 1
0x14002d940  add     [rax+8D90h], edi
0x14002d946  call    cs:__imp_W32GetUserGdiSessionState
0x14002d94d  nop     dword ptr [rax+rax+00h]
0x14002d952  mov     r12d, 2000048h
0x14002d958  cmp     rbx, [rax+28h]
0x14002d95c  cmovnz  r12d, esi
0x14002d960  mov     rcx, r13
0x14002d963  call    W32GetThreadWin32Thread
0x14002d968  mov     r14, rax
0x14002d96b  mov     [rsp+1C8h+BugCheckParameter3], rsi
0x14002d973  mov     rcx, rbx
0x14002d976  call    cs:__imp_PsGetProcessPeb
0x14002d97d  nop     dword ptr [rax+rax+00h]
0x14002d982  mov     [rsp+1C8h+Address], rax
0x14002d98a  mov     [rsp+1C8h+var_A8], 7D0h
0x14002d996  mov     rcx, [rsp+1C8h+Address]; Address
0x14002d99e  mov     [rsp+1C8h+var_A8], rdi
0x14002d9a6  mov     r8d, edi; Alignment
0x14002d9a9  mov     edx, edi; Length
0x14002d9ab  call    cs:__imp_ProbeForRead
0x14002d9b2  nop     dword ptr [rax+rax+00h]
0x14002d9b7  mov     rax, [rsp+1C8h+Address]
0x14002d9bf  mov     rcx, [rax+20h]
0x14002d9c3  mov     [rsp+1C8h+Address], rcx
0x14002d9cb  lea     rax, [rsp+1C8h+var_F8]
0x14002d9d3  mov     [rsp+1C8h+var_160], rax
0x14002d9d8  mov     [rsp+1C8h+var_68], rax
0x14002d9e0  mov     [rsp+1C8h+var_A0], 450h
0x14002d9ec  mov     rcx, [rsp+1C8h+Address]; Address
0x14002d9f4  mov     [rsp+1C8h+var_A0], rdi
0x14002d9fc  mov     r8d, edi; Alignment
0x14002d9ff  mov     edx, edi; Length
0x14002da01  call    cs:__imp_ProbeForRead
0x14002da08  nop     dword ptr [rax+rax+00h]
0x14002da0d  mov     rax, [rsp+1C8h+Address]
0x14002da15  mov     rcx, [rax+20h]
0x14002da19  mov     [rsp+1C8h+var_F8], rcx
0x14002da21  mov     rax, [rsp+1C8h+Address]
0x14002da29  mov     rcx, [rax+28h]
0x14002da2d  mov     [rsp+1C8h+var_F0], rcx
0x14002da35  mov     rax, [rsp+1C8h+Address]
0x14002da3d  mov     ecx, [rax+88h]
0x14002da43  mov     [rsp+1C8h+var_E8], ecx
0x14002da4a  mov     rax, [rsp+1C8h+Address]
0x14002da52  mov     ecx, [rax+8Ch]
0x14002da58  mov     [rsp+1C8h+var_E4], ecx
0x14002da5f  mov     rax, [rsp+1C8h+Address]
0x14002da67  mov     ecx, [rax+90h]
0x14002da6d  mov     [rsp+1C8h+var_E0], ecx
0x14002da74  mov     rax, [rsp+1C8h+Address]
0x14002da7c  mov     ecx, [rax+94h]
0x14002da82  mov     [rsp+1C8h+var_DC], ecx
0x14002da89  mov     rax, [rsp+1C8h+Address]
0x14002da91  mov     ecx, [rax+0A4h]
0x14002da97  mov     [rsp+1C8h+var_D8], ecx
0x14002da9e  mov     rax, [rsp+1C8h+Address]
0x14002daa6  mov     ecx, [rax+0A8h]
0x14002daac  mov     [rsp+1C8h+var_D4], ecx
0x14002dab3  mov     rcx, [rsp+1C8h+Address]
0x14002dabb  add     rcx, 0C0h
0x14002dac2  mov     [rsp+1C8h+var_60], rcx
0x14002daca  lea     r8, [rsp+1C8h+var_D0]
0x14002dad2  call    ??$DuplicateUnicodeStringFromUser@$0A@@@YAJV?$UserModePointer@UUSERMODE_UNICODE_STRING@@@@KPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeStringFromUser<0>(UserModePointer<USERMODE_UNICODE_STRING>,ulong,_UNICODE_STRING *)
0x14002dad7  test    eax, eax
0x14002dad9  js      loc_14002DBC9
0x14002dadf  mov     rbx, [rsp+1C8h+BugCheckParameter3]
0x14002dae7  test    rbx, rbx
0x14002daea  jnz     loc_14002DB77
0x14002daf0  lea     rdi, GreDeleteFastMutex
0x14002daf7  mov     rcx, [rsp+1C8h+Address]
0x14002daff  add     rcx, 0D0h
0x14002db06  mov     [rsp+1C8h+var_188], rcx
0x14002db0b  lea     r8, [rsp+1C8h+var_C0]
0x14002db13  call    ??$DuplicateUnicodeStringFromUser@$0A@@@YAJV?$UserModePointer@UUSERMODE_UNICODE_STRING@@@@KPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeStringFromUser<0>(UserModePointer<USERMODE_UNICODE_STRING>,ulong,_UNICODE_STRING *)
0x14002db18  test    eax, eax
0x14002db1a  js      loc_14002DC03
0x14002db20  mov     rbx, [rsp+1C8h+var_B8]
0x14002db28  test    rbx, rbx
0x14002db2b  jz      loc_14002DC3A
0x14002db31  mov     [rsp+1C8h+var_110], rbx
0x14002db39  cmp     [rsp+1C8h+var_148], 0FFFFFFFFFFFFFFFFh
0x14002db42  jnz     loc_14002DC11
0x14002db48  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002db4d  mov     rcx, [rax+178h]
0x14002db54  mov     [rsp+1C8h+var_158], rcx
0x14002db59  lea     rcx, [rsp+1C8h+var_158]
0x14002db5e  mov     [rax+178h], rcx
0x14002db65  mov     [rsp+1C8h+var_150], rbx
0x14002db6a  mov     [rsp+1C8h+var_148], rdi
0x14002db72  jmp     loc_14002DC3A
0x14002db77  mov     [rsp+1C8h+var_108], rbx
0x14002db7f  cmp     [rsp+1C8h+var_130], 0FFFFFFFFFFFFFFFFh
0x14002db88  jnz     short loc_14002DBD7
0x14002db8a  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002db8f  mov     rcx, [rax+178h]
0x14002db96  mov     [rsp+1C8h+BugCheckParameter2], rcx
0x14002db9e  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x14002dba6  mov     [rax+178h], rcx
0x14002dbad  mov     [rsp+1C8h+var_138], rbx
0x14002dbb5  lea     rdi, GreDeleteFastMutex
0x14002dbbc  mov     [rsp+1C8h+var_130], rdi
0x14002dbc4  jmp     loc_14002DAF7
0x14002dbc9  mov     ecx, eax; Status
0x14002dbcb  call    cs:__imp_ExRaiseStatus
0x14002dbd7  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002dbdc  mov     [rsp+1C8h+BugCheckParameter4], rax; BugCheckParameter4
0x14002dbe1  mov     r9, rbx; BugCheckParameter3
0x14002dbe4  lea     r8, [rsp+1C8h+BugCheckParameter2]; BugCheckParameter2
0x14002dbec  mov     edx, 12h; BugCheckParameter1
0x14002dbf1  mov     ecx, 164h; BugCheckCode
0x14002dbf6  call    cs:__imp_KeBugCheckEx
0x14002dc03  mov     ecx, eax; Status
0x14002dc05  call    cs:__imp_ExRaiseStatus
0x14002dc11  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002dc16  mov     [rsp+1C8h+BugCheckParameter4], rax; BugCheckParameter4
0x14002dc1b  mov     r9, rbx; BugCheckParameter3
0x14002dc1e  lea     r8, [rsp+1C8h+var_158]; BugCheckParameter2
0x14002dc23  mov     edx, 12h; BugCheckParameter1
0x14002dc28  mov     ecx, 164h; BugCheckCode
0x14002dc2d  call    cs:__imp_KeBugCheckEx
0x14002dc3a  jmp     short loc_14002DC48
0x14002dc3c  mov     edi, eax
0x14002dc3e  xor     esi, esi
0x14002dc40  mov     r13d, esi
0x14002dc43  jmp     loc_14002E1F3
0x14002dc48  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14002dc4f  nop     dword ptr [rax+rax+00h]
0x14002dc54  mov     r15, rax
0x14002dc57  test    rax, rax
0x14002dc5a  jz      short loc_14002DC68
0x14002dc5c  mov     rax, [rax]
0x14002dc5f  neg     rax
0x14002dc62  sbb     rcx, rcx
0x14002dc65  and     r15, rcx
0x14002dc68  mov     edi, r12d
0x14002dc6b  bts     edi, 8
0x14002dc6f  test    byte ptr [r15+0Ch], 80h
0x14002dc74  cmovz   edi, r12d
0x14002dc78  mov     rcx, r13; Thread
0x14002dc7b  call    cs:__imp_PsGetThreadProcessId
0x14002dc82  nop     dword ptr [rax+rax+00h]
0x14002dc87  mov     rbx, rax
0x14002dc8a  call    cs:__imp_W32GetUserSessionState
0x14002dc91  nop     dword ptr [rax+rax+00h]
0x14002dc96  mov     r13d, edi
0x14002dc99  mov     r12d, 2000000h
0x14002dc9f  or      r13d, r12d
0x14002dca2  cmp     [rax+0F750h], rbx
0x14002dca9  cmovnz  r13d, edi
0x14002dcad  lock or [r14+208h], r13d
0x14002dcb5  call    cs:__imp_W32GetUserSessionState
0x14002dcbc  nop     dword ptr [rax+rax+00h]
0x14002dcc1  mov     ecx, [rax+104E8h]
0x14002dcc7  test    cl, cl
0x14002dcc9  js      loc_14002DE5B
0x14002dccf  call    cs:__imp_W32GetUserSessionState
0x14002dcd6  nop     dword ptr [rax+rax+00h]
0x14002dcdb  cmp     [rax+3768h], rsi
0x14002dce2  jz      loc_14002E99B
0x14002dce8  call    cs:__imp_W32GetUserSessionState
0x14002dcef  nop     dword ptr [rax+rax+00h]
0x14002dcf4  cmp     [rax+3768h], rsi
0x14002dcfb  jz      short loc_14002DD1F
0x14002dcfd  call    cs:__imp_W32GetUserSessionState
0x14002dd04  nop     dword ptr [rax+rax+00h]
0x14002dd09  mov     rcx, [rax+3768h]
0x14002dd10  call    _HMPheFromObject
0x14002dd15  test    byte ptr [rax+19h], 1
0x14002dd19  jnz     loc_14002EA2F
0x14002dd1f  lea     rax, [r14+1D8h]
0x14002dd26  mov     [rsp+1C8h+var_188], rax
0x14002dd2b  call    cs:__imp_W32GetUserSessionState
0x14002dd32  nop     dword ptr [rax+rax+00h]
0x14002dd37  mov     rcx, [rax+3768h]
0x14002dd3e  mov     [rsp+1C8h+var_180], rcx
0x14002dd43  xor     edx, edx
0x14002dd45  lea     rcx, [rsp+1C8h+var_188]
0x14002dd4a  call    HMAssignmentLock
0x14002dd4f  lea     rax, [r14+440h]
0x14002dd56  mov     [r14+1E0h], rax
0x14002dd5d  test    dword ptr [r15+0Ch], 800000h
0x14002dd65  jnz     loc_14002EA58
0x14002dd6b  mov     [r14+1C8h], r15
0x14002dd72  mov     rax, [r15+148h]
0x14002dd79  mov     [r14+2B8h], rax
0x14002dd80  mov     [r15+148h], r14
0x14002dd87  inc     dword ptr [r15+178h]
0x14002dd8e  mov     rax, [rsp+1C8h+arg_10]
0x14002dd96  test    rax, rax
0x14002dd99  jnz     loc_14002DE2F
0x14002dd9f  mov     rax, [rsp+1C8h+arg_10]
0x14002dda7  add     rax, 800h
0x14002ddad  mov     [r14+200h], rax
0x14002ddb4  mov     rcx, [r14+200h]
0x14002ddbb  mov     eax, [r14+188h]
0x14002ddc2  mov     [rcx+0E8h], eax
0x14002ddc8  mov     rax, [r14+200h]
0x14002ddcf  mov     [rax+0ECh], esi
0x14002ddd5  mov     rax, [r14+200h]
0x14002dddc  add     rax, 0E8h
0x14002dde2  mov     [r14+190h], rax
0x14002dde9  mov     rcx, [r14+200h]
0x14002ddf0  mov     eax, [r14+18Ch]
0x14002ddf7  mov     [rcx+0F0h], eax
0x14002ddfd  mov     rax, [r14+200h]
0x14002de04  mov     [rax+0F4h], esi
0x14002de0a  mov     rax, [r14+200h]
0x14002de11  add     rax, 0F0h
0x14002de17  mov     [r14+198h], rax
0x14002de1e  jmp     loc_14002DEB6
0x14002de23  mov     edi, eax
0x14002de25  xor     esi, esi
0x14002de27  mov     r13d, esi
0x14002de2a  jmp     loc_14002E1F3
0x14002de2f  mov     rcx, [r14]; Thread
0x14002de32  mov     rbx, [rsp+1C8h+arg_10]
0x14002de3a  call    cs:__imp_PsGetThreadId
0x14002de41  nop     dword ptr [rax+rax+00h]
0x14002de46  mov     [rbx+78h], rax
0x14002de4a  jmp     loc_14002DD9F
0x14002de4f  mov     edi, eax
0x14002de51  xor     esi, esi
0x14002de53  mov     r13d, esi
0x14002de56  jmp     loc_14002E1F3
0x14002de5b  call    cs:__imp_W32GetUserSessionState
0x14002de62  nop     dword ptr [rax+rax+00h]
0x14002de67  cmp     [rax+3788h], rsi
0x14002de6e  jz      short loc_14002DE92
0x14002de70  call    cs:__imp_W32GetUserSessionState
0x14002de77  nop     dword ptr [rax+rax+00h]
0x14002de7c  mov     rcx, [rax+3788h]
0x14002de83  call    _HMPheFromObject
0x14002de88  test    byte ptr [rax+19h], 1
0x14002de8c  jnz     loc_14002E972
0x14002de92  lea     rax, [r14+1D8h]
0x14002de99  mov     [rsp+1C8h+var_188], rax
0x14002de9e  call    cs:__imp_W32GetUserSessionState
0x14002dea5  nop     dword ptr [rax+rax+00h]
0x14002deaa  mov     rcx, [rax+3788h]
0x14002deb1  jmp     loc_14002DD3E
0x14002deb6  test    [r15+0Ch], r12d
0x14002deba  jnz     loc_14002EA65
0x14002dec0  cmp     [r14+298h], esi
  ... truncated ...
```
