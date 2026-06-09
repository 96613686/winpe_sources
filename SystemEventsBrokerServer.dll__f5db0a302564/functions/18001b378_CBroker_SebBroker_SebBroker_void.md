# CBroker::SebBroker::~SebBroker(void)

- ea: `0x18001b378`
- end: `0x18001b596`
- name: `??1SebBroker@CBroker@@QEAA@XZ`
- size: `542`
- prototype: `void __fastcall(struct _RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180020900`

## callees

- `0x180005a50`
- `0x1800076a0`
- `0x18000c910`
- `0x180012a50`
- `0x1800133c0`
- `0x180013820`
- `0x180013920`
- `0x180014470`
- `0x180017120`
- `0x180019130`
- `0x18001b378`
- `0x18001b59c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b4a5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b4cc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b4a5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b4cc`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001b434`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001b434`
- `BrokerLib!BrDeleteBrokerInstance` at `0x18001b3bd`
- `BrokerLib!BrDeleteBrokerInstance` at `0x18001b3bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CBroker::SebBroker::~SebBroker(struct _RTL_SRWLOCK *this)
{
  _QWORD *v2; // rcx
  void **p_Ptr; // r14
  struct _RTL_SRWLOCK *v4; // rsi
  HPOWERNOTIFY *i; // rbx
  _QWORD *v6; // rdx
  __int64 v7; // rbx
  _QWORD *v8; // rax
  PVOID Ptr; // rcx
  std::_Ref_count_base *v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-40h] BYREF
  char v12; // [rsp+28h] [rbp-38h]
  CBroker::SebEvent *v13[2]; // [rsp+30h] [rbp-30h] BYREF
  std::_Ref_count_base *v14[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  if ( this[44].Ptr )
    BrDeleteBrokerInstance();
  *(_OWORD *)v13 = 0;
  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)&v11, this + 1, 1);
  if ( LOBYTE(this->Ptr) )
  {
    v4 = this;
    LOBYTE(this->Ptr) = 0;
    for ( i = (HPOWERNOTIFY *)this[40].Ptr; i != this[41].Ptr; ++i )
      PowerSettingUnregisterNotification(*i);
    p_Ptr = &this[2].Ptr;
    while ( 1 )
    {
      v6 = *(_QWORD **)*p_Ptr;
      if ( v6 == *p_Ptr )
        *(_OWORD *)v14 = 0;
      else
        std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(v14, v6 + 6);
      v7 = *(_QWORD *)std::shared_ptr<CBroker::SebBroker>::operator=(v13, v14);
      if ( v14[1] )
        std::_Ref_count_base::_Decref(v14[1]);
      if ( !v7 )
        break;
      v8 = std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(&v15, v13);
      Broker::BrokerEventTable<CBroker::SebEvent>::Remove(&this[2], v8);
      RtlReleaseSRWLockExclusive(v11);
      v12 = 0;
      CBroker::SebEvent::OnDisable(v13[0], 1);
      Broker::ScopedWriteLock::Acquire((Broker::ScopedWriteLock *)&v11);
    }
    RtlReleaseSRWLockExclusive(v11);
    v12 = 0;
    v2 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    p_Ptr = &this[2].Ptr;
    v4 = this;
  }
  if ( (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_(v2[2], 21, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v11);
  if ( v13[1] )
    std::_Ref_count_base::_Decref(v13[1]);
  Ptr = v4[40].Ptr;
  if ( Ptr )
  {
    std::_Deallocate<16>(Ptr, ((char *)v4[42].Ptr - (char *)Ptr) & 0xFFFFFFFFFFFFFFF8uLL);
    v4[40].Ptr = 0;
    v4[41].Ptr = 0;
    v4[42].Ptr = 0;
  }
  v10 = (std::_Ref_count_base *)this[5].Ptr;
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<CBroker::SebEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<CBroker::SebEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>,0>>(p_Ptr);
}

```

## disassembly

```asm
0x18001b378  push    rbp
0x18001b37a  push    rbx
0x18001b37b  push    rsi
0x18001b37c  push    rdi
0x18001b37d  push    r14
0x18001b37f  mov     rbp, rsp
0x18001b382  sub     rsp, 60h
0x18001b386  mov     rdi, rcx
0x18001b389  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b390  test    byte ptr [rcx+1Ch], 1
0x18001b394  jz      short loc_18001B3B1
0x18001b396  cmp     byte ptr [rcx+19h], 4
0x18001b39a  jb      short loc_18001B3B1
0x18001b39c  mov     edx, 12h
0x18001b3a1  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001b3a8  mov     rcx, [rcx+10h]
0x18001b3ac  call    WPP_SF_
0x18001b3b1  mov     rcx, [rdi+160h]
0x18001b3b8  test    rcx, rcx
0x18001b3bb  jz      short loc_18001B3C3
0x18001b3bd  call    cs:__imp_BrDeleteBrokerInstance
0x18001b3c3  xorps   xmm0, xmm0
0x18001b3c6  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18001b3cb  lea     rdx, [rdi+8]; struct _RTL_SRWLOCK *
0x18001b3cf  mov     r8b, 1; bool
0x18001b3d2  lea     rcx, [rbp+var_40]; this
0x18001b3d6  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18001b3db  cmp     byte ptr [rdi], 0
0x18001b3de  jnz     short loc_18001B41B
0x18001b3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3e7  test    byte ptr [rcx+1Ch], 1
0x18001b3eb  jz      short loc_18001B40F
0x18001b3ed  cmp     byte ptr [rcx+19h], 4
0x18001b3f1  jb      short loc_18001B40F
0x18001b3f3  mov     edx, 13h
0x18001b3f8  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001b3ff  mov     rcx, [rcx+10h]
0x18001b403  call    WPP_SF_
0x18001b408  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b40f  lea     r14, [rdi+10h]
0x18001b413  mov     rsi, rdi
0x18001b416  jmp     loc_18001B505
0x18001b41b  mov     rsi, rdi
0x18001b41e  mov     byte ptr [rdi], 0
0x18001b421  mov     rbx, [rdi+140h]
0x18001b428  cmp     rbx, [rdi+148h]
0x18001b42f  jz      short loc_18001B440
0x18001b431  mov     rcx, [rbx]; RegistrationHandle
0x18001b434  call    cs:__imp_PowerSettingUnregisterNotification
0x18001b43a  add     rbx, 8
0x18001b43e  jmp     short loc_18001B428
0x18001b440  lea     r14, [rdi+10h]
0x18001b444  mov     rax, [r14]
0x18001b447  mov     rdx, [rax]
0x18001b44a  cmp     rdx, rax
0x18001b44d  jz      short loc_18001B45E
0x18001b44f  add     rdx, 30h ; '0'
0x18001b453  lea     rcx, [rbp+var_20]
0x18001b457  call    ??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)
0x18001b45c  jmp     short loc_18001B466
0x18001b45e  xorps   xmm0, xmm0
0x18001b461  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18001b466  lea     rdx, [rbp+var_20]
0x18001b46a  lea     rcx, [rbp+var_30]
0x18001b46e  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x18001b473  mov     rbx, [rax]
0x18001b476  mov     rcx, [rbp+var_20+8]; this
0x18001b47a  test    rcx, rcx
0x18001b47d  jz      short loc_18001B484
0x18001b47f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001b484  test    rbx, rbx
0x18001b487  jz      short loc_18001B4C8
0x18001b489  lea     rdx, [rbp+var_30]
0x18001b48d  lea     rcx, [rbp+var_10]
0x18001b491  call    ??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)
0x18001b496  mov     rdx, rax
0x18001b499  mov     rcx, r14
0x18001b49c  call    ?Remove@?$BrokerEventTable@VSebEvent@CBroker@@@Broker@@QEAAXV?$shared_ptr@VSebEvent@CBroker@@@std@@@Z; Broker::BrokerEventTable<CBroker::SebEvent>::Remove(std::shared_ptr<CBroker::SebEvent>)
0x18001b4a1  mov     rcx, [rbp+var_40]
0x18001b4a5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001b4ab  mov     [rbp+var_38], 0
0x18001b4af  mov     dl, 1; bool
0x18001b4b1  mov     rcx, [rbp+var_30]; this
0x18001b4b5  call    ?OnDisable@SebEvent@CBroker@@QEAAX_N@Z; CBroker::SebEvent::OnDisable(bool)
0x18001b4ba  lea     rcx, [rbp+var_40]; this
0x18001b4be  call    ?Acquire@ScopedWriteLock@Broker@@QEAAXXZ; Broker::ScopedWriteLock::Acquire(void)
0x18001b4c3  jmp     loc_18001B444
0x18001b4c8  mov     rcx, [rbp+var_40]
0x18001b4cc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001b4d2  mov     [rbp+var_38], 0
0x18001b4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4dd  test    byte ptr [rcx+1Ch], 1
0x18001b4e1  jz      short loc_18001B505
0x18001b4e3  cmp     byte ptr [rcx+19h], 4
0x18001b4e7  jb      short loc_18001B505
0x18001b4e9  mov     edx, 14h
0x18001b4ee  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001b4f5  mov     rcx, [rcx+10h]
0x18001b4f9  call    WPP_SF_
0x18001b4fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b505  mov     ebx, 140h
0x18001b50a  test    byte ptr [rcx+1Ch], 1
0x18001b50e  jz      short loc_18001B52B
0x18001b510  cmp     byte ptr [rcx+19h], 4
0x18001b514  jb      short loc_18001B52B
0x18001b516  mov     edx, 15h
0x18001b51b  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001b522  mov     rcx, [rcx+10h]
0x18001b526  call    WPP_SF_
0x18001b52b  lea     rcx, [rbp+var_40]; this
0x18001b52f  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18001b534  mov     rcx, [rbp+var_30+8]; this
0x18001b538  test    rcx, rcx
0x18001b53b  jz      short loc_18001B542
0x18001b53d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001b542  mov     rcx, [rsi+rbx]
0x18001b546  test    rcx, rcx
0x18001b549  jz      short loc_18001B576
0x18001b54b  mov     rdx, [rsi+rbx+10h]
0x18001b550  sub     rdx, rcx
0x18001b553  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001b557  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b55c  mov     qword ptr [rsi+rbx], 0
0x18001b564  mov     qword ptr [rsi+rbx+8], 0
0x18001b56d  mov     qword ptr [rsi+rbx+10h], 0
0x18001b576  mov     rcx, [rdi+28h]; this
0x18001b57a  test    rcx, rcx
0x18001b57d  jz      short loc_18001B584
0x18001b57f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001b584  mov     rcx, r14
0x18001b587  add     rsp, 60h
0x18001b58b  pop     r14
0x18001b58d  pop     rdi
0x18001b58e  pop     rsi
0x18001b58f  pop     rbx
0x18001b590  pop     rbp
0x18001b591  jmp     ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<CBroker::SebEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<CBroker::SebEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>,0>>(void)
```
