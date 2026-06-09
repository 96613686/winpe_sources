# Broker::BrokeredEventTable::Remove(std::shared_ptr<Broker::BrokerEvent>)

- ea: `0x180004840`
- end: `0x180004acd`
- name: `?Remove@BrokeredEventTable@Broker@@QEAAXV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z`
- size: `653`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800183bc`
- `0x18001d73f`

## callees

- `0x180004840`
- `0x180004ae0`
- `0x180004e38`
- `0x180005be4`
- `0x180005ee0`
- `0x180006210`
- `0x18001659e`
- `0x1800165da`
- `0x18001e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Broker::BrokeredEventTable::Remove(_QWORD *a1, _QWORD *a2)
{
  const void *v4; // rdi
  __int64 *v5; // r9
  __int64 *v6; // r8
  __int64 *v7; // rbp
  __int64 *v8; // rax
  __int64 *v9; // r14
  __int64 *v10; // rbx
  __int64 *v11; // rsi
  char v12; // cl
  __int64 *v13; // rax
  __int64 v14; // rbx
  std::_Ref_count_base *v15; // rcx
  __int64 *v16; // rsi
  __int64 *v17; // rbx
  __int64 *v18; // rdi
  char v19; // cl
  __int64 *v20; // rax
  __int64 v21; // rbx
  std::_Ref_count_base *v22; // rcx
  __int64 result; // rax
  volatile signed __int32 *v24; // rbx
  __int64 v25; // rbx
  std::_Ref_count_base *v26; // rcx
  void **pExceptionObject; // [rsp+20h] [rbp-68h] BYREF
  __int128 v28; // [rsp+28h] [rbp-60h]
  int v29; // [rsp+38h] [rbp-50h]
  _QWORD *Buf2; // [rsp+98h] [rbp+10h] BYREF

  Buf2 = a2;
  v4 = *(const void **)(*a2 + 16LL);
  v5 = (__int64 *)*a1;
  v6 = *(__int64 **)(*a1 + 8LL);
  DWORD1(v28) = 0;
  v7 = v5;
  if ( !*((_BYTE *)v6 + 25) )
  {
    do
    {
      if ( v6[4] >= (unsigned __int64)v4 )
        v7 = v6;
      v8 = v6 + 2;
      if ( v6[4] >= (unsigned __int64)v4 )
        v8 = v6;
      v6 = (__int64 *)*v8;
    }
    while ( !*(_BYTE *)(*v8 + 25) );
  }
  if ( *((_BYTE *)v7 + 25) || (unsigned __int64)v4 < v7[4] || v7 == v5 )
  {
    v28 = 0;
    v29 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  v9 = (__int64 *)a1[2];
  v10 = (__int64 *)v9[1];
  DWORD1(v28) = 0;
  v11 = v9;
  if ( !*((_BYTE *)v10 + 25) )
  {
    do
    {
      if ( memcmp_0(v10 + 4, v4, 0x10u) < 0 )
      {
        v12 = 1;
      }
      else
      {
        v12 = 0;
        v11 = v10;
      }
      v13 = v10 + 2;
      if ( !v12 )
        v13 = v10;
      v10 = (__int64 *)*v13;
    }
    while ( !*(_BYTE *)(*v13 + 25) );
  }
  if ( !*((_BYTE *)v11 + 25) && memcmp_0(v4, v11 + 4, 0x10u) >= 0 && v11 != v9 )
  {
    v14 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(
            a1 + 2,
            v11);
    v15 = *(std::_Ref_count_base **)(v14 + 56);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    std::_Deallocate<16>(v14, 64);
  }
  Buf2 = *(_QWORD **)(*(_QWORD *)(*a2 + 16LL) + 16LL);
  v16 = (__int64 *)a1[4];
  v17 = (__int64 *)v16[1];
  DWORD1(v28) = 0;
  v18 = v16;
  if ( !*((_BYTE *)v17 + 25) )
  {
    do
    {
      if ( memcmp_0(v17 + 4, &Buf2, 8u) < 0 )
      {
        v19 = 1;
      }
      else
      {
        v19 = 0;
        v18 = v17;
      }
      v20 = v17 + 2;
      if ( !v19 )
        v20 = v17;
      v17 = (__int64 *)*v20;
    }
    while ( !*(_BYTE *)(*v20 + 25) );
  }
  if ( !*((_BYTE *)v18 + 25) && memcmp_0(&Buf2, v18 + 4, 8u) >= 0 && v18 != v16 )
  {
    v25 = std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(
            a1 + 4,
            v18);
    v26 = *(std::_Ref_count_base **)(v25 + 48);
    if ( v26 )
      std::_Ref_count_base::_Decref(v26);
    std::_Deallocate<16>(v25, 56);
  }
  v21 = std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(
          a1,
          v7);
  v22 = *(std::_Ref_count_base **)(v21 + 48);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  result = std::_Deallocate<16>(v21, 56);
  v24 = (volatile signed __int32 *)a2[1];
  if ( v24 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      result = (**(__int64 (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004840  mov     [rsp+Buf2], rdx
0x180004845  push    rbx
0x180004846  push    rbp
0x180004847  push    rsi
0x180004848  push    rdi
0x180004849  push    r12
0x18000484b  push    r13
0x18000484d  push    r14
0x18000484f  push    r15
0x180004851  sub     rsp, 48h
0x180004855  mov     r13, rdx
0x180004858  mov     r12, rcx
0x18000485b  mov     rax, [rdx]
0x18000485e  mov     rdi, [rax+10h]
0x180004862  mov     r9, [rcx]
0x180004865  mov     r8, [r9+8]
0x180004869  xor     eax, eax
0x18000486b  mov     [rsp+88h+var_5C], eax
0x18000486f  mov     rbp, r9
0x180004872  cmp     [r8+19h], al
0x180004876  jnz     short loc_18000489A
0x180004878  nop     dword ptr [rax+rax+00000000h]
0x180004880  cmp     [r8+20h], rdi
0x180004884  cmovnb  rbp, r8
0x180004888  lea     rax, [r8+10h]
0x18000488c  cmovnb  rax, r8
0x180004890  mov     r8, [rax]
0x180004893  cmp     byte ptr [r8+19h], 0
0x180004898  jz      short loc_180004880
0x18000489a  cmp     byte ptr [rbp+19h], 0
0x18000489e  jnz     loc_180004A9F
0x1800048a4  cmp     rdi, [rbp+20h]
0x1800048a8  jb      loc_180004A9F
0x1800048ae  cmp     rbp, r9
0x1800048b1  jz      loc_180004A9F
0x1800048b7  mov     r14, [rcx+10h]
0x1800048bb  mov     rbx, [r14+8]
0x1800048bf  xor     eax, eax
0x1800048c1  mov     [rsp+88h+var_5C], eax
0x1800048c5  mov     rsi, r14
0x1800048c8  cmp     [rbx+19h], al
0x1800048cb  jnz     short loc_180004902
0x1800048cd  nop     dword ptr [rax]
0x1800048d0  lea     rcx, [rbx+20h]; Buf1
0x1800048d4  mov     r8d, 10h; Size
0x1800048da  mov     rdx, rdi; Buf2
0x1800048dd  call    memcmp_0
0x1800048e2  test    eax, eax
0x1800048e4  js      loc_180004A58
0x1800048ea  xor     cl, cl
0x1800048ec  mov     rsi, rbx
0x1800048ef  lea     rax, [rbx+10h]
0x1800048f3  test    cl, cl
0x1800048f5  cmovz   rax, rbx
0x1800048f9  mov     rbx, [rax]
0x1800048fc  cmp     byte ptr [rbx+19h], 0
0x180004900  jz      short loc_1800048D0
0x180004902  cmp     byte ptr [rsi+19h], 0
0x180004906  jnz     short loc_18000494E
0x180004908  lea     rdx, [rsi+20h]; Buf2
0x18000490c  mov     r8d, 10h; Size
0x180004912  mov     rcx, rdi; Buf1
0x180004915  call    memcmp_0
0x18000491a  test    eax, eax
0x18000491c  js      short loc_18000494E
0x18000491e  cmp     rsi, r14
0x180004921  jz      short loc_18000494E
0x180004923  mov     rdx, rsi
0x180004926  lea     rcx, [r12+10h]
0x18000492b  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>)
0x180004930  mov     rbx, rax
0x180004933  mov     rcx, [rax+38h]; this
0x180004937  test    rcx, rcx
0x18000493a  jz      short loc_180004941
0x18000493c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004941  mov     edx, 40h ; '@'
0x180004946  mov     rcx, rbx
0x180004949  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000494e  mov     rax, [r13+0]
0x180004952  mov     rcx, [rax+10h]
0x180004956  mov     rax, [rcx+10h]
0x18000495a  mov     [rsp+88h+Buf2], rax
0x180004962  mov     rsi, [r12+20h]
0x180004967  mov     rbx, [rsi+8]
0x18000496b  xor     eax, eax
0x18000496d  mov     [rsp+88h+var_5C], eax
0x180004971  mov     rdi, rsi
0x180004974  cmp     [rbx+19h], al
0x180004977  jnz     short loc_1800049B7
0x180004979  nop     dword ptr [rax+00000000h]
0x180004980  lea     rcx, [rbx+20h]; Buf1
0x180004984  mov     r8d, 8; Size
0x18000498a  lea     rdx, [rsp+88h+Buf2]; Buf2
0x180004992  call    memcmp_0
0x180004997  test    eax, eax
0x180004999  js      loc_180004A5F
0x18000499f  xor     cl, cl
0x1800049a1  mov     rdi, rbx
0x1800049a4  lea     rax, [rbx+10h]
0x1800049a8  test    cl, cl
0x1800049aa  cmovz   rax, rbx
0x1800049ae  mov     rbx, [rax]
0x1800049b1  cmp     byte ptr [rbx+19h], 0
0x1800049b5  jz      short loc_180004980
0x1800049b7  cmp     byte ptr [rdi+19h], 0
0x1800049bb  jnz     short loc_1800049DC
0x1800049bd  lea     rdx, [rdi+20h]; Buf2
0x1800049c1  mov     r8d, 8; Size
0x1800049c7  lea     rcx, [rsp+88h+Buf2]; Buf1
0x1800049cf  call    memcmp_0
0x1800049d4  test    eax, eax
0x1800049d6  jns     loc_180004A66
0x1800049dc  mov     rdx, rbp
0x1800049df  mov     rcx, r12
0x1800049e2  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>)
0x1800049e7  mov     rbx, rax
0x1800049ea  mov     rcx, [rax+30h]; this
0x1800049ee  test    rcx, rcx
0x1800049f1  jz      short loc_1800049F8
0x1800049f3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800049f8  mov     edx, 38h ; '8'
0x1800049fd  mov     rcx, rbx
0x180004a00  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004a05  nop
0x180004a06  mov     rbx, [r13+8]
0x180004a0a  test    rbx, rbx
0x180004a0d  jz      short loc_180004A47
0x180004a0f  mov     edi, 0FFFFFFFFh
0x180004a14  mov     eax, edi
0x180004a16  lock xadd [rbx+8], eax
0x180004a1b  cmp     eax, 1
0x180004a1e  jnz     short loc_180004A47
0x180004a20  mov     rax, [rbx]
0x180004a23  mov     rcx, rbx
0x180004a26  mov     rax, [rax]
0x180004a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a2e  lock xadd [rbx+0Ch], edi
0x180004a33  cmp     edi, 1
0x180004a36  jnz     short loc_180004A47
0x180004a38  mov     rax, [rbx]
0x180004a3b  mov     rcx, rbx
0x180004a3e  mov     rax, [rax+8]
0x180004a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a47  add     rsp, 48h
0x180004a4b  pop     r15
0x180004a4d  pop     r14
0x180004a4f  pop     r13
0x180004a51  pop     r12
0x180004a53  pop     rdi
0x180004a54  pop     rsi
0x180004a55  pop     rbp
0x180004a56  pop     rbx
0x180004a57  retn
0x180004a58  mov     cl, 1
0x180004a5a  jmp     loc_1800048EF
0x180004a5f  mov     cl, 1
0x180004a61  jmp     loc_1800049A4
0x180004a66  cmp     rdi, rsi
0x180004a69  jz      loc_1800049DC
0x180004a6f  mov     rdx, rdi
0x180004a72  lea     rcx, [r12+20h]
0x180004a77  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>)
0x180004a7c  mov     rbx, rax
0x180004a7f  mov     rcx, [rax+30h]; this
0x180004a83  test    rcx, rcx
0x180004a86  jz      short loc_180004A8D
0x180004a88  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004a8d  mov     edx, 38h ; '8'
0x180004a92  mov     rcx, rbx
0x180004a95  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004a9a  jmp     loc_1800049DC
0x180004a9f  xorps   xmm0, xmm0
0x180004aa2  movups  xmmword ptr [rsp+28h], xmm0
0x180004aa7  mov     [rsp+88h+var_50], 3
0x180004aaf  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180004ab6  mov     [rsp+88h+pExceptionObject], rax
0x180004abb  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180004ac2  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180004ac7  call    _CxxThrowException_0
```
