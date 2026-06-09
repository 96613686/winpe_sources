# CComDllModule::StartApcAndHookThreads(void)

- ea: `0x18002c618`
- end: `0x18002c7c4`
- name: `?StartApcAndHookThreads@CComDllModule@@QEAAXXZ`
- size: `428`
- prototype: `void __fastcall(CComDllModule *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001154c`
- `0x180012344`
- `0x1800126b0`
- `0x180012850`
- `0x180012d28`
- `0x1800295a0`
- `0x18002a350`

## callees

- `0x18002c618`
- `0x18002e22c`
- `0x180036c00`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x18002c69d`
- `msvcrt!_beginthreadex` at `0x18002c6d7`
- `msvcrt!_beginthreadex` at `0x18002c69d`
- `msvcrt!_beginthreadex` at `0x18002c6d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c78e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c78e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002c734`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002c77d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002c734`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002c77d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c663`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c663`

## string_xrefs

- `0x18002c622`: `CComDllModule::StartApcAndHookThreads- ENTER`
- `0x18002c79f`: `CComDllModule::StartApcAndHookThreads- EXIT`

## pseudocode

```c
void __fastcall CComDllModule::StartApcAndHookThreads(CComDllModule *this)
{
  HANDLE Handles; // [rsp+30h] [rbp-18h] BYREF
  HANDLE v2; // [rsp+38h] [rbp-10h]
  CComDllModule *ThrdAddr; // [rsp+50h] [rbp+8h] BYREF

  ThrdAddr = this;
  WispTraceVerbose("%s\n", "CComDllModule::StartApcAndHookThreads- ENTER");
  if ( (g_pGIT || CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &g_pGIT) >= 0)
    && (LODWORD(ThrdAddr) = 0,
        (hObject = (HANDLE)_beginthreadex(0, 0, CComDllModule::ApcThreadProc, &_Module, 0, (unsigned int *)&ThrdAddr)) != 0)
    && (hThread = (HANDLE)_beginthreadex(0, 0, CComDllModule::HookThreadProc, &_Module, 0, (unsigned int *)&ThrdAddr)) != 0
    && qword_18016D218
    && (int)CRealTimePenService::CreateDispatchThread(qword_18016D218) >= 0 )
  {
    Handles = qword_18016D228;
    v2 = hObject;
    if ( WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF) )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    Handles = hEvent;
    v2 = hThread;
    if ( WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF) )
    {
      CloseHandle(hThread);
      hThread = 0;
    }
    WispTraceVerbose("%s\n", "CComDllModule::StartApcAndHookThreads- EXIT");
  }
  else
  {
    _InterlockedCompareExchange(&g_lServerFailing, 1, 0);
  }
}

```

## disassembly

```asm
0x18002c618  mov     [rsp+arg_0], rcx
0x18002c61d  push    rdi
0x18002c61e  sub     rsp, 40h
0x18002c622  lea     rdx, aCcomdllmoduleS_2; "CComDllModule::StartApcAndHookThreads- "...
0x18002c629  lea     rcx, aS_0; "%s\n"
0x18002c630  call    ?WispTraceVerbose@@YAXPEBDZZ; WispTraceVerbose(char const *,...)
0x18002c635  cmp     cs:?g_pGIT@@3PEAUIGlobalInterfaceTable@@EA, 0; IGlobalInterfaceTable * g_pGIT
0x18002c63d  mov     edi, 1
0x18002c642  jnz     short loc_18002C671
0x18002c644  lea     rax, ?g_pGIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pGIT
0x18002c64b  mov     r8d, edi; dwClsContext
0x18002c64e  lea     r9, IID_IGlobalInterfaceTable; riid
0x18002c655  mov     [rsp+48h+ppv], rax; ppv
0x18002c65a  xor     edx, edx; pUnkOuter
0x18002c65c  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18002c663  call    cs:__imp_CoCreateInstance
0x18002c669  test    eax, eax
0x18002c66b  js      loc_18002C7B4
0x18002c671  lea     rax, [rsp+48h+arg_0]
0x18002c676  mov     dword ptr [rsp+48h+arg_0], 0
0x18002c67e  mov     [rsp+48h+ThrdAddr], rax; ThrdAddr
0x18002c683  lea     r9, ?_Module@@3VCComDllModule@@A; ArgList
0x18002c68a  lea     r8, ?ApcThreadProc@CComDllModule@@SAKPEAX@Z; StartAddress
0x18002c691  mov     dword ptr [rsp+48h+ppv], 0; InitFlag
0x18002c699  xor     edx, edx; StackSize
0x18002c69b  xor     ecx, ecx; Security
0x18002c69d  call    cs:__imp__beginthreadex
0x18002c6a3  mov     cs:hObject, rax
0x18002c6aa  test    rax, rax
0x18002c6ad  jz      loc_18002C7B4
0x18002c6b3  lea     rax, [rsp+48h+arg_0]
0x18002c6b8  xor     edx, edx; StackSize
0x18002c6ba  mov     [rsp+48h+ThrdAddr], rax; ThrdAddr
0x18002c6bf  lea     r9, ?_Module@@3VCComDllModule@@A; ArgList
0x18002c6c6  lea     r8, ?HookThreadProc@CComDllModule@@SAKPEAX@Z; StartAddress
0x18002c6cd  mov     dword ptr [rsp+48h+ppv], 0; InitFlag
0x18002c6d5  xor     ecx, ecx; Security
0x18002c6d7  call    cs:__imp__beginthreadex
0x18002c6dd  mov     cs:hThread, rax
0x18002c6e4  test    rax, rax
0x18002c6e7  jz      loc_18002C7B4
0x18002c6ed  mov     rcx, cs:qword_18016D218; this
0x18002c6f4  test    rcx, rcx
0x18002c6f7  jz      loc_18002C7B4
0x18002c6fd  call    ?CreateDispatchThread@CRealTimePenService@@QEAAJXZ; CRealTimePenService::CreateDispatchThread(void)
0x18002c702  test    eax, eax
0x18002c704  js      loc_18002C7B4
0x18002c70a  mov     rax, cs:qword_18016D228
0x18002c711  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18002c716  xor     r8d, r8d; bWaitAll
0x18002c719  mov     [rsp+48h+Handles], rax
0x18002c71e  mov     rax, cs:hObject
0x18002c725  or      edi, 0FFFFFFFFh
0x18002c728  mov     r9d, edi; dwMilliseconds
0x18002c72b  mov     [rsp+48h+var_10], rax
0x18002c730  lea     ecx, [r8+2]; nCount
0x18002c734  call    cs:__imp_WaitForMultipleObjects
0x18002c73a  test    eax, eax
0x18002c73c  jz      short loc_18002C756
0x18002c73e  mov     rcx, cs:hObject; hObject
0x18002c745  call    cs:__imp_CloseHandle
0x18002c74b  mov     cs:hObject, 0
0x18002c756  mov     rax, cs:hEvent
0x18002c75d  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18002c762  xor     r8d, r8d; bWaitAll
0x18002c765  mov     [rsp+48h+Handles], rax
0x18002c76a  mov     rax, cs:hThread
0x18002c771  mov     r9d, edi; dwMilliseconds
0x18002c774  mov     [rsp+48h+var_10], rax
0x18002c779  lea     ecx, [r8+2]; nCount
0x18002c77d  call    cs:__imp_WaitForMultipleObjects
0x18002c783  test    eax, eax
0x18002c785  jz      short loc_18002C79F
0x18002c787  mov     rcx, cs:hThread; hObject
0x18002c78e  call    cs:__imp_CloseHandle
0x18002c794  mov     cs:hThread, 0
0x18002c79f  lea     rdx, aCcomdllmoduleS_0; "CComDllModule::StartApcAndHookThreads- "...
0x18002c7a6  lea     rcx, aS_0; "%s\n"
0x18002c7ad  call    ?WispTraceVerbose@@YAXPEBDZZ; WispTraceVerbose(char const *,...)
0x18002c7b2  jmp     short loc_18002C7BE
0x18002c7b4  xor     eax, eax
0x18002c7b6  lock cmpxchg cs:?g_lServerFailing@@3JA, edi; long g_lServerFailing
0x18002c7be  add     rsp, 40h
0x18002c7c2  pop     rdi
0x18002c7c3  retn
```
