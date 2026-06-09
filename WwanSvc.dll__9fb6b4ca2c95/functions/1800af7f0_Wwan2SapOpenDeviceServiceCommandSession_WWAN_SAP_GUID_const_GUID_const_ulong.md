# Wwan2SapOpenDeviceServiceCommandSession(WWAN_SAP *,_GUID const *,_GUID const *,ulong *)

- ea: `0x1800af7f0`
- end: `0x1800afa59`
- name: `?Wwan2SapOpenDeviceServiceCommandSession@@YAKPEAUWWAN_SAP@@PEBU_GUID@@1PEAK@Z`
- size: `617`
- prototype: `unsigned int __fastcall(struct WWAN_SAP *, const struct _GUID *, const struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800abf70`

## callees

- `0x180008abc`
- `0x180010e94`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x180014f1c`
- `0x18005bb50`
- `0x18007289c`
- `0x18007cb94`
- `0x180089388`
- `0x1800893b4`
- `0x1800af7f0`
- `0x1800b645c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800af844`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800af844`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af882`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af893`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af882`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af893`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af9ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af9ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af8a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af8a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af8c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af9f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af8c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af9f7`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800af8eb`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800af8eb`

## string_xrefs

- `0x1800af8db`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800af90a`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800afa0c`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800af8cf`: `CreateEvent`
- `0x1800af830`: `Wwan2SapOpenDeviceServiceCommandSession`
- `0x1800af86c`: `Wwan2SapOpenDeviceServiceCommandSession`
- `0x1800af9ca`: `Wwan2SapOpenDeviceServiceCommandSession`
- `0x1800afa2f`: `Wwan2SapOpenDeviceServiceCommandSession`
- `0x1800afa26`: `[%p] Failed to add subscription for command session open. Error = %d`
- `0x1800af863`: `[%p] Failed to get device service SAP for open command session`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapOpenDeviceServiceCommandSession(
        struct WWAN_SAP *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        MessageParams *a4)
{
  struct _WWAN_DEVICE_SERVICES_SAP *DeviceServicesSap; // rax
  HANDLE EventW; // rax
  MessageParams *v11; // rbx
  DWORD LastError; // eax
  DWORD v13; // eax
  MessageParams *v14; // r14
  unsigned int v15; // edx
  DWORD v16; // eax
  HANDLE hHandle; // [rsp+30h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-20h] BYREF
  MessageParams *v19[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+48h] BYREF

  v20 = 0;
  Binding = 0;
  if ( !a1 )
  {
    WwanLog::Error("Wwan2SapOpenDeviceServiceCommandSession", 0, L"[%p] Invalid parameters", 0);
    return 87;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  DeviceServicesSap = _wwan2SapGetDeviceServicesSap(a1, a2, 1);
  if ( !DeviceServicesSap )
  {
    WwanLog::Info(
      "Wwan2SapOpenDeviceServiceCommandSession",
      0,
      L"[%p] Failed to get device service SAP for open command session",
      a1);
    v20 = 14;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1);
    return v20;
  }
  ++*((_DWORD *)DeviceServicesSap + 8);
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&hHandle, EventW);
  v11 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x7FDu, "CreateEvent", LastError);
  }
  if ( RpcServerInqBindingHandle(&Binding) )
  {
    v13 = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x804u, "RpcServerInqBindingHandle", v13);
  }
  v19[0] = (MessageParams *)operator new(0x48u);
  v14 = MessageParams::MessageParams(v19[0]);
  v19[0] = v11;
  std::vector<void *>::push_back((char *)v14 + 48, v19);
  v19[0] = (MessageParams *)&v20;
  std::vector<void *>::push_back((char *)v14 + 48, v19);
  v19[0] = a1;
  std::vector<void *>::push_back((char *)v14 + 48, v19);
  v19[0] = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v14 + 48, v19);
  v19[0] = (MessageParams *)a3;
  std::vector<void *>::push_back((char *)v14 + 48, v19);
  v19[0] = a4;
  std::vector<void *>::push_back((char *)v14 + 48, v19);
  std::vector<void *>::_Emplace_one_at_back<void * const &>((char *)v14 + 48, &Binding);
  if ( !(unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(27, v14) )
  {
    if ( WaitForSingleObject(v11, 0xFFFFFFFF) )
    {
      v16 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x81Au, "WaitForSingleObject", v16);
    }
    if ( v20 )
      WwanLog::Error(
        "Wwan2SapOpenDeviceServiceCommandSession",
        0,
        L"[%p] Failed to add subscription for command session open. Error = %d",
        a1,
        v20);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
    return v20;
  }
  if ( v14 )
    MessageParams::`scalar deleting destructor'(v14, v15);
  WwanLog::Error("Wwan2SapOpenDeviceServiceCommandSession", 0, L"Notification dispatcher: Failed to Queue Message");
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return 31;
}

```

## disassembly

```asm
0x1800af7f0  push    rbp
0x1800af7f2  push    rbx
0x1800af7f3  push    rsi
0x1800af7f4  push    rdi
0x1800af7f5  push    r12
0x1800af7f7  push    r13
0x1800af7f9  push    r14
0x1800af7fb  push    r15
0x1800af7fd  mov     rbp, rsp
0x1800af800  sub     rsp, 58h
0x1800af804  mov     r12, r9
0x1800af807  mov     r13, r8
0x1800af80a  mov     r15, rdx
0x1800af80d  mov     rsi, rcx
0x1800af810  mov     [rbp+arg_0], 0
0x1800af817  mov     [rbp+Binding], 0
0x1800af81f  test    rcx, rcx
0x1800af822  jnz     short loc_1800AF844
0x1800af824  xor     r9d, r9d
0x1800af827  lea     r8, aPInvalidParame; "[%p] Invalid parameters"
0x1800af82e  xor     edx, edx; struct _GUID *
0x1800af830  lea     rcx, aWwan2sapopende_0; "Wwan2SapOpenDeviceServiceCommandSession"
0x1800af837  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af83c  lea     eax, [rsi+57h]
0x1800af83f  jmp     loc_1800AFA48
0x1800af844  call    cs:__imp_EnterCriticalSection
0x1800af84a  mov     r8d, 1; int
0x1800af850  mov     rdx, r15; struct _GUID *
0x1800af853  mov     rcx, rsi; struct WWAN_SAP *
0x1800af856  call    ?_wwan2SapGetDeviceServicesSap@@YAPEAU_WWAN_DEVICE_SERVICES_SAP@@PEAUWWAN_SAP@@PEBU_GUID@@H@Z; _wwan2SapGetDeviceServicesSap(WWAN_SAP *,_GUID const *,int)
0x1800af85b  test    rax, rax
0x1800af85e  jnz     short loc_1800AF88D
0x1800af860  mov     r9, rsi
0x1800af863  lea     r8, aPFailedToGetDe_0; "[%p] Failed to get device service SAP f"...
0x1800af86a  xor     edx, edx; struct _GUID *
0x1800af86c  lea     rcx, aWwan2sapopende_0; "Wwan2SapOpenDeviceServiceCommandSession"
0x1800af873  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800af878  mov     [rbp+arg_0], 0Eh
0x1800af87f  mov     rcx, rsi; lpCriticalSection
0x1800af882  call    cs:__imp_LeaveCriticalSection
0x1800af888  jmp     loc_1800AFA45
0x1800af88d  inc     dword ptr [rax+20h]
0x1800af890  mov     rcx, rsi; lpCriticalSection
0x1800af893  call    cs:__imp_LeaveCriticalSection
0x1800af899  xor     r9d, r9d; lpName
0x1800af89c  xor     r8d, r8d; bInitialState
0x1800af89f  lea     edx, [r9+1]; bManualReset
0x1800af8a3  xor     ecx, ecx; lpEventAttributes
0x1800af8a5  call    cs:__imp_CreateEventW
0x1800af8ab  mov     rdx, rax
0x1800af8ae  lea     rcx, [rbp+hHandle]
0x1800af8b2  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800af8b7  nop
0x1800af8b8  mov     rbx, [rbp+hHandle]
0x1800af8bc  lea     rax, [rbx+1]
0x1800af8c0  cmp     rax, 1
0x1800af8c4  ja      short loc_1800AF8E7
0x1800af8c6  call    cs:__imp_GetLastError
0x1800af8cc  mov     r9d, eax; unsigned int
0x1800af8cf  lea     r8, aCreateevent; "CreateEvent"
0x1800af8d6  mov     edx, 7FDh; unsigned int
0x1800af8db  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800af8e2  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800af8e7  lea     rcx, [rbp+Binding]; Binding
0x1800af8eb  call    cs:__imp_RpcServerInqBindingHandle
0x1800af8f1  test    eax, eax
0x1800af8f3  jz      short loc_1800AF916
0x1800af8f5  call    cs:__imp_GetLastError
0x1800af8fb  mov     r9d, eax; unsigned int
0x1800af8fe  lea     r8, aRpcserverinqbi_0; "RpcServerInqBindingHandle"
0x1800af905  mov     edx, 804h; unsigned int
0x1800af90a  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800af911  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800af916  mov     ecx, 48h ; 'H'; Size
0x1800af91b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800af920  mov     [rbp+var_18], rax
0x1800af924  mov     rcx, rax; this
0x1800af927  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800af92c  mov     r14, rax
0x1800af92f  lea     rdi, [rax+30h]
0x1800af933  mov     [rbp+var_18], rbx
0x1800af937  lea     rdx, [rbp+var_18]
0x1800af93b  mov     rcx, rdi
0x1800af93e  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af943  lea     rax, [rbp+arg_0]
0x1800af947  mov     [rbp+var_18], rax
0x1800af94b  lea     rdx, [rbp+var_18]
0x1800af94f  mov     rcx, rdi
0x1800af952  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af957  mov     [rbp+var_18], rsi
0x1800af95b  lea     rdx, [rbp+var_18]
0x1800af95f  mov     rcx, rdi
0x1800af962  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af967  mov     [rbp+var_18], r15
0x1800af96b  lea     rdx, [rbp+var_18]
0x1800af96f  mov     rcx, rdi
0x1800af972  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af977  mov     [rbp+var_18], r13
0x1800af97b  lea     rdx, [rbp+var_18]
0x1800af97f  mov     rcx, rdi
0x1800af982  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af987  mov     [rbp+var_18], r12
0x1800af98b  lea     rdx, [rbp+var_18]
0x1800af98f  mov     rcx, rdi
0x1800af992  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af997  lea     rdx, [rbp+Binding]
0x1800af99b  mov     rcx, rdi
0x1800af99e  call    ??$_Emplace_one_at_back@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAAEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_one_at_back<void * const &>(void * const &)
0x1800af9a3  mov     rdx, r14
0x1800af9a6  mov     ecx, 1Bh
0x1800af9ab  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800af9b0  test    eax, eax
0x1800af9b2  jz      short loc_1800AF9E7
0x1800af9b4  test    r14, r14
0x1800af9b7  jz      short loc_1800AF9C1
0x1800af9b9  mov     rcx, r14; this
0x1800af9bc  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800af9c1  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800af9c8  xor     edx, edx; struct _GUID *
0x1800af9ca  lea     rcx, aWwan2sapopende_0; "Wwan2SapOpenDeviceServiceCommandSession"
0x1800af9d1  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af9d6  nop
0x1800af9d7  lea     rcx, [rbp+hHandle]
0x1800af9db  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800af9e0  mov     eax, 1Fh
0x1800af9e5  jmp     short loc_1800AFA48
0x1800af9e7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800af9ea  mov     rcx, rbx; hHandle
0x1800af9ed  call    cs:__imp_WaitForSingleObject
0x1800af9f3  test    eax, eax
0x1800af9f5  jz      short loc_1800AFA18
0x1800af9f7  call    cs:__imp_GetLastError
0x1800af9fd  mov     r9d, eax; unsigned int
0x1800afa00  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800afa07  mov     edx, 81Ah; unsigned int
0x1800afa0c  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800afa13  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800afa18  mov     eax, [rbp+arg_0]
0x1800afa1b  test    eax, eax
0x1800afa1d  jz      short loc_1800AFA3C
0x1800afa1f  mov     [rsp+58h+var_38], eax
0x1800afa23  mov     r9, rsi
0x1800afa26  lea     r8, aPFailedToAddSu; "[%p] Failed to add subscription for com"...
0x1800afa2d  xor     edx, edx; struct _GUID *
0x1800afa2f  lea     rcx, aWwan2sapopende_0; "Wwan2SapOpenDeviceServiceCommandSession"
0x1800afa36  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800afa3b  nop
0x1800afa3c  lea     rcx, [rbp+hHandle]
0x1800afa40  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800afa45  mov     eax, [rbp+arg_0]
0x1800afa48  add     rsp, 58h
0x1800afa4c  pop     r15
0x1800afa4e  pop     r14
0x1800afa50  pop     r13
0x1800afa52  pop     r12
0x1800afa54  pop     rdi
0x1800afa55  pop     rsi
0x1800afa56  pop     rbx
0x1800afa57  pop     rbp
0x1800afa58  retn
```
