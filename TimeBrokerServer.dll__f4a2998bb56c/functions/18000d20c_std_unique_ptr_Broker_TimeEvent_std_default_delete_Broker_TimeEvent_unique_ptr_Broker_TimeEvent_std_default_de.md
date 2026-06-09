# std::unique_ptr<Broker::TimeEvent,std::default_delete<Broker::TimeEvent>>::~unique_ptr<Broker::TimeEvent,std::default_delete<Broker::TimeEvent>>(void)

- ea: `0x18000d20c`
- end: `0x18000d21a`
- name: `??1?$unique_ptr@VTimeEvent@Broker@@U?$default_delete@VTimeEvent@Broker@@@std@@@std@@QEAA@XZ`
- size: `14`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001aa42`
- `0x18001b5f8`

## callees

- `0x18000d20c`
- `0x180011858`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<Broker::TimeEvent>::~unique_ptr<Broker::TimeEvent>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<Broker::TimeEvent>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000d20c  mov     rdx, [rcx]
0x18000d20f  test    rdx, rdx
0x18000d212  jnz     short loc_18000D215
0x18000d214  retn
0x18000d215  jmp     ??R?$default_delete@VTimeEvent@Broker@@@std@@QEBAXPEAVTimeEvent@Broker@@@Z; std::default_delete<Broker::TimeEvent>::operator()(Broker::TimeEvent *)
```
