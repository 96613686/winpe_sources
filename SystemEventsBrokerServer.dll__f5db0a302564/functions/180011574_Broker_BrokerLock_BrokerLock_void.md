# Broker::BrokerLock::~BrokerLock(void)

- ea: `0x180011574`
- end: `0x18001158a`
- name: `??1BrokerLock@Broker@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(Broker::BrokerLock *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800198e0`
- `0x18001b008`
- `0x18001ecd0`
- `0x180022772`
- `0x180024290`
- `0x180024380`
- `0x1800245d0`
- `0x1800257b4`
- `0x1800258d0`
- `0x180025f91`

## callees

- `0x180011574`
- `0x180011590`

## pseudocode

```c
void __fastcall Broker::BrokerLock::~BrokerLock(Broker::BrokerLock *this)
{
  if ( *((_DWORD *)this + 3) )
    Broker::BrokerLock::Release(this);
}

```

## disassembly

```asm
0x180011574  sub     rsp, 28h
0x180011578  cmp     dword ptr [rcx+0Ch], 0
0x18001157c  jnz     short loc_180011583
0x18001157e  add     rsp, 28h
0x180011582  retn
0x180011583  call    ?Release@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Release(void)
0x180011588  jmp     short loc_18001157E
```
