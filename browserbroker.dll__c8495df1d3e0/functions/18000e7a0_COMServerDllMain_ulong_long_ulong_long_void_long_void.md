# COMServerDllMain(ulong,long (*)(ulong),long (*)(void),long (*)(void))

- ea: `0x18000e7a0`
- end: `0x18000e9aa`
- name: `?COMServerDllMain@@YAJKP6AJK@ZP6AJXZ1@Z`
- size: `522`
- prototype: `__int64 __fastcall(int, int (*)(unsigned int), int (*)(void), int (*)(void))`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001388`
- `0x180001438`
- `0x18000e7a0`
- `0x180025390`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e94b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e986`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e94b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e986`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e7df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e7df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e860`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e860`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e82b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e82b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e83d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e83d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000e891`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000e891`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e7ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e95a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e7ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e95a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e964`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e93d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e93d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000e84d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000e84d`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000e8a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000e8a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall COMServerDllMain(int a1, int (*a2)(unsigned int), int (*a3)(void), int (*a4)(void))
{
  signed int v5; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  _DWORD Parameter[2]; // [rsp+30h] [rbp-10h] BYREF
  int *v10; // [rsp+38h] [rbp-8h]
  int v11; // [rsp+50h] [rbp+10h] BYREF

  v11 = -2147467259;
  if ( (unsigned __int8)a1 == 1 )
  {
    g_pfnCOMServerCallback = a2;
    g_pfnIncrementServerRefCount = a3;
    g_pfnDecrementServerRefCount = a4;
    InitializeCriticalSectionEx(&g_csDll, 0, 0);
    if ( g_dwBrowserBrokerTls != -1 || (g_dwBrowserBrokerTls = TlsAlloc(), g_dwBrowserBrokerTls != -1) )
    {
      g_hDllMainEvent = CreateEventW(0, 0, 0, 0);
      if ( g_hDllMainEvent )
      {
        TraceLoggingRegisterEx_EventRegister_EventSetInformation();
        g_hExitMTLoop = CreateEventW(0, 0, 0, 0);
        if ( !g_hExitMTLoop
          || (Parameter[1] = 0,
              Parameter[0] = a1,
              v10 = &v11,
              (Thread = CreateThread(0, 0, DllMTThreadProc, Parameter, 0, 0)) == 0)
          || (CloseHandle(Thread), WaitForSingleObject(g_hDllMainEvent, 0xFFFFFFFF)) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v11 = LastError;
        }
        if ( v11 < 0 )
        {
          CloseHandle(g_hDllMainEvent);
          g_hDllMainEvent = 0;
        }
      }
      else
      {
        v5 = GetLastError();
        if ( v5 > 0 )
          return (unsigned __int16)v5 | 0x80070000;
        return (unsigned int)v5;
      }
    }
  }
  else if ( (unsigned __int8)a1 == 2 )
  {
    if ( g_hExitMTLoop )
    {
      SetEvent(g_hExitMTLoop);
      WaitForSingleObject(g_hDllMainEvent, 0xFFFFFFFF);
      CloseHandle(g_hExitMTLoop);
      g_hExitMTLoop = 0;
      CloseHandle(g_hDllMainEvent);
      g_hDllMainEvent = 0;
    }
    AcquireSRWLockExclusive(&SRWLock);
    wil::com_ptr_t<IAgileReference,wil::err_returncode_policy>::reset();
    ReleaseSRWLockExclusive(&SRWLock);
    if ( g_dwBrowserBrokerTls != -1 )
    {
      TlsFree(g_dwBrowserBrokerTls);
      g_dwBrowserBrokerTls = -1;
    }
    DeleteCriticalSection(&g_csDll);
    TraceLoggingUnregister_EventUnregister();
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000e7a0  mov     [rsp-8+arg_8], rsi
0x18000e7a5  mov     [rsp-8+arg_10], rdi
0x18000e7aa  push    rbp
0x18000e7ab  mov     rbp, rsp
0x18000e7ae  sub     rsp, 40h
0x18000e7b2  movzx   eax, cl
0x18000e7b5  mov     esi, ecx
0x18000e7b7  mov     [rbp+arg_0], 80004005h
0x18000e7be  sub     eax, 1
0x18000e7c1  jz      loc_18000E870
0x18000e7c7  cmp     eax, 1
0x18000e7ca  jnz     loc_18000E997
0x18000e7d0  mov     rcx, cs:?g_hExitMTLoop@@3PEAXEA; hEvent
0x18000e7d7  or      edi, 0FFFFFFFFh
0x18000e7da  test    rcx, rcx
0x18000e7dd  jz      short loc_18000E824
0x18000e7df  call    cs:__imp_SetEvent
0x18000e7e5  mov     rcx, cs:?g_hDllMainEvent@@3PEAXEA; hHandle
0x18000e7ec  mov     edx, edi; dwMilliseconds
0x18000e7ee  call    cs:__imp_WaitForSingleObject
0x18000e7f4  mov     rcx, cs:?g_hExitMTLoop@@3PEAXEA; hObject
0x18000e7fb  call    cs:__imp_CloseHandle
0x18000e801  mov     rcx, cs:?g_hDllMainEvent@@3PEAXEA; hObject
0x18000e808  mov     cs:?g_hExitMTLoop@@3PEAXEA, 0; void * g_hExitMTLoop
0x18000e813  call    cs:__imp_CloseHandle
0x18000e819  mov     cs:?g_hDllMainEvent@@3PEAXEA, 0; void * g_hDllMainEvent
0x18000e824  lea     rcx, SRWLock; SRWLock
0x18000e82b  call    cs:__imp_AcquireSRWLockExclusive
0x18000e831  call    ?reset@?$com_ptr_t@UIAgileReference@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAgileReference,wil::err_returncode_policy>::reset(void)
0x18000e836  lea     rcx, SRWLock; SRWLock
0x18000e83d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e843  mov     ecx, cs:?g_dwBrowserBrokerTls@@3KA; dwTlsIndex
0x18000e849  cmp     ecx, edi
0x18000e84b  jz      short loc_18000E859
0x18000e84d  call    cs:__imp_TlsFree
0x18000e853  mov     cs:?g_dwBrowserBrokerTls@@3KA, edi; ulong g_dwBrowserBrokerTls
0x18000e859  lea     rcx, g_csDll; lpCriticalSection
0x18000e860  call    cs:__imp_DeleteCriticalSection
0x18000e866  call    TraceLoggingUnregister_EventUnregister
0x18000e86b  jmp     loc_18000E997
0x18000e870  mov     cs:?g_pfnCOMServerCallback@@3P6AJK@ZEA, rdx; long (*g_pfnCOMServerCallback)(ulong)
0x18000e877  lea     rcx, g_csDll; lpCriticalSection
0x18000e87e  mov     cs:?g_pfnIncrementServerRefCount@@3P6AJXZEA, r8; long (*g_pfnIncrementServerRefCount)(void)
0x18000e885  xor     edx, edx; dwSpinCount
0x18000e887  xor     r8d, r8d; Flags
0x18000e88a  mov     cs:?g_pfnDecrementServerRefCount@@3P6AJXZEA, r9; long (*g_pfnDecrementServerRefCount)(void)
0x18000e891  call    cs:__imp_InitializeCriticalSectionEx
0x18000e897  or      edi, 0FFFFFFFFh
0x18000e89a  cmp     cs:?g_dwBrowserBrokerTls@@3KA, edi; ulong g_dwBrowserBrokerTls
0x18000e8a0  jnz     short loc_18000E8B6
0x18000e8a2  call    cs:__imp_TlsAlloc
0x18000e8a8  mov     cs:?g_dwBrowserBrokerTls@@3KA, eax; ulong g_dwBrowserBrokerTls
0x18000e8ae  cmp     eax, edi
0x18000e8b0  jz      loc_18000E997
0x18000e8b6  xor     r9d, r9d; lpName
0x18000e8b9  xor     r8d, r8d; bInitialState
0x18000e8bc  xor     edx, edx; bManualReset
0x18000e8be  xor     ecx, ecx; lpEventAttributes
0x18000e8c0  call    cs:__imp_CreateEventW
0x18000e8c6  mov     cs:?g_hDllMainEvent@@3PEAXEA, rax; void * g_hDllMainEvent
0x18000e8cd  test    rax, rax
0x18000e8d0  jnz     short loc_18000E8EC
0x18000e8d2  call    cs:__imp_GetLastError
0x18000e8d8  test    eax, eax
0x18000e8da  jle     short loc_18000E8E4
0x18000e8dc  movzx   eax, ax
0x18000e8df  or      eax, 80070000h
0x18000e8e4  mov     [rbp+arg_0], eax
0x18000e8e7  jmp     loc_18000E997
0x18000e8ec  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000e8f1  xor     r9d, r9d; lpName
0x18000e8f4  xor     r8d, r8d; bInitialState
0x18000e8f7  xor     edx, edx; bManualReset
0x18000e8f9  xor     ecx, ecx; lpEventAttributes
0x18000e8fb  call    cs:__imp_CreateEventW
0x18000e901  mov     cs:?g_hExitMTLoop@@3PEAXEA, rax; void * g_hExitMTLoop
0x18000e908  test    rax, rax
0x18000e90b  jz      short loc_18000E964
0x18000e90d  xor     eax, eax
0x18000e90f  mov     [rsp+40h+lpThreadId], 0; lpThreadId
0x18000e918  mov     [rbp+var_C], eax
0x18000e91b  lea     r9, [rbp+Parameter]; lpParameter
0x18000e91f  lea     rax, [rbp+arg_0]
0x18000e923  mov     [rbp+Parameter], esi
0x18000e926  lea     r8, ?DllMTThreadProc@@YAKPEAX@Z; lpStartAddress
0x18000e92d  mov     [rbp+var_8], rax
0x18000e931  xor     edx, edx; dwStackSize
0x18000e933  mov     [rsp+40h+dwCreationFlags], 0; dwCreationFlags
0x18000e93b  xor     ecx, ecx; lpThreadAttributes
0x18000e93d  call    cs:__imp_CreateThread
0x18000e943  test    rax, rax
0x18000e946  jz      short loc_18000E964
0x18000e948  mov     rcx, rax; hObject
0x18000e94b  call    cs:__imp_CloseHandle
0x18000e951  mov     rcx, cs:?g_hDllMainEvent@@3PEAXEA; hHandle
0x18000e958  mov     edx, edi; dwMilliseconds
0x18000e95a  call    cs:__imp_WaitForSingleObject
0x18000e960  test    eax, eax
0x18000e962  jz      short loc_18000E979
0x18000e964  call    cs:__imp_GetLastError
0x18000e96a  test    eax, eax
0x18000e96c  jle     short loc_18000E976
0x18000e96e  movzx   eax, ax
0x18000e971  or      eax, 80070000h
0x18000e976  mov     [rbp+arg_0], eax
0x18000e979  cmp     [rbp+arg_0], 0
0x18000e97d  jge     short loc_18000E997
0x18000e97f  mov     rcx, cs:?g_hDllMainEvent@@3PEAXEA; hObject
0x18000e986  call    cs:__imp_CloseHandle
0x18000e98c  mov     cs:?g_hDllMainEvent@@3PEAXEA, 0; void * g_hDllMainEvent
0x18000e997  mov     eax, [rbp+arg_0]
0x18000e99a  mov     rsi, [rsp+40h+arg_8]
0x18000e99f  mov     rdi, [rsp+40h+arg_10]
0x18000e9a4  add     rsp, 40h
0x18000e9a8  pop     rbp
0x18000e9a9  retn
```
