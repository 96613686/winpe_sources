# Broker::BrokerBase::CreateInstance(_GUID const *,_BROKER_CALLBACK_TABLE const *,_BROKER_CALLBACK_TABLE_V2 const *,unsigned __int64,ulong const *,_BROKER * *)

- ea: `0x180018004`
- end: `0x180018350`
- name: `?CreateInstance@BrokerBase@Broker@@SAXPEBU_GUID@@PEBU_BROKER_CALLBACK_TABLE@@PEBU_BROKER_CALLBACK_TABLE_V2@@_KPEBKPEAPEAU_BROKER@@@Z`
- size: `844`
- prototype: `static void(const struct _GUID *, const struct _BROKER_CALLBACK_TABLE *, const struct _BROKER_CALLBACK_TABLE_V2 *, unsigned __int64, const unsigned int *, struct _BROKER **)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180011690`
- `0x180016ab0`

## callees

- `0x180004500`
- `0x180004ae0`
- `0x18000a2a4`
- `0x18000b080`
- `0x18000b3a4`
- `0x18000b578`
- `0x18000d5cc`
- `0x18000eb40`
- `0x18000ed50`
- `0x180010c54`
- `0x180015af0`
- `0x180015b14`
- `0x1800165da`
- `0x180018004`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Broker::BrokerBase::CreateInstance(
        const struct _GUID *a1,
        const struct _BROKER_CALLBACK_TABLE *a2,
        const struct _BROKER_CALLBACK_TABLE_V2 *a3,
        unsigned __int64 a4,
        unsigned int *a5,
        struct _BROKER **a6)
{
  __int64 v10; // rcx
  _BROKER *v11; // rbx
  _DWORD *v12; // rdi
  void *v13; // rdx
  const struct _GUID *v14; // r8
  const unsigned __int16 *v15; // r9
  __int64 v16; // rcx
  __int64 *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // [rsp+0h] [rbp-148h] BYREF
  unsigned int v21[2]; // [rsp+20h] [rbp-128h]
  Broker::RpcIfRegistration *v22; // [rsp+30h] [rbp-118h] BYREF
  std::_Ref_count_base *v23; // [rsp+38h] [rbp-110h]
  _BROKER *v24; // [rsp+40h] [rbp-108h] BYREF
  std::_Ref_count_base *v25[2]; // [rsp+48h] [rbp-100h] BYREF
  unsigned int *Src; // [rsp+58h] [rbp-F0h]
  struct _BROKER **v27; // [rsp+60h] [rbp-E8h]
  _QWORD v28[3]; // [rsp+68h] [rbp-E0h] BYREF
  _BYTE v29[16]; // [rsp+80h] [rbp-C8h] BYREF
  _BYTE v30[16]; // [rsp+90h] [rbp-B8h] BYREF
  void **pExceptionObject; // [rsp+A0h] [rbp-A8h] BYREF
  __int128 v32; // [rsp+A8h] [rbp-A0h]
  int v33; // [rsp+B8h] [rbp-90h]
  int v34; // [rsp+C0h] [rbp-88h]
  void **v35; // [rsp+C8h] [rbp-80h] BYREF
  __int128 v36; // [rsp+D0h] [rbp-78h]
  int v37; // [rsp+E0h] [rbp-68h]
  int v38; // [rsp+E8h] [rbp-60h]
  struct _GUID v39; // [rsp+F0h] [rbp-58h] BYREF
  _BYTE v40[8]; // [rsp+100h] [rbp-48h] BYREF
  std::_Ref_count_base *v41; // [rsp+108h] [rbp-40h]

  Src = a5;
  v27 = a6;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids);
  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v30, &Broker::g_BrokerInterfaceLock, 1);
  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v29, &Broker::g_BrokersLock, 1);
  *(_OWORD *)v25 = 0;
  if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::find(
                    v10,
                    &v24,
                    a1) != Broker::g_Brokers )
  {
    v36 = 0;
    v37 = 1;
    v35 = &Broker::Win32Error::`vftable';
    v38 = 183;
    throw (Broker::Win32Error *)&v35;
  }
  if ( a3 && *((_QWORD *)a3 + 4) )
  {
    v32 = 0;
    v33 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v34 = 50;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v11 = (_BROKER *)operator new(0x20u);
  v24 = v11;
  *(_QWORD *)v11 = 0;
  *((_QWORD *)v11 + 1) = 0;
  *((_QWORD *)v11 + 2) = 0;
  *((_QWORD *)v11 + 3) = 0;
  *(struct _GUID *)v11 = *a1;
  try
  {
    v12 = operator new(0x160u);
    v12[2] = 1;
    v12[3] = 1;
    *(_QWORD *)v12 = &std::_Ref_count_obj2<Broker::BrokerBase>::`vftable';
    Broker::BrokerBase::BrokerBase((Broker::BrokerBase *)(v12 + 4), v11, a2, a3, a4, Src);
    v22 = (Broker::RpcIfRegistration *)(v12 + 4);
    v23 = (std::_Ref_count_base *)v12;
    std::shared_ptr<Broker::BrokerEvent>::operator=(v25, &v22);
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    if ( !qword_180028988 )
    {
      v22 = (Broker::RpcIfRegistration *)operator new(0x18u);
      Broker::BrokerBase::RpcIf = (Broker::RpcIfRegistration *)Broker::RpcIfRegistration::RpcIfRegistration(
                                                                 v22,
                                                                 v13,
                                                                 v14,
                                                                 v15,
                                                                 v21[0],
                                                                 0);
      if ( !Broker::BrokerBase::RpcIf )
      {
        v28[2] = 0;
        v28[1] = "bad allocation";
        v28[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)v28;
      }
    }
    v39 = *a1;
    std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(v40, v25);
    std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::_Emplace<std::pair<_GUID,std::shared_ptr<Broker::BrokerBase>>>(
      v16,
      &v22,
      &v39);
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
    v17 = (__int64 *)std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(&v22, v25);
    v18 = *v17;
    *v17 = *((_QWORD *)v11 + 2);
    *((_QWORD *)v11 + 2) = v18;
    v19 = v17[1];
    v17[1] = *((_QWORD *)v11 + 3);
    *((_QWORD *)v11 + 3) = v19;
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    *v27 = v11;
    if ( v25[1] )
      std::_Ref_count_base::_Decref(v25[1]);
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v29);
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v30);
  }
  catch ( ... )
  {
    _BROKER::`scalar deleting destructor'(v24, (unsigned int)&v20);
    throw;
  }
}

```

## disassembly

```asm
0x180018004  mov     [rsp+arg_0], rbx
0x180018009  mov     [rsp+arg_8], rsi
0x18001800e  push    rdi
0x18001800f  push    r12
0x180018011  push    r13
0x180018013  push    r14
0x180018015  push    r15
0x180018017  sub     rsp, 120h
0x18001801e  mov     rax, cs:__security_cookie
0x180018025  xor     rax, rsp
0x180018028  mov     [rsp+148h+var_38], rax
0x180018030  mov     r13, r9
0x180018033  mov     rsi, r8
0x180018036  mov     r12, rdx
0x180018039  mov     r15, rcx
0x18001803c  mov     rax, [rsp+148h+arg_20]
0x180018044  mov     [rsp+148h+Src], rax
0x180018049  mov     rax, [rsp+148h+arg_28]
0x180018051  mov     [rsp+148h+var_E8], rax
0x180018056  xor     edi, edi
0x180018058  mov     rcx, cs:WPP_GLOBAL_Control
0x18001805f  test    dword ptr [rcx+1Ch], 800h
0x180018066  jz      short loc_180018081
0x180018068  cmp     byte ptr [rcx+19h], 5
0x18001806c  jb      short loc_180018081
0x18001806e  lea     edx, [rdi+0Ah]
0x180018071  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180018078  mov     rcx, [rcx+10h]
0x18001807c  call    WPP_SF_
0x180018081  mov     r14d, 1
0x180018087  mov     r8b, r14b; bool
0x18001808a  lea     rdx, ?g_BrokerInterfaceLock@Broker@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x180018091  lea     rcx, [rsp+148h+var_B8]; this
0x180018099  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18001809e  nop
0x18001809f  mov     r8b, r14b; bool
0x1800180a2  lea     rdx, ?g_BrokersLock@Broker@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x1800180a9  lea     rcx, [rsp+148h+var_C8]; this
0x1800180b1  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x1800180b6  nop
0x1800180b7  xorps   xmm0, xmm0
0x1800180ba  movdqu  xmmword ptr [rsp+148h+var_100], xmm0
0x1800180c0  mov     r8, r15
0x1800180c3  lea     rdx, [rsp+148h+var_108]
0x1800180c8  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::find(_GUID const &)
0x1800180cd  mov     rcx, cs:?g_Brokers@Broker@@3V?$map@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@@std@@A; std::map<_GUID,std::shared_ptr<Broker::BrokerBase>> Broker::g_Brokers
0x1800180d4  cmp     [rax], rcx
0x1800180d7  jnz     loc_18001830E
0x1800180dd  test    rsi, rsi
0x1800180e0  jz      short loc_18001812A
0x1800180e2  cmp     [rsi+20h], rdi
0x1800180e6  jz      short loc_18001812A
0x1800180e8  xorps   xmm0, xmm0
0x1800180eb  movups  [rsp+148h+var_A0], xmm0
0x1800180f3  mov     [rsp+148h+var_90], r14d
0x1800180fb  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180018102  mov     [rsp+148h+pExceptionObject], rax
0x18001810a  mov     [rsp+148h+var_88], 32h ; '2'
0x180018115  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001811c  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180018124  call    _CxxThrowException_0
0x18001812a  mov     ecx, 20h ; ' '; Size
0x18001812f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018134  mov     rbx, rax
0x180018137  mov     [rsp+148h+var_108], rax
0x18001813c  mov     [rax], rdi
0x18001813f  mov     [rax+8], rdi
0x180018143  mov     [rax+10h], rdi
0x180018147  mov     [rax+18h], rdi
0x18001814b  movups  xmm0, xmmword ptr [r15]
0x18001814f  movdqu  xmmword ptr [rax], xmm0
0x180018153  mov     ecx, 160h; Size
0x180018158  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001815d  mov     rdi, rax
0x180018160  mov     [rsp+148h+var_118], rax
0x180018165  mov     [rax+8], r14d
0x180018169  mov     [rax+0Ch], r14d
0x18001816d  lea     rax, ??_7?$_Ref_count_obj2@VBrokerBase@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::BrokerBase>::`vftable'
0x180018174  mov     [rdi], rax
0x180018177  lea     r14, [rdi+10h]
0x18001817b  mov     rax, [rsp+148h+Src]
0x180018180  mov     [rsp+148h+var_120], rax; Src
0x180018185  mov     qword ptr [rsp+148h+var_128], r13; unsigned int
0x18001818a  mov     r9, rsi; struct _BROKER_CALLBACK_TABLE_V2 *
0x18001818d  mov     r8, r12; struct _BROKER_CALLBACK_TABLE *
0x180018190  mov     rdx, rbx; struct _BROKER *
0x180018193  mov     rcx, r14; this
0x180018196  call    ??0BrokerBase@Broker@@QEAA@QEAU_BROKER@@PEBU_BROKER_CALLBACK_TABLE@@PEBU_BROKER_CALLBACK_TABLE_V2@@_KPEBK@Z; Broker::BrokerBase::BrokerBase(_BROKER * const,_BROKER_CALLBACK_TABLE const *,_BROKER_CALLBACK_TABLE_V2 const *,unsigned __int64,ulong const *)
0x18001819b  nop
0x18001819c  mov     [rsp+148h+var_118], r14
0x1800181a1  mov     [rsp+148h+var_110], rdi
0x1800181a6  lea     rdx, [rsp+148h+var_118]
0x1800181ab  lea     rcx, [rsp+148h+var_100]
0x1800181b0  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x1800181b5  mov     rcx, [rsp+148h+var_110]; this
0x1800181ba  test    rcx, rcx
0x1800181bd  jz      short loc_1800181C4
0x1800181bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800181c4  cmp     cs:qword_180028988, 0
0x1800181cc  jnz     short loc_18001822C
0x1800181ce  mov     ecx, 18h; Size
0x1800181d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800181d8  mov     [rsp+148h+var_118], rax
0x1800181dd  mov     [rsp+148h+var_120], 0; int (*)(void *, void *)
0x1800181e6  mov     rcx, rax; this
0x1800181e9  call    ??0RpcIfRegistration@Broker@@QEAA@PEAXPEBU_GUID@@PEBGKP6AJ00@Z@Z; Broker::RpcIfRegistration::RpcIfRegistration(void *,_GUID const *,ushort const *,ulong,long (*)(void *,void *))
0x1800181ee  nop
0x1800181ef  mov     cs:?RpcIf@BrokerBase@Broker@@0PEAVRpcIfRegistration@2@EA, rax; Broker::RpcIfRegistration * Broker::BrokerBase::RpcIf
0x1800181f6  test    rax, rax
0x1800181f9  jnz     short loc_18001822C
0x1800181fb  xorps   xmm0, xmm0
0x1800181fe  movups  [rsp+148h+var_D8], xmm0
0x180018203  lea     rax, aBadAllocation; "bad allocation"
0x18001820a  mov     qword ptr [rsp+148h+var_D8], rax
0x18001820f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180018216  mov     [rsp+148h+var_E0], rax
0x18001821b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180018222  lea     rcx, [rsp+148h+var_E0]; pExceptionObject
0x180018227  call    _CxxThrowException_0
0x18001822c  movups  xmm0, xmmword ptr [r15]
0x180018230  movdqu  [rsp+148h+var_58], xmm0
0x180018239  lea     rdx, [rsp+148h+var_100]
0x18001823e  lea     rcx, [rsp+148h+var_48]
0x180018246  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x18001824b  nop
0x18001824c  lea     r8, [rsp+148h+var_58]
0x180018254  lea     rdx, [rsp+148h+var_118]
0x180018259  call    ??$_Emplace@U?$pair@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::_Emplace<std::pair<_GUID,std::shared_ptr<Broker::BrokerBase>>>(std::pair<_GUID,std::shared_ptr<Broker::BrokerBase>> &&)
0x18001825e  nop
0x18001825f  mov     rcx, [rsp+148h+var_40]; this
0x180018267  test    rcx, rcx
0x18001826a  jz      short loc_180018272
0x18001826c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018271  nop
0x180018272  lea     rdx, [rsp+148h+var_100]
0x180018277  lea     rcx, [rsp+148h+var_118]
0x18001827c  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x180018281  mov     rdx, [rax]
0x180018284  mov     rcx, [rbx+10h]
0x180018288  mov     [rax], rcx
0x18001828b  mov     [rbx+10h], rdx
0x18001828f  mov     rdx, [rax+8]
0x180018293  mov     rcx, [rbx+18h]
0x180018297  mov     [rax+8], rcx
0x18001829b  mov     [rbx+18h], rdx
0x18001829f  mov     rcx, [rsp+148h+var_110]; this
0x1800182a4  test    rcx, rcx
0x1800182a7  jz      short loc_1800182AE
0x1800182a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800182ae  mov     rax, [rsp+148h+var_E8]
0x1800182b3  mov     [rax], rbx
0x1800182b6  mov     rcx, [rsp+148h+var_100+8]; this
0x1800182bb  test    rcx, rcx
0x1800182be  jz      short loc_1800182C6
0x1800182c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800182c5  nop
0x1800182c6  lea     rcx, [rsp+148h+var_C8]; this
0x1800182ce  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x1800182d3  nop
0x1800182d4  lea     rcx, [rsp+148h+var_B8]; this
0x1800182dc  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x1800182e1  mov     rcx, [rsp+148h+var_38]
0x1800182e9  xor     rcx, rsp; StackCookie
0x1800182ec  call    __security_check_cookie
0x1800182f1  lea     r11, [rsp+148h+var_28]
0x1800182f9  mov     rbx, [r11+30h]
0x1800182fd  mov     rsi, [r11+38h]
0x180018301  mov     rsp, r11
0x180018304  pop     r15
0x180018306  pop     r14
0x180018308  pop     r13
0x18001830a  pop     r12
0x18001830c  pop     rdi
0x18001830d  retn
0x18001830e  xorps   xmm0, xmm0
0x180018311  movups  [rsp+148h+var_78], xmm0
0x180018319  mov     [rsp+148h+var_68], r14d
0x180018321  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180018328  mov     [rsp+148h+var_80], rax
0x180018330  mov     [rsp+148h+var_60], 0B7h
0x18001833b  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180018342  lea     rcx, [rsp+148h+var_80]; pExceptionObject
0x18001834a  call    _CxxThrowException_0
```
