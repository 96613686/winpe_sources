# WwanSapActivateNotification(WWAN_SAP const *,ushort const *)

- ea: `0x1800b0b5c`
- end: `0x1800b0c9b`
- name: `?WwanSapActivateNotification@@YAKPEBUWWAN_SAP@@PEBG@Z`
- size: `319`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ac3f0`

## callees

- `0x180008abc`
- `0x180010e94`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x18007289c`
- `0x18007cb94`
- `0x1800893b4`
- `0x1800b0b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0c57`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0c57`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0b84`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0c61`

## string_xrefs

- `0x1800b0bba`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b0c76`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b0bae`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapActivateNotification(const struct WWAN_SAP *a1, MessageParams *a2)
{
  HANDLE EventW; // rax
  MessageParams *v4; // rbx
  DWORD LastError; // eax
  MessageParams *v6; // rsi
  unsigned int v7; // edx
  unsigned int v8; // ebx
  DWORD v9; // eax
  unsigned int v11; // [rsp+50h] [rbp+30h] BYREF
  int v12; // [rsp+54h] [rbp+34h]
  HANDLE hHandle; // [rsp+58h] [rbp+38h] BYREF
  MessageParams *v14; // [rsp+60h] [rbp+40h] BYREF

  v12 = HIDWORD(a1);
  v11 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&hHandle, EventW);
  v4 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xC06u, "CreateEvent", LastError);
  }
  v14 = (MessageParams *)operator new(0x48u);
  v6 = MessageParams::MessageParams(v14);
  v14 = v4;
  std::vector<void *>::push_back((char *)v6 + 48, &v14);
  v14 = (MessageParams *)&v11;
  std::vector<void *>::push_back((char *)v6 + 48, &v14);
  v14 = a2;
  std::vector<void *>::push_back((char *)v6 + 48, &v14);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(50, v6) )
  {
    if ( v6 )
      MessageParams::`scalar deleting destructor'(v6, v7);
    WwanLog::Error("WwanSapActivateNotification", 0, L"Notification dispatcher: Failed to Queue Message");
    v8 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v4, 0xFFFFFFFF) )
    {
      v9 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xC18u, "WaitForSingleObject", v9);
    }
    v8 = v11;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v8;
}

```

## disassembly

```asm
0x1800b0b5c  mov     [rsp-28h+arg_0], rcx
0x1800b0b61  push    rbp
0x1800b0b62  push    rbx
0x1800b0b63  push    rsi
0x1800b0b64  push    rdi
0x1800b0b65  push    r14
0x1800b0b67  mov     rbp, rsp
0x1800b0b6a  sub     rsp, 20h
0x1800b0b6e  mov     r14, rdx
0x1800b0b71  mov     dword ptr [rbp+arg_0], 0
0x1800b0b78  xor     r9d, r9d; lpName
0x1800b0b7b  xor     r8d, r8d; bInitialState
0x1800b0b7e  lea     edx, [r9+1]; bManualReset
0x1800b0b82  xor     ecx, ecx; lpEventAttributes
0x1800b0b84  call    cs:__imp_CreateEventW
0x1800b0b8a  mov     rdx, rax
0x1800b0b8d  lea     rcx, [rbp+hHandle]
0x1800b0b91  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b0b96  nop
0x1800b0b97  mov     rbx, [rbp+hHandle]
0x1800b0b9b  lea     rax, [rbx+1]
0x1800b0b9f  cmp     rax, 1
0x1800b0ba3  ja      short loc_1800B0BC6
0x1800b0ba5  call    cs:__imp_GetLastError
0x1800b0bab  mov     r9d, eax; unsigned int
0x1800b0bae  lea     r8, aCreateevent; "CreateEvent"
0x1800b0bb5  mov     edx, 0C06h; unsigned int
0x1800b0bba  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b0bc1  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0bc6  mov     ecx, 48h ; 'H'; Size
0x1800b0bcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b0bd0  mov     [rbp+arg_10], rax
0x1800b0bd4  mov     rcx, rax; this
0x1800b0bd7  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b0bdc  mov     rsi, rax
0x1800b0bdf  lea     rdi, [rax+30h]
0x1800b0be3  mov     [rbp+arg_10], rbx
0x1800b0be7  lea     rdx, [rbp+arg_10]
0x1800b0beb  mov     rcx, rdi
0x1800b0bee  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b0bf3  lea     rax, [rbp+arg_0]
0x1800b0bf7  mov     [rbp+arg_10], rax
0x1800b0bfb  lea     rdx, [rbp+arg_10]
0x1800b0bff  mov     rcx, rdi
0x1800b0c02  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b0c07  mov     [rbp+arg_10], r14
0x1800b0c0b  lea     rdx, [rbp+arg_10]
0x1800b0c0f  mov     rcx, rdi
0x1800b0c12  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b0c17  mov     rdx, rsi
0x1800b0c1a  mov     ecx, 32h ; '2'
0x1800b0c1f  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b0c24  test    eax, eax
0x1800b0c26  jz      short loc_1800B0C51
0x1800b0c28  test    rsi, rsi
0x1800b0c2b  jz      short loc_1800B0C35
0x1800b0c2d  mov     rcx, rsi; this
0x1800b0c30  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b0c35  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b0c3c  xor     edx, edx; struct _GUID *
0x1800b0c3e  lea     rcx, aWwansapactivat; "WwanSapActivateNotification"
0x1800b0c45  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b0c4a  mov     ebx, 1Fh
0x1800b0c4f  jmp     short loc_1800B0C85
0x1800b0c51  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b0c54  mov     rcx, rbx; hHandle
0x1800b0c57  call    cs:__imp_WaitForSingleObject
0x1800b0c5d  test    eax, eax
0x1800b0c5f  jz      short loc_1800B0C82
0x1800b0c61  call    cs:__imp_GetLastError
0x1800b0c67  mov     r9d, eax; unsigned int
0x1800b0c6a  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b0c71  mov     edx, 0C18h; unsigned int
0x1800b0c76  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b0c7d  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0c82  mov     ebx, dword ptr [rbp+arg_0]
0x1800b0c85  lea     rcx, [rbp+hHandle]
0x1800b0c89  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b0c8e  mov     eax, ebx
0x1800b0c90  add     rsp, 20h
0x1800b0c94  pop     r14
0x1800b0c96  pop     rdi
0x1800b0c97  pop     rsi
0x1800b0c98  pop     rbx
0x1800b0c99  pop     rbp
0x1800b0c9a  retn
```
