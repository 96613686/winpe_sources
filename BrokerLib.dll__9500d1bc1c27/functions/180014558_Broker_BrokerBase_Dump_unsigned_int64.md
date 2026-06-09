# Broker::BrokerBase::Dump(unsigned __int64)

- ea: `0x180014558`
- end: `0x1800145ff`
- name: `?Dump@BrokerBase@Broker@@QEAAX_K@Z`
- size: `167`
- prototype: `void __fastcall(struct _RTL_SRWLOCK *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800144cc`

## callees

- `0x180004500`
- `0x180004ae0`
- `0x180005070`
- `0x180005b50`
- `0x18000baa0`
- `0x18000bc00`
- `0x180014558`
- `0x180014608`

## pseudocode

```c
void __fastcall Broker::BrokerBase::Dump(struct _RTL_SRWLOCK *this, unsigned __int64 a2)
{
  bool v4; // r8
  PVOID v5; // r9
  __int64 v6; // r9
  Broker::BrokerEvent **v7; // rbx
  std::_Ref_count_base *v8; // rcx
  _BYTE v9[16]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v10[3]; // [rsp+30h] [rbp-18h] BYREF
  void *v11; // [rsp+50h] [rbp+8h] BYREF

  WPP_SF__guid_(a2, 76, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, this[1].Ptr);
  Broker::ScopedReadLock::ScopedReadLock((Broker::ScopedReadLock *)v9, this, v4);
  v5 = *(PVOID *)this[26].Ptr;
  v11 = v5;
  while ( v5 != this[26].Ptr )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++((__int64 *)&v11);
    v7 = (Broker::BrokerEvent **)std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(
                                   v10,
                                   (_QWORD *)(v6 + 40));
    Broker::BrokerEvent::Dump(*v7, a2);
    v8 = v7[1];
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    v5 = v11;
  }
  Broker::ScopedReadLock::~ScopedReadLock((Broker::ScopedReadLock *)v9);
}

```

## disassembly

```asm
0x180014558  mov     [rsp+arg_8], rbx
0x18001455d  mov     [rsp+arg_10], rsi
0x180014562  push    rdi
0x180014563  sub     rsp, 40h
0x180014567  mov     rsi, rdx
0x18001456a  mov     rdi, rcx
0x18001456d  mov     r9, [rcx+8]
0x180014571  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180014578  mov     rcx, rsi
0x18001457b  mov     edx, 4Ch ; 'L'
0x180014580  call    WPP_SF__guid_
0x180014585  mov     rdx, rdi; struct _RTL_SRWLOCK *
0x180014588  lea     rcx, [rsp+48h+var_28]; this
0x18001458d  call    ??0ScopedReadLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedReadLock::ScopedReadLock(_RTL_SRWLOCK &,bool)
0x180014592  mov     r9, [rdi+0D0h]
0x180014599  mov     r9, [r9]
0x18001459c  mov     [rsp+48h+arg_0], r9
0x1800145a1  cmp     r9, [rdi+0D0h]
0x1800145a8  jz      short loc_1800145E5
0x1800145aa  lea     rcx, [rsp+48h+arg_0]
0x1800145af  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)
0x1800145b4  lea     rdx, [r9+28h]
0x1800145b8  lea     rcx, [rsp+48h+var_18]
0x1800145bd  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x1800145c2  mov     rdx, rsi; unsigned __int64
0x1800145c5  mov     rbx, rax
0x1800145c8  mov     rcx, [rax]; this
0x1800145cb  call    ?Dump@BrokerEvent@Broker@@QEAAX_K@Z; Broker::BrokerEvent::Dump(unsigned __int64)
0x1800145d0  mov     rcx, [rbx+8]; this
0x1800145d4  test    rcx, rcx
0x1800145d7  jz      short loc_1800145DE
0x1800145d9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800145de  mov     r9, [rsp+48h+arg_0]
0x1800145e3  jmp     short loc_1800145A1
0x1800145e5  lea     rcx, [rsp+48h+var_28]; this
0x1800145ea  call    ??1ScopedReadLock@Broker@@QEAA@XZ; Broker::ScopedReadLock::~ScopedReadLock(void)
0x1800145ef  mov     rbx, [rsp+48h+arg_8]
0x1800145f4  mov     rsi, [rsp+48h+arg_10]
0x1800145f9  add     rsp, 40h
0x1800145fd  pop     rdi
0x1800145fe  retn
```
