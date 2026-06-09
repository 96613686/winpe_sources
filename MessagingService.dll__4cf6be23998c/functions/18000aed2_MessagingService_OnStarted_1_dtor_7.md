# _MessagingService::OnStarted_::_1_::dtor$7

- ea: `0x18000aed2`
- end: `0x18000aede`
- name: `_MessagingService::OnStarted_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002be4`

## pseudocode

```c
__int64 __fastcall MessagingService::OnStarted_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<TransportManager>::~CComPtr<TransportManager>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x18000aed2  lea     rcx, [rdx+38h]
0x18000aed9  jmp     ??1?$CComPtr@VTransportManager@@@ATL@@QEAA@XZ; ATL::CComPtr<TransportManager>::~CComPtr<TransportManager>(void)
```
