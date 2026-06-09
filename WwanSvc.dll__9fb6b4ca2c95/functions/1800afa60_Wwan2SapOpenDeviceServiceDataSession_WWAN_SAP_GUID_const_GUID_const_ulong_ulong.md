# Wwan2SapOpenDeviceServiceDataSession(WWAN_SAP *,_GUID const *,_GUID const *,ulong *,ulong *)

- ea: `0x1800afa60`
- end: `0x1800afc63`
- name: `?Wwan2SapOpenDeviceServiceDataSession@@YAKPEAUWWAN_SAP@@PEBU_GUID@@1PEAK2@Z`
- size: `515`
- prototype: `unsigned int __fastcall(struct WWAN_SAP *, const struct _GUID *, const struct _GUID *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x1800abfc0`

## callees

- `0x180008abc`
- `0x180010e94`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x18007289c`
- `0x18007cb94`
- `0x180089388`
- `0x1800893b4`
- `0x1800afa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800afc1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800afc1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800afabe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800afabe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afadf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afb0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afc24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afadf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afb0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afc24`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800afb04`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800afb04`

## string_xrefs

- `0x1800afaf4`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800afb23`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800afc39`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800afae8`: `CreateEvent`
- `0x1800afaa0`: `Wwan2SapOpenDeviceServiceDataSession`
- `0x1800afbf7`: `Wwan2SapOpenDeviceServiceDataSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapOpenDeviceServiceDataSession(
        struct WWAN_SAP *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        MessageParams *a4,
        unsigned int *a5)
{
  HANDLE EventW; // rax
  MessageParams *v11; // rbx
  DWORD LastError; // eax
  DWORD v13; // eax
  MessageParams *v14; // rsi
  unsigned int v15; // edx
  DWORD v16; // eax
  HANDLE hHandle; // [rsp+20h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-20h] BYREF
  MessageParams *v19[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+48h] BYREF

  v20 = 0;
  Binding = 0;
  if ( a1 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&hHandle, EventW);
    v11 = (MessageParams *)hHandle;
    if ( (unsigned __int64)hHandle + 1 <= 1 )
    {
      LastError = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x943u, "CreateEvent", LastError);
    }
    if ( RpcServerInqBindingHandle(&Binding) )
    {
      v13 = GetLastError();
      __FatalError(
        "onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c",
        0x94Au,
        "RpcServerInqBindingHandle",
        v13);
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
    v19[0] = (MessageParams *)a5;
    std::vector<void *>::push_back((char *)v14 + 48, v19);
    std::vector<void *>::_Emplace_one_at_back<void * const &>((char *)v14 + 48, &Binding);
    if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(32, v14) )
    {
      if ( v14 )
        MessageParams::`scalar deleting destructor'(v14, v15);
      WwanLog::Error("Wwan2SapOpenDeviceServiceDataSession", 0, L"Notification dispatcher: Failed to Queue Message");
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
      return 31;
    }
    else
    {
      if ( WaitForSingleObject(v11, 0xFFFFFFFF) )
      {
        v16 = GetLastError();
        __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x960u, "WaitForSingleObject", v16);
      }
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
      return v20;
    }
  }
  else
  {
    WwanLog::Error("Wwan2SapOpenDeviceServiceDataSession", 0, L"[%p] Invalid parameters", 0);
    return 87;
  }
}

```

## disassembly

```asm
0x1800afa60  push    rbp
0x1800afa62  push    rbx
0x1800afa63  push    rsi
0x1800afa64  push    rdi
0x1800afa65  push    r12
0x1800afa67  push    r13
0x1800afa69  push    r14
0x1800afa6b  push    r15
0x1800afa6d  mov     rbp, rsp
0x1800afa70  sub     rsp, 48h
0x1800afa74  mov     r15, r9
0x1800afa77  mov     r12, r8
0x1800afa7a  mov     r13, rdx
0x1800afa7d  mov     r14, rcx
0x1800afa80  mov     [rbp+arg_0], 0
0x1800afa87  mov     [rbp+Binding], 0
0x1800afa8f  xor     r9d, r9d; lpName
0x1800afa92  test    rcx, rcx
0x1800afa95  jnz     short loc_1800AFAB5
0x1800afa97  lea     r8, aPInvalidParame; "[%p] Invalid parameters"
0x1800afa9e  xor     edx, edx; struct _GUID *
0x1800afaa0  lea     rcx, aWwan2sapopende; "Wwan2SapOpenDeviceServiceDataSession"
0x1800afaa7  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800afaac  lea     eax, [r14+57h]
0x1800afab0  jmp     loc_1800AFC52
0x1800afab5  xor     r8d, r8d; bInitialState
0x1800afab8  lea     edx, [r8+1]; bManualReset
0x1800afabc  xor     ecx, ecx; lpEventAttributes
0x1800afabe  call    cs:__imp_CreateEventW
0x1800afac4  mov     rdx, rax
0x1800afac7  lea     rcx, [rbp+hHandle]
0x1800afacb  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800afad0  nop
0x1800afad1  mov     rbx, [rbp+hHandle]
0x1800afad5  lea     rax, [rbx+1]
0x1800afad9  cmp     rax, 1
0x1800afadd  ja      short loc_1800AFB00
0x1800afadf  call    cs:__imp_GetLastError
0x1800afae5  mov     r9d, eax; unsigned int
0x1800afae8  lea     r8, aCreateevent; "CreateEvent"
0x1800afaef  mov     edx, 943h; unsigned int
0x1800afaf4  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800afafb  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800afb00  lea     rcx, [rbp+Binding]; Binding
0x1800afb04  call    cs:__imp_RpcServerInqBindingHandle
0x1800afb0a  test    eax, eax
0x1800afb0c  jz      short loc_1800AFB2F
0x1800afb0e  call    cs:__imp_GetLastError
0x1800afb14  mov     r9d, eax; unsigned int
0x1800afb17  lea     r8, aRpcserverinqbi_0; "RpcServerInqBindingHandle"
0x1800afb1e  mov     edx, 94Ah; unsigned int
0x1800afb23  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800afb2a  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800afb2f  mov     ecx, 48h ; 'H'; Size
0x1800afb34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800afb39  mov     [rbp+var_18], rax
0x1800afb3d  mov     rcx, rax; this
0x1800afb40  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800afb45  mov     rsi, rax
0x1800afb48  lea     rdi, [rax+30h]
0x1800afb4c  mov     [rbp+var_18], rbx
0x1800afb50  lea     rdx, [rbp+var_18]
0x1800afb54  mov     rcx, rdi
0x1800afb57  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800afb5c  lea     rax, [rbp+arg_0]
0x1800afb60  mov     [rbp+var_18], rax
0x1800afb64  lea     rdx, [rbp+var_18]
0x1800afb68  mov     rcx, rdi
0x1800afb6b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800afb70  mov     [rbp+var_18], r14
0x1800afb74  lea     rdx, [rbp+var_18]
0x1800afb78  mov     rcx, rdi
0x1800afb7b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800afb80  mov     [rbp+var_18], r13
0x1800afb84  lea     rdx, [rbp+var_18]
0x1800afb88  mov     rcx, rdi
0x1800afb8b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800afb90  mov     [rbp+var_18], r12
0x1800afb94  lea     rdx, [rbp+var_18]
0x1800afb98  mov     rcx, rdi
0x1800afb9b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800afba0  mov     [rbp+var_18], r15
0x1800afba4  lea     rdx, [rbp+var_18]
0x1800afba8  mov     rcx, rdi
0x1800afbab  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800afbb0  mov     rax, [rbp+arg_20]
0x1800afbb4  mov     [rbp+var_18], rax
0x1800afbb8  lea     rdx, [rbp+var_18]
0x1800afbbc  mov     rcx, rdi
0x1800afbbf  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800afbc4  lea     rdx, [rbp+Binding]
0x1800afbc8  mov     rcx, rdi
0x1800afbcb  call    ??$_Emplace_one_at_back@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAAEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_one_at_back<void * const &>(void * const &)
0x1800afbd0  mov     rdx, rsi
0x1800afbd3  mov     ecx, 20h ; ' '
0x1800afbd8  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800afbdd  test    eax, eax
0x1800afbdf  jz      short loc_1800AFC14
0x1800afbe1  test    rsi, rsi
0x1800afbe4  jz      short loc_1800AFBEE
0x1800afbe6  mov     rcx, rsi; this
0x1800afbe9  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800afbee  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800afbf5  xor     edx, edx; struct _GUID *
0x1800afbf7  lea     rcx, aWwan2sapopende; "Wwan2SapOpenDeviceServiceDataSession"
0x1800afbfe  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800afc03  nop
0x1800afc04  lea     rcx, [rbp+hHandle]
0x1800afc08  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800afc0d  mov     eax, 1Fh
0x1800afc12  jmp     short loc_1800AFC52
0x1800afc14  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800afc17  mov     rcx, rbx; hHandle
0x1800afc1a  call    cs:__imp_WaitForSingleObject
0x1800afc20  test    eax, eax
0x1800afc22  jz      short loc_1800AFC46
0x1800afc24  call    cs:__imp_GetLastError
0x1800afc2a  mov     r9d, eax; unsigned int
0x1800afc2d  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800afc34  mov     edx, 960h; unsigned int
0x1800afc39  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800afc40  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800afc45  nop
0x1800afc46  lea     rcx, [rbp+hHandle]
0x1800afc4a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800afc4f  mov     eax, [rbp+arg_0]
0x1800afc52  add     rsp, 48h
0x1800afc56  pop     r15
0x1800afc58  pop     r14
0x1800afc5a  pop     r13
0x1800afc5c  pop     r12
0x1800afc5e  pop     rdi
0x1800afc5f  pop     rsi
0x1800afc60  pop     rbx
0x1800afc61  pop     rbp
0x1800afc62  retn
```
