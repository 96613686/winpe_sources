# ServiceMain(ulong,ushort * *)

- ea: `0x180005de0`
- end: `0x180005ee1`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `257`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180005bb0`
- `0x180005c74`
- `0x180005de0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005e2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005e2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e46`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005eba`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005eba`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005dfe`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005dfe`
- `vmsif!VmsIfInitializeEventServer` at `0x180005e4c`
- `vmsif!VmsIfInitializeEventServer` at `0x180005e4c`

## string_xrefs

- `0x180005df7`: `NvAgent`
- `0x180005e6b`: `NvAgent`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  unsigned int v2; // r8d
  HANDLE EventA; // rax
  HANDLE v4; // rcx
  int v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  HANDLE v9; // rcx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *v12; // [rsp+60h] [rbp+18h] BYREF

  NvAgentService::Instance = RegisterServiceCtrlHandlerExW(
                               L"NvAgent",
                               NvAgentService::Handler,
                               &NvAgentService::Instance);
  if ( NvAgentService::Instance )
  {
    NvAgentService::SetStatus((NvAgentService *)&NvAgentService::Instance, 2u, v2);
    EventA = CreateEventA(0, 1, 0, 0);
    v4 = hObject;
    hObject = EventA;
    if ( v4 )
      CloseHandle(v4);
    v5 = VmsIfInitializeEventServer();
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, v6, v7, (const char *)(unsigned int)v5, v10);
    byte_18000B3C0 = 1;
    v12 = 0;
    (*(void (__fastcall **)(void **, const WCHAR *, HANDLE, void (__fastcall *)(NvAgentService *, unsigned __int8), void *, int))(qword_18000B3A8 + 192))(
      &v12,
      L"NvAgent",
      hObject,
      NvAgentService::StopCallback,
      &NvAgentService::Instance,
      24);
    v9 = WaitHandle;
    WaitHandle = v12;
    if ( v9 )
      UnregisterWaitEx(v9, 0);
    NvAgentService::SetStatus((NvAgentService *)&NvAgentService::Instance, 4u, v8);
  }
}

```

## disassembly

```asm
0x180005de0  push    rbx
0x180005de2  sub     rsp, 40h
0x180005de6  lea     rbx, ?Instance@NvAgentService@@2V1@A; NvAgentService NvAgentService::Instance
0x180005ded  mov     r8, rbx; lpContext
0x180005df0  lea     rdx, ?Handler@NvAgentService@@KAKKKPEAX0@Z; lpHandlerProc
0x180005df7  lea     rcx, ServiceName; "NvAgent"
0x180005dfe  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180005e04  mov     cs:?Instance@NvAgentService@@2V1@A, rax; NvAgentService NvAgentService::Instance
0x180005e0b  test    rax, rax
0x180005e0e  jz      loc_180005ECD
0x180005e14  mov     edx, 2; unsigned int
0x180005e19  mov     rcx, rbx; this
0x180005e1c  call    ?SetStatus@NvAgentService@@IEAAXKK@Z; NvAgentService::SetStatus(ulong,ulong)
0x180005e21  xor     r9d, r9d; lpName
0x180005e24  xor     r8d, r8d; bInitialState
0x180005e27  xor     ecx, ecx; lpEventAttributes
0x180005e29  lea     edx, [r9+1]; bManualReset
0x180005e2d  call    cs:__imp_CreateEventA
0x180005e33  mov     rcx, cs:hObject; hObject
0x180005e3a  mov     cs:hObject, rax
0x180005e41  test    rcx, rcx
0x180005e44  jz      short loc_180005E4C
0x180005e46  call    cs:__imp_CloseHandle
0x180005e4c  call    cs:__imp_VmsIfInitializeEventServer
0x180005e52  test    eax, eax
0x180005e54  js      short loc_180005ED3
0x180005e56  mov     rax, cs:qword_18000B3A8
0x180005e5d  lea     r9, ?StopCallback@NvAgentService@@CAXPEAXE@Z; NvAgentService::StopCallback(void *,uchar)
0x180005e64  mov     r8, cs:hObject
0x180005e6b  lea     rdx, ServiceName; "NvAgent"
0x180005e72  mov     cs:byte_18000B3C0, 1
0x180005e79  lea     rcx, [rsp+48h+arg_10]
0x180005e7e  mov     [rsp+48h+arg_10], 0
0x180005e87  mov     rax, [rax+0C0h]
0x180005e8e  mov     [rsp+48h+var_20], 18h
0x180005e96  mov     [rsp+48h+var_28], rbx
0x180005e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea0  mov     rcx, cs:WaitHandle; WaitHandle
0x180005ea7  mov     rax, [rsp+48h+arg_10]
0x180005eac  mov     cs:WaitHandle, rax
0x180005eb3  test    rcx, rcx
0x180005eb6  jz      short loc_180005EC0
0x180005eb8  xor     edx, edx; CompletionEvent
0x180005eba  call    cs:__imp_UnregisterWaitEx
0x180005ec0  mov     edx, 4; unsigned int
0x180005ec5  mov     rcx, rbx; this
0x180005ec8  call    ?SetStatus@NvAgentService@@IEAAXKK@Z; NvAgentService::SetStatus(ulong,ulong)
0x180005ecd  add     rsp, 40h
0x180005ed1  pop     rbx
0x180005ed2  retn
0x180005ed3  mov     rcx, [rsp+48h]; this
0x180005ed8  mov     r9d, eax; char *
0x180005edb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
