# CComDllModule::ShutdownApcAndHookThreads(void)

- ea: `0x18005f060`
- end: `0x18005f1de`
- name: `?ShutdownApcAndHookThreads@CComDllModule@@QEAAXXZ`
- size: `382`
- prototype: `void __fastcall(CComDllModule *__hidden this)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800126b0`
- `0x180012850`
- `0x180012b04`
- `0x180012db0`
- `0x18002158c`
- `0x180021adc`
- `0x180022804`
- `0x1800295a0`

## callees

- `0x180036c00`
- `0x18005f060`
- `0x180065ec8`
- `0x180079728`
- `0x180079a58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f0a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f140`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f0a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f140`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18005f0f9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18005f191`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18005f0f9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18005f191`

## string_xrefs

- `0x18005f066`: `CComDllModule::ShutdownApcAndHookThreads- ENTER`
- `0x18005f0b0`: `CComDllModule::ShutdownApcAndHookThreads`
- `0x18005f10f`: `CComDllModule::ShutdownApcAndHookThreads`
- `0x18005f148`: `CComDllModule::ShutdownApcAndHookThreads`
- `0x18005f1a7`: `CComDllModule::ShutdownApcAndHookThreads`
- `0x18005f0b7`: `%s : Unable to set ApcThreadExit event during shutdown.\n`
- `0x18005f119`: `%s : Unexpected return code (0x%d) from WaitForApcThread.\n`
- `0x18005f14f`: `%s : Unable to set HookThreadExit event during shutdown.\n`
- `0x18005f1b1`: `%s : Unexpected return code (0x%d) from WaitForHookThread.\n`
- `0x18005f1c5`: `CComDllModule::ShutdownApcAndHookThreads- EXIT`

## pseudocode

```c
void __fastcall CComDllModule::ShutdownApcAndHookThreads(CComDllModule *this)
{
  BOOL v1; // ebx
  DWORD v2; // ebx
  BOOL v3; // ebx
  DWORD v4; // ebx
  HANDLE Handles[3]; // [rsp+20h] [rbp-18h] BYREF

  WispTraceVerbose("%s\n", "CComDllModule::ShutdownApcAndHookThreads- ENTER");
  *(_OWORD *)Handles = 0;
  if ( qword_18016D218 )
    CRealTimePenService::DestroyDispatchThread(qword_18016D218);
  if ( hObject )
  {
    v1 = SetEvent(qword_18016D230);
    WispTraceErrorIf(
      !v1,
      "%s : Unable to set ApcThreadExit event during shutdown.\n",
      "CComDllModule::ShutdownApcAndHookThreads");
    if ( v1 )
    {
      Handles[0] = qword_18016D238;
      Handles[1] = hObject;
      v2 = WaitForMultipleObjects(2u, Handles, 0, 0x1D4C0u);
      SafeCloseHandle(&hObject);
      WispTraceErrorIf(
        v2 != 0,
        "%s : Unexpected return code (0x%d) from WaitForApcThread.\n",
        "CComDllModule::ShutdownApcAndHookThreads",
        v2);
    }
  }
  if ( hThread )
  {
    v3 = SetEvent(qword_18016D250);
    WispTraceErrorIf(
      !v3,
      "%s : Unable to set HookThreadExit event during shutdown.\n",
      "CComDllModule::ShutdownApcAndHookThreads");
    if ( v3 )
    {
      Handles[0] = qword_18016D258;
      Handles[1] = hThread;
      v4 = WaitForMultipleObjects(2u, Handles, 0, 0x1D4C0u);
      SafeCloseHandle(&hThread);
      WispTraceErrorIf(
        v4 != 0,
        "%s : Unexpected return code (0x%d) from WaitForHookThread.\n",
        "CComDllModule::ShutdownApcAndHookThreads",
        v4);
    }
  }
  WispTraceVerbose("%s\n", "CComDllModule::ShutdownApcAndHookThreads- EXIT");
}

```

## disassembly

```asm
0x18005f060  push    rbx
0x18005f062  sub     rsp, 30h
0x18005f066  lea     rdx, aCcomdllmoduleS_3; "CComDllModule::ShutdownApcAndHookThread"...
0x18005f06d  lea     rcx, aS_0; "%s\n"
0x18005f074  call    ?WispTraceVerbose@@YAXPEBDZZ; WispTraceVerbose(char const *,...)
0x18005f079  mov     rcx, cs:qword_18016D218; this
0x18005f080  xorps   xmm0, xmm0
0x18005f083  movdqu  xmmword ptr [rsp+38h+Handles], xmm0
0x18005f089  test    rcx, rcx
0x18005f08c  jz      short loc_18005F093
0x18005f08e  call    ?DestroyDispatchThread@CRealTimePenService@@QEAAJXZ; CRealTimePenService::DestroyDispatchThread(void)
0x18005f093  cmp     cs:hObject, 0
0x18005f09b  jz      loc_18005F12B
0x18005f0a1  mov     rcx, cs:qword_18016D230; hEvent
0x18005f0a8  call    cs:__imp_SetEvent
0x18005f0ae  test    eax, eax
0x18005f0b0  lea     r8, aCcomdllmoduleS; "CComDllModule::ShutdownApcAndHookThread"...
0x18005f0b7  lea     rdx, aSUnableToSetAp; "%s : Unable to set ApcThreadExit event "...
0x18005f0be  mov     ebx, eax
0x18005f0c0  setz    cl
0x18005f0c3  movzx   ecx, cl; bool
0x18005f0c6  call    ?WispTraceErrorIf@@YAX_NPEBDZZ; WispTraceErrorIf(bool,char const *,...)
0x18005f0cb  test    ebx, ebx
0x18005f0cd  jz      short loc_18005F12B
0x18005f0cf  mov     rax, cs:qword_18016D238
0x18005f0d6  lea     rdx, [rsp+38h+Handles]; lpHandles
0x18005f0db  xor     r8d, r8d; bWaitAll
0x18005f0de  mov     [rsp+38h+Handles], rax
0x18005f0e3  mov     rax, cs:hObject
0x18005f0ea  mov     r9d, 1D4C0h; dwMilliseconds
0x18005f0f0  mov     [rsp+38h+Handles+8], rax
0x18005f0f5  lea     ecx, [r8+2]; nCount
0x18005f0f9  call    cs:__imp_WaitForMultipleObjects
0x18005f0ff  lea     rcx, hObject; void **
0x18005f106  mov     ebx, eax
0x18005f108  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18005f10d  test    ebx, ebx
0x18005f10f  lea     r8, aCcomdllmoduleS; "CComDllModule::ShutdownApcAndHookThread"...
0x18005f116  mov     r9d, ebx
0x18005f119  lea     rdx, aSUnexpectedRet_0; "%s : Unexpected return code (0x%d) from"...
0x18005f120  setnz   cl
0x18005f123  movzx   ecx, cl; bool
0x18005f126  call    ?WispTraceErrorIf@@YAX_NPEBDZZ; WispTraceErrorIf(bool,char const *,...)
0x18005f12b  cmp     cs:hThread, 0
0x18005f133  jz      loc_18005F1C5
0x18005f139  mov     rcx, cs:qword_18016D250; hEvent
0x18005f140  call    cs:__imp_SetEvent
0x18005f146  test    eax, eax
0x18005f148  lea     r8, aCcomdllmoduleS; "CComDllModule::ShutdownApcAndHookThread"...
0x18005f14f  lea     rdx, aSUnableToSetHo; "%s : Unable to set HookThreadExit event"...
0x18005f156  mov     ebx, eax
0x18005f158  setz    cl
0x18005f15b  movzx   ecx, cl; bool
0x18005f15e  call    ?WispTraceErrorIf@@YAX_NPEBDZZ; WispTraceErrorIf(bool,char const *,...)
0x18005f163  test    ebx, ebx
0x18005f165  jz      short loc_18005F1C5
0x18005f167  mov     rax, cs:qword_18016D258
0x18005f16e  lea     rdx, [rsp+38h+Handles]; lpHandles
0x18005f173  xor     r8d, r8d; bWaitAll
0x18005f176  mov     [rsp+38h+Handles], rax
0x18005f17b  mov     rax, cs:hThread
0x18005f182  mov     r9d, 1D4C0h; dwMilliseconds
0x18005f188  mov     [rsp+38h+Handles+8], rax
0x18005f18d  lea     ecx, [r8+2]; nCount
0x18005f191  call    cs:__imp_WaitForMultipleObjects
0x18005f197  lea     rcx, hThread; void **
0x18005f19e  mov     ebx, eax
0x18005f1a0  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18005f1a5  test    ebx, ebx
0x18005f1a7  lea     r8, aCcomdllmoduleS; "CComDllModule::ShutdownApcAndHookThread"...
0x18005f1ae  mov     r9d, ebx
0x18005f1b1  lea     rdx, aSUnexpectedRet; "%s : Unexpected return code (0x%d) from"...
0x18005f1b8  setnz   r10b
0x18005f1bc  movzx   ecx, r10b; bool
0x18005f1c0  call    ?WispTraceErrorIf@@YAX_NPEBDZZ; WispTraceErrorIf(bool,char const *,...)
0x18005f1c5  lea     rdx, aCcomdllmoduleS_1; "CComDllModule::ShutdownApcAndHookThread"...
0x18005f1cc  lea     rcx, aS_0; "%s\n"
0x18005f1d3  call    ?WispTraceVerbose@@YAXPEBDZZ; WispTraceVerbose(char const *,...)
0x18005f1d8  add     rsp, 30h
0x18005f1dc  pop     rbx
0x18005f1dd  retn
```
