# std::vector<Broker::BILayer::NotificationChannel::TCallback,std::allocator<Broker::BILayer::NotificationChannel::TCallback>>::_Tidy(void)

- ea: `0x180014e54`
- end: `0x180014ea1`
- name: `?_Tidy@?$vector@UTCallback@NotificationChannel@BILayer@Broker@@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@AEAAXXZ`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c4c0`
- `0x18000d2a8`
- `0x18000d6e4`
- `0x180014dc8`
- `0x180014e48`

## callees

- `0x180004e38`
- `0x18000dbb4`
- `0x180014e54`

## pseudocode

```c
__int64 __fastcall std::vector<Broker::BILayer::NotificationChannel::TCallback>::_Tidy(
        Broker::BILayer::NotificationChannel::TCallback **a1)
{
  Broker::BILayer::NotificationChannel::TCallback *v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<Broker::BILayer::NotificationChannel::TCallback>>(v2);
    result = std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFF00uLL);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180014e54  push    rbx
0x180014e56  sub     rsp, 20h
0x180014e5a  mov     rbx, rcx
0x180014e5d  mov     rcx, [rcx]; this
0x180014e60  test    rcx, rcx
0x180014e63  jz      short loc_180014E9B
0x180014e65  mov     rdx, [rbx+8]
0x180014e69  call    ??$_Destroy_range@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@YAXPEAUTCallback@NotificationChannel@BILayer@Broker@@QEAU1234@AEAV?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@0@@Z; std::_Destroy_range<std::allocator<Broker::BILayer::NotificationChannel::TCallback>>(Broker::BILayer::NotificationChannel::TCallback *,Broker::BILayer::NotificationChannel::TCallback * const,std::allocator<Broker::BILayer::NotificationChannel::TCallback> &)
0x180014e6e  mov     rdx, [rbx+10h]
0x180014e72  sub     rdx, [rbx]
0x180014e75  mov     rcx, [rbx]
0x180014e78  and     rdx, 0FFFFFFFFFFFFFF00h
0x180014e7f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014e84  mov     qword ptr [rbx], 0
0x180014e8b  mov     qword ptr [rbx+8], 0
0x180014e93  mov     qword ptr [rbx+10h], 0
0x180014e9b  add     rsp, 20h
0x180014e9f  pop     rbx
0x180014ea0  retn
```
