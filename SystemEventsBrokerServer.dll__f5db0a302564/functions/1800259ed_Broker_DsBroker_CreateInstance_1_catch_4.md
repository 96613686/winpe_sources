# _Broker::DsBroker::CreateInstance_::_1_::catch$4

- ea: `0x1800259ed`
- end: `0x180025a16`
- name: `_Broker::DsBroker::CreateInstance_::_1_::catch$4`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001d9ac`
- `0x1800259ed`

## import_xrefs

- `BrokerLib!BrDeleteBrokerInstance` at `0x180025a06`
- `BrokerLib!BrDeleteBrokerInstance` at `0x180025a06`

## pseudocode

```c
void __fastcall __noreturn Broker::DsBroker::CreateInstance_::_1_::catch_4(__int64 a1, __int64 a2)
{
  if ( *(_QWORD *)(a2 + 200) )
    BrDeleteBrokerInstance();
  throw;
}

```

## disassembly

```asm
0x1800259ed  mov     [rsp+arg_8], rdx
0x1800259f2  push    rbp
0x1800259f3  sub     rsp, 30h
0x1800259f7  mov     rbp, rdx
0x1800259fa  mov     rcx, [rbp+0C8h]
0x180025a01  test    rcx, rcx
0x180025a04  jz      short loc_180025A0C
0x180025a06  call    cs:__imp_BrDeleteBrokerInstance
0x180025a0c  xor     edx, edx; pThrowInfo
0x180025a0e  xor     ecx, ecx; pExceptionObject
0x180025a10  call    _CxxThrowException_0
```
