# Broker::BrokerEventTable_CBroker::SebEvent_::ForEach__lambda_1f13a272e36841c663cc19eb81071f3b___

- ea: `0x180020220`
- end: `0x1800202c8`
- name: `Broker::BrokerEventTable_CBroker::SebEvent_::ForEach__lambda_1f13a272e36841c663cc19eb81071f3b___`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001b80c`

## callees

- `0x1800076a0`
- `0x1800133c0`
- `0x180013860`
- `0x1800145c0`
- `0x18001b1f4`
- `0x180020220`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerEventTable_CBroker::SebEvent_::ForEach__lambda_1f13a272e36841c663cc19eb81071f3b___(
        __int64 ***a1,
        __int64 a2)
{
  __int64 v4; // r9
  _QWORD *v5; // rbx
  __int64 v6; // rcx
  _OWORD *v7; // rdx
  std::_Ref_count_base *v8; // rcx
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  __int64 *v10; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v11; // [rsp+50h] [rbp+18h]

  v10 = **a1;
  while ( v10 != (__int64 *)*a1 )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>,std::_Iterator_base0>::operator++(&v10);
    v5 = std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(v9, (_QWORD *)(v4 + 48));
    v11 = v5;
    if ( !Broker::ApplicationIdentity::operator!=(*v5 + 8LL, *(_QWORD *)(a2 + 8)) )
    {
      v6 = *(_QWORD *)(a2 + 16);
      v7 = *(_OWORD **)(v6 + 8);
      if ( v7 == *(_OWORD **)(v6 + 16) )
      {
        std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v6);
      }
      else
      {
        *v7 = *(_OWORD *)(*v5 + 120LL);
        *(_QWORD *)(v6 + 8) += 16LL;
      }
    }
    v8 = (std::_Ref_count_base *)v5[1];
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
  }
}

```

## disassembly

```asm
0x180020220  mov     [rsp+arg_8], rbx
0x180020225  mov     [rsp+arg_18], rsi
0x18002022a  push    rdi
0x18002022b  sub     rsp, 30h
0x18002022f  mov     rsi, rdx
0x180020232  mov     rdi, rcx
0x180020235  mov     rax, [rcx]
0x180020238  mov     r8, [rax]
0x18002023b  mov     [rsp+38h+arg_0], r8
0x180020240  mov     r9, [rsp+38h+arg_0]
0x180020245  cmp     r9, [rdi]
0x180020248  jz      short loc_1800202B8
0x18002024a  lea     rcx, [rsp+38h+arg_0]
0x18002024f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>,std::_Iterator_base0>::operator++(void)
0x180020254  lea     rdx, [r9+30h]
0x180020258  lea     rcx, [rsp+38h+var_18]
0x18002025d  call    ??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)
0x180020262  mov     rbx, rax
0x180020265  mov     [rsp+38h+arg_10], rax
0x18002026a  mov     rcx, [rax]
0x18002026d  add     rcx, 8
0x180020271  mov     rdx, [rsi+8]
0x180020275  call    ??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z; Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)
0x18002027a  test    al, al
0x18002027c  jnz     short loc_1800202A8
0x18002027e  mov     rcx, [rsi+10h]
0x180020282  mov     r8, [rbx]
0x180020285  add     r8, 78h ; 'x'
0x180020289  mov     rdx, [rcx+8]
0x18002028d  cmp     rdx, [rcx+10h]
0x180020291  jz      short loc_1800202A2
0x180020293  movups  xmm0, xmmword ptr [r8]
0x180020297  movdqu  xmmword ptr [rdx], xmm0
0x18002029b  add     qword ptr [rcx+8], 10h
0x1800202a0  jmp     short loc_1800202A8
0x1800202a2  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x1800202a7  nop
0x1800202a8  mov     rcx, [rbx+8]; this
0x1800202ac  test    rcx, rcx
0x1800202af  jz      short loc_180020240
0x1800202b1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800202b6  jmp     short loc_180020240
0x1800202b8  mov     rbx, [rsp+38h+arg_8]
0x1800202bd  mov     rsi, [rsp+38h+arg_18]
0x1800202c2  add     rsp, 30h
0x1800202c6  pop     rdi
0x1800202c7  retn
```
