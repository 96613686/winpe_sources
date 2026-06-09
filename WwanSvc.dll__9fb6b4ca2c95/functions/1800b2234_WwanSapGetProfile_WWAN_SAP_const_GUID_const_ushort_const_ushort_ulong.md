# WwanSapGetProfile(WWAN_SAP const *,_GUID const *,ushort const *,ushort * *,ulong *)

- ea: `0x1800b2234`
- end: `0x1800b23b5`
- name: `?WwanSapGetProfile@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEBGPEAPEAGPEAK@Z`
- size: `385`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ac9b0`
- `0x1800aca10`

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
- `0x1800b2234`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b236d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b236d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2266`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2377`

## string_xrefs

- `0x1800b229c`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b238c`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2290`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapGetProfile(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        MessageParams *a3,
        unsigned __int16 **a4,
        unsigned int *a5)
{
  HANDLE EventW; // rax
  MessageParams *v9; // rbx
  DWORD LastError; // eax
  MessageParams *v11; // rsi
  unsigned int v12; // edx
  unsigned int v13; // ebx
  DWORD v14; // eax
  unsigned int v16; // [rsp+60h] [rbp+40h] BYREF
  int v17; // [rsp+64h] [rbp+44h]
  HANDLE hHandle; // [rsp+68h] [rbp+48h] BYREF
  MessageParams *v19; // [rsp+70h] [rbp+50h] BYREF

  v17 = HIDWORD(a1);
  v16 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&hHandle, EventW);
  v9 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x452u, "CreateEvent", LastError);
  }
  v19 = (MessageParams *)operator new(0x48u);
  v11 = MessageParams::MessageParams(v19);
  v19 = v9;
  std::vector<void *>::push_back((char *)v11 + 48, &v19);
  v19 = (MessageParams *)&v16;
  std::vector<void *>::push_back((char *)v11 + 48, &v19);
  v19 = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v11 + 48, &v19);
  v19 = a3;
  std::vector<void *>::push_back((char *)v11 + 48, &v19);
  v19 = (MessageParams *)a4;
  std::vector<void *>::push_back((char *)v11 + 48, &v19);
  std::vector<void *>::push_back((char *)v11 + 48, &a5);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(15, v11) )
  {
    if ( v11 )
      MessageParams::`scalar deleting destructor'(v11, v12);
    WwanLog::Error("WwanSapGetProfile", 0, L"Notification dispatcher: Failed to Queue Message");
    v13 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v9, 0xFFFFFFFF) )
    {
      v14 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x467u, "WaitForSingleObject", v14);
    }
    v13 = v16;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v13;
}

```

## disassembly

```asm
0x1800b2234  mov     [rsp-38h+arg_0], rcx
0x1800b2239  push    rbp
0x1800b223a  push    rbx
0x1800b223b  push    rsi
0x1800b223c  push    rdi
0x1800b223d  push    r12
0x1800b223f  push    r14
0x1800b2241  push    r15
0x1800b2243  mov     rbp, rsp
0x1800b2246  sub     rsp, 20h
0x1800b224a  mov     r14, r9
0x1800b224d  mov     r15, r8
0x1800b2250  mov     r12, rdx
0x1800b2253  mov     dword ptr [rbp+arg_0], 0
0x1800b225a  xor     r9d, r9d; lpName
0x1800b225d  xor     r8d, r8d; bInitialState
0x1800b2260  lea     edx, [r9+1]; bManualReset
0x1800b2264  xor     ecx, ecx; lpEventAttributes
0x1800b2266  call    cs:__imp_CreateEventW
0x1800b226c  mov     rdx, rax
0x1800b226f  lea     rcx, [rbp+hHandle]
0x1800b2273  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b2278  nop
0x1800b2279  mov     rbx, [rbp+hHandle]
0x1800b227d  lea     rax, [rbx+1]
0x1800b2281  cmp     rax, 1
0x1800b2285  ja      short loc_1800B22A8
0x1800b2287  call    cs:__imp_GetLastError
0x1800b228d  mov     r9d, eax; unsigned int
0x1800b2290  lea     r8, aCreateevent; "CreateEvent"
0x1800b2297  mov     edx, 452h; unsigned int
0x1800b229c  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b22a3  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b22a8  mov     ecx, 48h ; 'H'; Size
0x1800b22ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b22b2  mov     [rbp+arg_10], rax
0x1800b22b6  mov     rcx, rax; this
0x1800b22b9  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b22be  mov     rsi, rax
0x1800b22c1  lea     rdi, [rax+30h]
0x1800b22c5  mov     [rbp+arg_10], rbx
0x1800b22c9  lea     rdx, [rbp+arg_10]
0x1800b22cd  mov     rcx, rdi
0x1800b22d0  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b22d5  lea     rax, [rbp+arg_0]
0x1800b22d9  mov     [rbp+arg_10], rax
0x1800b22dd  lea     rdx, [rbp+arg_10]
0x1800b22e1  mov     rcx, rdi
0x1800b22e4  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b22e9  mov     [rbp+arg_10], r12
0x1800b22ed  lea     rdx, [rbp+arg_10]
0x1800b22f1  mov     rcx, rdi
0x1800b22f4  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b22f9  mov     [rbp+arg_10], r15
0x1800b22fd  lea     rdx, [rbp+arg_10]
0x1800b2301  mov     rcx, rdi
0x1800b2304  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2309  mov     [rbp+arg_10], r14
0x1800b230d  lea     rdx, [rbp+arg_10]
0x1800b2311  mov     rcx, rdi
0x1800b2314  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2319  mov     rax, [rbp+arg_20]
0x1800b231d  mov     [rbp+arg_20], rax
0x1800b2321  lea     rdx, [rbp+arg_20]
0x1800b2325  mov     rcx, rdi
0x1800b2328  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b232d  mov     rdx, rsi
0x1800b2330  mov     ecx, 0Fh
0x1800b2335  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b233a  test    eax, eax
0x1800b233c  jz      short loc_1800B2367
0x1800b233e  test    rsi, rsi
0x1800b2341  jz      short loc_1800B234B
0x1800b2343  mov     rcx, rsi; this
0x1800b2346  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b234b  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b2352  xor     edx, edx; struct _GUID *
0x1800b2354  lea     rcx, aWwansapgetprof; "WwanSapGetProfile"
0x1800b235b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b2360  mov     ebx, 1Fh
0x1800b2365  jmp     short loc_1800B239B
0x1800b2367  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b236a  mov     rcx, rbx; hHandle
0x1800b236d  call    cs:__imp_WaitForSingleObject
0x1800b2373  test    eax, eax
0x1800b2375  jz      short loc_1800B2398
0x1800b2377  call    cs:__imp_GetLastError
0x1800b237d  mov     r9d, eax; unsigned int
0x1800b2380  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b2387  mov     edx, 467h; unsigned int
0x1800b238c  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2393  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2398  mov     ebx, dword ptr [rbp+arg_0]
0x1800b239b  lea     rcx, [rbp+hHandle]
0x1800b239f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b23a4  mov     eax, ebx
0x1800b23a6  add     rsp, 20h
0x1800b23aa  pop     r15
0x1800b23ac  pop     r14
0x1800b23ae  pop     r12
0x1800b23b0  pop     rdi
0x1800b23b1  pop     rsi
0x1800b23b2  pop     rbx
0x1800b23b3  pop     rbp
0x1800b23b4  retn
```
