# WwanSapGetProfileList(WWAN_SAP const *,_GUID const *,WWAN_PROFILE_INFO_LIST * *)

- ea: `0x1800b2544`
- end: `0x1800b26a2`
- name: `?WwanSapGetProfileList@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEAPEAUWWAN_PROFILE_INFO_LIST@@@Z`
- size: `350`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, struct WWAN_PROFILE_INFO_LIST **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800accb0`

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
- `0x1800b2544`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2658`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2658`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2575`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2662`

## string_xrefs

- `0x1800b25ab`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2677`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b259f`: `CreateEvent`

## pseudocode

```c
__int64 __fastcall WwanSapGetProfileList(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        struct WWAN_PROFILE_INFO_LIST **a3)
{
  HANDLE EventW; // rax
  MessageParams *v6; // rbx
  DWORD LastError; // eax
  MessageParams *v8; // rsi
  unsigned int v9; // edx
  unsigned int v10; // ebx
  DWORD v11; // eax
  unsigned int v13; // [rsp+50h] [rbp+30h] BYREF
  int v14; // [rsp+54h] [rbp+34h]
  HANDLE hHandle; // [rsp+58h] [rbp+38h] BYREF
  MessageParams *v16; // [rsp+60h] [rbp+40h] BYREF

  v14 = HIDWORD(a1);
  v13 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&hHandle, EventW);
  v6 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x475u, "CreateEvent", LastError);
  }
  v16 = (MessageParams *)operator new(0x48u);
  v8 = MessageParams::MessageParams(v16);
  v16 = v6;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)&v13;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)a3;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(16, v8) )
  {
    if ( v8 )
      MessageParams::`scalar deleting destructor'(v8, v9);
    WwanLog::Error("WwanSapGetProfileList", 0, L"Notification dispatcher: Failed to Queue Message");
    v10 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v6, 0xFFFFFFFF) )
    {
      v11 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x488u, "WaitForSingleObject", v11);
    }
    v10 = v13;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v10;
}

```

## disassembly

```asm
0x1800b2544  mov     [rsp-28h+arg_18], rbx
0x1800b2549  mov     [rsp-28h+arg_0], rcx
0x1800b254e  push    rbp
0x1800b254f  push    rsi
0x1800b2550  push    rdi
0x1800b2551  push    r14
0x1800b2553  push    r15
0x1800b2555  mov     rbp, rsp
0x1800b2558  sub     rsp, 20h
0x1800b255c  mov     r14, r8
0x1800b255f  mov     r15, rdx
0x1800b2562  mov     dword ptr [rbp+arg_0], 0
0x1800b2569  xor     r9d, r9d; lpName
0x1800b256c  xor     r8d, r8d; bInitialState
0x1800b256f  lea     edx, [r9+1]; bManualReset
0x1800b2573  xor     ecx, ecx; lpEventAttributes
0x1800b2575  call    cs:__imp_CreateEventW
0x1800b257b  mov     rdx, rax
0x1800b257e  lea     rcx, [rbp+hHandle]
0x1800b2582  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b2587  nop
0x1800b2588  mov     rbx, [rbp+hHandle]
0x1800b258c  lea     rax, [rbx+1]
0x1800b2590  cmp     rax, 1
0x1800b2594  ja      short loc_1800B25B7
0x1800b2596  call    cs:__imp_GetLastError
0x1800b259c  mov     r9d, eax; unsigned int
0x1800b259f  lea     r8, aCreateevent; "CreateEvent"
0x1800b25a6  mov     edx, 475h; unsigned int
0x1800b25ab  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b25b2  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b25b7  mov     ecx, 48h ; 'H'; Size
0x1800b25bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b25c1  mov     [rbp+arg_10], rax
0x1800b25c5  mov     rcx, rax; this
0x1800b25c8  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b25cd  mov     rsi, rax
0x1800b25d0  lea     rdi, [rax+30h]
0x1800b25d4  mov     [rbp+arg_10], rbx
0x1800b25d8  lea     rdx, [rbp+arg_10]
0x1800b25dc  mov     rcx, rdi
0x1800b25df  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b25e4  lea     rax, [rbp+arg_0]
0x1800b25e8  mov     [rbp+arg_10], rax
0x1800b25ec  lea     rdx, [rbp+arg_10]
0x1800b25f0  mov     rcx, rdi
0x1800b25f3  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b25f8  mov     [rbp+arg_10], r15
0x1800b25fc  lea     rdx, [rbp+arg_10]
0x1800b2600  mov     rcx, rdi
0x1800b2603  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2608  mov     [rbp+arg_10], r14
0x1800b260c  lea     rdx, [rbp+arg_10]
0x1800b2610  mov     rcx, rdi
0x1800b2613  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2618  mov     rdx, rsi
0x1800b261b  mov     ecx, 10h
0x1800b2620  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b2625  test    eax, eax
0x1800b2627  jz      short loc_1800B2652
0x1800b2629  test    rsi, rsi
0x1800b262c  jz      short loc_1800B2636
0x1800b262e  mov     rcx, rsi; this
0x1800b2631  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b2636  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b263d  xor     edx, edx; struct _GUID *
0x1800b263f  lea     rcx, aWwansapgetprof_5; "WwanSapGetProfileList"
0x1800b2646  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b264b  mov     ebx, 1Fh
0x1800b2650  jmp     short loc_1800B2686
0x1800b2652  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2655  mov     rcx, rbx; hHandle
0x1800b2658  call    cs:__imp_WaitForSingleObject
0x1800b265e  test    eax, eax
0x1800b2660  jz      short loc_1800B2683
0x1800b2662  call    cs:__imp_GetLastError
0x1800b2668  mov     r9d, eax; unsigned int
0x1800b266b  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b2672  mov     edx, 488h; unsigned int
0x1800b2677  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b267e  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2683  mov     ebx, dword ptr [rbp+arg_0]
0x1800b2686  lea     rcx, [rbp+hHandle]
0x1800b268a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b268f  mov     eax, ebx
0x1800b2691  mov     rbx, [rsp+20h+arg_18]
0x1800b2696  add     rsp, 20h
0x1800b269a  pop     r15
0x1800b269c  pop     r14
0x1800b269e  pop     rdi
0x1800b269f  pop     rsi
0x1800b26a0  pop     rbp
0x1800b26a1  retn
```
