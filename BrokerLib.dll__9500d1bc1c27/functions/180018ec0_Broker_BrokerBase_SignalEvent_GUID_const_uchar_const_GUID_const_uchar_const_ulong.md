# Broker::BrokerBase::SignalEvent(_GUID const &,uchar const *,_GUID const *,uchar const *,ulong)

- ea: `0x180018ec0`
- end: `0x180018f75`
- name: `?SignalEvent@BrokerBase@Broker@@QEAAXAEBU_GUID@@PEBEPEBU3@1K@Z`
- size: `181`
- prototype: `void __usercall(struct _RTL_SRWLOCK *this@<rcx>, const struct _GUID *@<rdx>, const unsigned __int8 *@<r8>, const struct _GUID *@<r9>, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180017090`

## callees

- `0x180004ae0`
- `0x180005724`
- `0x180005b90`
- `0x180009d9c`
- `0x18000baa0`
- `0x18000bc00`
- `0x180018ec0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Broker::BrokerBase::SignalEvent(
        struct _RTL_SRWLOCK *this,
        const struct _GUID *a2,
        const unsigned __int8 *a3,
        struct _GUID *a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  Broker::BrokerEvent *v10; // [rsp+30h] [rbp-48h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-40h]
  _BYTE v12[56]; // [rsp+40h] [rbp-38h] BYREF

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, (_DWORD)a3, this[1].Ptr, (__int64)a2);
  Broker::ScopedReadLock::ScopedReadLock((Broker::ScopedReadLock *)v12, this, (bool)a3);
  Broker::BrokeredEventTable::Find(&this[26], &v10, a2);
  Broker::BrokerEvent::Signal(v10, a3, a4, a5, a6, 0);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  Broker::ScopedReadLock::~ScopedReadLock((Broker::ScopedReadLock *)v12);
}

```

## disassembly

```asm
0x180018ec0  push    rbx
0x180018ec2  push    rbp
0x180018ec3  push    rsi
0x180018ec4  push    rdi
0x180018ec5  sub     rsp, 58h
0x180018ec9  mov     rsi, r9
0x180018ecc  mov     rbp, r8
0x180018ecf  mov     rdi, rdx
0x180018ed2  mov     rbx, rcx
0x180018ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x180018edc  test    dword ptr [rcx+1Ch], 800h
0x180018ee3  jz      short loc_180018F02
0x180018ee5  cmp     byte ptr [rcx+19h], 5
0x180018ee9  jb      short loc_180018F02
0x180018eeb  mov     edx, 46h ; 'F'
0x180018ef0  mov     qword ptr [rsp+78h+var_58], rdi
0x180018ef5  mov     r9, [rbx+8]
0x180018ef9  mov     rcx, [rcx+10h]
0x180018efd  call    WPP_SF__guid__guid_
0x180018f02  mov     rdx, rbx; struct _RTL_SRWLOCK *
0x180018f05  lea     rcx, [rsp+78h+var_38]; this
0x180018f0a  call    ??0ScopedReadLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedReadLock::ScopedReadLock(_RTL_SRWLOCK &,bool)
0x180018f0f  nop
0x180018f10  lea     rcx, [rbx+0D0h]
0x180018f17  mov     r8, rdi
0x180018f1a  lea     rdx, [rsp+78h+var_48]
0x180018f1f  call    ?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokeredEventTable::Find(_GUID const &)
0x180018f24  nop
0x180018f25  mov     [rsp+78h+var_50], 0; struct _GUID *
0x180018f2e  mov     eax, [rsp+78h+arg_28]
0x180018f35  mov     [rsp+78h+var_58], eax; unsigned int
0x180018f39  mov     r9, [rsp+78h+arg_20]; unsigned __int8 *
0x180018f41  mov     r8, rsi; struct _GUID *
0x180018f44  mov     rdx, rbp; unsigned __int8 *
0x180018f47  mov     rcx, [rsp+78h+var_48]; this
0x180018f4c  call    ?Signal@BrokerEvent@Broker@@QEAAXPEBEPEBU_GUID@@0K1@Z; Broker::BrokerEvent::Signal(uchar const *,_GUID const *,uchar const *,ulong,_GUID const *)
0x180018f51  nop
0x180018f52  mov     rcx, [rsp+78h+var_40]; this
0x180018f57  test    rcx, rcx
0x180018f5a  jz      short loc_180018F62
0x180018f5c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018f61  nop
0x180018f62  lea     rcx, [rsp+78h+var_38]; this
0x180018f67  call    ??1ScopedReadLock@Broker@@QEAA@XZ; Broker::ScopedReadLock::~ScopedReadLock(void)
0x180018f6c  add     rsp, 58h
0x180018f70  pop     rdi
0x180018f71  pop     rsi
0x180018f72  pop     rbp
0x180018f73  pop     rbx
0x180018f74  retn
```
