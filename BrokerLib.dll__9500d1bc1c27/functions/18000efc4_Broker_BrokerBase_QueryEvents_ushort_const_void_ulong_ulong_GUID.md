# Broker::BrokerBase::QueryEvents(ushort const *,void *,ulong,ulong *,_GUID * *)

- ea: `0x18000efc4`
- end: `0x18000f209`
- name: `?QueryEvents@BrokerBase@Broker@@QEAAXPEBGPEAXKPEAKPEAPEAU_GUID@@@Z`
- size: `581`
- prototype: `void(Broker::BrokerBase *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012300`

## callees

- `0x180003cd0`
- `0x180003db0`
- `0x180004500`
- `0x180004ae0`
- `0x180005070`
- `0x18000efc4`
- `0x18000f210`
- `0x18000f794`
- `0x1800165da`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000f14b`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f14b`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000f029`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000f029`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Broker::BrokerBase::QueryEvents(
        Broker::BrokerBase *this,
        const unsigned __int16 *a2,
        char *pSid,
        int a4,
        unsigned int *a5,
        struct _GUID **a6)
{
  unsigned int *v10; // r12
  struct _GUID **v11; // r15
  unsigned int *v12; // r9
  __int64 v13; // r9
  _QWORD *v14; // rdx
  unsigned int v15; // r14d
  __int64 v16; // rcx
  struct _GUID *v17; // rsi
  _QWORD *v18; // rbx
  unsigned int *v19; // rax
  __int128 v20; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-D8h]
  __int64 v22; // [rsp+58h] [rbp-D0h] BYREF
  std::_Ref_count_base *v23; // [rsp+60h] [rbp-C8h]
  _QWORD v24[3]; // [rsp+70h] [rbp-B8h] BYREF
  int v25; // [rsp+88h] [rbp-A0h]
  __int128 *v26; // [rsp+90h] [rbp-98h]
  _QWORD v27[4]; // [rsp+A0h] [rbp-88h] BYREF
  char v28; // [rsp+C0h] [rbp-68h]
  void **pExceptionObject; // [rsp+C8h] [rbp-60h] BYREF
  __int128 v30; // [rsp+D0h] [rbp-58h]
  int v31; // [rsp+E0h] [rbp-48h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid__sid_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x49u,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1),
      pSid,
      a2,
      a4);
  v27[3] = this;
  RtlAcquireSRWLockShared(this);
  v28 = 1;
  v10 = a5;
  if ( !a5 || (v11 = a6) == 0 )
  {
    v30 = 0;
    v31 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  v20 = 0;
  v21 = 0;
  v24[0] = this;
  v24[1] = a2;
  v24[2] = pSid;
  v25 = a4;
  v26 = &v20;
  v12 = (unsigned int *)**((_QWORD **)this + 26);
  a5 = v12;
  while ( v12 != *((unsigned int **)this + 26) )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(&a5);
    v14 = std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(&v22, (_QWORD *)(v13 + 40));
    lambda_46d4d6d60962dc4f8846c758390ed2fa_::operator()((__int64)v24, v14);
    v12 = a5;
  }
  v15 = 0;
  v16 = (__int64)(*((_QWORD *)&v20 + 1) - v20) >> 4;
  if ( v16 )
  {
    v19 = (unsigned int *)BciHeapAlloc(16 * v16);
    try
    {
      v17 = (struct _GUID *)v19;
      a5 = v19;
      if ( !v19 )
      {
        v27[2] = 0;
        v27[1] = "bad allocation";
        v27[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)v27;
      }
      v18 = (_QWORD *)v20;
    }
    catch ( ... )
    {
      BciHeapFree(a5);
      throw;
    }
    while ( v18 != *((_QWORD **)&v20 + 1) )
    {
      std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(&v22, v18);
      v17[v15++] = *(struct _GUID *)*(_QWORD *)(v22 + 16);
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
      v18 += 2;
    }
  }
  else
  {
    v17 = 0;
  }
  *v10 = v15;
  *v11 = v17;
  std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(&v20);
  RtlReleaseSRWLockShared(this);
}

```

## disassembly

```asm
0x18000efc4  push    rbx
0x18000efc6  push    rsi
0x18000efc7  push    rdi
0x18000efc8  push    r12
0x18000efca  push    r14
0x18000efcc  push    r15
0x18000efce  sub     rsp, 0F8h
0x18000efd5  mov     ebx, r9d
0x18000efd8  mov     rsi, r8
0x18000efdb  mov     r14, rdx
0x18000efde  mov     rdi, rcx
0x18000efe1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efe8  test    dword ptr [rcx+1Ch], 800h
0x18000efef  jz      short loc_18000F01E
0x18000eff1  cmp     byte ptr [rcx+19h], 5
0x18000eff5  jb      short loc_18000F01E
0x18000eff7  mov     edx, 49h ; 'I'
0x18000effc  mov     dword ptr [rsp+128h+var_F8], ebx; char
0x18000f000  mov     [rsp+128h+var_100], r14; __int64
0x18000f005  mov     [rsp+128h+pSid], r8; pSid
0x18000f00a  mov     r9, [rdi+8]
0x18000f00e  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000f015  mov     rcx, [rcx+10h]; LoggerHandle
0x18000f019  call    WPP_SF__guid__sid_Sd
0x18000f01e  mov     [rsp+128h+var_70], rdi
0x18000f026  mov     rcx, rdi
0x18000f029  call    cs:__imp_RtlAcquireSRWLockShared
0x18000f02f  mov     [rsp+128h+var_68], 1
0x18000f037  mov     r12, [rsp+128h+arg_20]
0x18000f03f  test    r12, r12
0x18000f042  jz      short loc_18000F051
0x18000f044  mov     r15, [rsp+128h+arg_28]
0x18000f04c  test    r15, r15
0x18000f04f  jnz     short loc_18000F08B
0x18000f051  xorps   xmm0, xmm0
0x18000f054  movups  [rsp+128h+var_58], xmm0
0x18000f05c  mov     [rsp+128h+var_48], 4
0x18000f067  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18000f06e  mov     [rsp+128h+pExceptionObject], rax
0x18000f076  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000f07d  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18000f085  call    _CxxThrowException_0
0x18000f08b  xorps   xmm0, xmm0
0x18000f08e  movdqu  [rsp+128h+var_E8], xmm0
0x18000f094  mov     [rsp+128h+var_D8], 0
0x18000f09d  mov     [rsp+128h+var_B8], rdi
0x18000f0a2  mov     [rsp+128h+var_B0], r14
0x18000f0a7  mov     [rsp+128h+var_A8], rsi
0x18000f0af  mov     [rsp+128h+var_A0], ebx
0x18000f0b6  mov     eax, [rsp+128h+var_9C]
0x18000f0bd  mov     [rsp+128h+var_9C], eax
0x18000f0c4  lea     rax, [rsp+128h+var_E8]
0x18000f0c9  mov     [rsp+128h+var_98], rax
0x18000f0d1  mov     r9, [rdi+0D0h]
0x18000f0d8  mov     r9, [r9]
0x18000f0db  mov     [rsp+128h+arg_20], r9
0x18000f0e3  cmp     r9, [rdi+0D0h]
0x18000f0ea  jz      short loc_18000F11E
0x18000f0ec  lea     rcx, [rsp+128h+arg_20]
0x18000f0f4  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)
0x18000f0f9  lea     rdx, [r9+28h]
0x18000f0fd  lea     rcx, [rsp+128h+var_D0]
0x18000f102  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x18000f107  mov     rdx, rax
0x18000f10a  lea     rcx, [rsp+128h+var_B8]
0x18000f10f  call    _lambda_46d4d6d60962dc4f8846c758390ed2fa___operator__
0x18000f114  mov     r9, [rsp+128h+arg_20]
0x18000f11c  jmp     short loc_18000F0E3
0x18000f11e  xor     r14d, r14d
0x18000f121  mov     rcx, qword ptr [rsp+128h+var_E8+8]
0x18000f126  sub     rcx, qword ptr [rsp+128h+var_E8]
0x18000f12b  sar     rcx, 4
0x18000f12f  test    rcx, rcx
0x18000f132  jnz     short loc_18000F1A7
0x18000f134  xor     esi, esi
0x18000f136  mov     [r12], r14d
0x18000f13a  mov     [r15], rsi
0x18000f13d  lea     rcx, [rsp+128h+var_E8]
0x18000f142  call    ?_Tidy@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(void)
0x18000f147  nop
0x18000f148  mov     rcx, rdi
0x18000f14b  call    cs:__imp_RtlReleaseSRWLockShared
0x18000f151  add     rsp, 0F8h
0x18000f158  pop     r15
0x18000f15a  pop     r14
0x18000f15c  pop     r12
0x18000f15e  pop     rdi
0x18000f15f  pop     rsi
0x18000f160  pop     rbx
0x18000f161  retn
0x18000f162  cmp     rbx, qword ptr [rsp+128h+var_E8+8]
0x18000f167  jz      short loc_18000F1A5
0x18000f169  mov     rdx, rbx
0x18000f16c  lea     rcx, [rsp+128h+var_D0]
0x18000f171  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x18000f176  mov     rcx, [rsp+128h+var_D0]
0x18000f17b  mov     rax, [rcx+10h]
0x18000f17f  mov     ecx, r14d
0x18000f182  add     rcx, rcx
0x18000f185  movups  xmm0, xmmword ptr [rax]
0x18000f188  movdqu  xmmword ptr [rsi+rcx*8], xmm0
0x18000f18d  inc     r14d
0x18000f190  mov     rcx, [rsp+128h+var_C8]; this
0x18000f195  test    rcx, rcx
0x18000f198  jz      short loc_18000F19F
0x18000f19a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f19f  add     rbx, 10h
0x18000f1a3  jmp     short loc_18000F162
0x18000f1a5  jmp     short loc_18000F136
0x18000f1a7  shl     rcx, 4; unsigned __int64
0x18000f1ab  call    ?BciHeapAlloc@@YAPEAX_K@Z; BciHeapAlloc(unsigned __int64)
0x18000f1b0  mov     rsi, rax
0x18000f1b3  mov     [rsp+128h+arg_20], rax
0x18000f1bb  test    rax, rax
0x18000f1be  jnz     short loc_18000F1FD
0x18000f1c0  xorps   xmm0, xmm0
0x18000f1c3  movups  [rsp+128h+var_80], xmm0
0x18000f1cb  lea     rax, aBadAllocation; "bad allocation"
0x18000f1d2  mov     qword ptr [rsp+128h+var_80], rax
0x18000f1da  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000f1e1  mov     [rsp+128h+var_88], rax
0x18000f1e9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f1f0  lea     rcx, [rsp+128h+var_88]; pExceptionObject
0x18000f1f8  call    _CxxThrowException_0
0x18000f1fd  mov     rbx, qword ptr [rsp+128h+var_E8]
0x18000f202  jmp     loc_18000F162
```
