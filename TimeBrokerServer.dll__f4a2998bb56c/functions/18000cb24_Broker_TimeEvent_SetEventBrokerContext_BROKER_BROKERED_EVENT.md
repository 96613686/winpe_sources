# Broker::TimeEvent::SetEventBrokerContext(_BROKER *,_BROKERED_EVENT *)

- ea: `0x18000cb24`
- end: `0x18000cb73`
- name: `?SetEventBrokerContext@TimeEvent@Broker@@QEAAXPEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z`
- size: `79`
- prototype: `void __fastcall(Broker::TimeEvent *__hidden this, struct _BROKER *, struct _BROKERED_EVENT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a698`

## callees

- `0x18000cb24`
- `0x180013978`

## pseudocode

```c
void __fastcall Broker::TimeEvent::SetEventBrokerContext(
        Broker::TimeEvent *this,
        struct _BROKER *a2,
        struct _BROKERED_EVENT *a3)
{
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  __int128 v4; // [rsp+28h] [rbp-20h]
  int v5; // [rsp+38h] [rbp-10h]

  if ( !a2 || !a3 )
  {
    v5 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v4 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  *((_QWORD *)this + 30) = a2;
  *((_QWORD *)this + 31) = a3;
}

```

## disassembly

```asm
0x18000cb24  sub     rsp, 48h
0x18000cb28  test    rdx, rdx
0x18000cb2b  jz      short loc_18000CB45
0x18000cb2d  test    r8, r8
0x18000cb30  jz      short loc_18000CB45
0x18000cb32  mov     [rcx+0F0h], rdx
0x18000cb39  mov     [rcx+0F8h], r8
0x18000cb40  add     rsp, 48h
0x18000cb44  retn
0x18000cb45  xorps   xmm0, xmm0
0x18000cb48  mov     [rsp+48h+var_10], 4
0x18000cb50  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18000cb57  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000cb5e  mov     [rsp+48h+pExceptionObject], rax
0x18000cb63  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000cb68  movups  [rsp+48h+var_20], xmm0
0x18000cb6d  call    _CxxThrowException_0
```
