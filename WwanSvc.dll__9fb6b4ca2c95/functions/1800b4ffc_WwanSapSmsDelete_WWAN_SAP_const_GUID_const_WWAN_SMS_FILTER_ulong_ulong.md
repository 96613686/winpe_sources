# WwanSapSmsDelete(WWAN_SAP const *,_GUID const *,_WWAN_SMS_FILTER *,ulong *,ulong *)

- ea: `0x1800b4ffc`
- end: `0x1800b517d`
- name: `?WwanSapSmsDelete@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEAU_WWAN_SMS_FILTER@@PEAK3@Z`
- size: `385`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, struct _WWAN_SMS_FILTER *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ad7e0`

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
- `0x1800b4ffc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b5135`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b5135`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b502e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b502e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b504f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b513f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b504f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b513f`

## string_xrefs

- `0x1800b5064`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5154`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5058`: `CreateEvent`
- `0x1800b511c`: `WwanSapSmsDelete`

## pseudocode

```c
__int64 __fastcall WwanSapSmsDelete(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        struct _WWAN_SMS_FILTER *a3,
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
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x3D8u, "CreateEvent", LastError);
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
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(12, v11) )
  {
    if ( v11 )
      MessageParams::`scalar deleting destructor'(v11, v12);
    WwanLog::Error("WwanSapSmsDelete", 0, L"Notification dispatcher: Failed to Queue Message");
    v13 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v9, 0xFFFFFFFF) )
    {
      v14 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x3EDu, "WaitForSingleObject", v14);
    }
    v13 = v16;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v13;
}

```

## disassembly

```asm
0x1800b4ffc  mov     [rsp-38h+arg_0], rcx
0x1800b5001  push    rbp
0x1800b5002  push    rbx
0x1800b5003  push    rsi
0x1800b5004  push    rdi
0x1800b5005  push    r12
0x1800b5007  push    r14
0x1800b5009  push    r15
0x1800b500b  mov     rbp, rsp
0x1800b500e  sub     rsp, 20h
0x1800b5012  mov     r14, r9
0x1800b5015  mov     r15, r8
0x1800b5018  mov     r12, rdx
0x1800b501b  mov     dword ptr [rbp+arg_0], 0
0x1800b5022  xor     r9d, r9d; lpName
0x1800b5025  xor     r8d, r8d; bInitialState
0x1800b5028  lea     edx, [r9+1]; bManualReset
0x1800b502c  xor     ecx, ecx; lpEventAttributes
0x1800b502e  call    cs:__imp_CreateEventW
0x1800b5034  mov     rdx, rax
0x1800b5037  lea     rcx, [rbp+hHandle]
0x1800b503b  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b5040  nop
0x1800b5041  mov     rbx, [rbp+hHandle]
0x1800b5045  lea     rax, [rbx+1]
0x1800b5049  cmp     rax, 1
0x1800b504d  ja      short loc_1800B5070
0x1800b504f  call    cs:__imp_GetLastError
0x1800b5055  mov     r9d, eax; unsigned int
0x1800b5058  lea     r8, aCreateevent; "CreateEvent"
0x1800b505f  mov     edx, 3D8h; unsigned int
0x1800b5064  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b506b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5070  mov     ecx, 48h ; 'H'; Size
0x1800b5075  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b507a  mov     [rbp+arg_10], rax
0x1800b507e  mov     rcx, rax; this
0x1800b5081  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b5086  mov     rsi, rax
0x1800b5089  lea     rdi, [rax+30h]
0x1800b508d  mov     [rbp+arg_10], rbx
0x1800b5091  lea     rdx, [rbp+arg_10]
0x1800b5095  mov     rcx, rdi
0x1800b5098  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b509d  lea     rax, [rbp+arg_0]
0x1800b50a1  mov     [rbp+arg_10], rax
0x1800b50a5  lea     rdx, [rbp+arg_10]
0x1800b50a9  mov     rcx, rdi
0x1800b50ac  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b50b1  mov     [rbp+arg_10], r12
0x1800b50b5  lea     rdx, [rbp+arg_10]
0x1800b50b9  mov     rcx, rdi
0x1800b50bc  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b50c1  mov     [rbp+arg_10], r15
0x1800b50c5  lea     rdx, [rbp+arg_10]
0x1800b50c9  mov     rcx, rdi
0x1800b50cc  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b50d1  mov     [rbp+arg_10], r14
0x1800b50d5  lea     rdx, [rbp+arg_10]
0x1800b50d9  mov     rcx, rdi
0x1800b50dc  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b50e1  mov     rax, [rbp+arg_20]
0x1800b50e5  mov     [rbp+arg_20], rax
0x1800b50e9  lea     rdx, [rbp+arg_20]
0x1800b50ed  mov     rcx, rdi
0x1800b50f0  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b50f5  mov     rdx, rsi
0x1800b50f8  mov     ecx, 0Ch
0x1800b50fd  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b5102  test    eax, eax
0x1800b5104  jz      short loc_1800B512F
0x1800b5106  test    rsi, rsi
0x1800b5109  jz      short loc_1800B5113
0x1800b510b  mov     rcx, rsi; this
0x1800b510e  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b5113  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b511a  xor     edx, edx; struct _GUID *
0x1800b511c  lea     rcx, aWwansapsmsdele; "WwanSapSmsDelete"
0x1800b5123  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b5128  mov     ebx, 1Fh
0x1800b512d  jmp     short loc_1800B5163
0x1800b512f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b5132  mov     rcx, rbx; hHandle
0x1800b5135  call    cs:__imp_WaitForSingleObject
0x1800b513b  test    eax, eax
0x1800b513d  jz      short loc_1800B5160
0x1800b513f  call    cs:__imp_GetLastError
0x1800b5145  mov     r9d, eax; unsigned int
0x1800b5148  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b514f  mov     edx, 3EDh; unsigned int
0x1800b5154  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b515b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5160  mov     ebx, dword ptr [rbp+arg_0]
0x1800b5163  lea     rcx, [rbp+hHandle]
0x1800b5167  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b516c  mov     eax, ebx
0x1800b516e  add     rsp, 20h
0x1800b5172  pop     r15
0x1800b5174  pop     r14
0x1800b5176  pop     r12
0x1800b5178  pop     rdi
0x1800b5179  pop     rsi
0x1800b517a  pop     rbx
0x1800b517b  pop     rbp
0x1800b517c  retn
```
