# Wwan2SapCloseDeviceServiceCommandSession(WWAN_SAP *,_GUID const *,_GUID const *,ulong *)

- ea: `0x1800af038`
- end: `0x1800af25b`
- name: `?Wwan2SapCloseDeviceServiceCommandSession@@YAKPEAUWWAN_SAP@@PEBU_GUID@@1PEAK@Z`
- size: `547`
- prototype: `unsigned int __fastcall(struct WWAN_SAP *, const struct _GUID *, const struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800abe20`

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
- `0x1800893b4`
- `0x1800af038`
- `0x1800b645c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800af084`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800af084`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af0bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af0d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af0bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af0d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af1ef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af1ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af0e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af0e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af1f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af1f9`

## string_xrefs

- `0x1800af118`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800af20e`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800af10c`: `CreateEvent`
- `0x1800af0a0`: `[%p] Failed to get device service SAP for close command session`
- `0x1800af070`: `Wwan2SapCloseDeviceServiceCommandSession`
- `0x1800af0a9`: `Wwan2SapCloseDeviceServiceCommandSession`
- `0x1800af1cc`: `Wwan2SapCloseDeviceServiceCommandSession`
- `0x1800af231`: `Wwan2SapCloseDeviceServiceCommandSession`
- `0x1800af228`: `[%p] Failed to delete subscription for command session close. Error = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapCloseDeviceServiceCommandSession(
        struct WWAN_SAP *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        MessageParams *a4)
{
  struct _WWAN_DEVICE_SERVICES_SAP *DeviceServicesSap; // rax
  HANDLE EventW; // rax
  MessageParams *v11; // rbx
  DWORD LastError; // eax
  MessageParams *v13; // r14
  unsigned int v14; // edx
  DWORD v15; // eax
  HANDLE hHandle; // [rsp+30h] [rbp-18h] BYREF
  MessageParams *v17[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+90h] [rbp+48h] BYREF

  v18 = 0;
  if ( !a1 )
  {
    WwanLog::Error("Wwan2SapCloseDeviceServiceCommandSession", 0, L"[%p] Invalid parameters", 0);
    return 87;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  DeviceServicesSap = _wwan2SapGetDeviceServicesSap(a1, a2, 0);
  if ( !DeviceServicesSap )
  {
    WwanLog::Info(
      "Wwan2SapCloseDeviceServiceCommandSession",
      0,
      L"[%p] Failed to get device service SAP for close command session",
      a1);
    v18 = 12;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1);
    return v18;
  }
  ++*((_DWORD *)DeviceServicesSap + 8);
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&hHandle, EventW);
  v11 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x84Du, "CreateEvent", LastError);
  }
  v17[0] = (MessageParams *)operator new(0x48u);
  v13 = MessageParams::MessageParams(v17[0]);
  v17[0] = v11;
  std::vector<void *>::push_back((char *)v13 + 48, v17);
  v17[0] = (MessageParams *)&v18;
  std::vector<void *>::push_back((char *)v13 + 48, v17);
  v17[0] = a1;
  std::vector<void *>::push_back((char *)v13 + 48, v17);
  v17[0] = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v13 + 48, v17);
  v17[0] = (MessageParams *)a3;
  std::vector<void *>::push_back((char *)v13 + 48, v17);
  v17[0] = a4;
  std::vector<void *>::push_back((char *)v13 + 48, v17);
  if ( !(unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(28, v13) )
  {
    if ( WaitForSingleObject(v11, 0xFFFFFFFF) )
    {
      v15 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x862u, "WaitForSingleObject", v15);
    }
    if ( v18 )
      WwanLog::Error(
        "Wwan2SapCloseDeviceServiceCommandSession",
        0,
        L"[%p] Failed to delete subscription for command session close. Error = %d",
        a1,
        v18);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
    return v18;
  }
  if ( v13 )
    MessageParams::`scalar deleting destructor'(v13, v14);
  WwanLog::Error("Wwan2SapCloseDeviceServiceCommandSession", 0, L"Notification dispatcher: Failed to Queue Message");
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return 31;
}

```

## disassembly

```asm
0x1800af038  push    rbp
0x1800af03a  push    rbx
0x1800af03b  push    rsi
0x1800af03c  push    rdi
0x1800af03d  push    r12
0x1800af03f  push    r13
0x1800af041  push    r14
0x1800af043  push    r15
0x1800af045  mov     rbp, rsp
0x1800af048  sub     rsp, 48h
0x1800af04c  mov     r12, r9
0x1800af04f  mov     r13, r8
0x1800af052  mov     r15, rdx
0x1800af055  mov     rsi, rcx
0x1800af058  mov     [rbp+arg_0], 0
0x1800af05f  test    rcx, rcx
0x1800af062  jnz     short loc_1800AF084
0x1800af064  xor     r9d, r9d
0x1800af067  lea     r8, aPInvalidParame; "[%p] Invalid parameters"
0x1800af06e  xor     edx, edx; struct _GUID *
0x1800af070  lea     rcx, aWwan2sapclosed; "Wwan2SapCloseDeviceServiceCommandSessio"...
0x1800af077  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af07c  lea     eax, [rsi+57h]
0x1800af07f  jmp     loc_1800AF24A
0x1800af084  call    cs:__imp_EnterCriticalSection
0x1800af08a  xor     r8d, r8d; int
0x1800af08d  mov     rdx, r15; struct _GUID *
0x1800af090  mov     rcx, rsi; struct WWAN_SAP *
0x1800af093  call    ?_wwan2SapGetDeviceServicesSap@@YAPEAU_WWAN_DEVICE_SERVICES_SAP@@PEAUWWAN_SAP@@PEBU_GUID@@H@Z; _wwan2SapGetDeviceServicesSap(WWAN_SAP *,_GUID const *,int)
0x1800af098  test    rax, rax
0x1800af09b  jnz     short loc_1800AF0CA
0x1800af09d  mov     r9, rsi
0x1800af0a0  lea     r8, aPFailedToGetDe; "[%p] Failed to get device service SAP f"...
0x1800af0a7  xor     edx, edx; struct _GUID *
0x1800af0a9  lea     rcx, aWwan2sapclosed; "Wwan2SapCloseDeviceServiceCommandSessio"...
0x1800af0b0  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800af0b5  mov     [rbp+arg_0], 0Ch
0x1800af0bc  mov     rcx, rsi; lpCriticalSection
0x1800af0bf  call    cs:__imp_LeaveCriticalSection
0x1800af0c5  jmp     loc_1800AF247
0x1800af0ca  inc     dword ptr [rax+20h]
0x1800af0cd  mov     rcx, rsi; lpCriticalSection
0x1800af0d0  call    cs:__imp_LeaveCriticalSection
0x1800af0d6  xor     r9d, r9d; lpName
0x1800af0d9  xor     r8d, r8d; bInitialState
0x1800af0dc  lea     edx, [r9+1]; bManualReset
0x1800af0e0  xor     ecx, ecx; lpEventAttributes
0x1800af0e2  call    cs:__imp_CreateEventW
0x1800af0e8  mov     rdx, rax
0x1800af0eb  lea     rcx, [rbp+hHandle]
0x1800af0ef  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800af0f4  nop
0x1800af0f5  mov     rbx, [rbp+hHandle]
0x1800af0f9  lea     rax, [rbx+1]
0x1800af0fd  cmp     rax, 1
0x1800af101  ja      short loc_1800AF124
0x1800af103  call    cs:__imp_GetLastError
0x1800af109  mov     r9d, eax; unsigned int
0x1800af10c  lea     r8, aCreateevent; "CreateEvent"
0x1800af113  mov     edx, 84Dh; unsigned int
0x1800af118  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800af11f  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800af124  mov     ecx, 48h ; 'H'; Size
0x1800af129  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800af12e  mov     [rbp+var_10], rax
0x1800af132  mov     rcx, rax; this
0x1800af135  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800af13a  mov     r14, rax
0x1800af13d  lea     rdi, [rax+30h]
0x1800af141  mov     [rbp+var_10], rbx
0x1800af145  lea     rdx, [rbp+var_10]
0x1800af149  mov     rcx, rdi
0x1800af14c  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af151  lea     rax, [rbp+arg_0]
0x1800af155  mov     [rbp+var_10], rax
0x1800af159  lea     rdx, [rbp+var_10]
0x1800af15d  mov     rcx, rdi
0x1800af160  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af165  mov     [rbp+var_10], rsi
0x1800af169  lea     rdx, [rbp+var_10]
0x1800af16d  mov     rcx, rdi
0x1800af170  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af175  mov     [rbp+var_10], r15
0x1800af179  lea     rdx, [rbp+var_10]
0x1800af17d  mov     rcx, rdi
0x1800af180  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af185  mov     [rbp+var_10], r13
0x1800af189  lea     rdx, [rbp+var_10]
0x1800af18d  mov     rcx, rdi
0x1800af190  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af195  mov     [rbp+var_10], r12
0x1800af199  lea     rdx, [rbp+var_10]
0x1800af19d  mov     rcx, rdi
0x1800af1a0  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800af1a5  mov     rdx, r14
0x1800af1a8  mov     ecx, 1Ch
0x1800af1ad  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800af1b2  test    eax, eax
0x1800af1b4  jz      short loc_1800AF1E9
0x1800af1b6  test    r14, r14
0x1800af1b9  jz      short loc_1800AF1C3
0x1800af1bb  mov     rcx, r14; this
0x1800af1be  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800af1c3  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800af1ca  xor     edx, edx; struct _GUID *
0x1800af1cc  lea     rcx, aWwan2sapclosed; "Wwan2SapCloseDeviceServiceCommandSessio"...
0x1800af1d3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af1d8  nop
0x1800af1d9  lea     rcx, [rbp+hHandle]
0x1800af1dd  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800af1e2  mov     eax, 1Fh
0x1800af1e7  jmp     short loc_1800AF24A
0x1800af1e9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800af1ec  mov     rcx, rbx; hHandle
0x1800af1ef  call    cs:__imp_WaitForSingleObject
0x1800af1f5  test    eax, eax
0x1800af1f7  jz      short loc_1800AF21A
0x1800af1f9  call    cs:__imp_GetLastError
0x1800af1ff  mov     r9d, eax; unsigned int
0x1800af202  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800af209  mov     edx, 862h; unsigned int
0x1800af20e  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800af215  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800af21a  mov     eax, [rbp+arg_0]
0x1800af21d  test    eax, eax
0x1800af21f  jz      short loc_1800AF23E
0x1800af221  mov     [rsp+48h+var_28], eax
0x1800af225  mov     r9, rsi
0x1800af228  lea     r8, aPFailedToDelet; "[%p] Failed to delete subscription for "...
0x1800af22f  xor     edx, edx; struct _GUID *
0x1800af231  lea     rcx, aWwan2sapclosed; "Wwan2SapCloseDeviceServiceCommandSessio"...
0x1800af238  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af23d  nop
0x1800af23e  lea     rcx, [rbp+hHandle]
0x1800af242  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800af247  mov     eax, [rbp+arg_0]
0x1800af24a  add     rsp, 48h
0x1800af24e  pop     r15
0x1800af250  pop     r14
0x1800af252  pop     r13
0x1800af254  pop     r12
0x1800af256  pop     rdi
0x1800af257  pop     rsi
0x1800af258  pop     rbx
0x1800af259  pop     rbp
0x1800af25a  retn
```
