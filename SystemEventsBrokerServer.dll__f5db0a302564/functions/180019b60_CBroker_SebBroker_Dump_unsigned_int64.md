# CBroker::SebBroker::Dump(unsigned __int64)

- ea: `0x180019b60`
- end: `0x180019c15`
- name: `?Dump@SebBroker@CBroker@@QEAAX_K@Z`
- size: `181`
- prototype: `void __fastcall(struct _RTL_SRWLOCK *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800197fc`

## callees

- `0x180005a50`
- `0x1800076a0`
- `0x1800133c0`
- `0x180013820`
- `0x180013920`
- `0x1800145c0`
- `0x180019b60`
- `0x180019dac`

## pseudocode

```c
void __fastcall CBroker::SebBroker::Dump(struct _RTL_SRWLOCK *this, unsigned __int64 a2)
{
  __int64 *v4; // r9
  __int64 v5; // r9
  CBroker::SebEvent **v6; // rbx
  std::_Ref_count_base *v7; // rcx
  _BYTE v8[16]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 *v10; // [rsp+50h] [rbp+8h] BYREF

  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v8, this + 1, 1);
  WPP_SF_(a2, 74, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  v4 = *(__int64 **)this[2].Ptr;
  v10 = v4;
  while ( v4 != this[2].Ptr )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>,std::_Iterator_base0>::operator++(&v10);
    v6 = (CBroker::SebEvent **)std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(v9, (_QWORD *)(v5 + 48));
    CBroker::SebEvent::Dump(*v6, a2);
    v7 = v6[1];
    if ( v7 )
      std::_Ref_count_base::_Decref(v7);
    v4 = v10;
  }
  WPP_SF_(a2, 75, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v8);
}

```

## disassembly

```asm
0x180019b60  mov     [rsp+arg_8], rbx
0x180019b65  mov     [rsp+arg_10], rsi
0x180019b6a  push    rdi
0x180019b6b  sub     rsp, 40h
0x180019b6f  mov     rdi, rdx
0x180019b72  mov     rsi, rcx
0x180019b75  lea     rdx, [rcx+8]; struct _RTL_SRWLOCK *
0x180019b79  mov     r8b, 1; bool
0x180019b7c  lea     rcx, [rsp+48h+var_28]; this
0x180019b81  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x180019b86  mov     edx, 4Ah ; 'J'
0x180019b8b  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180019b92  mov     rcx, rdi
0x180019b95  call    WPP_SF_
0x180019b9a  mov     r9, [rsi+10h]
0x180019b9e  mov     r9, [r9]
0x180019ba1  mov     [rsp+48h+arg_0], r9
0x180019ba6  cmp     r9, [rsi+10h]
0x180019baa  jz      short loc_180019BE7
0x180019bac  lea     rcx, [rsp+48h+arg_0]
0x180019bb1  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>,std::_Iterator_base0>::operator++(void)
0x180019bb6  lea     rdx, [r9+30h]
0x180019bba  lea     rcx, [rsp+48h+var_18]
0x180019bbf  call    ??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)
0x180019bc4  mov     rdx, rdi; unsigned __int64
0x180019bc7  mov     rbx, rax
0x180019bca  mov     rcx, [rax]; this
0x180019bcd  call    ?Dump@SebEvent@CBroker@@QEAAX_K@Z; CBroker::SebEvent::Dump(unsigned __int64)
0x180019bd2  mov     rcx, [rbx+8]; this
0x180019bd6  test    rcx, rcx
0x180019bd9  jz      short loc_180019BE0
0x180019bdb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019be0  mov     r9, [rsp+48h+arg_0]
0x180019be5  jmp     short loc_180019BA6
0x180019be7  mov     edx, 4Bh ; 'K'
0x180019bec  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180019bf3  mov     rcx, rdi
0x180019bf6  call    WPP_SF_
0x180019bfb  lea     rcx, [rsp+48h+var_28]; this
0x180019c00  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x180019c05  mov     rbx, [rsp+48h+arg_8]
0x180019c0a  mov     rsi, [rsp+48h+arg_10]
0x180019c0f  add     rsp, 40h
0x180019c13  pop     rdi
0x180019c14  retn
```
