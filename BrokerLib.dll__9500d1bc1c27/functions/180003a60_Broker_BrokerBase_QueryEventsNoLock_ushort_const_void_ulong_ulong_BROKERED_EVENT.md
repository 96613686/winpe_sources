# Broker::BrokerBase::QueryEventsNoLock(ushort const *,void *,ulong,ulong *,_BROKERED_EVENT * * *)

- ea: `0x180003a60`
- end: `0x180003cca`
- name: `?QueryEventsNoLock@BrokerBase@Broker@@QEAAXPEBGPEAXKPEAKPEAPEAPEAU_BROKERED_EVENT@@@Z`
- size: `618`
- prototype: `void(Broker::BrokerBase *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int *, struct _BROKERED_EVENT ***)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800124b0`

## callees

- `0x180003a60`
- `0x180003cd0`
- `0x180004140`
- `0x180004500`
- `0x180005070`
- `0x18000f210`
- `0x18000f794`
- `0x1800165da`
- `0x18001e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerBase::QueryEventsNoLock(
        Broker::BrokerBase *this,
        const unsigned __int16 *a2,
        char *pSid,
        int a4,
        unsigned int *a5,
        struct _BROKERED_EVENT ***a6)
{
  unsigned int v10; // esi
  unsigned int *v11; // r15
  struct _BROKERED_EVENT ***v12; // r12
  unsigned int *v13; // r9
  __int64 v14; // r9
  _QWORD *v15; // rdx
  __int64 v16; // rcx
  unsigned int *v17; // r14
  __int64 v18; // r9
  _QWORD *i; // rbx
  __int64 v20; // rax
  volatile signed __int32 *v21; // rdi
  __int64 *v22; // rdx
  __int64 v23; // [rsp+0h] [rbp-118h] BYREF
  char v24[16]; // [rsp+30h] [rbp-E8h]
  __int128 v25; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-C8h]
  _QWORD v27[3]; // [rsp+60h] [rbp-B8h] BYREF
  int v28; // [rsp+78h] [rbp-A0h]
  __int128 *v29; // [rsp+80h] [rbp-98h]
  _QWORD v30[4]; // [rsp+90h] [rbp-88h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-68h] BYREF
  void **pExceptionObject; // [rsp+C0h] [rbp-58h] BYREF
  __int128 v33; // [rsp+C8h] [rbp-50h]
  int v34; // [rsp+D8h] [rbp-40h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v18 = *((_QWORD *)this + 1);
    v10 = 0;
    if ( !v18 )
      v18 = 0;
    *(_DWORD *)v24 = a4;
    WPP_SF__guid__sid_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x4Au,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      v18,
      pSid,
      a2,
      *(_QWORD *)v24);
  }
  else
  {
    v10 = 0;
  }
  v11 = a5;
  if ( !a5 || (v12 = a6) == 0 )
  {
    v33 = 0;
    v34 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  v25 = 0;
  v26 = 0;
  v27[0] = this;
  v27[1] = a2;
  v27[2] = pSid;
  v28 = a4;
  v29 = &v25;
  v13 = (unsigned int *)**((_QWORD **)this + 26);
  a5 = v13;
  while ( v13 != *((unsigned int **)this + 26) )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(&a5);
    v15 = std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(&v31, (_QWORD *)(v14 + 40));
    lambda_d904bc99c926903c35d2775759621159_::operator()((__int64)v27, v15);
    v13 = a5;
  }
  v16 = (__int64)(*((_QWORD *)&v25 + 1) - v25) >> 4;
  if ( v16 )
  {
    v17 = (unsigned int *)BciHeapAlloc(8 * v16);
    a5 = v17;
    if ( !v17 )
    {
      v30[2] = 0;
      v30[1] = "bad allocation";
      v30[0] = &std::bad_alloc::`vftable';
      try
      {
        throw (std::bad_alloc *)v30;
      }
      catch ( ... )
      {
        v22 = &v23;
        BciHeapFree((void *)v22[40]);
        throw;
      }
    }
    for ( i = (_QWORD *)v25; i != *((_QWORD **)&v25 + 1); i += 2 )
    {
      v20 = i[1];
      if ( v20 )
        _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
      v21 = (volatile signed __int32 *)i[1];
      *(_QWORD *)&v17[2 * v10++] = *(_QWORD *)(*i + 16LL);
      if ( v21 )
      {
        if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
          if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        }
      }
    }
  }
  else
  {
    v17 = 0;
  }
  *v11 = v10;
  *v12 = (struct _BROKERED_EVENT **)v17;
  std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(&v25);
}

```

## disassembly

```asm
0x180003a60  push    rbx
0x180003a62  push    rsi
0x180003a63  push    rdi
0x180003a64  push    r12
0x180003a66  push    r13
0x180003a68  push    r14
0x180003a6a  push    r15
0x180003a6c  sub     rsp, 0E0h
0x180003a73  mov     edi, r9d
0x180003a76  mov     r14, r8
0x180003a79  mov     r13, rdx
0x180003a7c  mov     rbx, rcx
0x180003a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a86  test    dword ptr [rcx+1Ch], 800h
0x180003a8d  jnz     loc_180003BAB
0x180003a93  xor     esi, esi
0x180003a95  mov     r15, [rsp+118h+arg_20]
0x180003a9d  test    r15, r15
0x180003aa0  jz      short loc_180003AAF
0x180003aa2  mov     r12, [rsp+118h+arg_28]
0x180003aaa  test    r12, r12
0x180003aad  jnz     short loc_180003AE9
0x180003aaf  xorps   xmm0, xmm0
0x180003ab2  movups  [rsp+118h+var_50], xmm0
0x180003aba  mov     [rsp+118h+var_40], 4
0x180003ac5  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180003acc  mov     [rsp+118h+pExceptionObject], rax
0x180003ad4  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180003adb  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180003ae3  call    _CxxThrowException_0
0x180003ae9  xorps   xmm0, xmm0
0x180003aec  movdqu  [rsp+118h+var_D8], xmm0
0x180003af2  mov     [rsp+118h+var_C8], rsi
0x180003af7  mov     [rsp+118h+var_B8], rbx
0x180003afc  mov     [rsp+118h+var_B0], r13
0x180003b01  mov     [rsp+118h+var_A8], r14
0x180003b06  mov     [rsp+118h+var_A0], edi
0x180003b0a  mov     eax, [rsp+118h+var_9C]
0x180003b0e  mov     [rsp+118h+var_9C], eax
0x180003b12  lea     rax, [rsp+118h+var_D8]
0x180003b17  mov     [rsp+118h+var_98], rax
0x180003b1f  mov     r9, [rbx+0D0h]
0x180003b26  mov     r9, [r9]
0x180003b29  mov     [rsp+118h+arg_20], r9
0x180003b31  cmp     r9, [rbx+0D0h]
0x180003b38  jz      short loc_180003B6F
0x180003b3a  lea     rcx, [rsp+118h+arg_20]
0x180003b42  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)
0x180003b47  lea     rdx, [r9+28h]
0x180003b4b  lea     rcx, [rsp+118h+var_68]
0x180003b53  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x180003b58  mov     rdx, rax
0x180003b5b  lea     rcx, [rsp+118h+var_B8]
0x180003b60  call    _lambda_d904bc99c926903c35d2775759621159___operator__
0x180003b65  mov     r9, [rsp+118h+arg_20]
0x180003b6d  jmp     short loc_180003B31
0x180003b6f  mov     rcx, qword ptr [rsp+118h+var_D8+8]
0x180003b74  sub     rcx, qword ptr [rsp+118h+var_D8]
0x180003b79  sar     rcx, 4
0x180003b7d  test    rcx, rcx
0x180003b80  jnz     short loc_180003BEC
0x180003b82  mov     r14, rsi
0x180003b85  jmp     short $+2
0x180003b87  mov     [r15], esi
0x180003b8a  mov     [r12], r14
0x180003b8e  lea     rcx, [rsp+118h+var_D8]
0x180003b93  call    ?_Tidy@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(void)
0x180003b98  add     rsp, 0E0h
0x180003b9f  pop     r15
0x180003ba1  pop     r14
0x180003ba3  pop     r13
0x180003ba5  pop     r12
0x180003ba7  pop     rdi
0x180003ba8  pop     rsi
0x180003ba9  pop     rbx
0x180003baa  retn
0x180003bab  cmp     byte ptr [rcx+19h], 5
0x180003baf  jb      loc_180003A93
0x180003bb5  mov     r9, [rbx+8]
0x180003bb9  xor     esi, esi
0x180003bbb  test    r9, r9
0x180003bbe  jz      loc_180003C83
0x180003bc4  mov     edx, 4Ah ; 'J'
0x180003bc9  mov     dword ptr [rsp+118h+var_E8], edi; char
0x180003bcd  mov     [rsp+118h+var_F0], r13; __int64
0x180003bd2  mov     [rsp+118h+pSid], r14; pSid
0x180003bd7  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180003bde  mov     rcx, [rcx+10h]; LoggerHandle
0x180003be2  call    WPP_SF__guid__sid_Sd
0x180003be7  jmp     loc_180003A95
0x180003bec  lea     rcx, ds:0[rcx*8]; unsigned __int64
0x180003bf4  call    ?BciHeapAlloc@@YAPEAX_K@Z; BciHeapAlloc(unsigned __int64)
0x180003bf9  mov     r14, rax
0x180003bfc  mov     [rsp+118h+arg_20], rax
0x180003c04  test    rax, rax
0x180003c07  jz      loc_180003C8B
0x180003c0d  mov     rbx, qword ptr [rsp+118h+var_D8]
0x180003c12  cmp     rbx, qword ptr [rsp+118h+var_D8+8]
0x180003c17  jz      loc_180003B87
0x180003c1d  mov     rax, [rbx+8]
0x180003c21  test    rax, rax
0x180003c24  jz      short loc_180003C2A
0x180003c26  lock inc dword ptr [rax+8]
0x180003c2a  mov     rdi, [rbx+8]
0x180003c2e  mov     rax, [rbx]
0x180003c31  mov     ecx, esi
0x180003c33  mov     rax, [rax+10h]
0x180003c37  mov     [r14+rcx*8], rax
0x180003c3b  inc     esi
0x180003c3d  test    rdi, rdi
0x180003c40  jz      short loc_180003C7D
0x180003c42  mov     eax, 0FFFFFFFFh
0x180003c47  lock xadd [rdi+8], eax
0x180003c4c  cmp     eax, 1
0x180003c4f  jnz     short loc_180003C7D
0x180003c51  mov     rax, [rdi]
0x180003c54  mov     rcx, rdi
0x180003c57  mov     rax, [rax]
0x180003c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c5f  mov     eax, 0FFFFFFFFh
0x180003c64  lock xadd [rdi+0Ch], eax
0x180003c69  cmp     eax, 1
0x180003c6c  jnz     short loc_180003C7D
0x180003c6e  mov     rax, [rdi]
0x180003c71  mov     rcx, rdi
0x180003c74  mov     rax, [rax+8]
0x180003c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c7d  add     rbx, 10h
0x180003c81  jmp     short loc_180003C12
0x180003c83  mov     r9, rsi
0x180003c86  jmp     loc_180003BC4
0x180003c8b  xorps   xmm0, xmm0
0x180003c8e  movups  [rsp+118h+var_80], xmm0
0x180003c96  lea     rax, aBadAllocation; "bad allocation"
0x180003c9d  mov     qword ptr [rsp+118h+var_80], rax
0x180003ca5  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180003cac  mov     [rsp+118h+var_88], rax
0x180003cb4  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180003cbb  lea     rcx, [rsp+118h+var_88]; pExceptionObject
0x180003cc3  call    _CxxThrowException_0
```
