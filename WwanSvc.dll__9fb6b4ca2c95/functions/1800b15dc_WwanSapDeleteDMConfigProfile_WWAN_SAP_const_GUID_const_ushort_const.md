# WwanSapDeleteDMConfigProfile(WWAN_SAP const *,_GUID const *,ushort const *)

- ea: `0x1800b15dc`
- end: `0x1800b173a`
- name: `?WwanSapDeleteDMConfigProfile@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEBG@Z`
- size: `350`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800ac750`

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
- `0x1800b15dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b16f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b16f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b160d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b160d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b162e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b162e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16fa`

## string_xrefs

- `0x1800b1643`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b170f`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1637`: `CreateEvent`
- `0x1800b16d7`: `WwanSapDeleteDMConfigProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapDeleteDMConfigProfile(const struct WWAN_SAP *a1, const struct _GUID *a2, MessageParams *a3)
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
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xA6Bu, "CreateEvent", LastError);
  }
  v16 = (MessageParams *)operator new(0x48u);
  v8 = MessageParams::MessageParams(v16);
  v16 = v6;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)&v13;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = a3;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(39, v8) )
  {
    if ( v8 )
      MessageParams::`scalar deleting destructor'(v8, v9);
    WwanLog::Error("WwanSapDeleteDMConfigProfile", 0, L"Notification dispatcher: Failed to Queue Message");
    v10 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v6, 0xFFFFFFFF) )
    {
      v11 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xA7Eu, "WaitForSingleObject", v11);
    }
    v10 = v13;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v10;
}

```

## disassembly

```asm
0x1800b15dc  mov     [rsp-28h+arg_18], rbx
0x1800b15e1  mov     [rsp-28h+arg_0], rcx
0x1800b15e6  push    rbp
0x1800b15e7  push    rsi
0x1800b15e8  push    rdi
0x1800b15e9  push    r14
0x1800b15eb  push    r15
0x1800b15ed  mov     rbp, rsp
0x1800b15f0  sub     rsp, 20h
0x1800b15f4  mov     r14, r8
0x1800b15f7  mov     r15, rdx
0x1800b15fa  mov     dword ptr [rbp+arg_0], 0
0x1800b1601  xor     r9d, r9d; lpName
0x1800b1604  xor     r8d, r8d; bInitialState
0x1800b1607  lea     edx, [r9+1]; bManualReset
0x1800b160b  xor     ecx, ecx; lpEventAttributes
0x1800b160d  call    cs:__imp_CreateEventW
0x1800b1613  mov     rdx, rax
0x1800b1616  lea     rcx, [rbp+hHandle]
0x1800b161a  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b161f  nop
0x1800b1620  mov     rbx, [rbp+hHandle]
0x1800b1624  lea     rax, [rbx+1]
0x1800b1628  cmp     rax, 1
0x1800b162c  ja      short loc_1800B164F
0x1800b162e  call    cs:__imp_GetLastError
0x1800b1634  mov     r9d, eax; unsigned int
0x1800b1637  lea     r8, aCreateevent; "CreateEvent"
0x1800b163e  mov     edx, 0A6Bh; unsigned int
0x1800b1643  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b164a  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b164f  mov     ecx, 48h ; 'H'; Size
0x1800b1654  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b1659  mov     [rbp+arg_10], rax
0x1800b165d  mov     rcx, rax; this
0x1800b1660  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b1665  mov     rsi, rax
0x1800b1668  lea     rdi, [rax+30h]
0x1800b166c  mov     [rbp+arg_10], rbx
0x1800b1670  lea     rdx, [rbp+arg_10]
0x1800b1674  mov     rcx, rdi
0x1800b1677  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b167c  lea     rax, [rbp+arg_0]
0x1800b1680  mov     [rbp+arg_10], rax
0x1800b1684  lea     rdx, [rbp+arg_10]
0x1800b1688  mov     rcx, rdi
0x1800b168b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1690  mov     [rbp+arg_10], r15
0x1800b1694  lea     rdx, [rbp+arg_10]
0x1800b1698  mov     rcx, rdi
0x1800b169b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b16a0  mov     [rbp+arg_10], r14
0x1800b16a4  lea     rdx, [rbp+arg_10]
0x1800b16a8  mov     rcx, rdi
0x1800b16ab  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b16b0  mov     rdx, rsi
0x1800b16b3  mov     ecx, 27h ; '''
0x1800b16b8  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b16bd  test    eax, eax
0x1800b16bf  jz      short loc_1800B16EA
0x1800b16c1  test    rsi, rsi
0x1800b16c4  jz      short loc_1800B16CE
0x1800b16c6  mov     rcx, rsi; this
0x1800b16c9  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b16ce  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b16d5  xor     edx, edx; struct _GUID *
0x1800b16d7  lea     rcx, aWwansapdeleted; "WwanSapDeleteDMConfigProfile"
0x1800b16de  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b16e3  mov     ebx, 1Fh
0x1800b16e8  jmp     short loc_1800B171E
0x1800b16ea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b16ed  mov     rcx, rbx; hHandle
0x1800b16f0  call    cs:__imp_WaitForSingleObject
0x1800b16f6  test    eax, eax
0x1800b16f8  jz      short loc_1800B171B
0x1800b16fa  call    cs:__imp_GetLastError
0x1800b1700  mov     r9d, eax; unsigned int
0x1800b1703  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b170a  mov     edx, 0A7Eh; unsigned int
0x1800b170f  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1716  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b171b  mov     ebx, dword ptr [rbp+arg_0]
0x1800b171e  lea     rcx, [rbp+hHandle]
0x1800b1722  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b1727  mov     eax, ebx
0x1800b1729  mov     rbx, [rsp+20h+arg_18]
0x1800b172e  add     rsp, 20h
0x1800b1732  pop     r15
0x1800b1734  pop     r14
0x1800b1736  pop     rdi
0x1800b1737  pop     rsi
0x1800b1738  pop     rbp
0x1800b1739  retn
```
