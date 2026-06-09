# CProcessChainInternal::Start(uchar *)

- ea: `0x1801db964`
- end: `0x1801dbc10`
- name: `?Start@CProcessChainInternal@@QEAAJPEAE@Z`
- size: `684`
- prototype: `__int64 __fastcall(CProcessChainInternal *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800423f0`

## callees

- `0x1801db498`
- `0x1801db504`
- `0x1801db590`
- `0x1801db5e8`
- `0x1801db964`
- `0x18021f010`

## import_xrefs

- `KERNEL32!CreateIoCompletionPort` at `0x1801dba04`
- `KERNEL32!CreateIoCompletionPort` at `0x1801dba04`
- `KERNEL32!CreateJobObjectW` at `0x1801db9d4`
- `KERNEL32!CreateJobObjectW` at `0x1801db9d4`
- `KERNEL32!SetInformationJobObject` at `0x1801dbaa9`
- `KERNEL32!SetInformationJobObject` at `0x1801dbaa9`
- `KERNEL32!AssignProcessToJobObject` at `0x1801dbabe`
- `KERNEL32!AssignProcessToJobObject` at `0x1801dbabe`
- `KERNEL32!ResumeThread` at `0x1801dbacc`
- `KERNEL32!ResumeThread` at `0x1801dbacc`
- `KERNEL32!TerminateProcess` at `0x1801dbbe1`
- `KERNEL32!TerminateProcess` at `0x1801dbbe1`
- `KERNEL32!GetFileAttributesW` at `0x1801db996`
- `KERNEL32!GetFileAttributesW` at `0x1801db996`
- `KERNEL32!CreateThread` at `0x1801dba31`
- `KERNEL32!CreateThread` at `0x1801dba31`
- `KERNEL32!CreateWaitableTimerW` at `0x1801dba54`
- `KERNEL32!CreateWaitableTimerW` at `0x1801dba54`
- `KERNEL32!SetWaitableTimer` at `0x1801dbafe`
- `KERNEL32!SetWaitableTimer` at `0x1801dbafe`
- `KERNEL32!CloseHandle` at `0x1801dbbf0`
- `KERNEL32!CloseHandle` at `0x1801dbbff`
- `KERNEL32!CloseHandle` at `0x1801dbbf0`
- `KERNEL32!CloseHandle` at `0x1801dbbff`
- `KERNEL32!GetLastError` at `0x1801db9e2`
- `KERNEL32!GetLastError` at `0x1801dbb08`
- `KERNEL32!GetLastError` at `0x1801dbb0e`
- `KERNEL32!GetLastError` at `0x1801dbb24`
- `KERNEL32!GetLastError` at `0x1801dbb2a`
- `KERNEL32!GetLastError` at `0x1801dbbcb`
- `KERNEL32!GetLastError` at `0x1801db9e2`
- `KERNEL32!GetLastError` at `0x1801dbb08`
- `KERNEL32!GetLastError` at `0x1801dbb0e`
- `KERNEL32!GetLastError` at `0x1801dbb24`
- `KERNEL32!GetLastError` at `0x1801dbb2a`
- `KERNEL32!GetLastError` at `0x1801dbbcb`
- `USER32!MsgWaitForMultipleObjects` at `0x1801dbb99`
- `USER32!MsgWaitForMultipleObjects` at `0x1801dbb99`

## pseudocode

```c
__int64 __fastcall CProcessChainInternal::Start(CProcessChainInternal *this, unsigned __int8 *a2)
{
  unsigned __int16 *v2; // rbx
  signed int v4; // ebx
  CProcessChainInternal *v5; // rcx
  HANDLE JobObjectW; // rbx
  HANDLE IoCompletionPort; // rax
  HANDLE Thread; // rax
  HANDLE WaitableTimerW; // rax
  void (__fastcall *v10)(_QWORD, _QWORD); // rax
  __int64 v11; // rax
  void *v12; // rcx
  signed int LastError; // eax
  bool v14; // sf
  signed int v15; // eax
  __int64 v16; // rax
  BOOL v17; // ebx
  DWORD v18; // eax
  CProcessChainInternal *v19; // rcx
  DWORD v20; // eax
  __int128 JobObjectInformation; // [rsp+30h] [rbp-48h] BYREF
  HANDLE pHandles; // [rsp+40h] [rbp-38h] BYREF
  __int64 v24; // [rsp+48h] [rbp-30h]
  struct _PROCESS_INFORMATION hProcess; // [rsp+50h] [rbp-28h] BYREF
  LARGE_INTEGER DueTime; // [rsp+A8h] [rbp+30h] BYREF

  DueTime.QuadPart = (LONGLONG)a2;
  v2 = (unsigned __int16 *)((char *)this + 4);
  memset(&hProcess, 0, sizeof(hProcess));
  JobObjectInformation = 0;
  if ( *((_WORD *)this + 2) && GetFileAttributesW((LPCWSTR)this + 2) == -1 )
  {
    v4 = -2147024809;
    goto LABEL_41;
  }
  CProcessChainInternal::Cleanup(this);
  v4 = CProcessChainInternal::LaunchExecutableSuspended(v5, v2, *((unsigned __int16 **)this + 66), &hProcess);
  if ( v4 >= 0 )
  {
    JobObjectW = CreateJobObjectW(0, 0);
    if ( !JobObjectW )
      GetLastError();
    *((_QWORD *)this + 68) = JobObjectW;
    if ( JobObjectW )
    {
      IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
      *((_QWORD *)this + 70) = IoCompletionPort;
      if ( IoCompletionPort )
      {
        Thread = CreateThread(0, 0, CProcessChainInternal::ProcessChainThread, this, 0, 0);
        *((_QWORD *)this + 69) = Thread;
        if ( Thread )
        {
          if ( *(int *)this > 0 )
          {
            WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
            *((_QWORD *)this + 71) = WaitableTimerW;
            if ( !WaitableTimerW )
              goto LABEL_21;
          }
          v10 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)this + 76);
          if ( v10 )
            v10(*((_QWORD *)this + 67), LODWORD(hProcess.hProcess));
          v11 = *((_QWORD *)this + 70);
          v12 = (void *)*((_QWORD *)this + 68);
          *(_QWORD *)&JobObjectInformation = 0;
          *((_QWORD *)&JobObjectInformation + 1) = v11;
          if ( !SetInformationJobObject(v12, JobObjectAssociateCompletionPortInformation, &JobObjectInformation, 0x10u)
            || !AssignProcessToJobObject(*((HANDLE *)this + 68), hProcess.hProcess) )
          {
            goto LABEL_21;
          }
          ResumeThread(hProcess.hThread);
          if ( *(int *)this > 0 )
          {
            DueTime.QuadPart = -10000LL * *(int *)this;
            if ( !SetWaitableTimer(*((HANDLE *)this + 71), &DueTime, 0, 0, 0, 0) )
            {
              GetLastError();
              LastError = GetLastError();
              v14 = LastError < 0;
              if ( LastError > 0 )
                v14 = 1;
              if ( v14 )
              {
LABEL_21:
                GetLastError();
                v15 = GetLastError();
                v4 = v15;
                if ( v15 > 0 )
                  v4 = (unsigned __int16)v15 | 0x80070000;
                if ( v4 >= 0 )
                  goto LABEL_41;
                goto LABEL_39;
              }
            }
          }
          *((_BYTE *)this + 576) = 1;
          if ( *((_BYTE *)this + 577) )
          {
LABEL_36:
            v4 = 0;
            goto LABEL_41;
          }
          pHandles = (HANDLE)*((_QWORD *)this + 69);
          v16 = *((_QWORD *)this + 71);
          v24 = 0;
          if ( v16 )
            v24 = v16;
          v17 = v16 != 0;
          while ( 1 )
          {
            v18 = MsgWaitForMultipleObjects(v17 + 1, &pHandles, 0, 0xFFFFFFFF, 0x1CBFu);
            if ( !v18 )
              goto LABEL_36;
            v20 = v18 - 1;
            if ( v20 )
            {
              if ( v20 == 1 )
                goto LABEL_34;
            }
            else
            {
              if ( *((_QWORD *)this + 71) )
              {
                CProcessChainInternal::CancelWait(this);
                goto LABEL_36;
              }
LABEL_34:
              CProcessChainInternal::HandleWindowsMessage(v19);
            }
          }
        }
      }
      GetLastError();
    }
    v4 = -2147418113;
LABEL_39:
    if ( !hProcess.hProcess )
      goto LABEL_43;
    TerminateProcess(hProcess.hProcess, 0);
  }
LABEL_41:
  if ( hProcess.hProcess )
    CloseHandle(hProcess.hProcess);
LABEL_43:
  if ( hProcess.hThread )
    CloseHandle(hProcess.hThread);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801db964  mov     qword ptr [rsp-20h+DueTime], rdx
0x1801db969  push    rbp
0x1801db96a  push    rbx
0x1801db96b  push    rsi
0x1801db96c  push    rdi
0x1801db96d  mov     rbp, rsp
0x1801db970  sub     rsp, 78h
0x1801db974  xor     eax, eax
0x1801db976  lea     rbx, [rcx+4]
0x1801db97a  xorps   xmm0, xmm0
0x1801db97d  mov     [rbp+var_18], rax
0x1801db981  xor     esi, esi
0x1801db983  mov     rdi, rcx
0x1801db986  movups  xmmword ptr [rbp+hProcess], xmm0
0x1801db98a  movups  [rbp+JobObjectInformation], xmm0
0x1801db98e  cmp     [rbx], si
0x1801db991  jz      short loc_1801DB9AB
0x1801db993  mov     rcx, rbx; lpFileName
0x1801db996  call    cs:__imp_GetFileAttributesW
0x1801db99c  cmp     eax, 0FFFFFFFFh
0x1801db99f  jnz     short loc_1801DB9AB
0x1801db9a1  mov     ebx, 80070057h
0x1801db9a6  jmp     loc_1801DBBE7
0x1801db9ab  mov     rcx, rdi; this
0x1801db9ae  call    ?Cleanup@CProcessChainInternal@@IEAAXXZ; CProcessChainInternal::Cleanup(void)
0x1801db9b3  mov     r8, [rdi+210h]; unsigned __int16 *
0x1801db9ba  lea     r9, [rbp+hProcess]; struct _PROCESS_INFORMATION *
0x1801db9be  mov     rdx, rbx; unsigned __int16 *
0x1801db9c1  call    ?LaunchExecutableSuspended@CProcessChainInternal@@IEAAJPEAG0PEAU_PROCESS_INFORMATION@@@Z; CProcessChainInternal::LaunchExecutableSuspended(ushort *,ushort *,_PROCESS_INFORMATION *)
0x1801db9c6  mov     ebx, eax
0x1801db9c8  test    eax, eax
0x1801db9ca  js      loc_1801DBBE7
0x1801db9d0  xor     edx, edx; lpName
0x1801db9d2  xor     ecx, ecx; lpJobAttributes
0x1801db9d4  call    cs:__imp_CreateJobObjectW
0x1801db9da  mov     rbx, rax
0x1801db9dd  test    rax, rax
0x1801db9e0  jnz     short loc_1801DB9E8
0x1801db9e2  call    cs:__imp_GetLastError
0x1801db9e8  mov     [rdi+220h], rbx
0x1801db9ef  test    rbx, rbx
0x1801db9f2  jz      loc_1801DBBD1
0x1801db9f8  xor     r9d, r9d; NumberOfConcurrentThreads
0x1801db9fb  xor     r8d, r8d; CompletionKey
0x1801db9fe  xor     edx, edx; ExistingCompletionPort
0x1801dba00  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1801dba04  call    cs:__imp_CreateIoCompletionPort
0x1801dba0a  mov     [rdi+230h], rax
0x1801dba11  test    rax, rax
0x1801dba14  jz      loc_1801DBBCB
0x1801dba1a  mov     [rsp+78h+lpThreadId], rsi; lpThreadId
0x1801dba1f  lea     r8, ?ProcessChainThread@CProcessChainInternal@@KAKPEAX@Z; lpStartAddress
0x1801dba26  mov     r9, rdi; lpParameter
0x1801dba29  mov     [rsp+78h+dwCreationFlags], esi; dwCreationFlags
0x1801dba2d  xor     edx, edx; dwStackSize
0x1801dba2f  xor     ecx, ecx; lpThreadAttributes
0x1801dba31  call    cs:__imp_CreateThread
0x1801dba37  mov     [rdi+228h], rax
0x1801dba3e  test    rax, rax
0x1801dba41  jz      loc_1801DBBCB
0x1801dba47  cmp     [rdi], esi
0x1801dba49  jle     short loc_1801DBA6A
0x1801dba4b  xor     r8d, r8d; lpTimerName
0x1801dba4e  xor     ecx, ecx; lpTimerAttributes
0x1801dba50  lea     edx, [r8+1]; bManualReset
0x1801dba54  call    cs:__imp_CreateWaitableTimerW
0x1801dba5a  mov     [rdi+238h], rax
0x1801dba61  test    rax, rax
0x1801dba64  jz      loc_1801DBB24
0x1801dba6a  mov     rax, [rdi+260h]
0x1801dba71  test    rax, rax
0x1801dba74  jz      short loc_1801DBA85
0x1801dba76  mov     edx, dword ptr [rbp+hProcess]
0x1801dba79  mov     rcx, [rdi+218h]
0x1801dba80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dba85  mov     rax, [rdi+230h]
0x1801dba8c  lea     r8, [rbp+JobObjectInformation]; lpJobObjectInformation
0x1801dba90  mov     rcx, [rdi+220h]; hJob
0x1801dba97  mov     r9d, 10h; cbJobObjectInformationLength
0x1801dba9d  mov     qword ptr [rbp+JobObjectInformation], rsi
0x1801dbaa1  mov     qword ptr [rbp+JobObjectInformation+8], rax
0x1801dbaa5  lea     edx, [r9-9]; JobObjectInformationClass
0x1801dbaa9  call    cs:__imp_SetInformationJobObject
0x1801dbaaf  test    eax, eax
0x1801dbab1  jz      short loc_1801DBB24
0x1801dbab3  mov     rdx, [rbp+hProcess]; hProcess
0x1801dbab7  mov     rcx, [rdi+220h]; hJob
0x1801dbabe  call    cs:__imp_AssignProcessToJobObject
0x1801dbac4  test    eax, eax
0x1801dbac6  jz      short loc_1801DBB24
0x1801dbac8  mov     rcx, [rbp+hProcess+8]; hThread
0x1801dbacc  call    cs:__imp_ResumeThread
0x1801dbad2  cmp     [rdi], esi
0x1801dbad4  jle     short loc_1801DBB4C
0x1801dbad6  movsxd  rax, dword ptr [rdi]
0x1801dbad9  lea     rdx, [rbp+DueTime]; lpDueTime
0x1801dbadd  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1801dbae4  mov     dword ptr [rsp+78h+lpThreadId], esi; fResume
0x1801dbae8  xor     r9d, r9d; pfnCompletionRoutine
0x1801dbaeb  mov     qword ptr [rbp+DueTime], rcx
0x1801dbaef  xor     r8d, r8d; lPeriod
0x1801dbaf2  mov     rcx, [rdi+238h]; hTimer
0x1801dbaf9  mov     qword ptr [rsp+78h+dwCreationFlags], rsi; lpArgToCompletionRoutine
0x1801dbafe  call    cs:__imp_SetWaitableTimer
0x1801dbb04  test    eax, eax
0x1801dbb06  jnz     short loc_1801DBB4C
0x1801dbb08  call    cs:__imp_GetLastError
0x1801dbb0e  call    cs:__imp_GetLastError
0x1801dbb14  test    eax, eax
0x1801dbb16  jle     short loc_1801DBB22
0x1801dbb18  movzx   eax, ax
0x1801dbb1b  or      eax, 80070000h
0x1801dbb20  test    eax, eax
0x1801dbb22  jns     short loc_1801DBB4C
0x1801dbb24  call    cs:__imp_GetLastError
0x1801dbb2a  call    cs:__imp_GetLastError
0x1801dbb30  mov     ebx, eax
0x1801dbb32  test    eax, eax
0x1801dbb34  jle     short loc_1801DBB3F
0x1801dbb36  movzx   ebx, ax
0x1801dbb39  or      ebx, 80070000h
0x1801dbb3f  test    ebx, ebx
0x1801dbb41  jns     loc_1801DBBE7
0x1801dbb47  jmp     loc_1801DBBD6
0x1801dbb4c  mov     byte ptr [rdi+240h], 1
0x1801dbb53  cmp     [rdi+241h], sil
0x1801dbb5a  jnz     short loc_1801DBBC7
0x1801dbb5c  mov     rax, [rdi+228h]
0x1801dbb63  mov     [rbp+pHandles], rax
0x1801dbb67  mov     rax, [rdi+238h]
0x1801dbb6e  mov     [rbp+var_30], rsi
0x1801dbb72  test    rax, rax
0x1801dbb75  jz      short loc_1801DBB7B
0x1801dbb77  mov     [rbp+var_30], rax
0x1801dbb7b  test    rax, rax
0x1801dbb7e  mov     ebx, esi
0x1801dbb80  setnz   bl
0x1801dbb83  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1801dbb87  mov     [rsp+78h+dwCreationFlags], 1CBFh; dwWakeMask
0x1801dbb8f  xor     r8d, r8d; fWaitAll
0x1801dbb92  lea     rdx, [rbp+pHandles]; pHandles
0x1801dbb96  lea     ecx, [rbx+1]; nCount
0x1801dbb99  call    cs:__imp_MsgWaitForMultipleObjects
0x1801dbb9f  test    eax, eax
0x1801dbba1  jz      short loc_1801DBBC7
0x1801dbba3  sub     eax, 1
0x1801dbba6  jz      short loc_1801DBBAF
0x1801dbba8  cmp     eax, 1
0x1801dbbab  jnz     short loc_1801DBB83
0x1801dbbad  jmp     short loc_1801DBBB8
0x1801dbbaf  cmp     [rdi+238h], rsi
0x1801dbbb6  jnz     short loc_1801DBBBF
0x1801dbbb8  call    ?HandleWindowsMessage@CProcessChainInternal@@IEAAXXZ; CProcessChainInternal::HandleWindowsMessage(void)
0x1801dbbbd  jmp     short loc_1801DBB83
0x1801dbbbf  mov     rcx, rdi; this
0x1801dbbc2  call    ?CancelWait@CProcessChainInternal@@QEAAJXZ; CProcessChainInternal::CancelWait(void)
0x1801dbbc7  mov     ebx, esi
0x1801dbbc9  jmp     short loc_1801DBBE7
0x1801dbbcb  call    cs:__imp_GetLastError
0x1801dbbd1  mov     ebx, 8000FFFFh
0x1801dbbd6  mov     rcx, [rbp+hProcess]; hProcess
0x1801dbbda  test    rcx, rcx
0x1801dbbdd  jz      short loc_1801DBBF6
0x1801dbbdf  xor     edx, edx; uExitCode
0x1801dbbe1  call    cs:__imp_TerminateProcess
0x1801dbbe7  mov     rcx, [rbp+hProcess]; hObject
0x1801dbbeb  test    rcx, rcx
0x1801dbbee  jz      short loc_1801DBBF6
0x1801dbbf0  call    cs:__imp_CloseHandle
0x1801dbbf6  mov     rcx, [rbp+hProcess+8]; hObject
0x1801dbbfa  test    rcx, rcx
0x1801dbbfd  jz      short loc_1801DBC05
0x1801dbbff  call    cs:__imp_CloseHandle
0x1801dbc05  mov     eax, ebx
0x1801dbc07  add     rsp, 78h
0x1801dbc0b  pop     rdi
0x1801dbc0c  pop     rsi
0x1801dbc0d  pop     rbx
0x1801dbc0e  pop     rbp
0x1801dbc0f  retn
```
