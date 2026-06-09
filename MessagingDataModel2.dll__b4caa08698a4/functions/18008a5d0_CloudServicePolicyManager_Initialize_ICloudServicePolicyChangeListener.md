# CloudServicePolicyManager::_Initialize(ICloudServicePolicyChangeListener *)

- ea: `0x18008a5d0`
- end: `0x18008a730`
- name: `?_Initialize@CloudServicePolicyManager@@AEAAJPEAUICloudServicePolicyChangeListener@@@Z`
- size: `352`
- prototype: `int(CloudServicePolicyManager *__hidden this, struct ICloudServicePolicyChangeListener *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016a0`
- `0x1800065c8`
- `0x180015050`
- `0x180089f34`
- `0x18008a468`
- `0x18008a5d0`
- `0x1800c6940`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18008a6b2`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18008a6b2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18008a6d7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18008a705`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18008a6d7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18008a705`

## string_xrefs

- `0x18008a603`: `CloudServicePolicyManager::_Initialize`

## pseudocode

```c
__int64 __fastcall CloudServicePolicyManager::_Initialize(CloudServicePolicyManager *this, struct IUnknown *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // ebx
  int v8; // eax
  const OLECHAR *v9; // rcx
  unsigned int v11; // edi
  int v12; // [rsp+20h] [rbp-258h]
  const OLECHAR *v13[2]; // [rsp+40h] [rbp-238h] BYREF
  unsigned __int16 v14[256]; // [rsp+50h] [rbp-228h] BYREF

  v12 = 231;
  StringCchPrintfW(v14, 0x100u, L"%S(%d):%s", "CloudServicePolicyManager::_Initialize", v12, L"Enter");
  if ( (unsigned int)dword_1800FD5F0 > 5 )
  {
    v13[0] = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v4,
      (int)byte_1800F1985,
      v5,
      v6,
      v13);
  }
  *((_DWORD *)this + 10) = CloudServicePolicyManager::_GetMdmSyncPolicyState();
  if ( *((struct IUnknown **)this + 12) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 12, a2);
  v7 = 0;
  while ( 1 )
  {
    v13[0] = 0;
    v8 = RtlSubscribeWnfStateChangeNotification(
           v13,
           qword_1800FDCE0[v7],
           0,
           CloudServicePolicyManager::_WnfChangedCallback,
           this,
           0,
           0,
           0);
    if ( v8 < 0 )
      break;
    v9 = (const OLECHAR *)*((_QWORD *)this + v7 + 6);
    *((const OLECHAR **)this + v7 + 6) = v13[0];
    v13[0] = v9;
    if ( v9 )
      RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( (unsigned int)++v7 >= 6 )
      return 0;
  }
  v11 = v8 | 0x10000000;
  Log_HREvent_64(v8 | 0x10000000);
  if ( v13[0] )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  return v11;
}

```

## disassembly

```asm
0x18008a5d0  mov     [rsp+arg_10], rbx
0x18008a5d5  push    rbp
0x18008a5d6  push    rsi
0x18008a5d7  push    rdi
0x18008a5d8  sub     rsp, 260h
0x18008a5df  mov     rax, cs:__security_cookie
0x18008a5e6  xor     rax, rsp
0x18008a5e9  mov     [rsp+278h+var_28], rax
0x18008a5f1  lea     rax, aEnter; "Enter"
0x18008a5f8  mov     rbx, rdx
0x18008a5fb  mov     rsi, rcx
0x18008a5fe  mov     [rsp+278h+var_250], rax
0x18008a603  lea     r9, aCloudservicepo_9; "CloudServicePolicyManager::_Initialize"
0x18008a60a  mov     dword ptr [rsp+278h+var_258], 0E7h
0x18008a612  lea     r8, aSDS; "%S(%d):%s"
0x18008a619  mov     edx, 100h; unsigned __int64
0x18008a61e  lea     rcx, [rsp+278h+var_228]; unsigned __int16 *
0x18008a623  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008a628  mov     eax, cs:dword_1800FD5F0
0x18008a62e  cmp     eax, 5
0x18008a631  jbe     short loc_18008A653
0x18008a633  lea     rax, [rsp+278h+var_228]
0x18008a638  mov     [rsp+278h+var_238], rax
0x18008a63d  lea     rdx, byte_1800F1985
0x18008a644  lea     rax, [rsp+278h+var_238]
0x18008a649  mov     [rsp+278h+var_258], rax
0x18008a64e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18008a653  call    ?_GetMdmSyncPolicyState@CloudServicePolicyManager@@CAKXZ; CloudServicePolicyManager::_GetMdmSyncPolicyState(void)
0x18008a658  lea     rcx, [rsi+60h]; struct IUnknown **
0x18008a65c  mov     [rsi+28h], eax
0x18008a65f  cmp     [rcx], rbx
0x18008a662  jz      short loc_18008A66C
0x18008a664  mov     rdx, rbx; struct IUnknown *
0x18008a667  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18008a66c  xor     ebx, ebx
0x18008a66e  mov     [rsp+278h+var_240], 0
0x18008a676  lea     rdx, qword_1800FDCE0
0x18008a67d  mov     [rsp+278h+var_248], 0
0x18008a685  lea     r9, ?_WnfChangedCallback@CloudServicePolicyManager@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CloudServicePolicyManager::_WnfChangedCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18008a68c  movsxd  rbp, ebx
0x18008a68f  lea     rcx, [rsp+278h+var_238]
0x18008a694  mov     [rsp+278h+var_250], 0
0x18008a69d  xor     r8d, r8d
0x18008a6a0  mov     [rsp+278h+var_238], 0
0x18008a6a9  mov     [rsp+278h+var_258], rsi
0x18008a6ae  mov     rdx, [rdx+rbp*8]
0x18008a6b2  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18008a6b8  mov     edi, eax
0x18008a6ba  test    eax, eax
0x18008a6bc  js      short loc_18008A6E8
0x18008a6be  mov     rcx, [rsi+rbp*8+30h]
0x18008a6c3  mov     rax, [rsp+278h+var_238]
0x18008a6c8  mov     [rsi+rbp*8+30h], rax
0x18008a6cd  mov     [rsp+278h+var_238], rcx
0x18008a6d2  test    rcx, rcx
0x18008a6d5  jz      short loc_18008A6DD
0x18008a6d7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18008a6dd  inc     ebx
0x18008a6df  cmp     ebx, 6
0x18008a6e2  jb      short loc_18008A66E
0x18008a6e4  xor     eax, eax
0x18008a6e6  jmp     short loc_18008A70D
0x18008a6e8  bts     edi, 1Ch
0x18008a6ec  xor     edx, edx
0x18008a6ee  mov     ecx, edi; int
0x18008a6f0  mov     r9d, 0F3h
0x18008a6f6  call    Log_HREvent_64
0x18008a6fb  mov     rcx, [rsp+278h+var_238]
0x18008a700  test    rcx, rcx
0x18008a703  jz      short loc_18008A70B
0x18008a705  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18008a70b  mov     eax, edi
0x18008a70d  mov     rcx, [rsp+278h+var_28]
0x18008a715  xor     rcx, rsp; StackCookie
0x18008a718  call    __security_check_cookie
0x18008a71d  mov     rbx, [rsp+278h+arg_10]
0x18008a725  add     rsp, 260h
0x18008a72c  pop     rdi
0x18008a72d  pop     rsi
0x18008a72e  pop     rbp
0x18008a72f  retn
```
