# Broker::DsBroker::~DsBroker(void)

- ea: `0x1800218b4`
- end: `0x1800218cb`
- name: `??1DsBroker@Broker@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Broker::DsBroker *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021a60`

## callees

- `0x1800218b4`

## import_xrefs

- `BrokerLib!BrDeleteBrokerInstance` at `0x1800218c0`
- `BrokerLib!BrDeleteBrokerInstance` at `0x1800218c0`

## pseudocode

```c
void __fastcall Broker::DsBroker::~DsBroker(Broker::DsBroker *this)
{
  if ( *(_QWORD *)this )
    BrDeleteBrokerInstance();
}

```

## disassembly

```asm
0x1800218b4  sub     rsp, 28h
0x1800218b8  mov     rcx, [rcx]
0x1800218bb  test    rcx, rcx
0x1800218be  jz      short loc_1800218C6
0x1800218c0  call    cs:__imp_BrDeleteBrokerInstance
0x1800218c6  add     rsp, 28h
0x1800218ca  retn
```
