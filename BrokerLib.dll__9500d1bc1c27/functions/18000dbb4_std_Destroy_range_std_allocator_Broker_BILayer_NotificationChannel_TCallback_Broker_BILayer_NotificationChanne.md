# std::_Destroy_range<std::allocator<Broker::BILayer::NotificationChannel::TCallback>>(Broker::BILayer::NotificationChannel::TCallback *,Broker::BILayer::NotificationChannel::TCallback * const,std::allocator<Broker::BILayer::NotificationChannel::TCallback> &)

- ea: `0x18000dbb4`
- end: `0x18000dbe8`
- name: `??$_Destroy_range@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@YAXPEAUTCallback@NotificationChannel@BILayer@Broker@@QEAU1234@AEAV?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@0@@Z`
- size: `52`
- prototype: `__int64 __fastcall(Broker::BILayer::NotificationChannel::TCallback *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d690`
- `0x180014dc8`
- `0x180014e54`
- `0x180014f3c`
- `0x180017294`

## callees

- `0x18000dbb4`
- `0x18000dbf0`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<Broker::BILayer::NotificationChannel::TCallback>>(
        Broker::BILayer::NotificationChannel::TCallback *this,
        Broker::BILayer::NotificationChannel::TCallback *a2)
{
  Broker::BILayer::NotificationChannel::TCallback *v3; // rbx

  if ( this != a2 )
  {
    v3 = this;
    do
    {
      Broker::BILayer::NotificationChannel::TCallback::~TCallback(v3);
      v3 = (Broker::BILayer::NotificationChannel::TCallback *)((char *)v3 + 256);
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x18000dbb4  cmp     rcx, rdx
0x18000dbb7  jz      short locret_18000DBE7
0x18000dbb9  mov     [rsp+arg_0], rbx
0x18000dbbe  push    rdi
0x18000dbbf  sub     rsp, 20h
0x18000dbc3  mov     rdi, rdx
0x18000dbc6  mov     rbx, rcx
0x18000dbc9  mov     rcx, rbx; this
0x18000dbcc  call    ??1TCallback@NotificationChannel@BILayer@Broker@@QEAA@XZ; Broker::BILayer::NotificationChannel::TCallback::~TCallback(void)
0x18000dbd1  add     rbx, 100h
0x18000dbd8  cmp     rbx, rdi
0x18000dbdb  jnz     short loc_18000DBC9
0x18000dbdd  mov     rbx, [rsp+28h+arg_0]
0x18000dbe2  add     rsp, 20h
0x18000dbe6  pop     rdi
0x18000dbe7  retn
```
