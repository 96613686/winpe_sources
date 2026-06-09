# HANDLELOCK::vUnlockAndRelease(void)

- ea: `0x14001cbec`
- end: `0x14001d245`
- name: `?vUnlockAndRelease@HANDLELOCK@@QEAAXXZ`
- size: `1625`
- prototype: `void __fastcall(HANDLELOCK *__hidden this)`
- caller_count: `7`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001bfa0`
- `0x14001ef1c`
- `0x140021d00`
- `0x14002205c`
- `0x140035730`
- `0x140093b98`
- `0x1401e2180`

## callees

- `0x140013ff0`
- `0x14001ca10`
- `0x14001cbec`
- `0x14001e5e0`
- `0x140028974`
- `0x1400411c0`
- `0x140190650`
- `0x1401ab6b0`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14001cd9d`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001cd9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ceca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ceca`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14001cc3f`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14001cc3f`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001ccc2`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001ccc2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001cc27`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001cc27`
- `ntoskrnl!PsSetProcessWin32Process` at `0x14001d22c`
- `ntoskrnl!PsSetProcessWin32Process` at `0x14001d22c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001cdac`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001d026`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001cdac`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001d026`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14001d06f`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14001d06f`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001d017`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001d017`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001ccab`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001ccab`
- `ntoskrnl!ObfReferenceObject` at `0x14001cc69`
- `ntoskrnl!ObfReferenceObject` at `0x14001d0aa`
- `ntoskrnl!ObfReferenceObject` at `0x14001cc69`
- `ntoskrnl!ObfReferenceObject` at `0x14001d0aa`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001ce3e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001ce3e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001cd1b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d0bf`
- `ntoskrnl!ObfDereferenceObject` at `0x14001cd1b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d0bf`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14001d088`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14001d088`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001cdd4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001ce18`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001cdd4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001ce18`

## pseudocode

```c
void __fastcall HANDLELOCK::vUnlockAndRelease(HANDLELOCK *this)
{
  signed int v2; // r15d
  _QWORD *v3; // rdi
  PVOID *CurrentProcessWin32Process; // rax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rcx
  HSEMAPHORE v7; // r14
  int v8; // ecx
  int v9; // r8d
  struct _KTHREAD *CurrentThread; // r12
  __int64 v11; // rbp
  __int64 *ThreadWin32Thread; // rax
  __int64 v13; // rax
  __int64 v14; // rbp
  void *v16; // rdi
  bool v17; // cl
  char v18; // di
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  __int64 *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rbx
  __int64 CurrentProcess; // rax
  char ProcessSessionId; // al
  int v31; // ecx
  int v32; // r8d
  int (*v33)(void); // rax
  char v34; // bl
  __int64 v35; // rdi
  void (__fastcall *v36)(__int64, __int64); // rax
  __int64 v37; // rdx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdi
  __int64 *v43; // rdi
  __int64 v44; // rbx
  __int64 v45; // rax
  unsigned int v46; // ecx
  int v47; // ebx
  int v48; // r8d
  unsigned __int64 v49; // rax
  unsigned __int64 i; // rcx
  __int64 v51; // rdx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  int CurrentWin32kSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  bool v60; // cl
  PVOID *ProcessWin32Process; // rax
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  PEPROCESS Process; // [rsp+78h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(*(_QWORD *)this + 8LL) & 0xFFFFFFFE;
  if ( !v2 || v2 == -2147483630 )
    goto LABEL_19;
  v3 = (_QWORD *)*((_QWORD *)this + 2);
  if ( v2 == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
  {
    CurrentProcessWin32Process = (PVOID *)PsGetCurrentProcessWin32Process();
    v5 = (volatile signed __int32 *)CurrentProcessWin32Process;
    if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process || !CurrentProcessWin32Process )
      goto LABEL_19;
    ObfReferenceObject(*CurrentProcessWin32Process);
    _InterlockedIncrement(v5 + 2);
    goto LABEL_8;
  }
  Process = 0;
  if ( PsLookupProcessByProcessId((HANDLE)v2, &Process) >= 0 )
  {
    ProcessWin32Process = (PVOID *)PsGetProcessWin32Process(Process);
    v5 = (volatile signed __int32 *)ProcessWin32Process;
    if ( ProcessWin32Process && !*ProcessWin32Process )
    {
      v5 = 0;
    }
    else if ( ProcessWin32Process )
    {
      ObfReferenceObject(*ProcessWin32Process);
      _InterlockedIncrement(v5 + 2);
    }
    ObfDereferenceObject(Process);
    if ( v5 )
    {
LABEL_8:
      v7 = (HSEMAPHORE)(*v3 + 1512LL);
      GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v6, v7);
      --*((_DWORD *)v5 + 15);
      if ( v7 )
      {
        if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
          McTemplateK0pz_EtwWriteTransfer(v8, (unsigned int)&LockRelease, v9, (_DWORD)v7, (__int64)L"Hmgr");
        CurrentThread = KeGetCurrentThread();
        v11 = 0;
        if ( !(unsigned __int8)KeIsAttachedProcess()
          || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
              CurrentThreadProcess = PsGetCurrentThreadProcess(),
              CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
        {
          ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
          if ( ThreadWin32Thread )
            v11 = *ThreadWin32Thread;
        }
        v13 = v11 + 8;
        v14 = -v11;
        if ( (v13 & -(__int64)(v14 != 0)) != 0 && (*(_BYTE *)((v13 & -(__int64)(v14 != 0)) + 0x1C))-- == 1 )
          *(_QWORD *)(v13 & -(__int64)(v14 != 0)) &= ~0x100000uLL;
        GreReleaseSemaphoreSharedInternal(v7);
      }
      v16 = *(void **)v5;
      v17 = (v5[69] & 0x200) != 0;
      if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
      {
        v60 = !v17;
        if ( v60 )
        {
          if ( v60 )
            UserDeleteW32Process((PVOID)v5);
        }
        else
        {
          PsSetProcessWin32Process(*(_QWORD *)v5, 0, v5);
          GreDeleteFastMutex((PVOID)v5);
        }
      }
      ObfDereferenceObject(v16);
    }
  }
LABEL_19:
  v18 = 15;
  v19 = *(unsigned __int8 *)(*(_QWORD *)this + 14LL);
  if ( v19 > 0xF )
  {
    v18 = 23;
    if ( v19 > 0x17 )
    {
      v18 = 24;
      v62 = v19 - 24;
      if ( !v62 )
        goto LABEL_29;
      v63 = v62 - 1;
      if ( !v63 )
      {
        v18 = 25;
        goto LABEL_29;
      }
      v64 = v63 - 1;
      if ( !v64 )
      {
        v18 = 26;
        goto LABEL_29;
      }
      v65 = v64 - 1;
      if ( !v65 )
      {
        v18 = 27;
        goto LABEL_29;
      }
      v66 = v65 - 1;
      if ( !v66 )
      {
        v18 = 28;
        goto LABEL_29;
      }
      v67 = v66 - 1;
      if ( !v67 )
      {
        v18 = 29;
        goto LABEL_29;
      }
      if ( v67 == 1 )
      {
        v18 = 30;
        goto LABEL_29;
      }
    }
    else
    {
      if ( v19 == 23 )
        goto LABEL_29;
      v55 = v19 - 16;
      if ( !v55 )
      {
        v18 = 16;
        goto LABEL_29;
      }
      v56 = v55 - 1;
      if ( !v56 )
      {
        v18 = 17;
        goto LABEL_29;
      }
      v57 = v56 - 1;
      if ( !v57 )
      {
        v18 = 18;
        goto LABEL_29;
      }
      v71 = v57 - 1;
      if ( !v71 )
      {
        v18 = 19;
        goto LABEL_29;
      }
      v72 = v71 - 1;
      if ( !v72 )
      {
        v18 = 20;
        goto LABEL_29;
      }
      v73 = v72 - 1;
      if ( !v73 )
      {
        v18 = 21;
        goto LABEL_29;
      }
      if ( v73 == 1 )
      {
        v18 = 22;
        goto LABEL_29;
      }
    }
  }
  else
  {
    if ( v19 == 15 )
      goto LABEL_29;
    v18 = 7;
    if ( v19 > 7 )
    {
      v18 = 8;
      v52 = v19 - 8;
      if ( !v52 )
        goto LABEL_29;
      v53 = v52 - 1;
      if ( !v53 )
      {
        v18 = 9;
        goto LABEL_29;
      }
      v54 = v53 - 1;
      if ( !v54 )
      {
        v18 = 10;
        goto LABEL_29;
      }
      v68 = v54 - 1;
      if ( !v68 )
      {
        v18 = 11;
        goto LABEL_29;
      }
      v69 = v68 - 1;
      if ( !v69 )
      {
        v18 = 12;
        goto LABEL_29;
      }
      v70 = v69 - 1;
      if ( !v70 )
      {
        v18 = 13;
        goto LABEL_29;
      }
      if ( v70 == 1 )
      {
        v18 = 14;
        goto LABEL_29;
      }
    }
    else
    {
      if ( v19 == 7 )
        goto LABEL_29;
      if ( !*(_BYTE *)(*(_QWORD *)this + 14LL) )
      {
        v18 = 0;
        goto LABEL_29;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        v18 = 1;
        goto LABEL_29;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v18 = 2;
        goto LABEL_29;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v18 = 3;
        goto LABEL_29;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v18 = 4;
        goto LABEL_29;
      }
      v46 = v23 - 1;
      if ( !v46 )
      {
        v18 = 5;
        goto LABEL_29;
      }
      if ( v46 == 1 )
      {
        v18 = 6;
        goto LABEL_29;
      }
    }
  }
  v18 = -1;
LABEL_29:
  v24 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 96LL))(
                     *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                     **(unsigned int **)this);
  if ( (Microsoft_Windows_Win32kEnableBits & 0x20000000000LL) != 0 )
  {
    v28 = *v24;
    CurrentProcess = PsGetCurrentProcess(v26, v25, v27);
    ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess);
    McTemplateK0pqqq_EtwWriteTransfer(v31, (unsigned int)&GdiDestroyHandle, v32, v28, v18, ProcessSessionId, v2);
  }
  v33 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2688LL);
  if ( v33 )
  {
    if ( v33() >= 0 )
    {
      v34 = *(_BYTE *)(*(_QWORD *)this + 14LL);
      v35 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 96LL))(
                         *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                         **(unsigned int **)this);
      v36 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2696LL);
      if ( v36 )
      {
        LOBYTE(v37) = v34;
        v36(v35, v37);
      }
    }
  }
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    v39 = *CurrentThreadWin32Thread;
  else
    v39 = 0;
  v40 = v39 + 8;
  v41 = -v39;
  if ( (v40 & -(__int64)(v41 != 0)) != 0 )
  {
    v42 = *(_QWORD *)((v40 & -(__int64)(v41 != 0)) + 0x148);
    if ( v42 )
    {
      v47 = (unsigned __int16)*(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2)
                                                                                                 + 8LL)
                                                                                   + 96LL))(
                                           *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                                           **(unsigned int **)this);
      v48 = v47
          | (*(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 96LL))(
                          *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                          **(unsigned int **)this) >> 8)
          & 0xFF0000;
      v49 = *(_QWORD *)(v42 + 24);
      for ( i = 0; i < v49; ++i )
      {
        v51 = *(_QWORD *)(v42 + 40);
        if ( *(_DWORD *)(v51 + 4 * i) == v48 )
        {
          *(_DWORD *)(v51 + 4 * i) = *(_DWORD *)(v51 + 4 * v49 - 4);
          *(_DWORD *)(*(_QWORD *)(v42 + 40) + 4LL * (*(_QWORD *)(v42 + 24))-- - 4) = 0;
          break;
        }
      }
    }
  }
  *(_BYTE *)(*(_QWORD *)this + 14LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 16LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 8LL) = 0;
  v43 = *(__int64 **)(*((_QWORD *)this + 2) + 8LL);
  v44 = *v43;
  v45 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v43 + 96))(v43, **(unsigned int **)this);
  (*(void (__fastcall **)(__int64 *, __int64))(v44 + 56))(v43, v45);
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = 0;
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14001cbec  mov     [rsp+arg_10], rbx
0x14001cbf1  mov     [rsp+arg_18], rbp
0x14001cbf6  push    rsi
0x14001cbf7  push    rdi
0x14001cbf8  push    r12
0x14001cbfa  push    r14
0x14001cbfc  push    r15
0x14001cbfe  sub     rsp, 40h
0x14001cc02  mov     rax, [rcx]
0x14001cc05  mov     rsi, rcx
0x14001cc08  mov     r15d, [rax+8]
0x14001cc0c  and     r15d, 0FFFFFFFEh
0x14001cc10  jz      loc_14001CD27
0x14001cc16  cmp     r15d, 80000012h
0x14001cc1d  jz      loc_14001CD27
0x14001cc23  mov     rdi, [rcx+10h]
0x14001cc27  call    cs:__imp_PsGetCurrentProcessId
0x14001cc2e  nop     dword ptr [rax+rax+00h]
0x14001cc33  and     eax, 0FFFFFFFCh
0x14001cc36  cmp     r15d, eax
0x14001cc39  jnz     loc_14001D05E
0x14001cc3f  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14001cc46  nop     dword ptr [rax+rax+00h]
0x14001cc4b  mov     rbx, rax
0x14001cc4e  test    rax, rax
0x14001cc51  jz      short loc_14001CC5D
0x14001cc53  cmp     qword ptr [rax], 0
0x14001cc57  jz      loc_14001CD27
0x14001cc5d  test    rbx, rbx
0x14001cc60  jz      loc_14001CD27
0x14001cc66  mov     rcx, [rax]; Object
0x14001cc69  call    cs:__imp_ObfReferenceObject
0x14001cc70  nop     dword ptr [rax+rax+00h]
0x14001cc75  lock inc dword ptr [rbx+8]
0x14001cc79  mov     r14, [rdi]
0x14001cc7c  add     r14, 5E8h
0x14001cc83  mov     rdx, r14
0x14001cc86  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14001cc8b  dec     dword ptr [rbx+3Ch]
0x14001cc8e  test    r14, r14
0x14001cc91  jz      short loc_14001CCF8
0x14001cc93  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14001cc9a  jnz     loc_14001D1F7
0x14001cca0  mov     r12, gs:188h
0x14001cca9  xor     ebp, ebp
0x14001ccab  call    cs:__imp_KeIsAttachedProcess
0x14001ccb2  nop     dword ptr [rax+rax+00h]
0x14001ccb7  test    al, al
0x14001ccb9  jnz     loc_14001D010
0x14001ccbf  mov     rcx, r12
0x14001ccc2  call    cs:__imp_PsGetThreadWin32Thread
0x14001ccc9  nop     dword ptr [rax+rax+00h]
0x14001ccce  test    rax, rax
0x14001ccd1  jz      short loc_14001CCD6
0x14001ccd3  mov     rbp, [rax]
0x14001ccd6  lea     rax, [rbp+8]
0x14001ccda  neg     rbp
0x14001ccdd  sbb     rdx, rdx
0x14001cce0  and     rdx, rax
0x14001cce3  jz      short loc_14001CCF0
0x14001cce5  add     byte ptr [rdx+1Ch], 0FFh
0x14001cce9  jnz     short loc_14001CCF0
0x14001cceb  btr     qword ptr [rdx], 14h
0x14001ccf0  mov     rcx, r14; HSEMAPHORE
0x14001ccf3  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14001ccf8  mov     ecx, [rbx+114h]
0x14001ccfe  mov     rdi, [rbx]
0x14001cd01  shr     ecx, 9
0x14001cd04  and     cl, 1
0x14001cd07  or      eax, 0FFFFFFFFh
0x14001cd0a  lock xadd [rbx+8], eax
0x14001cd0f  cmp     eax, 1
0x14001cd12  jz      loc_14001D03F
0x14001cd18  mov     rcx, rdi; Object
0x14001cd1b  call    cs:__imp_ObfDereferenceObject
0x14001cd22  nop     dword ptr [rax+rax+00h]
0x14001cd27  mov     rdx, [rsi]
0x14001cd2a  mov     edi, 0Fh
0x14001cd2f  movzx   ecx, byte ptr [rdx+0Eh]
0x14001cd33  cmp     ecx, edi
0x14001cd35  ja      loc_14001CFB8
0x14001cd3b  jz      short loc_14001CD7B
0x14001cd3d  mov     edi, 7
0x14001cd42  cmp     ecx, edi
0x14001cd44  ja      loc_14001CF91
0x14001cd4a  jz      short loc_14001CD7B
0x14001cd4c  test    ecx, ecx
0x14001cd4e  jz      loc_14001D174
0x14001cd54  sub     ecx, 1
0x14001cd57  jz      loc_14001CF67
0x14001cd5d  sub     ecx, 1
0x14001cd60  jz      loc_14001D16A
0x14001cd66  sub     ecx, 1
0x14001cd69  jz      loc_14001D160
0x14001cd6f  sub     ecx, 1
0x14001cd72  jnz     loc_14001CEF0
0x14001cd78  lea     edi, [rcx+4]
0x14001cd7b  mov     rax, [rsi+10h]
0x14001cd7f  mov     edx, [rdx]
0x14001cd81  mov     rcx, [rax+8]
0x14001cd85  mov     rax, [rcx]
0x14001cd88  mov     rax, [rax+60h]
0x14001cd8c  call    _guard_dispatch_icall
0x14001cd91  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+5, 2
0x14001cd98  jz      short loc_14001CDD4
0x14001cd9a  mov     rbx, [rax]
0x14001cd9d  call    cs:__imp_PsGetCurrentProcess
0x14001cda4  nop     dword ptr [rax+rax+00h]
0x14001cda9  mov     rcx, rax
0x14001cdac  call    cs:__imp_PsGetProcessSessionIdEx
0x14001cdb3  nop     dword ptr [rax+rax+00h]
0x14001cdb8  mov     [rsp+68h+var_38], r15d
0x14001cdbd  lea     rdx, GdiDestroyHandle
0x14001cdc4  mov     [rsp+68h+var_40], eax
0x14001cdc8  mov     r9, rbx
0x14001cdcb  mov     dword ptr [rsp+68h+var_48], edi
0x14001cdcf  call    McTemplateK0pqqq_EtwWriteTransfer
0x14001cdd4  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14001cddb  nop     dword ptr [rax+rax+00h]
0x14001cde0  mov     rcx, [rax+18h]
0x14001cde4  mov     rax, [rcx+0A80h]
0x14001cdeb  test    rax, rax
0x14001cdee  jz      short loc_14001CE3E
0x14001cdf0  call    _guard_dispatch_icall
0x14001cdf5  test    eax, eax
0x14001cdf7  js      short loc_14001CE3E
0x14001cdf9  mov     rax, [rsi+10h]
0x14001cdfd  mov     rdx, [rsi]
0x14001ce00  mov     rcx, [rax+8]
0x14001ce04  mov     bl, [rdx+0Eh]
0x14001ce07  mov     edx, [rdx]
0x14001ce09  mov     rax, [rcx]
0x14001ce0c  mov     rax, [rax+60h]
0x14001ce10  call    _guard_dispatch_icall
0x14001ce15  mov     rdi, [rax]
0x14001ce18  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14001ce1f  nop     dword ptr [rax+rax+00h]
0x14001ce24  mov     r8, [rax+18h]
0x14001ce28  mov     rax, [r8+0A88h]
0x14001ce2f  test    rax, rax
0x14001ce32  jz      short loc_14001CE3E
0x14001ce34  mov     dl, bl
0x14001ce36  mov     rcx, rdi
0x14001ce39  call    _guard_dispatch_icall
0x14001ce3e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001ce45  nop     dword ptr [rax+rax+00h]
0x14001ce4a  test    rax, rax
0x14001ce4d  jz      loc_14001CFEE
0x14001ce53  mov     rcx, [rax]
0x14001ce56  lea     rax, [rcx+8]
0x14001ce5a  neg     rcx
0x14001ce5d  sbb     rdi, rdi
0x14001ce60  and     rdi, rax
0x14001ce63  jz      short loc_14001CE75
0x14001ce65  mov     rdi, [rdi+148h]
0x14001ce6c  test    rdi, rdi
0x14001ce6f  jnz     loc_14001CF01
0x14001ce75  mov     rax, [rsi]
0x14001ce78  mov     byte ptr [rax+0Eh], 0
0x14001ce7c  mov     rax, [rsi]
0x14001ce7f  mov     qword ptr [rax+10h], 0
0x14001ce87  mov     rax, [rsi]
0x14001ce8a  mov     dword ptr [rax+8], 0
0x14001ce91  mov     rax, [rsi+10h]
0x14001ce95  mov     rdx, [rsi]
0x14001ce98  mov     rdi, [rax+8]
0x14001ce9c  mov     edx, [rdx]
0x14001ce9e  mov     rcx, rdi
0x14001cea1  mov     rbx, [rdi]
0x14001cea4  mov     rax, [rbx+60h]
0x14001cea8  call    _guard_dispatch_icall
0x14001cead  mov     rdx, rax
0x14001ceb0  mov     rcx, rdi
0x14001ceb3  mov     rax, [rbx+38h]
0x14001ceb7  call    _guard_dispatch_icall
0x14001cebc  mov     dword ptr [rsi+8], 0
0x14001cec3  mov     qword ptr [rsi], 0
0x14001ceca  call    cs:__imp_KeLeaveCriticalRegion
0x14001ced1  nop     dword ptr [rax+rax+00h]
0x14001ced6  lea     r11, [rsp+68h+var_28]
0x14001cedb  mov     rbx, [r11+40h]
0x14001cedf  mov     rbp, [r11+48h]
0x14001cee3  mov     rsp, r11
0x14001cee6  pop     r15
0x14001cee8  pop     r14
0x14001ceea  pop     r12
0x14001ceec  pop     rdi
0x14001ceed  pop     rsi
0x14001ceee  retn
0x14001cef0  sub     ecx, 1
0x14001cef3  jnz     loc_14001CFFF
0x14001cef9  lea     edi, [rcx+5]
0x14001cefc  jmp     loc_14001CD7B
0x14001cf01  mov     rax, [rsi+10h]
0x14001cf05  mov     rdx, [rsi]
0x14001cf08  mov     rcx, [rax+8]
0x14001cf0c  mov     edx, [rdx]
0x14001cf0e  mov     rax, [rcx]
0x14001cf11  mov     rax, [rax+60h]
0x14001cf15  call    _guard_dispatch_icall
0x14001cf1a  mov     rdx, [rsi]
0x14001cf1d  mov     ebx, [rax]
0x14001cf1f  mov     rax, [rsi+10h]
0x14001cf23  mov     edx, [rdx]
0x14001cf25  movzx   ebx, bx
0x14001cf28  mov     rcx, [rax+8]
0x14001cf2c  mov     rax, [rcx]
0x14001cf2f  mov     rax, [rax+60h]
0x14001cf33  call    _guard_dispatch_icall
0x14001cf38  mov     r8d, [rax]
0x14001cf3b  shr     r8d, 8
0x14001cf3f  and     r8d, 0FF0000h
0x14001cf46  or      r8d, ebx
0x14001cf49  mov     rax, [rdi+18h]
0x14001cf4d  xor     ecx, ecx
0x14001cf4f  cmp     rcx, rax
0x14001cf52  jnb     loc_14001CE75
0x14001cf58  mov     rdx, [rdi+28h]
0x14001cf5c  cmp     [rdx+rcx*4], r8d
0x14001cf60  jz      short loc_14001CF71
0x14001cf62  inc     rcx
0x14001cf65  jmp     short loc_14001CF4F
0x14001cf67  mov     edi, 1
0x14001cf6c  jmp     loc_14001CD7B
0x14001cf71  mov     eax, [rdx+rax*4-4]
0x14001cf75  mov     [rdx+rcx*4], eax
0x14001cf78  mov     rcx, [rdi+18h]
0x14001cf7c  mov     rax, [rdi+28h]
0x14001cf80  mov     dword ptr [rax+rcx*4-4], 0
0x14001cf88  dec     qword ptr [rdi+18h]
0x14001cf8c  jmp     loc_14001CE75
0x14001cf91  mov     edi, 8
0x14001cf96  sub     ecx, edi
0x14001cf98  jz      loc_14001CD7B
0x14001cf9e  sub     ecx, 1
0x14001cfa1  jz      loc_14001D156
0x14001cfa7  sub     ecx, 1
0x14001cfaa  jnz     loc_14001D128
0x14001cfb0  lea     edi, [rcx+0Ah]
0x14001cfb3  jmp     loc_14001CD7B
0x14001cfb8  mov     edi, 17h
0x14001cfbd  cmp     ecx, edi
0x14001cfbf  ja      loc_14001D0DD
0x14001cfc5  jz      loc_14001CD7B
0x14001cfcb  sub     ecx, 10h
0x14001cfce  jnz     short loc_14001CFD8
0x14001cfd0  lea     edi, [rcx+10h]
0x14001cfd3  jmp     loc_14001CD7B
0x14001cfd8  sub     ecx, 1
0x14001cfdb  jz      short loc_14001CFF5
0x14001cfdd  sub     ecx, 1
0x14001cfe0  jnz     loc_14001D13F
0x14001cfe6  lea     edi, [rcx+12h]
0x14001cfe9  jmp     loc_14001CD7B
0x14001cfee  xor     ecx, ecx
0x14001cff0  jmp     loc_14001CE56
0x14001cff5  mov     edi, 11h
0x14001cffa  jmp     loc_14001CD7B
0x14001cfff  cmp     ecx, 1
0x14001d002  jnz     loc_14001D1EF
0x14001d008  lea     edi, [rcx+5]
0x14001d00b  jmp     loc_14001CD7B
0x14001d010  call    W32GetCurrentWin32kSessionId
0x14001d015  mov     edi, eax
0x14001d017  call    cs:__imp_PsGetCurrentThreadProcess
0x14001d01e  nop     dword ptr [rax+rax+00h]
0x14001d023  mov     rcx, rax
0x14001d026  call    cs:__imp_PsGetProcessSessionIdEx
0x14001d02d  nop     dword ptr [rax+rax+00h]
0x14001d032  cmp     edi, eax
0x14001d034  jz      loc_14001CCBF
0x14001d03a  jmp     loc_14001CCD6
0x14001d03f  xor     cl, 1
0x14001d042  jz      loc_14001D224
0x14001d048  cmp     cl, 1
0x14001d04b  jnz     loc_14001CD18
0x14001d051  mov     rcx, rbx; Buffer
0x14001d054  call    UserDeleteW32Process
0x14001d059  jmp     loc_14001CD18
0x14001d05e  movsxd  rcx, r15d; ProcessId
0x14001d061  lea     rdx, [rsp+68h+Process]; Process
0x14001d066  mov     [rsp+68h+Process], 0
0x14001d06f  call    cs:__imp_PsLookupProcessByProcessId
0x14001d076  nop     dword ptr [rax+rax+00h]
0x14001d07b  test    eax, eax
0x14001d07d  js      loc_14001CD27
0x14001d083  mov     rcx, [rsp+68h+Process]
0x14001d088  call    cs:__imp_PsGetProcessWin32Process
0x14001d08f  nop     dword ptr [rax+rax+00h]
0x14001d094  mov     rbx, rax
0x14001d097  test    rax, rax
0x14001d09a  jz      short loc_14001D0A2
0x14001d09c  cmp     qword ptr [rax], 0
0x14001d0a0  jz      short loc_14001D0D9
0x14001d0a2  test    rbx, rbx
0x14001d0a5  jz      short loc_14001D0BA
0x14001d0a7  mov     rcx, [rax]; Object
0x14001d0aa  call    cs:__imp_ObfReferenceObject
0x14001d0b1  nop     dword ptr [rax+rax+00h]
0x14001d0b6  lock inc dword ptr [rbx+8]
  ... truncated ...
```
