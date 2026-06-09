# Broker::BrokerEventTable_CBroker::SebEvent_::FindFirst__lambda_cbeaae26278add60d0c1457e76ea093d___

- ea: `0x18001ae14`
- end: `0x18001aed2`
- name: `Broker::BrokerEventTable_CBroker::SebEvent_::FindFirst__lambda_cbeaae26278add60d0c1457e76ea093d___`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ad04`

## callees

- `0x1800076a0`
- `0x1800133c0`
- `0x180013860`
- `0x1800145c0`
- `0x18001ae14`

## pseudocode

```c
_QWORD *__fastcall Broker::BrokerEventTable_CBroker::SebEvent_::FindFirst__lambda_cbeaae26278add60d0c1457e76ea093d___(
        __int64 ***a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v6; // rax
  _QWORD *v7; // rbp
  _QWORD *v8; // rdi
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rcx
  _QWORD v12[5]; // [rsp+20h] [rbp-28h] BYREF
  __int64 *i; // [rsp+50h] [rbp+8h] BYREF

  v6 = **a1;
  for ( i = v6; ; v6 = i )
  {
    if ( v6 == (__int64 *)*a1 )
    {
      *a2 = 0;
      a2[1] = 0;
      return a2;
    }
    v7 = v6 + 6;
    v8 = std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(v12, v6 + 6);
    if ( !Broker::ApplicationIdentity::operator!=(*v8 + 8LL, *(_QWORD *)(a3 + 8))
      && *(_DWORD *)(*v8 + 96LL) == *(_DWORD *)(a3 + 16) )
    {
      break;
    }
    v9 = (std::_Ref_count_base *)v8[1];
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>,std::_Iterator_base0>::operator++(&i);
  }
  v10 = (std::_Ref_count_base *)v8[1];
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(a2, v7);
  return a2;
}

```

## disassembly

```asm
0x18001ae14  mov     [rsp+arg_8], rbx
0x18001ae19  mov     [rsp+arg_10], rbp
0x18001ae1e  push    rsi
0x18001ae1f  push    rdi
0x18001ae20  push    r14
0x18001ae22  sub     rsp, 30h
0x18001ae26  mov     rax, [rcx]
0x18001ae29  mov     r14, r8
0x18001ae2c  mov     rbx, rdx
0x18001ae2f  mov     rsi, rcx
0x18001ae32  mov     rax, [rax]
0x18001ae35  mov     [rsp+48h+arg_0], rax
0x18001ae3a  cmp     rax, [rsi]
0x18001ae3d  jz      short loc_18001AEAD
0x18001ae3f  lea     rbp, [rax+30h]
0x18001ae43  mov     rdx, rbp
0x18001ae46  lea     rcx, [rsp+48h+var_28]
0x18001ae4b  call    ??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)
0x18001ae50  mov     rdx, [r14+8]
0x18001ae54  mov     rdi, rax
0x18001ae57  mov     rcx, [rax]
0x18001ae5a  add     rcx, 8
0x18001ae5e  call    ??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z; Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)
0x18001ae63  test    al, al
0x18001ae65  jnz     short loc_18001AE73
0x18001ae67  mov     rdx, [rdi]
0x18001ae6a  mov     ecx, [r14+10h]
0x18001ae6e  cmp     [rdx+60h], ecx
0x18001ae71  jz      short loc_18001AE92
0x18001ae73  mov     rcx, [rdi+8]; this
0x18001ae77  test    rcx, rcx
0x18001ae7a  jz      short loc_18001AE81
0x18001ae7c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ae81  lea     rcx, [rsp+48h+arg_0]
0x18001ae86  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>,std::_Iterator_base0>::operator++(void)
0x18001ae8b  mov     rax, [rsp+48h+arg_0]
0x18001ae90  jmp     short loc_18001AE3A
0x18001ae92  mov     rcx, [rdi+8]; this
0x18001ae96  test    rcx, rcx
0x18001ae99  jz      short loc_18001AEA0
0x18001ae9b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001aea0  mov     rdx, rbp
0x18001aea3  mov     rcx, rbx
0x18001aea6  call    ??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)
0x18001aeab  jmp     short loc_18001AEBC
0x18001aead  mov     qword ptr [rbx], 0
0x18001aeb4  mov     qword ptr [rbx+8], 0
0x18001aebc  mov     rbp, [rsp+48h+arg_10]
0x18001aec1  mov     rax, rbx
0x18001aec4  mov     rbx, [rsp+48h+arg_8]
0x18001aec9  add     rsp, 30h
0x18001aecd  pop     r14
0x18001aecf  pop     rdi
0x18001aed0  pop     rsi
0x18001aed1  retn
```
