# CComDllModule::ApcThreadProc(void *)

- ea: `0x180036d30`
- end: `0x180036e15`
- name: `?ApcThreadProc@CComDllModule@@SAKPEAX@Z`
- size: `229`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800346d8`
- `0x180036d30`
- `0x18005f3b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036d88`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036de5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036d88`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036de5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180036dbe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180036dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036d3a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180036d48`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180036d48`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180036dd8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180036dd8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180036d52`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180036d52`

## pseudocode

```c
__int64 __fastcall CComDllModule::ApcThreadProc(void *a1)
{
  HANDLE CurrentThread; // rax
  HRESULT v2; // ebx
  DWORD v4; // eax
  DWORD v5; // eax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 2);
  v2 = CoInitializeEx(0, 0);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147417850 )
  {
    SetEvent(qword_18016D228);
    Handles[0] = qword_18016D230;
    Handles[1] = hTimer;
    while ( 1 )
    {
      v4 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 1);
      if ( !v4 )
        break;
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 != 191 )
          break;
      }
      else
      {
        CCContext::UpdateContexts();
        dword_18016D268 = 0;
        CComDllModule::StartWaitTimer((CComDllModule *)&_Module);
      }
    }
    if ( v2 >= 0 )
      CoUninitialize();
    SetEvent(qword_18016D238);
    return 0;
  }
  else
  {
    _InterlockedCompareExchange(&g_lServerFailing, 1, 0);
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x180036d30  mov     [rsp+arg_0], rbx
0x180036d35  push    rdi
0x180036d36  sub     rsp, 40h
0x180036d3a  call    cs:__imp_GetCurrentThread
0x180036d40  mov     rcx, rax; hThread
0x180036d43  mov     edx, 2; nPriority
0x180036d48  call    cs:__imp_SetThreadPriority
0x180036d4e  xor     edx, edx; dwCoInit
0x180036d50  xor     ecx, ecx; pvReserved
0x180036d52  call    cs:__imp_CoInitializeEx
0x180036d58  mov     ebx, eax
0x180036d5a  mov     eax, 80000000h
0x180036d5f  lea     ecx, [rbx+rax]
0x180036d62  test    eax, ecx
0x180036d64  jnz     short loc_180036D81
0x180036d66  cmp     ebx, 80010106h
0x180036d6c  jz      short loc_180036D81
0x180036d6e  mov     edi, 1
0x180036d73  xor     eax, eax
0x180036d75  lock cmpxchg cs:?g_lServerFailing@@3JA, edi; long g_lServerFailing
0x180036d7d  mov     eax, ebx
0x180036d7f  jmp     short loc_180036DED
0x180036d81  mov     rcx, cs:qword_18016D228; hEvent
0x180036d88  call    cs:__imp_SetEvent
0x180036d8e  mov     rax, cs:qword_18016D230
0x180036d95  mov     [rsp+48h+Handles], rax
0x180036d9a  mov     rax, cs:hTimer
0x180036da1  mov     [rsp+48h+var_10], rax
0x180036da6  xor     r8d, r8d; bWaitAll
0x180036da9  mov     [rsp+48h+bAlertable], 1; bAlertable
0x180036db1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180036db5  lea     rdx, [rsp+48h+Handles]; lpHandles
0x180036dba  lea     ecx, [r8+2]; nCount
0x180036dbe  call    cs:__imp_WaitForMultipleObjectsEx
0x180036dc4  test    eax, eax
0x180036dc6  jz      short loc_180036DD4
0x180036dc8  sub     eax, 1
0x180036dcb  jz      short loc_180036DF8
0x180036dcd  cmp     eax, 0BFh
0x180036dd2  jz      short loc_180036DA6
0x180036dd4  test    ebx, ebx
0x180036dd6  js      short loc_180036DDE
0x180036dd8  call    cs:__imp_CoUninitialize
0x180036dde  mov     rcx, cs:qword_18016D238; hEvent
0x180036de5  call    cs:__imp_SetEvent
0x180036deb  xor     eax, eax
0x180036ded  mov     rbx, [rsp+48h+arg_0]
0x180036df2  add     rsp, 40h
0x180036df6  pop     rdi
0x180036df7  retn
0x180036df8  call    ?UpdateContexts@CCContext@@SAXXZ; CCContext::UpdateContexts(void)
0x180036dfd  lea     rcx, ?_Module@@3VCComDllModule@@A; this
0x180036e04  mov     cs:dword_18016D268, 0
0x180036e0e  call    ?StartWaitTimer@CComDllModule@@QEAAXXZ; CComDllModule::StartWaitTimer(void)
0x180036e13  jmp     short loc_180036DA6
```
