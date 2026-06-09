# StateRepository::Tracing::Broker::`scalar deleting destructor'(uint)

- ea: `0x180004190`
- end: `0x1800041c4`
- name: `??_GBroker@Tracing@StateRepository@@UEAAPEAXI@Z`
- size: `52`
- prototype: `StateRepository::Tracing::Broker *__fastcall(StateRepository::Tracing::Broker *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002160`
- `0x18000402c`
- `0x180004190`

## pseudocode

```c
StateRepository::Tracing::Broker *__fastcall StateRepository::Tracing::Broker::`scalar deleting destructor'(
        StateRepository::Tracing::Broker *this,
        char a2)
{
  wil::TraceLoggingProvider::~TraceLoggingProvider(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004190  mov     [rsp+arg_0], rbx
0x180004195  push    rdi
0x180004196  sub     rsp, 20h
0x18000419a  mov     ebx, edx
0x18000419c  mov     rdi, rcx
0x18000419f  call    ??1TraceLoggingProvider@wil@@MEAA@XZ; wil::TraceLoggingProvider::~TraceLoggingProvider(void)
0x1800041a4  test    bl, 1
0x1800041a7  jz      short loc_1800041B6
0x1800041a9  mov     edx, 20h ; ' '
0x1800041ae  mov     rcx, rdi; Block
0x1800041b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800041b6  mov     rbx, [rsp+28h+arg_0]
0x1800041bb  mov     rax, rdi
0x1800041be  add     rsp, 20h
0x1800041c2  pop     rdi
0x1800041c3  retn
```
