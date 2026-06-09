# Broker::SebBroker::Dump(unsigned __int64)

- ea: `0x1800198e0`
- end: `0x180019b57`
- name: `?Dump@SebBroker@Broker@@QEAAX_K@Z`
- size: `631`
- prototype: `void __fastcall(Broker::SebBroker *this, TRACEHANDLE)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800197fc`

## callees

- `0x180001dc0`
- `0x1800030e0`
- `0x180005a50`
- `0x180006d90`
- `0x1800076a0`
- `0x18000e770`
- `0x180011574`
- `0x1800137c0`
- `0x180013820`
- `0x180013920`
- `0x1800198e0`
- `0x180019c1c`
- `0x18001d9ac`
- `0x18001e998`
- `0x18001f63c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800199b9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800199b9`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180019a82`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180019a82`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x1800199e5`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x1800199e5`
- `BrokerLib!BrBufferFree` at `0x180019b1b`
- `BrokerLib!BrBufferFree` at `0x180019b1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::SebBroker::Dump(Broker::SebBroker *this, TRACEHANDLE a2)
{
  __int64 v4; // r8
  Broker::SebEvent *v5; // rdi
  _QWORD *v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  __int64 i; // rbx
  unsigned int BrokeredEventInfo2; // eax
  unsigned int v11; // edi
  Broker::SebEvent *v12[2]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+40h] [rbp-19h] BYREF
  char v14; // [rsp+48h] [rbp-11h]
  _BYTE v15[16]; // [rsp+50h] [rbp-9h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp+7h] BYREF
  __int128 v17; // [rsp+68h] [rbp+Fh]
  int v18; // [rsp+78h] [rbp+1Fh]
  unsigned int v19; // [rsp+80h] [rbp+27h]
  unsigned int v20; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v21; // [rsp+D0h] [rbp+77h] BYREF
  _QWORD *v22; // [rsp+D8h] [rbp+7Fh] BYREF

  v21 = 0;
  v20 = 0;
  Broker::BrokerLock::BrokerLock((Broker::BrokerLock *)v15, *((struct _BROKER **)this + 17), 1);
  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)&v13, (struct _RTL_SRWLOCK *)this + 1, 1);
  WPP_SF_(a2, 112, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  v5 = (Broker::SebEvent *)**((_QWORD **)this + 2);
  v12[0] = v5;
  while ( v5 != *((Broker::SebEvent **)this + 2) )
  {
    v6 = (_QWORD *)***((_QWORD ***)v5 + 5);
    v22 = v6;
    while ( v6 != **((_QWORD ***)v5 + 5) )
    {
      if ( v6[5] )
      {
        WPP_SF_dd(a2, 113, v4, *((unsigned int *)v5 + 8), *((_DWORD *)v6 + 8));
        Broker::_SessionInfo::Dump((Broker::_SessionInfo *)v6[5], a2);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++((__int64 *)&v22);
      v6 = v22;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++((__int64 *)v12);
    v5 = v12[0];
  }
  RtlReleaseSRWLockExclusive(v13);
  v14 = 0;
  v7 = BrQueryBrokeredEvents2(*((_QWORD *)this + 17), 0, 0, 0xFFFFFFFFLL, &v20, &v21);
  v8 = v7;
  if ( v7 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v7);
    v17 = 0;
    v18 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v19 = v8;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  for ( i = 0; (unsigned int)i < v20; i = (unsigned int)(i + 1) )
  {
    v22 = 0;
    *(_OWORD *)v12 = 0;
    BrokeredEventInfo2 = BrGetBrokeredEventInfo2(*((_QWORD *)this + 17), *(_QWORD *)(v21 + 8 * i), 0, 0, &v22);
    v11 = BrokeredEventInfo2;
    if ( BrokeredEventInfo2 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          115,
          &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
          BrokeredEventInfo2);
      v17 = 0;
      v18 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v19 = v11;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>::operator=(v12, v22);
    Broker::SebEvent::Dump(v12[0], a2);
    if ( v12[1] )
      std::_Ref_count_base::_Decref(v12[1]);
  }
  if ( v21 )
    BrBufferFree();
  WPP_SF_(a2, 116, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v13);
  Broker::BrokerLock::~BrokerLock((Broker::BrokerLock *)v15);
}

```

## disassembly

```asm
0x1800198e0  push    rbp
0x1800198e2  push    rbx
0x1800198e3  push    rsi
0x1800198e4  push    rdi
0x1800198e5  push    r14
0x1800198e7  lea     rbp, [rsp-37h]
0x1800198ec  sub     rsp, 90h
0x1800198f3  mov     rsi, rdx
0x1800198f6  mov     r14, rcx
0x1800198f9  mov     [rbp+57h+arg_10], 0
0x180019901  mov     [rbp+57h+arg_0], 0
0x180019908  mov     r8d, 1; int
0x18001990e  mov     rdx, [rcx+88h]; struct _BROKER *
0x180019915  lea     rcx, [rbp+57h+var_60]; this
0x180019919  call    ??0BrokerLock@Broker@@QEAA@PEAU_BROKER@@HH@Z; Broker::BrokerLock::BrokerLock(_BROKER *,int,int)
0x18001991e  nop
0x18001991f  lea     rdx, [r14+8]; struct _RTL_SRWLOCK *
0x180019923  mov     r8b, 1; bool
0x180019926  lea     rcx, [rbp+57h+var_70]; this
0x18001992a  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18001992f  nop
0x180019930  mov     edx, 70h ; 'p'
0x180019935  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001993c  mov     rcx, rsi
0x18001993f  call    WPP_SF_
0x180019944  mov     rdi, [r14+10h]
0x180019948  mov     rdi, [rdi]
0x18001994b  mov     [rbp+57h+var_80], rdi
0x18001994f  cmp     rdi, [r14+10h]
0x180019953  jz      short loc_1800199B5
0x180019955  mov     rax, [rdi+28h]
0x180019959  mov     rbx, [rax]
0x18001995c  mov     rbx, [rbx]
0x18001995f  mov     [rbp+57h+arg_18], rbx
0x180019963  mov     rax, [rdi+28h]
0x180019967  cmp     rbx, [rax]
0x18001996a  jz      short loc_1800199A6
0x18001996c  cmp     qword ptr [rbx+28h], 0
0x180019971  jz      short loc_180019997
0x180019973  mov     edx, 71h ; 'q'
0x180019978  mov     eax, [rbx+20h]
0x18001997b  mov     dword ptr [rsp+0B0h+var_90], eax
0x18001997f  mov     r9d, [rdi+20h]
0x180019983  mov     rcx, rsi
0x180019986  call    WPP_SF_dd
0x18001998b  mov     rdx, rsi; unsigned __int64
0x18001998e  mov     rcx, [rbx+28h]; this
0x180019992  call    ?Dump@_SessionInfo@Broker@@QEAAX_K@Z; Broker::_SessionInfo::Dump(unsigned __int64)
0x180019997  lea     rcx, [rbp+57h+arg_18]
0x18001999b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x1800199a0  mov     rbx, [rbp+57h+arg_18]
0x1800199a4  jmp     short loc_180019963
0x1800199a6  lea     rcx, [rbp+57h+var_80]
0x1800199aa  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(void)
0x1800199af  mov     rdi, [rbp+57h+var_80]
0x1800199b3  jmp     short loc_18001994F
0x1800199b5  mov     rcx, [rbp+57h+var_70]
0x1800199b9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800199bf  mov     [rbp+57h+var_68], 0
0x1800199c3  lea     rax, [rbp+57h+arg_10]
0x1800199c7  mov     [rsp+0B0h+var_88], rax
0x1800199cc  lea     rax, [rbp+57h+arg_0]
0x1800199d0  mov     [rsp+0B0h+var_90], rax
0x1800199d5  or      r9d, 0FFFFFFFFh
0x1800199d9  xor     r8d, r8d
0x1800199dc  xor     edx, edx
0x1800199de  mov     rcx, [r14+88h]
0x1800199e5  call    cs:__imp_BrQueryBrokeredEvents2
0x1800199eb  mov     ebx, eax
0x1800199ed  test    eax, eax
0x1800199ef  jz      short loc_180019A49
0x1800199f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199f8  test    byte ptr [rcx+1Ch], 1
0x1800199fc  jz      short loc_180019A1C
0x1800199fe  cmp     byte ptr [rcx+19h], 2
0x180019a02  jb      short loc_180019A1C
0x180019a04  mov     edx, 72h ; 'r'
0x180019a09  mov     r9d, eax
0x180019a0c  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180019a13  mov     rcx, [rcx+10h]
0x180019a17  call    WPP_SF_d
0x180019a1c  xorps   xmm0, xmm0
0x180019a1f  movups  [rbp+57h+var_48], xmm0
0x180019a23  mov     [rbp+57h+var_38], 1
0x180019a2a  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180019a31  mov     [rbp+57h+pExceptionObject], rax
0x180019a35  mov     [rbp+57h+var_30], ebx
0x180019a38  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180019a3f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019a43  call    _CxxThrowException_0
0x180019a49  xor     ebx, ebx
0x180019a4b  cmp     ebx, [rbp+57h+arg_0]
0x180019a4e  jnb     loc_180019B12
0x180019a54  mov     [rbp+57h+arg_18], 0
0x180019a5c  xorps   xmm0, xmm0
0x180019a5f  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180019a64  lea     rcx, [rbp+57h+arg_18]
0x180019a68  mov     [rsp+0B0h+var_90], rcx
0x180019a6d  xor     r9d, r9d
0x180019a70  xor     r8d, r8d
0x180019a73  mov     rdx, [rbp+57h+arg_10]
0x180019a77  mov     rdx, [rdx+rbx*8]
0x180019a7b  mov     rcx, [r14+88h]
0x180019a82  call    cs:__imp_BrGetBrokeredEventInfo2
0x180019a88  mov     edi, eax
0x180019a8a  test    eax, eax
0x180019a8c  jnz     short loc_180019ABA
0x180019a8e  mov     rdx, [rbp+57h+arg_18]
0x180019a92  lea     rcx, [rbp+57h+var_80]
0x180019a96  call    ??4?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>::operator=(std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>> const &)
0x180019a9b  mov     rdx, rsi; unsigned __int64
0x180019a9e  mov     rcx, [rbp+57h+var_80]; this
0x180019aa2  call    ?Dump@SebEvent@Broker@@QEAAX_K@Z; Broker::SebEvent::Dump(unsigned __int64)
0x180019aa7  nop
0x180019aa8  mov     rcx, [rbp+57h+var_80+8]; this
0x180019aac  test    rcx, rcx
0x180019aaf  jz      short loc_180019AB6
0x180019ab1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019ab6  inc     ebx
0x180019ab8  jmp     short loc_180019A4B
0x180019aba  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ac1  test    byte ptr [rcx+1Ch], 1
0x180019ac5  jz      short loc_180019AE5
0x180019ac7  cmp     byte ptr [rcx+19h], 2
0x180019acb  jb      short loc_180019AE5
0x180019acd  mov     edx, 73h ; 's'
0x180019ad2  mov     r9d, edi
0x180019ad5  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180019adc  mov     rcx, [rcx+10h]
0x180019ae0  call    WPP_SF_d
0x180019ae5  xorps   xmm0, xmm0
0x180019ae8  movups  [rbp+57h+var_48], xmm0
0x180019aec  mov     [rbp+57h+var_38], 1
0x180019af3  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180019afa  mov     [rbp+57h+pExceptionObject], rax
0x180019afe  mov     [rbp+57h+var_30], edi
0x180019b01  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180019b08  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019b0c  call    _CxxThrowException_0
0x180019b12  mov     rcx, [rbp+57h+arg_10]
0x180019b16  test    rcx, rcx
0x180019b19  jz      short loc_180019B21
0x180019b1b  call    cs:__imp_BrBufferFree
0x180019b21  mov     edx, 74h ; 't'
0x180019b26  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180019b2d  mov     rcx, rsi
0x180019b30  call    WPP_SF_
0x180019b35  nop
0x180019b36  lea     rcx, [rbp+57h+var_70]; this
0x180019b3a  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x180019b3f  nop
0x180019b40  lea     rcx, [rbp+57h+var_60]; this
0x180019b44  call    ??1BrokerLock@Broker@@QEAA@XZ; Broker::BrokerLock::~BrokerLock(void)
0x180019b49  add     rsp, 90h
0x180019b50  pop     r14
0x180019b52  pop     rdi
0x180019b53  pop     rsi
0x180019b54  pop     rbx
0x180019b55  pop     rbp
0x180019b56  retn
```
