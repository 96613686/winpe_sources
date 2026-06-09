# WwanSapGetTrafficDescriptorList(WWAN_SAP const *,_GUID const *,WWAN_TRAFFIC_DESCRIPTOR_LIST * *)

- ea: `0x1800b2bdc`
- end: `0x1800b2d3a`
- name: `?WwanSapGetTrafficDescriptorList@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEAPEAUWWAN_TRAFFIC_DESCRIPTOR_LIST@@@Z`
- size: `350`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, struct WWAN_TRAFFIC_DESCRIPTOR_LIST **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ace90`

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
- `0x1800b2bdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2cf0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2cf0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2c0d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2cfa`

## string_xrefs

- `0x1800b2c43`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2d0f`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2c37`: `CreateEvent`
- `0x1800b2cd7`: `WwanSapGetTrafficDescriptorList`

## pseudocode

```c
__int64 __fastcall WwanSapGetTrafficDescriptorList(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        struct WWAN_TRAFFIC_DESCRIPTOR_LIST **a3)
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
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xC9Eu, "CreateEvent", LastError);
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
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(54, v8) )
  {
    if ( v8 )
      MessageParams::`scalar deleting destructor'(v8, v9);
    WwanLog::Error("WwanSapGetTrafficDescriptorList", 0, L"Notification dispatcher: Failed to Queue Message");
    v10 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v6, 0xFFFFFFFF) )
    {
      v11 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xCB1u, "WaitForSingleObject", v11);
    }
    v10 = v13;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v10;
}

```

## disassembly

```asm
0x1800b2bdc  mov     [rsp-28h+arg_18], rbx
0x1800b2be1  mov     [rsp-28h+arg_0], rcx
0x1800b2be6  push    rbp
0x1800b2be7  push    rsi
0x1800b2be8  push    rdi
0x1800b2be9  push    r14
0x1800b2beb  push    r15
0x1800b2bed  mov     rbp, rsp
0x1800b2bf0  sub     rsp, 20h
0x1800b2bf4  mov     r14, r8
0x1800b2bf7  mov     r15, rdx
0x1800b2bfa  mov     dword ptr [rbp+arg_0], 0
0x1800b2c01  xor     r9d, r9d; lpName
0x1800b2c04  xor     r8d, r8d; bInitialState
0x1800b2c07  lea     edx, [r9+1]; bManualReset
0x1800b2c0b  xor     ecx, ecx; lpEventAttributes
0x1800b2c0d  call    cs:__imp_CreateEventW
0x1800b2c13  mov     rdx, rax
0x1800b2c16  lea     rcx, [rbp+hHandle]
0x1800b2c1a  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b2c1f  nop
0x1800b2c20  mov     rbx, [rbp+hHandle]
0x1800b2c24  lea     rax, [rbx+1]
0x1800b2c28  cmp     rax, 1
0x1800b2c2c  ja      short loc_1800B2C4F
0x1800b2c2e  call    cs:__imp_GetLastError
0x1800b2c34  mov     r9d, eax; unsigned int
0x1800b2c37  lea     r8, aCreateevent; "CreateEvent"
0x1800b2c3e  mov     edx, 0C9Eh; unsigned int
0x1800b2c43  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2c4a  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2c4f  mov     ecx, 48h ; 'H'; Size
0x1800b2c54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2c59  mov     [rbp+arg_10], rax
0x1800b2c5d  mov     rcx, rax; this
0x1800b2c60  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b2c65  mov     rsi, rax
0x1800b2c68  lea     rdi, [rax+30h]
0x1800b2c6c  mov     [rbp+arg_10], rbx
0x1800b2c70  lea     rdx, [rbp+arg_10]
0x1800b2c74  mov     rcx, rdi
0x1800b2c77  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2c7c  lea     rax, [rbp+arg_0]
0x1800b2c80  mov     [rbp+arg_10], rax
0x1800b2c84  lea     rdx, [rbp+arg_10]
0x1800b2c88  mov     rcx, rdi
0x1800b2c8b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2c90  mov     [rbp+arg_10], r15
0x1800b2c94  lea     rdx, [rbp+arg_10]
0x1800b2c98  mov     rcx, rdi
0x1800b2c9b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2ca0  mov     [rbp+arg_10], r14
0x1800b2ca4  lea     rdx, [rbp+arg_10]
0x1800b2ca8  mov     rcx, rdi
0x1800b2cab  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2cb0  mov     rdx, rsi
0x1800b2cb3  mov     ecx, 36h ; '6'
0x1800b2cb8  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b2cbd  test    eax, eax
0x1800b2cbf  jz      short loc_1800B2CEA
0x1800b2cc1  test    rsi, rsi
0x1800b2cc4  jz      short loc_1800B2CCE
0x1800b2cc6  mov     rcx, rsi; this
0x1800b2cc9  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b2cce  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b2cd5  xor     edx, edx; struct _GUID *
0x1800b2cd7  lea     rcx, aWwansapgettraf; "WwanSapGetTrafficDescriptorList"
0x1800b2cde  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b2ce3  mov     ebx, 1Fh
0x1800b2ce8  jmp     short loc_1800B2D1E
0x1800b2cea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2ced  mov     rcx, rbx; hHandle
0x1800b2cf0  call    cs:__imp_WaitForSingleObject
0x1800b2cf6  test    eax, eax
0x1800b2cf8  jz      short loc_1800B2D1B
0x1800b2cfa  call    cs:__imp_GetLastError
0x1800b2d00  mov     r9d, eax; unsigned int
0x1800b2d03  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b2d0a  mov     edx, 0CB1h; unsigned int
0x1800b2d0f  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2d16  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2d1b  mov     ebx, dword ptr [rbp+arg_0]
0x1800b2d1e  lea     rcx, [rbp+hHandle]
0x1800b2d22  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b2d27  mov     eax, ebx
0x1800b2d29  mov     rbx, [rsp+20h+arg_18]
0x1800b2d2e  add     rsp, 20h
0x1800b2d32  pop     r15
0x1800b2d34  pop     r14
0x1800b2d36  pop     rdi
0x1800b2d37  pop     rsi
0x1800b2d38  pop     rbp
0x1800b2d39  retn
```
