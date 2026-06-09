# _MessagingService::OnStarted_::_1_::dtor$0

- ea: `0x18000ae9c`
- end: `0x18000aea8`
- name: `_MessagingService::OnStarted_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002fa0`

## pseudocode

```c
void __fastcall MessagingService::OnStarted_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CComInit::~CComInit((CComInit *)(a2 + 48));
}

```

## disassembly

```asm
0x18000ae9c  lea     rcx, [rdx+30h]; this
0x18000aea3  jmp     ??1CComInit@@QEAA@XZ; CComInit::~CComInit(void)
```
