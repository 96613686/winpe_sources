# WwanSapGetProfileState(WWAN_SAP const *,_GUID const *,ushort const *,WWAN_PROFILE_STATE_TYPE *)

- ea: `0x1800b2a68`
- end: `0x1800b2bd5`
- name: `?WwanSapGetProfileState@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEBGPEAW4WWAN_PROFILE_STATE_TYPE@@@Z`
- size: `365`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, const unsigned __int16 *, enum WWAN_PROFILE_STATE_TYPE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ace30`

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
- `0x1800b2a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2b8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2b8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2a9a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2b97`

## string_xrefs

- `0x1800b2ad0`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2bac`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`

## pseudocode

```c
__int64 __fastcall WwanSapGetProfileState(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        MessageParams *a3,
        enum WWAN_PROFILE_STATE_TYPE *a4)
{
  HANDLE EventW; // rax
  MessageParams *v8; // rbx
  DWORD LastError; // eax
  MessageParams *v10; // rsi
  unsigned int v11; // edx
  unsigned int v12; // ebx
  DWORD v13; // eax
  unsigned int v15; // [rsp+60h] [rbp+40h] BYREF
  int v16; // [rsp+64h] [rbp+44h]
  HANDLE hHandle; // [rsp+68h] [rbp+48h] BYREF
  MessageParams *v18; // [rsp+70h] [rbp+50h] BYREF

  v16 = HIDWORD(a1);
  v15 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&hHandle, EventW);
  v8 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError(
      "onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c",
      0x4DCu,
      "Failure while creating an Event",
      LastError);
  }
  v18 = (MessageParams *)operator new(0x48u);
  v10 = MessageParams::MessageParams(v18);
  v18 = v8;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = (MessageParams *)&v15;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = a3;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = a4;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(21, v10) )
  {
    if ( v10 )
      MessageParams::`scalar deleting destructor'(v10, v11);
    WwanLog::Error("WwanSapGetProfileState", 0, L"Notification dispatcher: Failed to Queue Message");
    v12 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v8, 0xFFFFFFFF) )
    {
      v13 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x4F0u, "WaitForSingleObject", v13);
    }
    v12 = v15;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v12;
}

```

## disassembly

```asm
0x1800b2a68  mov     [rsp-38h+arg_0], rcx
0x1800b2a6d  push    rbp
0x1800b2a6e  push    rbx
0x1800b2a6f  push    rsi
0x1800b2a70  push    rdi
0x1800b2a71  push    r12
0x1800b2a73  push    r14
0x1800b2a75  push    r15
0x1800b2a77  mov     rbp, rsp
0x1800b2a7a  sub     rsp, 20h
0x1800b2a7e  mov     r14, r9
0x1800b2a81  mov     r15, r8
0x1800b2a84  mov     r12, rdx
0x1800b2a87  mov     dword ptr [rbp+arg_0], 0
0x1800b2a8e  xor     r9d, r9d; lpName
0x1800b2a91  xor     r8d, r8d; bInitialState
0x1800b2a94  lea     edx, [r9+1]; bManualReset
0x1800b2a98  xor     ecx, ecx; lpEventAttributes
0x1800b2a9a  call    cs:__imp_CreateEventW
0x1800b2aa0  mov     rdx, rax
0x1800b2aa3  lea     rcx, [rbp+hHandle]
0x1800b2aa7  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b2aac  nop
0x1800b2aad  mov     rbx, [rbp+hHandle]
0x1800b2ab1  lea     rax, [rbx+1]
0x1800b2ab5  cmp     rax, 1
0x1800b2ab9  ja      short loc_1800B2ADC
0x1800b2abb  call    cs:__imp_GetLastError
0x1800b2ac1  mov     r9d, eax; unsigned int
0x1800b2ac4  lea     r8, aFailureWhileCr; "Failure while creating an Event"
0x1800b2acb  mov     edx, 4DCh; unsigned int
0x1800b2ad0  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2ad7  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2adc  mov     ecx, 48h ; 'H'; Size
0x1800b2ae1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2ae6  mov     [rbp+arg_10], rax
0x1800b2aea  mov     rcx, rax; this
0x1800b2aed  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b2af2  mov     rsi, rax
0x1800b2af5  lea     rdi, [rax+30h]
0x1800b2af9  mov     [rbp+arg_10], rbx
0x1800b2afd  lea     rdx, [rbp+arg_10]
0x1800b2b01  mov     rcx, rdi
0x1800b2b04  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2b09  lea     rax, [rbp+arg_0]
0x1800b2b0d  mov     [rbp+arg_10], rax
0x1800b2b11  lea     rdx, [rbp+arg_10]
0x1800b2b15  mov     rcx, rdi
0x1800b2b18  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2b1d  mov     [rbp+arg_10], r12
0x1800b2b21  lea     rdx, [rbp+arg_10]
0x1800b2b25  mov     rcx, rdi
0x1800b2b28  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2b2d  mov     [rbp+arg_10], r15
0x1800b2b31  lea     rdx, [rbp+arg_10]
0x1800b2b35  mov     rcx, rdi
0x1800b2b38  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2b3d  mov     [rbp+arg_10], r14
0x1800b2b41  lea     rdx, [rbp+arg_10]
0x1800b2b45  mov     rcx, rdi
0x1800b2b48  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2b4d  mov     rdx, rsi
0x1800b2b50  mov     ecx, 15h
0x1800b2b55  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b2b5a  test    eax, eax
0x1800b2b5c  jz      short loc_1800B2B87
0x1800b2b5e  test    rsi, rsi
0x1800b2b61  jz      short loc_1800B2B6B
0x1800b2b63  mov     rcx, rsi; this
0x1800b2b66  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b2b6b  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b2b72  xor     edx, edx; struct _GUID *
0x1800b2b74  lea     rcx, aWwansapgetprof_2; "WwanSapGetProfileState"
0x1800b2b7b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b2b80  mov     ebx, 1Fh
0x1800b2b85  jmp     short loc_1800B2BBB
0x1800b2b87  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2b8a  mov     rcx, rbx; hHandle
0x1800b2b8d  call    cs:__imp_WaitForSingleObject
0x1800b2b93  test    eax, eax
0x1800b2b95  jz      short loc_1800B2BB8
0x1800b2b97  call    cs:__imp_GetLastError
0x1800b2b9d  mov     r9d, eax; unsigned int
0x1800b2ba0  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b2ba7  mov     edx, 4F0h; unsigned int
0x1800b2bac  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2bb3  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2bb8  mov     ebx, dword ptr [rbp+arg_0]
0x1800b2bbb  lea     rcx, [rbp+hHandle]
0x1800b2bbf  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b2bc4  mov     eax, ebx
0x1800b2bc6  add     rsp, 20h
0x1800b2bca  pop     r15
0x1800b2bcc  pop     r14
0x1800b2bce  pop     r12
0x1800b2bd0  pop     rdi
0x1800b2bd1  pop     rsi
0x1800b2bd2  pop     rbx
0x1800b2bd3  pop     rbp
0x1800b2bd4  retn
```
