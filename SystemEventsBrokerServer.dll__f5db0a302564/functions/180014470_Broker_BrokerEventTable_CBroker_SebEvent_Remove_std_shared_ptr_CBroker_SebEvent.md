# Broker::BrokerEventTable<CBroker::SebEvent>::Remove(std::shared_ptr<CBroker::SebEvent>)

- ea: `0x180014470`
- end: `0x1800145ae`
- name: `?Remove@?$BrokerEventTable@VSebEvent@CBroker@@@Broker@@QEAAXV?$shared_ptr@VSebEvent@CBroker@@@std@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b378`

## callees

- `0x1800076a0`
- `0x18000c3a0`
- `0x180014470`
- `0x18001d364`
- `0x18001d9ac`
- `0x180022434`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerEventTable<CBroker::SebEvent>::Remove(__int64 **a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 *v5; // rbp
  __int64 v6; // rbx
  __int64 v7; // rsi
  char v8; // cl
  __int64 *v9; // rax
  _QWORD *v10; // rbx
  std::_Ref_count_base *v11; // rcx
  volatile signed __int32 *v12; // rbx
  void **pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  __int128 v14; // [rsp+28h] [rbp-50h]
  int v15; // [rsp+38h] [rbp-40h]

  v4 = *a2;
  v5 = *a1;
  v6 = (*a1)[1];
  DWORD1(v14) = 0;
  v7 = (__int64)v5;
  if ( !*(_BYTE *)(v6 + 25) )
  {
    do
    {
      if ( memcmp_0((const void *)(v6 + 32), (const void *)(v4 + 120), 0x10u) >= 0 )
      {
        v8 = 0;
        v7 = v6;
      }
      else
      {
        v8 = 1;
      }
      v9 = (__int64 *)(v6 + 16);
      if ( !v8 )
        v9 = (__int64 *)v6;
      v6 = *v9;
    }
    while ( !*(_BYTE *)(*v9 + 25) );
  }
  if ( *(_BYTE *)(v7 + 25)
    || memcmp_0((const void *)(v4 + 120), (const void *)(v7 + 32), 0x10u) < 0
    || (__int64 *)v7 == v5 )
  {
    v14 = 0;
    v15 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  v10 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>::_Extract(
          a1,
          (_QWORD *)v7);
  v11 = (std::_Ref_count_base *)v10[7];
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  operator delete(v10);
  v12 = (volatile signed __int32 *)a2[1];
  if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
    if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
  }
}

```

## disassembly

```asm
0x180014470  mov     [rsp+arg_8], rdx
0x180014475  push    rbx
0x180014476  push    rbp
0x180014477  push    rsi
0x180014478  push    rdi
0x180014479  push    r14
0x18001447b  push    r15
0x18001447d  sub     rsp, 48h
0x180014481  mov     r14, rdx
0x180014484  mov     r15, rcx
0x180014487  mov     rdi, [rdx]
0x18001448a  mov     rbp, [rcx]
0x18001448d  mov     rbx, [rbp+8]
0x180014491  xor     eax, eax
0x180014493  mov     [rsp+78h+var_4C], eax
0x180014497  mov     rsi, rbp
0x18001449a  cmp     [rbx+19h], al
0x18001449d  jnz     short loc_1800144D0
0x18001449f  nop
0x1800144a0  lea     rcx, [rbx+20h]; Buf1
0x1800144a4  mov     r8d, 10h; Size
0x1800144aa  lea     rdx, [rdi+78h]; Buf2
0x1800144ae  call    memcmp_0
0x1800144b3  test    eax, eax
0x1800144b5  jns     loc_180014576
0x1800144bb  mov     cl, 1
0x1800144bd  lea     rax, [rbx+10h]
0x1800144c1  test    cl, cl
0x1800144c3  cmovz   rax, rbx
0x1800144c7  mov     rbx, [rax]
0x1800144ca  cmp     byte ptr [rbx+19h], 0
0x1800144ce  jz      short loc_1800144A0
0x1800144d0  cmp     byte ptr [rsi+19h], 0
0x1800144d4  jnz     loc_180014580
0x1800144da  lea     rdx, [rsi+20h]; Buf2
0x1800144de  mov     r8d, 10h; Size
0x1800144e4  lea     rcx, [rdi+78h]; Buf1
0x1800144e8  call    memcmp_0
0x1800144ed  test    eax, eax
0x1800144ef  js      loc_180014580
0x1800144f5  cmp     rsi, rbp
0x1800144f8  jz      loc_180014580
0x1800144fe  mov     rdx, rsi
0x180014501  mov     rcx, r15
0x180014504  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>,std::_Iterator_base0>)
0x180014509  mov     rbx, rax
0x18001450c  mov     rcx, [rax+38h]; this
0x180014510  test    rcx, rcx
0x180014513  jz      short loc_18001451A
0x180014515  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001451a  mov     edx, 40h ; '@'; unsigned __int64
0x18001451f  mov     rcx, rbx; void *
0x180014522  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014527  nop
0x180014528  mov     rbx, [r14+8]
0x18001452c  test    rbx, rbx
0x18001452f  jz      short loc_180014569
0x180014531  mov     edi, 0FFFFFFFFh
0x180014536  mov     eax, edi
0x180014538  lock xadd [rbx+8], eax
0x18001453d  cmp     eax, 1
0x180014540  jnz     short loc_180014569
0x180014542  mov     rax, [rbx]
0x180014545  mov     rcx, rbx
0x180014548  mov     rax, [rax]
0x18001454b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014550  lock xadd [rbx+0Ch], edi
0x180014555  cmp     edi, 1
0x180014558  jnz     short loc_180014569
0x18001455a  mov     rax, [rbx]
0x18001455d  mov     rcx, rbx
0x180014560  mov     rax, [rax+8]
0x180014564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014569  add     rsp, 48h
0x18001456d  pop     r15
0x18001456f  pop     r14
0x180014571  pop     rdi
0x180014572  pop     rsi
0x180014573  pop     rbp
0x180014574  pop     rbx
0x180014575  retn
0x180014576  xor     cl, cl
0x180014578  mov     rsi, rbx
0x18001457b  jmp     loc_1800144BD
0x180014580  xorps   xmm0, xmm0
0x180014583  movups  xmmword ptr [rsp+28h], xmm0
0x180014588  mov     [rsp+78h+var_40], 3
0x180014590  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180014597  mov     [rsp+78h+pExceptionObject], rax
0x18001459c  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x1800145a3  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800145a8  call    _CxxThrowException_0
```
