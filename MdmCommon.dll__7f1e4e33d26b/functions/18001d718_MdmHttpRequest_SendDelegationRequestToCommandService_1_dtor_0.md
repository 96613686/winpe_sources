# _MdmHttpRequest::SendDelegationRequestToCommandService_::_1_::dtor$0

- ea: `0x18001d718`
- end: `0x18001d724`
- name: `_MdmHttpRequest::SendDelegationRequestToCommandService_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002de4`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::SendDelegationRequestToCommandService_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 96));
}

```

## disassembly

```asm
0x18001d718  lea     rcx, [rdx+60h]
0x18001d71f  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
