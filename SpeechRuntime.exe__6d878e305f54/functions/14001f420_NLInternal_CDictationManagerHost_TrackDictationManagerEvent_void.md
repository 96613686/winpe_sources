# NLInternal::CDictationManagerHost::TrackDictationManagerEvent(void *)

- ea: `0x14001f420`
- end: `0x14001f521`
- name: `?TrackDictationManagerEvent@CDictationManagerHost@NLInternal@@SAJPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011650`

## callees

- `0x140011ea8`
- `0x14001f420`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x14001f487`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x14001f487`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001f44b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001f44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f4cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f4cd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14001f515`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14001f515`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14001f4b7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14001f4b7`

## pseudocode

```c
signed int __fastcall NLInternal::CDictationManagerHost::TrackDictationManagerEvent(void *a1)
{
  DWORD v2; // eax
  DWORD v3; // eax
  signed int result; // eax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD ExitCode; // [rsp+58h] [rbp+10h] BYREF
  int v7; // [rsp+60h] [rbp+18h] BYREF

  if ( NLInternal::CDictationManagerHost::s_dmModule )
    return 0;
  if ( NLInternal::CDictationManagerHost::s_initializedEvent == (HANDLE)-1LL )
    NLInternal::CDictationManagerHost::s_initializedEvent = CreateEventW(0, 0, 0, 0);
  NLInternal::CDictationManagerHost::s_hShutdown = a1;
  v7 = 0;
  NLInternal::CDictationManagerHost::s_threadHandle = (HANDLE)_o__beginthreadex(
                                                                0,
                                                                0,
                                                                NLInternal::CDictationManagerHost::WorkerThreadProc,
                                                                a1,
                                                                0,
                                                                &v7);
  Handles[0] = NLInternal::CDictationManagerHost::s_threadHandle;
  Handles[1] = NLInternal::CDictationManagerHost::s_initializedEvent;
  v2 = WaitForMultipleObjects(2u, Handles, 0, 0xC8u);
  if ( !v2 )
  {
    ExitCode = 0;
    GetExitCodeThread(NLInternal::CDictationManagerHost::s_threadHandle, &ExitCode);
    return ExitCode;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    DoTraceMessage(16, "DictationManagerHost initialize succeeded");
    return 0;
  }
  if ( v3 == 257 )
    return -2147024638;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14001f420  push    rbx
0x14001f422  sub     rsp, 40h
0x14001f426  cmp     cs:?s_dmModule@CDictationManagerHost@NLInternal@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * NLInternal::CDictationManagerHost::s_dmModule
0x14001f42e  mov     rbx, rcx
0x14001f431  jnz     loc_14001F4F9
0x14001f437  cmp     cs:?s_initializedEvent@CDictationManagerHost@NLInternal@@0PEAXEA, 0FFFFFFFFFFFFFFFFh; void * NLInternal::CDictationManagerHost::s_initializedEvent
0x14001f43f  jnz     short loc_14001F458
0x14001f441  xor     r9d, r9d; lpName
0x14001f444  xor     r8d, r8d; bInitialState
0x14001f447  xor     edx, edx; bManualReset
0x14001f449  xor     ecx, ecx; lpEventAttributes
0x14001f44b  call    cs:__imp_CreateEventW
0x14001f451  mov     cs:?s_initializedEvent@CDictationManagerHost@NLInternal@@0PEAXEA, rax; void * NLInternal::CDictationManagerHost::s_initializedEvent
0x14001f458  lea     rax, [rsp+48h+arg_10]
0x14001f45d  mov     cs:?s_hShutdown@CDictationManagerHost@NLInternal@@0PEAXEA, rbx; void * NLInternal::CDictationManagerHost::s_hShutdown
0x14001f464  mov     [rsp+48h+var_20], rax
0x14001f469  lea     r8, ?WorkerThreadProc@CDictationManagerHost@NLInternal@@CAIPEAX@Z; NLInternal::CDictationManagerHost::WorkerThreadProc(void *)
0x14001f470  mov     r9, rbx
0x14001f473  mov     [rsp+48h+var_28], 0
0x14001f47b  xor     edx, edx
0x14001f47d  mov     [rsp+48h+arg_10], 0
0x14001f485  xor     ecx, ecx
0x14001f487  call    cs:__imp__o__beginthreadex
0x14001f48d  xor     r8d, r8d; bWaitAll
0x14001f490  mov     cs:?s_threadHandle@CDictationManagerHost@NLInternal@@0PEAXEA, rax; void * NLInternal::CDictationManagerHost::s_threadHandle
0x14001f497  mov     [rsp+48h+Handles], rax
0x14001f49c  lea     rdx, [rsp+48h+Handles]; lpHandles
0x14001f4a1  mov     rax, cs:?s_initializedEvent@CDictationManagerHost@NLInternal@@0PEAXEA; void * NLInternal::CDictationManagerHost::s_initializedEvent
0x14001f4a8  mov     r9d, 0C8h; dwMilliseconds
0x14001f4ae  mov     [rsp+48h+var_10], rax
0x14001f4b3  lea     ecx, [r8+2]; nCount
0x14001f4b7  call    cs:__imp_WaitForMultipleObjects
0x14001f4bd  test    eax, eax
0x14001f4bf  jz      short loc_14001F501
0x14001f4c1  sub     eax, 1
0x14001f4c4  jz      short loc_14001F4E8
0x14001f4c6  cmp     eax, 101h
0x14001f4cb  jz      short loc_14001F4E1
0x14001f4cd  call    cs:__imp_GetLastError
0x14001f4d3  test    eax, eax
0x14001f4d5  jle     short loc_14001F4FB
0x14001f4d7  movzx   eax, ax
0x14001f4da  or      eax, 80070000h
0x14001f4df  jmp     short loc_14001F4FB
0x14001f4e1  mov     eax, 80070102h
0x14001f4e6  jmp     short loc_14001F4FB
0x14001f4e8  lea     rdx, aDictationmanag; "DictationManagerHost initialize succeed"...
0x14001f4ef  mov     ecx, 10h; int
0x14001f4f4  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001f4f9  xor     eax, eax
0x14001f4fb  add     rsp, 40h
0x14001f4ff  pop     rbx
0x14001f500  retn
0x14001f501  mov     rcx, cs:?s_threadHandle@CDictationManagerHost@NLInternal@@0PEAXEA; hThread
0x14001f508  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x14001f50d  mov     [rsp+48h+ExitCode], 0
0x14001f515  call    cs:__imp_GetExitCodeThread
0x14001f51b  mov     eax, [rsp+48h+ExitCode]
0x14001f51f  jmp     short loc_14001F4FB
```
