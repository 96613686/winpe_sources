# Broker::BrokerBase::DestroyInstance(_BROKER *)

- ea: `0x18001364c`
- end: `0x1800137dd`
- name: `?DestroyInstance@BrokerBase@Broker@@SAXPEAU_BROKER@@@Z`
- size: `401`
- prototype: `void __fastcall(struct _BROKER *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012220`

## callees

- `0x180004ae0`
- `0x1800058e0`
- `0x18000a3a0`
- `0x18000b080`
- `0x18000b3a4`
- `0x18000f42c`
- `0x1800109b4`
- `0x18001364c`
- `0x180015470`
- `0x180017828`
- `0x1800178c8`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800136b9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800136dd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800136b9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800136dd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013750`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800137a8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800137b2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013750`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800137a8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800137b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800136bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800136e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800136bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800136e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Broker::BrokerBase::DestroyInstance(struct _BROKER *a1)
{
  char v2; // di
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // edx
  _BROKER *v8; // rcx
  Broker::BrokerBase *v9; // [rsp+40h] [rbp-10h] BYREF
  std::_Ref_count_base *v10; // [rsp+48h] [rbp-8h]
  struct _BROKER *v11; // [rsp+70h] [rbp+20h] BYREF
  __int64 v12; // [rsp+78h] [rbp+28h] BYREF

  v11 = a1;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids);
  Broker::BrokerBase::GetInstance(&v9, a1);
  Broker::BrokerBase::UninitializeBroker(v9);
  RtlAcquireSRWLockExclusive(&Broker::g_BrokerInterfaceLock);
  GetCurrentThreadId();
  v2 = 1;
  RtlAcquireSRWLockExclusive(&Broker::g_BrokersLock);
  GetCurrentThreadId();
  std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::find(
    v3,
    &v12,
    a1);
  if ( v12 != Broker::g_Brokers )
  {
    v4 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>>::_Extract(&Broker::g_Brokers);
    std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>>>(
      v5,
      v4);
    if ( (_QWORD)xmmword_180028998 == *((_QWORD *)&xmmword_180028998 + 1) )
    {
      std::vector<_BROKER *>::_Emplace_reallocate<_BROKER * const &>(v6, xmmword_180028998, &v11);
    }
    else
    {
      *(_QWORD *)xmmword_180028998 = a1;
      *(_QWORD *)&xmmword_180028998 = xmmword_180028998 + 8;
    }
  }
  if ( !qword_180028988 )
  {
    RtlReleaseSRWLockExclusive(&Broker::g_BrokersLock);
    v2 = 0;
    if ( Broker::BrokerBase::RpcIf )
    {
      Broker::RpcIfRegistration::`scalar deleting destructor'(Broker::BrokerBase::RpcIf, v7);
      Broker::BrokerBase::RpcIf = 0;
    }
    while ( Broker::g_DeletedBrokers != (void *)xmmword_180028998 )
    {
      v8 = *(_BROKER **)(xmmword_180028998 - 8);
      *(_QWORD *)&xmmword_180028998 = xmmword_180028998 - 8;
      if ( v8 )
        _BROKER::`scalar deleting destructor'(v8, v7);
    }
  }
  if ( v2 )
    RtlReleaseSRWLockExclusive(&Broker::g_BrokersLock);
  RtlReleaseSRWLockExclusive(&Broker::g_BrokerInterfaceLock);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
}

```

## disassembly

```asm
0x18001364c  mov     [rsp-18h+arg_10], rbx
0x180013651  mov     [rsp-18h+arg_18], rdi
0x180013656  mov     [rsp-18h+arg_0], rcx
0x18001365b  push    rbp
0x18001365c  push    r14
0x18001365e  push    r15
0x180013660  mov     rbp, rsp
0x180013663  sub     rsp, 50h
0x180013667  mov     rbx, rcx
0x18001366a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013671  test    dword ptr [rcx+1Ch], 800h
0x180013678  jz      short loc_180013695
0x18001367a  cmp     byte ptr [rcx+19h], 5
0x18001367e  jb      short loc_180013695
0x180013680  mov     edx, 0Bh
0x180013685  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18001368c  mov     rcx, [rcx+10h]
0x180013690  call    WPP_SF_
0x180013695  mov     rdx, rbx
0x180013698  lea     rcx, [rbp+var_10]
0x18001369c  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x1800136a1  nop
0x1800136a2  mov     rcx, [rbp+var_10]; this
0x1800136a6  call    ?UninitializeBroker@BrokerBase@Broker@@QEAAXXZ; Broker::BrokerBase::UninitializeBroker(void)
0x1800136ab  lea     r15, ?g_BrokerInterfaceLock@Broker@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Broker::g_BrokerInterfaceLock
0x1800136b2  mov     [rbp+var_30], r15
0x1800136b6  mov     rcx, r15
0x1800136b9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800136bf  call    cs:__imp_GetCurrentThreadId
0x1800136c5  mov     [rbp+var_24], eax
0x1800136c8  mov     dil, 1
0x1800136cb  mov     [rbp+var_28], dil
0x1800136cf  lea     r14, ?g_BrokersLock@Broker@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Broker::g_BrokersLock
0x1800136d6  mov     [rbp+var_20], r14
0x1800136da  mov     rcx, r14
0x1800136dd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800136e3  call    cs:__imp_GetCurrentThreadId
0x1800136e9  mov     [rbp+var_14], eax
0x1800136ec  mov     [rbp+var_18], dil
0x1800136f0  mov     r8, rbx
0x1800136f3  lea     rdx, [rbp+arg_8]
0x1800136f7  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::find(_GUID const &)
0x1800136fc  mov     rdx, [rbp+arg_8]
0x180013700  cmp     rdx, cs:?g_Brokers@Broker@@3V?$map@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@@std@@A; std::map<_GUID,std::shared_ptr<Broker::BrokerBase>> Broker::g_Brokers
0x180013707  jz      short loc_180013743
0x180013709  lea     rcx, ?g_Brokers@Broker@@3V?$map@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@@std@@A; std::map<_GUID,std::shared_ptr<Broker::BrokerBase>> Broker::g_Brokers
0x180013710  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>>,std::_Iterator_base0>)
0x180013715  mov     rdx, rax
0x180013718  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>> &,std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *> *)
0x18001371d  mov     rdx, qword ptr cs:xmmword_180028998
0x180013724  cmp     rdx, qword ptr cs:xmmword_180028998+8
0x18001372b  jz      short loc_18001373A
0x18001372d  mov     [rdx], rbx
0x180013730  add     qword ptr cs:xmmword_180028998, 8
0x180013738  jmp     short loc_180013743
0x18001373a  lea     r8, [rbp+arg_0]
0x18001373e  call    ??$_Emplace_reallocate@AEBQEAU_BROKER@@@?$vector@PEAU_BROKER@@V?$allocator@PEAU_BROKER@@@std@@@std@@AEAAPEAPEAU_BROKER@@QEAPEAU2@AEBQEAU2@@Z; std::vector<_BROKER *>::_Emplace_reallocate<_BROKER * const &>(_BROKER * * const,_BROKER * const &)
0x180013743  cmp     cs:qword_180028988, 0
0x18001374b  jnz     short loc_1800137A0
0x18001374d  mov     rcx, r14
0x180013750  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180013756  xor     dil, dil
0x180013759  mov     rcx, cs:?RpcIf@BrokerBase@Broker@@0PEAVRpcIfRegistration@2@EA; this
0x180013760  test    rcx, rcx
0x180013763  jz      short loc_180013775
0x180013765  call    ??_GRpcIfRegistration@Broker@@QEAAPEAXI@Z; Broker::RpcIfRegistration::`scalar deleting destructor'(uint)
0x18001376a  mov     cs:?RpcIf@BrokerBase@Broker@@0PEAVRpcIfRegistration@2@EA, 0; Broker::RpcIfRegistration * Broker::BrokerBase::RpcIf
0x180013775  mov     rax, qword ptr cs:xmmword_180028998
0x18001377c  cmp     cs:?g_DeletedBrokers@Broker@@3V?$vector@PEAU_BROKER@@V?$allocator@PEAU_BROKER@@@std@@@std@@A, rax; std::vector<_BROKER *> Broker::g_DeletedBrokers
0x180013783  jz      short loc_1800137A0
0x180013785  mov     rcx, [rax-8]; this
0x180013789  add     rax, 0FFFFFFFFFFFFFFF8h
0x18001378d  mov     qword ptr cs:xmmword_180028998, rax
0x180013794  test    rcx, rcx
0x180013797  jz      short loc_180013775
0x180013799  call    ??_G_BROKER@@QEAAPEAXI@Z; _BROKER::`scalar deleting destructor'(uint)
0x18001379e  jmp     short loc_180013775
0x1800137a0  test    dil, dil
0x1800137a3  jz      short loc_1800137AF
0x1800137a5  mov     rcx, r14
0x1800137a8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800137ae  nop
0x1800137af  mov     rcx, r15
0x1800137b2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800137b8  nop
0x1800137b9  mov     rcx, [rbp+var_8]; this
0x1800137bd  test    rcx, rcx
0x1800137c0  jz      short loc_1800137C7
0x1800137c2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800137c7  lea     r11, [rsp+50h+var_s0]
0x1800137cc  mov     rbx, [r11+30h]
0x1800137d0  mov     rdi, [r11+38h]
0x1800137d4  mov     rsp, r11
0x1800137d7  pop     r15
0x1800137d9  pop     r14
0x1800137db  pop     rbp
0x1800137dc  retn
```
