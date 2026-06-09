# WwanSapGetDMConfigBinary(WWAN_SAP const *,WWAN_GET_DM_CONFIG_BINARY_INFO *,ulong *,ulong *)

- ea: `0x1800b1d0c`
- end: `0x1800b1e79`
- name: `?WwanSapGetDMConfigBinary@@YAKPEBUWWAN_SAP@@PEAUWWAN_GET_DM_CONFIG_BINARY_INFO@@PEAK2@Z`
- size: `365`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, struct WWAN_GET_DM_CONFIG_BINARY_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800ac8b0`

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
- `0x1800b1d0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1e31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1e31`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1d3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1e3b`

## string_xrefs

- `0x1800b1d74`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1e50`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1d68`: `CreateEvent`
- `0x1800b1e18`: `WwanSapGetDMConfigBinary`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapGetDMConfigBinary(
        const struct WWAN_SAP *a1,
        struct WWAN_GET_DM_CONFIG_BINARY_INFO *a2,
        MessageParams *a3,
        MessageParams *a4)
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
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xA8Du, "CreateEvent", LastError);
  }
  v18 = (MessageParams *)operator new(0x48u);
  v10 = MessageParams::MessageParams(v18);
  v18 = v8;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = (MessageParams *)&v15;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = a2;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = a3;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = a4;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(41, v10) )
  {
    if ( v10 )
      MessageParams::`scalar deleting destructor'(v10, v11);
    WwanLog::Error("WwanSapGetDMConfigBinary", 0, L"Notification dispatcher: Failed to Queue Message");
    v12 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v8, 0xFFFFFFFF) )
    {
      v13 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xAA1u, "WaitForSingleObject", v13);
    }
    v12 = v15;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v12;
}

```

## disassembly

```asm
0x1800b1d0c  mov     [rsp-38h+arg_0], rcx
0x1800b1d11  push    rbp
0x1800b1d12  push    rbx
0x1800b1d13  push    rsi
0x1800b1d14  push    rdi
0x1800b1d15  push    r12
0x1800b1d17  push    r14
0x1800b1d19  push    r15
0x1800b1d1b  mov     rbp, rsp
0x1800b1d1e  sub     rsp, 20h
0x1800b1d22  mov     r14, r9
0x1800b1d25  mov     r15, r8
0x1800b1d28  mov     r12, rdx
0x1800b1d2b  mov     dword ptr [rbp+arg_0], 0
0x1800b1d32  xor     r9d, r9d; lpName
0x1800b1d35  xor     r8d, r8d; bInitialState
0x1800b1d38  lea     edx, [r9+1]; bManualReset
0x1800b1d3c  xor     ecx, ecx; lpEventAttributes
0x1800b1d3e  call    cs:__imp_CreateEventW
0x1800b1d44  mov     rdx, rax
0x1800b1d47  lea     rcx, [rbp+hHandle]
0x1800b1d4b  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b1d50  nop
0x1800b1d51  mov     rbx, [rbp+hHandle]
0x1800b1d55  lea     rax, [rbx+1]
0x1800b1d59  cmp     rax, 1
0x1800b1d5d  ja      short loc_1800B1D80
0x1800b1d5f  call    cs:__imp_GetLastError
0x1800b1d65  mov     r9d, eax; unsigned int
0x1800b1d68  lea     r8, aCreateevent; "CreateEvent"
0x1800b1d6f  mov     edx, 0A8Dh; unsigned int
0x1800b1d74  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1d7b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b1d80  mov     ecx, 48h ; 'H'; Size
0x1800b1d85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b1d8a  mov     [rbp+arg_10], rax
0x1800b1d8e  mov     rcx, rax; this
0x1800b1d91  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b1d96  mov     rsi, rax
0x1800b1d99  lea     rdi, [rax+30h]
0x1800b1d9d  mov     [rbp+arg_10], rbx
0x1800b1da1  lea     rdx, [rbp+arg_10]
0x1800b1da5  mov     rcx, rdi
0x1800b1da8  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1dad  lea     rax, [rbp+arg_0]
0x1800b1db1  mov     [rbp+arg_10], rax
0x1800b1db5  lea     rdx, [rbp+arg_10]
0x1800b1db9  mov     rcx, rdi
0x1800b1dbc  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1dc1  mov     [rbp+arg_10], r12
0x1800b1dc5  lea     rdx, [rbp+arg_10]
0x1800b1dc9  mov     rcx, rdi
0x1800b1dcc  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1dd1  mov     [rbp+arg_10], r15
0x1800b1dd5  lea     rdx, [rbp+arg_10]
0x1800b1dd9  mov     rcx, rdi
0x1800b1ddc  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1de1  mov     [rbp+arg_10], r14
0x1800b1de5  lea     rdx, [rbp+arg_10]
0x1800b1de9  mov     rcx, rdi
0x1800b1dec  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1df1  mov     rdx, rsi
0x1800b1df4  mov     ecx, 29h ; ')'
0x1800b1df9  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b1dfe  test    eax, eax
0x1800b1e00  jz      short loc_1800B1E2B
0x1800b1e02  test    rsi, rsi
0x1800b1e05  jz      short loc_1800B1E0F
0x1800b1e07  mov     rcx, rsi; this
0x1800b1e0a  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b1e0f  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b1e16  xor     edx, edx; struct _GUID *
0x1800b1e18  lea     rcx, aWwansapgetdmco; "WwanSapGetDMConfigBinary"
0x1800b1e1f  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b1e24  mov     ebx, 1Fh
0x1800b1e29  jmp     short loc_1800B1E5F
0x1800b1e2b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b1e2e  mov     rcx, rbx; hHandle
0x1800b1e31  call    cs:__imp_WaitForSingleObject
0x1800b1e37  test    eax, eax
0x1800b1e39  jz      short loc_1800B1E5C
0x1800b1e3b  call    cs:__imp_GetLastError
0x1800b1e41  mov     r9d, eax; unsigned int
0x1800b1e44  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b1e4b  mov     edx, 0AA1h; unsigned int
0x1800b1e50  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1e57  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b1e5c  mov     ebx, dword ptr [rbp+arg_0]
0x1800b1e5f  lea     rcx, [rbp+hHandle]
0x1800b1e63  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b1e68  mov     eax, ebx
0x1800b1e6a  add     rsp, 20h
0x1800b1e6e  pop     r15
0x1800b1e70  pop     r14
0x1800b1e72  pop     r12
0x1800b1e74  pop     rdi
0x1800b1e75  pop     rsi
0x1800b1e76  pop     rbx
0x1800b1e77  pop     rbp
0x1800b1e78  retn
```
