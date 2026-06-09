# CWofTasksHandler::Worker(void)

- ea: `0x180003ac0`
- end: `0x180003d60`
- name: `?Worker@CWofTasksHandler@@UEAAJXZ`
- size: `672`
- prototype: `__int64 __fastcall(const wchar_t **this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002e74`
- `0x1800032fc`
- `0x1800038dc`
- `0x180003ac0`
- `0x1800043d8`
- `0x1800049d0`
- `0x18000519a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003c06`
- `KERNEL32!GetLastError` at `0x180003cb5`
- `KERNEL32!GetLastError` at `0x180003cdb`
- `KERNEL32!GetLastError` at `0x180003c06`
- `KERNEL32!GetLastError` at `0x180003cb5`
- `KERNEL32!GetLastError` at `0x180003cdb`
- `KERNEL32!CloseHandle` at `0x180003c6e`
- `KERNEL32!CloseHandle` at `0x180003cfe`
- `KERNEL32!CloseHandle` at `0x180003d12`
- `KERNEL32!CloseHandle` at `0x180003c6e`
- `KERNEL32!CloseHandle` at `0x180003cfe`
- `KERNEL32!CloseHandle` at `0x180003d12`
- `KERNEL32!SetThreadPriority` at `0x180003b09`
- `KERNEL32!SetThreadPriority` at `0x180003d2d`
- `KERNEL32!SetThreadPriority` at `0x180003b09`
- `KERNEL32!SetThreadPriority` at `0x180003d2d`
- `KERNEL32!CreateEventW` at `0x180003bf0`
- `KERNEL32!CreateEventW` at `0x180003bf0`
- `KERNEL32!GetCurrentThread` at `0x180003afb`
- `KERNEL32!GetCurrentThread` at `0x180003d1f`
- `KERNEL32!GetCurrentThread` at `0x180003afb`
- `KERNEL32!GetCurrentThread` at `0x180003d1f`
- `KERNEL32!GetOverlappedResult` at `0x180003cab`
- `KERNEL32!GetOverlappedResult` at `0x180003cab`
- `ntdll!WinSqmSetDWORD` at `0x180003bba`
- `ntdll!WinSqmSetDWORD` at `0x180003bba`
- `ntdll!RtlPublishWnfStateData` at `0x180003b94`
- `ntdll!RtlPublishWnfStateData` at `0x180003b94`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003af5`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003af5`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003d3f`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003d3f`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180003cd1`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180003cd1`

## pseudocode

```c
__int64 __fastcall CWofTasksHandler::Worker(const wchar_t **this)
{
  HANDLE CurrentThread; // rax
  DWORD started; // ebx
  DWORD v4; // esi
  int v5; // eax
  signed int LastError; // eax
  int v7; // esi
  signed int v8; // eax
  HANDLE v9; // rax
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp+8h] BYREF

  NumberOfBytesTransferred = 0;
  if ( !RegHandle )
    EventRegister(&WofEventProviderId, 0, 0, &RegHandle);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 0x10000);
  ExitFlag = 0;
  if ( !wcscmp_0(this[1], L"WimHashManagement") )
  {
    started = IdentifyTaskAction((enum _WOF_TASK_ACTION *)&NumberOfBytesTransferred);
    if ( !started )
    {
      v4 = NumberOfBytesTransferred;
      if ( NumberOfBytesTransferred <= 1 )
      {
        started = TaskChangeFileHashes(NumberOfBytesTransferred);
        if ( _InterlockedCompareExchange((volatile signed __int32 *)&ExitFlag, 0, 0) != 1 && !v4 )
        {
          NumberOfBytesTransferred = started;
          v5 = RtlPublishWnfStateData(WNF_FVE_WIM_HASH_GENERATION_COMPLETION, 0, &NumberOfBytesTransferred, 4, 0);
          if ( v5 < 0 )
            LogError(&WofTaskReportHashGenerationToBitlockerErrorEventId, v5 | 0x10000000);
          WinSqmSetDWORD(0, 12810, started);
        }
      }
    }
    goto LABEL_36;
  }
  started = 0;
  if ( wcscmp_0(this[1], L"WimHashValidation") )
    goto LABEL_36;
  NumberOfBytesTransferred = 0;
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    if ( started )
      goto LABEL_21;
  }
  started = WofStartBackgroundIntegrityValidation(&Overlapped);
  if ( (int)(started + 0x80000000) >= 0 && started != -2147023899 )
  {
    if ( started == -2147024846 || started == -2147024895 )
    {
      DisableValidationTask();
      started = 0;
    }
LABEL_21:
    if ( Overlapped.hEvent != (HANDLE)-1LL )
    {
      CloseHandle(Overlapped.hEvent);
      Overlapped.hEvent = (HANDLE)-1LL;
    }
    goto LABEL_36;
  }
  started = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&HashValidationEvent, 1u) == 1 )
  {
    if ( !CancelIoEx(hObject, &Overlapped) )
      GetLastError();
    v7 = 1;
  }
  else
  {
    v7 = 0;
    if ( !GetOverlappedResult(hObject, &Overlapped, &NumberOfBytesTransferred, 1) )
    {
      v8 = GetLastError();
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 != -2147023901 )
        started = v8;
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&HashValidationEvent, 0xFFFFFFFF) == 1 || v7 )
  {
    CloseHandle(Overlapped.hEvent);
    Overlapped.hEvent = (HANDLE)-1LL;
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
LABEL_36:
  v9 = GetCurrentThread();
  SetThreadPriority(v9, 0x20000);
  if ( !RegHandle )
  {
    EventUnregister(0);
    RegHandle = 0;
  }
  return started;
}

```

## disassembly

```asm
0x180003ac0  mov     [rsp+arg_10], rbx
0x180003ac5  push    rsi
0x180003ac6  push    rdi
0x180003ac7  push    r14
0x180003ac9  sub     rsp, 30h
0x180003acd  cmp     cs:RegHandle, 0
0x180003ad5  mov     rdi, rcx
0x180003ad8  mov     [rsp+48h+NumberOfBytesTransferred], 0
0x180003ae0  jnz     short loc_180003AFB
0x180003ae2  lea     r9, RegHandle; RegHandle
0x180003ae9  xor     r8d, r8d; CallbackContext
0x180003aec  xor     edx, edx; EnableCallback
0x180003aee  lea     rcx, WofEventProviderId; ProviderId
0x180003af5  call    cs:__imp_EventRegister
0x180003afb  call    cs:__imp_GetCurrentThread
0x180003b01  mov     rcx, rax; hThread
0x180003b04  mov     edx, 10000h; nPriority
0x180003b09  call    cs:__imp_SetThreadPriority
0x180003b0f  mov     cs:?ExitFlag@@3KA, 0; ulong ExitFlag
0x180003b19  lea     rdx, aWimhashmanagem; "WimHashManagement"
0x180003b20  mov     rcx, [rdi+8]; String1
0x180003b24  call    wcscmp_0
0x180003b29  test    eax, eax
0x180003b2b  jnz     loc_180003BC5
0x180003b31  lea     rcx, [rsp+48h+NumberOfBytesTransferred]; enum _WOF_TASK_ACTION *
0x180003b36  call    ?IdentifyTaskAction@@YAJPEAW4_WOF_TASK_ACTION@@@Z; IdentifyTaskAction(_WOF_TASK_ACTION *)
0x180003b3b  mov     ebx, eax
0x180003b3d  test    eax, eax
0x180003b3f  jnz     loc_180003D1F
0x180003b45  mov     esi, [rsp+48h+NumberOfBytesTransferred]
0x180003b49  lea     edi, [rax+1]
0x180003b4c  cmp     esi, edi
0x180003b4e  ja      loc_180003D1F
0x180003b54  mov     ecx, esi
0x180003b56  call    ?TaskChangeFileHashes@@YAJW4_WOF_TASK_ACTION@@@Z; TaskChangeFileHashes(_WOF_TASK_ACTION)
0x180003b5b  xor     ecx, ecx
0x180003b5d  mov     ebx, eax
0x180003b5f  xor     eax, eax
0x180003b61  lock cmpxchg cs:?ExitFlag@@3KA, ecx; ulong ExitFlag
0x180003b69  cmp     eax, edi
0x180003b6b  jz      loc_180003D1F
0x180003b71  test    esi, esi
0x180003b73  jnz     loc_180003D1F
0x180003b79  mov     [rsp+48h+var_28], rcx
0x180003b7e  lea     r9d, [rdi+3]
0x180003b82  mov     rcx, cs:WNF_FVE_WIM_HASH_GENERATION_COMPLETION
0x180003b89  lea     r8, [rsp+48h+NumberOfBytesTransferred]
0x180003b8e  xor     edx, edx
0x180003b90  mov     [rsp+48h+NumberOfBytesTransferred], ebx
0x180003b94  call    cs:__imp_RtlPublishWnfStateData
0x180003b9a  test    eax, eax
0x180003b9c  jns     short loc_180003BB0
0x180003b9e  bts     eax, 1Ch
0x180003ba2  lea     rcx, WofTaskReportHashGenerationToBitlockerErrorEventId; EventDescriptor
0x180003ba9  mov     edx, eax; int
0x180003bab  call    ?LogError@@YAXPEBU_EVENT_DESCRIPTOR@@H@Z; LogError(_EVENT_DESCRIPTOR const *,int)
0x180003bb0  mov     r8d, ebx
0x180003bb3  mov     edx, 320Ah
0x180003bb8  xor     ecx, ecx
0x180003bba  call    cs:__imp_WinSqmSetDWORD
0x180003bc0  jmp     loc_180003D1F
0x180003bc5  mov     rcx, [rdi+8]; String1
0x180003bc9  lea     rdx, aWimhashvalidat; "WimHashValidation"
0x180003bd0  xor     ebx, ebx
0x180003bd2  call    wcscmp_0
0x180003bd7  test    eax, eax
0x180003bd9  jnz     loc_180003D1F
0x180003bdf  lea     edi, [rbx+1]
0x180003be2  mov     [rsp+48h+NumberOfBytesTransferred], ebx
0x180003be6  mov     edx, edi; bManualReset
0x180003be8  xor     r9d, r9d; lpName
0x180003beb  xor     r8d, r8d; bInitialState
0x180003bee  xor     ecx, ecx; lpEventAttributes
0x180003bf0  call    cs:__imp_CreateEventW
0x180003bf6  or      r14, 0FFFFFFFFFFFFFFFFh
0x180003bfa  mov     cs:Overlapped.hEvent, rax
0x180003c01  cmp     rax, r14
0x180003c04  jnz     short loc_180003C1F
0x180003c06  call    cs:__imp_GetLastError
0x180003c0c  mov     ebx, eax
0x180003c0e  test    eax, eax
0x180003c10  jle     short loc_180003C1B
0x180003c12  movzx   ebx, ax
0x180003c15  or      ebx, 80070000h
0x180003c1b  test    ebx, ebx
0x180003c1d  jnz     short loc_180003C5E
0x180003c1f  lea     rdx, hObject
0x180003c26  lea     rcx, Overlapped; lpOverlapped
0x180003c2d  call    WofStartBackgroundIntegrityValidation
0x180003c32  mov     ecx, 80000000h
0x180003c37  mov     ebx, eax
0x180003c39  add     eax, ecx
0x180003c3b  test    ecx, eax
0x180003c3d  jnz     short loc_180003C80
0x180003c3f  cmp     ebx, 800703E5h
0x180003c45  jz      short loc_180003C80
0x180003c47  cmp     ebx, 80070032h
0x180003c4d  jz      short loc_180003C57
0x180003c4f  cmp     ebx, 80070001h
0x180003c55  jnz     short loc_180003C5E
0x180003c57  call    ?DisableValidationTask@@YAJXZ; DisableValidationTask(void)
0x180003c5c  xor     ebx, ebx
0x180003c5e  mov     rcx, cs:Overlapped.hEvent; hObject
0x180003c65  cmp     rcx, r14
0x180003c68  jz      loc_180003D1F
0x180003c6e  call    cs:__imp_CloseHandle
0x180003c74  mov     cs:Overlapped.hEvent, r14
0x180003c7b  jmp     loc_180003D1F
0x180003c80  xor     ebx, ebx
0x180003c82  mov     eax, edi
0x180003c84  lock xadd cs:?HashValidationEvent@@3U_HASH_VALIDATION_EVENT@@A, eax; _HASH_VALIDATION_EVENT HashValidationEvent
0x180003c8c  mov     rcx, cs:hObject; hFile
0x180003c93  lea     rdx, Overlapped; lpOverlapped
0x180003c9a  add     eax, edi
0x180003c9c  cmp     eax, 2
0x180003c9f  jz      short loc_180003CD1
0x180003ca1  mov     r9d, edi; bWait
0x180003ca4  lea     r8, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180003ca9  xor     esi, esi
0x180003cab  call    cs:__imp_GetOverlappedResult
0x180003cb1  test    eax, eax
0x180003cb3  jnz     short loc_180003CE3
0x180003cb5  call    cs:__imp_GetLastError
0x180003cbb  test    eax, eax
0x180003cbd  jle     short loc_180003CC7
0x180003cbf  movzx   eax, ax
0x180003cc2  or      eax, 80070000h
0x180003cc7  cmp     eax, 800703E3h
0x180003ccc  cmovnz  ebx, eax
0x180003ccf  jmp     short loc_180003CE3
0x180003cd1  call    cs:__imp_CancelIoEx
0x180003cd7  test    eax, eax
0x180003cd9  jnz     short loc_180003CE1
0x180003cdb  call    cs:__imp_GetLastError
0x180003ce1  mov     esi, edi
0x180003ce3  mov     eax, r14d
0x180003ce6  lock xadd cs:?HashValidationEvent@@3U_HASH_VALIDATION_EVENT@@A, eax; _HASH_VALIDATION_EVENT HashValidationEvent
0x180003cee  add     eax, r14d
0x180003cf1  jz      short loc_180003CF7
0x180003cf3  test    esi, esi
0x180003cf5  jz      short loc_180003D1F
0x180003cf7  mov     rcx, cs:Overlapped.hEvent; hObject
0x180003cfe  call    cs:__imp_CloseHandle
0x180003d04  mov     rcx, cs:hObject; hObject
0x180003d0b  mov     cs:Overlapped.hEvent, r14
0x180003d12  call    cs:__imp_CloseHandle
0x180003d18  mov     cs:hObject, r14
0x180003d1f  call    cs:__imp_GetCurrentThread
0x180003d25  mov     rcx, rax; hThread
0x180003d28  mov     edx, 20000h; nPriority
0x180003d2d  call    cs:__imp_SetThreadPriority
0x180003d33  cmp     cs:RegHandle, 0
0x180003d3b  jnz     short loc_180003D50
0x180003d3d  xor     ecx, ecx; RegHandle
0x180003d3f  call    cs:__imp_EventUnregister
0x180003d45  mov     cs:RegHandle, 0
0x180003d50  mov     eax, ebx
0x180003d52  mov     rbx, [rsp+48h+arg_10]
0x180003d57  add     rsp, 30h
0x180003d5b  pop     r14
0x180003d5d  pop     rdi
0x180003d5e  pop     rsi
0x180003d5f  retn
```
