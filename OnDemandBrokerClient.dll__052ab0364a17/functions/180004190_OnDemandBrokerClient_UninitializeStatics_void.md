# OnDemandBrokerClient::UninitializeStatics(void)

- ea: `0x180004190`
- end: `0x1800041d8`
- name: `?UninitializeStatics@OnDemandBrokerClient@@SAXXZ`
- size: `72`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800042e0`

## callees

- `0x180004190`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800041d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000419b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000419b`

## pseudocode

```c
void OnDemandBrokerClient::UninitializeStatics(void)
{
  EnterCriticalSection(&OnDemandBrokerClient::s_instancelock);
  if ( OnDemandBrokerClient::s_instance )
    (*(void (__fastcall **)(struct OnDemandBrokerClient *))(*(_QWORD *)OnDemandBrokerClient::s_instance + 16LL))(OnDemandBrokerClient::s_instance);
  LeaveCriticalSection(&OnDemandBrokerClient::s_instancelock);
  DeleteCriticalSection(&OnDemandBrokerClient::s_instancelock);
}

```

## disassembly

```asm
0x180004190  sub     rsp, 28h
0x180004194  lea     rcx, ?s_instancelock@OnDemandBrokerClient@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000419b  call    cs:__imp_EnterCriticalSection
0x1800041a1  mov     rcx, cs:?s_instance@OnDemandBrokerClient@@0PEAV1@EA; OnDemandBrokerClient * OnDemandBrokerClient::s_instance
0x1800041a8  test    rcx, rcx
0x1800041ab  jz      short loc_1800041B9
0x1800041ad  mov     rax, [rcx]
0x1800041b0  mov     rax, [rax+10h]
0x1800041b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b9  lea     rcx, ?s_instancelock@OnDemandBrokerClient@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800041c0  call    cs:__imp_LeaveCriticalSection
0x1800041c6  lea     rcx, ?s_instancelock@OnDemandBrokerClient@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION OnDemandBrokerClient::s_instancelock
0x1800041cd  add     rsp, 28h
0x1800041d1  jmp     cs:__imp_DeleteCriticalSection
```
