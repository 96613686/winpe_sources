# Broker::SebBroker::~SebBroker(void)

- ea: `0x180018754`
- end: `0x18001891f`
- name: `??1SebBroker@Broker@@QEAA@XZ`
- size: `459`
- prototype: `void __fastcall(struct _RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f100`

## callees

- `0x180005a50`
- `0x180006d90`
- `0x1800076a0`
- `0x18000f370`
- `0x1800137c0`
- `0x180013820`
- `0x180013920`
- `0x180016b68`
- `0x180017120`
- `0x180017294`
- `0x180018754`
- `0x180018928`
- `0x180018a08`
- `0x180019040`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800188bf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800188bf`
- `BrokerLib!BrDeleteBrokerInstance` at `0x1800187b1`
- `BrokerLib!BrDeleteBrokerInstance` at `0x1800187b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Broker::SebBroker::~SebBroker(struct _RTL_SRWLOCK *this)
{
  void **p_Ptr; // r14
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdi
  _QWORD *v6; // rbx
  __int64 v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // [rsp+20h] [rbp-50h] BYREF
  char v14; // [rsp+28h] [rbp-48h]
  std::_Ref_count_base *v15[2]; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v16[16]; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v17[16]; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v18[16]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v19; // [rsp+90h] [rbp+20h] BYREF
  __int64 v20; // [rsp+98h] [rbp+28h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  if ( LOBYTE(this->Ptr) )
  {
    LOBYTE(this->Ptr) = 0;
    if ( this[17].Ptr )
      BrDeleteBrokerInstance();
    Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)&v13, this + 1, 1);
    p_Ptr = &this[2].Ptr;
    v3 = *(_QWORD *)this[2].Ptr;
    v20 = v3;
    while ( (void *)v3 != *p_Ptr )
    {
      v4 = ***(_QWORD ***)(v3 + 40);
      v19 = v4;
      while ( v4 != **(_QWORD **)(v3 + 40) )
      {
        v5 = v4 + 40;
        std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>::reset(v4 + 40);
        *(_OWORD *)v15 = 0;
        std::shared_ptr<CBroker::SebBroker>::operator=(v5, v15);
        if ( v15[1] )
          std::_Ref_count_base::_Decref(v15[1]);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v19);
        v4 = v19;
      }
      v6 = (_QWORD *)(v3 + 32);
      v7 = std::map<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>::_Try_emplace<unsigned __int64 const &,>(
             (__int64 *)&this[2],
             (__int64)v16,
             v6);
      std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<Broker::_SessionInfo>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::clear(*(_QWORD *)(*(_QWORD *)v7 + 40LL));
      v8 = (_QWORD *)std::map<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>::_Try_emplace<unsigned __int64 const &,>(
                       (__int64 *)&this[2],
                       (__int64)v17,
                       v6);
      std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>::reset(*v8 + 40LL);
      *(_OWORD *)v15 = 0;
      v9 = (_QWORD *)std::map<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>::_Try_emplace<unsigned __int64 const &,>(
                       (__int64 *)&this[2],
                       (__int64)v18,
                       v6);
      std::shared_ptr<CBroker::SebBroker>::operator=(*v9 + 40LL, v15);
      if ( v15[1] )
        std::_Ref_count_base::_Decref(v15[1]);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(
        &v20,
        v10,
        v11,
        v12);
      v3 = v20;
    }
    std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::clear(&this[2]);
    RtlReleaseSRWLockExclusive(v13);
    v14 = 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v13);
  }
  else
  {
    p_Ptr = &this[2].Ptr;
  }
  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)&this[4]);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>(p_Ptr);
}

```

## disassembly

```asm
0x180018754  mov     [rsp-18h+arg_10], rbx
0x180018759  mov     [rsp-18h+arg_18], rsi
0x18001875e  push    rbp
0x18001875f  push    rdi
0x180018760  push    r14
0x180018762  mov     rbp, rsp
0x180018765  sub     rsp, 70h
0x180018769  mov     rsi, rcx
0x18001876c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018773  test    byte ptr [rcx+1Ch], 1
0x180018777  jz      short loc_180018794
0x180018779  cmp     byte ptr [rcx+19h], 4
0x18001877d  jb      short loc_180018794
0x18001877f  mov     edx, 13h
0x180018784  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001878b  mov     rcx, [rcx+10h]
0x18001878f  call    WPP_SF_
0x180018794  cmp     byte ptr [rsi], 0
0x180018797  jnz     short loc_1800187A2
0x180018799  lea     r14, [rsi+10h]
0x18001879d  jmp     loc_1800188FA
0x1800187a2  mov     byte ptr [rsi], 0
0x1800187a5  mov     rcx, [rsi+88h]
0x1800187ac  test    rcx, rcx
0x1800187af  jz      short loc_1800187B7
0x1800187b1  call    cs:__imp_BrDeleteBrokerInstance
0x1800187b7  lea     rdx, [rsi+8]; struct _RTL_SRWLOCK *
0x1800187bb  mov     r8b, 1; bool
0x1800187be  lea     rcx, [rbp+var_50]; this
0x1800187c2  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x1800187c7  lea     r14, [rsi+10h]
0x1800187cb  mov     rbx, [r14]
0x1800187ce  mov     rbx, [rbx]
0x1800187d1  mov     [rbp+arg_8], rbx
0x1800187d5  cmp     rbx, [r14]
0x1800187d8  jz      loc_1800188B3
0x1800187de  mov     rax, [rbx+28h]
0x1800187e2  mov     rax, [rax]
0x1800187e5  mov     rax, [rax]
0x1800187e8  mov     [rbp+arg_0], rax
0x1800187ec  mov     rcx, [rbx+28h]
0x1800187f0  cmp     rax, [rcx]
0x1800187f3  jz      short loc_180018832
0x1800187f5  lea     rdi, [rax+28h]
0x1800187f9  mov     rcx, rdi
0x1800187fc  call    ?reset@?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@QEAAXXZ; std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>::reset(void)
0x180018801  xorps   xmm0, xmm0
0x180018804  movdqu  xmmword ptr [rbp+var_40], xmm0
0x180018809  lea     rdx, [rbp+var_40]
0x18001880d  mov     rcx, rdi
0x180018810  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x180018815  mov     rcx, [rbp+var_40+8]; this
0x180018819  test    rcx, rcx
0x18001881c  jz      short loc_180018823
0x18001881e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018823  lea     rcx, [rbp+arg_0]
0x180018827  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x18001882c  mov     rax, [rbp+arg_0]
0x180018830  jmp     short loc_1800187EC
0x180018832  add     rbx, 20h ; ' '
0x180018836  mov     r8, rbx
0x180018839  lea     rdx, [rbp+var_30]
0x18001883d  mov     rcx, r14
0x180018840  call    ??$_Try_emplace@AEB_K$$V@?$map@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x180018845  mov     rcx, [rax]
0x180018848  mov     rcx, [rcx+28h]
0x18001884c  call    ?clear@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::clear(void)
0x180018851  mov     r8, rbx
0x180018854  lea     rdx, [rbp+var_20]
0x180018858  mov     rcx, r14
0x18001885b  call    ??$_Try_emplace@AEB_K$$V@?$map@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x180018860  mov     rcx, [rax]
0x180018863  add     rcx, 28h ; '('
0x180018867  call    ?reset@?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@QEAAXXZ; std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>::reset(void)
0x18001886c  xorps   xmm0, xmm0
0x18001886f  movdqu  xmmword ptr [rbp+var_40], xmm0
0x180018874  mov     r8, rbx
0x180018877  lea     rdx, [rbp+var_10]
0x18001887b  mov     rcx, r14
0x18001887e  call    ??$_Try_emplace@AEB_K$$V@?$map@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x180018883  mov     rcx, [rax]
0x180018886  add     rcx, 28h ; '('
0x18001888a  lea     rdx, [rbp+var_40]
0x18001888e  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x180018893  mov     rcx, [rbp+var_40+8]; this
0x180018897  test    rcx, rcx
0x18001889a  jz      short loc_1800188A1
0x18001889c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800188a1  lea     rcx, [rbp+arg_8]
0x1800188a5  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(void)
0x1800188aa  mov     rbx, [rbp+arg_8]
0x1800188ae  jmp     loc_1800187D5
0x1800188b3  mov     rcx, r14
0x1800188b6  call    ?clear@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::clear(void)
0x1800188bb  mov     rcx, [rbp+var_50]
0x1800188bf  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800188c5  mov     [rbp+var_48], 0
0x1800188c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188d0  test    byte ptr [rcx+1Ch], 1
0x1800188d4  jz      short loc_1800188F1
0x1800188d6  cmp     byte ptr [rcx+19h], 4
0x1800188da  jb      short loc_1800188F1
0x1800188dc  mov     edx, 14h
0x1800188e1  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x1800188e8  mov     rcx, [rcx+10h]
0x1800188ec  call    WPP_SF_
0x1800188f1  lea     rcx, [rbp+var_50]; this
0x1800188f5  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x1800188fa  lea     rcx, [rsi+20h]; this
0x1800188fe  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180018903  mov     rcx, r14
0x180018906  lea     r11, [rsp+70h+var_s0]
0x18001890b  mov     rbx, [r11+30h]
0x18001890f  mov     rsi, [r11+38h]
0x180018913  mov     rsp, r11
0x180018916  pop     r14
0x180018918  pop     rdi
0x180018919  pop     rbp
0x18001891a  jmp     ??1?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>(void)
```
