# WwanSapGetProfileListByPurpose(WWAN_SAP const *,_GUID const *,_GUID const *,WWAN_PROFILE_INFO_LIST * *)

- ea: `0x1800b26a8`
- end: `0x1800b2815`
- name: `?WwanSapGetProfileListByPurpose@@YAKPEBUWWAN_SAP@@PEBU_GUID@@1PEAPEAUWWAN_PROFILE_INFO_LIST@@@Z`
- size: `365`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, const struct _GUID *, struct WWAN_PROFILE_INFO_LIST **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800acd00`

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
- `0x1800b26a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b27cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b27cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b26da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b26da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b26fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b27d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b26fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b27d7`

## string_xrefs

- `0x1800b2710`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b27ec`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2704`: `CreateEvent`

## pseudocode

```c
__int64 __fastcall WwanSapGetProfileListByPurpose(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        struct WWAN_PROFILE_INFO_LIST **a4)
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
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x497u, "CreateEvent", LastError);
  }
  v18 = (MessageParams *)operator new(0x48u);
  v10 = MessageParams::MessageParams(v18);
  v18 = v8;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = (MessageParams *)&v15;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = (MessageParams *)a3;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = (MessageParams *)a4;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(17, v10) )
  {
    if ( v10 )
      MessageParams::`scalar deleting destructor'(v10, v11);
    WwanLog::Error("WwanSapGetProfileListByPurpose", 0, L"Notification dispatcher: Failed to Queue Message");
    v12 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v8, 0xFFFFFFFF) )
    {
      v13 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x4ABu, "WaitForSingleObject", v13);
    }
    v12 = v15;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v12;
}

```

## disassembly

```asm
0x1800b26a8  mov     [rsp-38h+arg_0], rcx
0x1800b26ad  push    rbp
0x1800b26ae  push    rbx
0x1800b26af  push    rsi
0x1800b26b0  push    rdi
0x1800b26b1  push    r12
0x1800b26b3  push    r14
0x1800b26b5  push    r15
0x1800b26b7  mov     rbp, rsp
0x1800b26ba  sub     rsp, 20h
0x1800b26be  mov     r14, r9
0x1800b26c1  mov     r15, r8
0x1800b26c4  mov     r12, rdx
0x1800b26c7  mov     dword ptr [rbp+arg_0], 0
0x1800b26ce  xor     r9d, r9d; lpName
0x1800b26d1  xor     r8d, r8d; bInitialState
0x1800b26d4  lea     edx, [r9+1]; bManualReset
0x1800b26d8  xor     ecx, ecx; lpEventAttributes
0x1800b26da  call    cs:__imp_CreateEventW
0x1800b26e0  mov     rdx, rax
0x1800b26e3  lea     rcx, [rbp+hHandle]
0x1800b26e7  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b26ec  nop
0x1800b26ed  mov     rbx, [rbp+hHandle]
0x1800b26f1  lea     rax, [rbx+1]
0x1800b26f5  cmp     rax, 1
0x1800b26f9  ja      short loc_1800B271C
0x1800b26fb  call    cs:__imp_GetLastError
0x1800b2701  mov     r9d, eax; unsigned int
0x1800b2704  lea     r8, aCreateevent; "CreateEvent"
0x1800b270b  mov     edx, 497h; unsigned int
0x1800b2710  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2717  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b271c  mov     ecx, 48h ; 'H'; Size
0x1800b2721  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2726  mov     [rbp+arg_10], rax
0x1800b272a  mov     rcx, rax; this
0x1800b272d  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b2732  mov     rsi, rax
0x1800b2735  lea     rdi, [rax+30h]
0x1800b2739  mov     [rbp+arg_10], rbx
0x1800b273d  lea     rdx, [rbp+arg_10]
0x1800b2741  mov     rcx, rdi
0x1800b2744  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2749  lea     rax, [rbp+arg_0]
0x1800b274d  mov     [rbp+arg_10], rax
0x1800b2751  lea     rdx, [rbp+arg_10]
0x1800b2755  mov     rcx, rdi
0x1800b2758  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b275d  mov     [rbp+arg_10], r12
0x1800b2761  lea     rdx, [rbp+arg_10]
0x1800b2765  mov     rcx, rdi
0x1800b2768  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b276d  mov     [rbp+arg_10], r15
0x1800b2771  lea     rdx, [rbp+arg_10]
0x1800b2775  mov     rcx, rdi
0x1800b2778  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b277d  mov     [rbp+arg_10], r14
0x1800b2781  lea     rdx, [rbp+arg_10]
0x1800b2785  mov     rcx, rdi
0x1800b2788  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b278d  mov     rdx, rsi
0x1800b2790  mov     ecx, 11h
0x1800b2795  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b279a  test    eax, eax
0x1800b279c  jz      short loc_1800B27C7
0x1800b279e  test    rsi, rsi
0x1800b27a1  jz      short loc_1800B27AB
0x1800b27a3  mov     rcx, rsi; this
0x1800b27a6  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b27ab  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b27b2  xor     edx, edx; struct _GUID *
0x1800b27b4  lea     rcx, aWwansapgetprof_3; "WwanSapGetProfileListByPurpose"
0x1800b27bb  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b27c0  mov     ebx, 1Fh
0x1800b27c5  jmp     short loc_1800B27FB
0x1800b27c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b27ca  mov     rcx, rbx; hHandle
0x1800b27cd  call    cs:__imp_WaitForSingleObject
0x1800b27d3  test    eax, eax
0x1800b27d5  jz      short loc_1800B27F8
0x1800b27d7  call    cs:__imp_GetLastError
0x1800b27dd  mov     r9d, eax; unsigned int
0x1800b27e0  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b27e7  mov     edx, 4ABh; unsigned int
0x1800b27ec  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b27f3  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b27f8  mov     ebx, dword ptr [rbp+arg_0]
0x1800b27fb  lea     rcx, [rbp+hHandle]
0x1800b27ff  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b2804  mov     eax, ebx
0x1800b2806  add     rsp, 20h
0x1800b280a  pop     r15
0x1800b280c  pop     r14
0x1800b280e  pop     r12
0x1800b2810  pop     rdi
0x1800b2811  pop     rsi
0x1800b2812  pop     rbx
0x1800b2813  pop     rbp
0x1800b2814  retn
```
