# WwanSapSmsRead(WWAN_SAP const *,_GUID const *,_WWAN_SMS_READ *,ulong *,ulong *)

- ea: `0x1800b5184`
- end: `0x1800b5305`
- name: `?WwanSapSmsRead@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEAU_WWAN_SMS_READ@@PEAK3@Z`
- size: `385`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, struct _WWAN_SMS_READ *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ad840`

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
- `0x1800b5184`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b52bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b52bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b51b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b51b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b51d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b52c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b51d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b52c7`

## string_xrefs

- `0x1800b51ec`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b52dc`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b51e0`: `CreateEvent`
- `0x1800b52a4`: `WwanSapSmsRead`

## pseudocode

```c
__int64 __fastcall WwanSapSmsRead(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        struct _WWAN_SMS_READ *a3,
        MessageParams *a4,
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
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x384u, "CreateEvent", LastError);
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
  v19 = a4;
  std::vector<void *>::push_back((char *)v11 + 48, &v19);
  std::vector<void *>::push_back((char *)v11 + 48, &a5);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(10, v11) )
  {
    if ( v11 )
      MessageParams::`scalar deleting destructor'(v11, v12);
    WwanLog::Error("WwanSapSmsRead", 0, L"Notification dispatcher: Failed to Queue Message");
    v13 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v9, 0xFFFFFFFF) )
    {
      v14 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x399u, "WaitForSingleObject", v14);
    }
    v13 = v16;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v13;
}

```

## disassembly

```asm
0x1800b5184  mov     [rsp-38h+arg_0], rcx
0x1800b5189  push    rbp
0x1800b518a  push    rbx
0x1800b518b  push    rsi
0x1800b518c  push    rdi
0x1800b518d  push    r12
0x1800b518f  push    r14
0x1800b5191  push    r15
0x1800b5193  mov     rbp, rsp
0x1800b5196  sub     rsp, 20h
0x1800b519a  mov     r14, r9
0x1800b519d  mov     r15, r8
0x1800b51a0  mov     r12, rdx
0x1800b51a3  mov     dword ptr [rbp+arg_0], 0
0x1800b51aa  xor     r9d, r9d; lpName
0x1800b51ad  xor     r8d, r8d; bInitialState
0x1800b51b0  lea     edx, [r9+1]; bManualReset
0x1800b51b4  xor     ecx, ecx; lpEventAttributes
0x1800b51b6  call    cs:__imp_CreateEventW
0x1800b51bc  mov     rdx, rax
0x1800b51bf  lea     rcx, [rbp+hHandle]
0x1800b51c3  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b51c8  nop
0x1800b51c9  mov     rbx, [rbp+hHandle]
0x1800b51cd  lea     rax, [rbx+1]
0x1800b51d1  cmp     rax, 1
0x1800b51d5  ja      short loc_1800B51F8
0x1800b51d7  call    cs:__imp_GetLastError
0x1800b51dd  mov     r9d, eax; unsigned int
0x1800b51e0  lea     r8, aCreateevent; "CreateEvent"
0x1800b51e7  mov     edx, 384h; unsigned int
0x1800b51ec  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b51f3  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b51f8  mov     ecx, 48h ; 'H'; Size
0x1800b51fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b5202  mov     [rbp+arg_10], rax
0x1800b5206  mov     rcx, rax; this
0x1800b5209  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b520e  mov     rsi, rax
0x1800b5211  lea     rdi, [rax+30h]
0x1800b5215  mov     [rbp+arg_10], rbx
0x1800b5219  lea     rdx, [rbp+arg_10]
0x1800b521d  mov     rcx, rdi
0x1800b5220  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b5225  lea     rax, [rbp+arg_0]
0x1800b5229  mov     [rbp+arg_10], rax
0x1800b522d  lea     rdx, [rbp+arg_10]
0x1800b5231  mov     rcx, rdi
0x1800b5234  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b5239  mov     [rbp+arg_10], r12
0x1800b523d  lea     rdx, [rbp+arg_10]
0x1800b5241  mov     rcx, rdi
0x1800b5244  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b5249  mov     [rbp+arg_10], r15
0x1800b524d  lea     rdx, [rbp+arg_10]
0x1800b5251  mov     rcx, rdi
0x1800b5254  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b5259  mov     [rbp+arg_10], r14
0x1800b525d  lea     rdx, [rbp+arg_10]
0x1800b5261  mov     rcx, rdi
0x1800b5264  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b5269  mov     rax, [rbp+arg_20]
0x1800b526d  mov     [rbp+arg_20], rax
0x1800b5271  lea     rdx, [rbp+arg_20]
0x1800b5275  mov     rcx, rdi
0x1800b5278  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b527d  mov     rdx, rsi
0x1800b5280  mov     ecx, 0Ah
0x1800b5285  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b528a  test    eax, eax
0x1800b528c  jz      short loc_1800B52B7
0x1800b528e  test    rsi, rsi
0x1800b5291  jz      short loc_1800B529B
0x1800b5293  mov     rcx, rsi; this
0x1800b5296  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b529b  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b52a2  xor     edx, edx; struct _GUID *
0x1800b52a4  lea     rcx, aWwansapsmsread; "WwanSapSmsRead"
0x1800b52ab  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b52b0  mov     ebx, 1Fh
0x1800b52b5  jmp     short loc_1800B52EB
0x1800b52b7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b52ba  mov     rcx, rbx; hHandle
0x1800b52bd  call    cs:__imp_WaitForSingleObject
0x1800b52c3  test    eax, eax
0x1800b52c5  jz      short loc_1800B52E8
0x1800b52c7  call    cs:__imp_GetLastError
0x1800b52cd  mov     r9d, eax; unsigned int
0x1800b52d0  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b52d7  mov     edx, 399h; unsigned int
0x1800b52dc  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b52e3  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b52e8  mov     ebx, dword ptr [rbp+arg_0]
0x1800b52eb  lea     rcx, [rbp+hHandle]
0x1800b52ef  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b52f4  mov     eax, ebx
0x1800b52f6  add     rsp, 20h
0x1800b52fa  pop     r15
0x1800b52fc  pop     r14
0x1800b52fe  pop     r12
0x1800b5300  pop     rdi
0x1800b5301  pop     rsi
0x1800b5302  pop     rbx
0x1800b5303  pop     rbp
0x1800b5304  retn
```
