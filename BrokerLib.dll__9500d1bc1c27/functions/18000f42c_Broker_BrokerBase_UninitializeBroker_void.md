# Broker::BrokerBase::UninitializeBroker(void)

- ea: `0x18000f42c`
- end: `0x18000f57b`
- name: `?UninitializeBroker@BrokerBase@Broker@@QEAAXXZ`
- size: `335`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001364c`

## callees

- `0x180004ae0`
- `0x180005b50`
- `0x18000d5cc`
- `0x18000f42c`
- `0x180013a30`
- `0x180014d90`
- `0x1800183bc`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f47e`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f47e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f4be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f4be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f574`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f4c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f4c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Broker::BrokerBase::UninitializeBroker(Broker::BrokerBase *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 First; // rax
  std::_Ref_count_base *v7[2]; // [rsp+20h] [rbp-30h] BYREF
  Broker::BrokerBase *v8; // [rsp+30h] [rbp-20h]
  char v9; // [rsp+38h] [rbp-18h]
  DWORD CurrentThreadId; // [rsp+3Ch] [rbp-14h]
  _BYTE v11[8]; // [rsp+40h] [rbp-10h] BYREF
  std::_Ref_count_base *v12; // [rsp+48h] [rbp-8h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1));
  if ( _InterlockedExchange64((volatile __int64 *)this + 40, 0) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  std::shared_ptr<Broker::RpcServerRegistration>::reset((char *)this + 288);
  *((_QWORD *)this + 38) = 0;
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 39);
  *((_QWORD *)this + 39) = 0;
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v8 = this;
  RtlAcquireSRWLockExclusive(this);
  CurrentThreadId = GetCurrentThreadId();
  v9 = 1;
  if ( *((_QWORD *)this + 27) )
  {
    v4 = **((_QWORD **)this + 26);
    v5 = *(_QWORD *)(v4 + 48);
    if ( v5 )
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
    v3 = *(std::_Ref_count_base **)(v4 + 40);
    v7[0] = v3;
    v7[1] = *(std::_Ref_count_base **)(v4 + 48);
  }
  else
  {
    *(_OWORD *)v7 = 0;
    v3 = 0;
  }
  while ( v3 )
  {
    Broker::BrokerBase::DestroyEvent(this, 3, v7);
    First = Broker::BrokeredEventTable::GetFirst((char *)this + 208, v11);
    std::shared_ptr<Broker::BrokerEvent>::operator=(v7, First);
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    v3 = v7[0];
  }
  if ( v7[1] )
    std::_Ref_count_base::_Decref(v7[1]);
  RtlReleaseSRWLockExclusive(this);
}

```

## disassembly

```asm
0x18000f42c  mov     [rsp-8+arg_0], rbx
0x18000f431  mov     [rsp-8+arg_8], rdi
0x18000f436  push    rbp
0x18000f437  mov     rbp, rsp
0x18000f43a  sub     rsp, 50h
0x18000f43e  mov     rbx, rcx
0x18000f441  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f448  test    dword ptr [rcx+1Ch], 800h
0x18000f44f  jz      short loc_18000F470
0x18000f451  cmp     byte ptr [rcx+19h], 5
0x18000f455  jb      short loc_18000F470
0x18000f457  mov     edx, 14h
0x18000f45c  mov     r9, [rbx+8]
0x18000f460  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000f467  mov     rcx, [rcx+10h]
0x18000f46b  call    WPP_SF__guid_
0x18000f470  xor     ecx, ecx
0x18000f472  xchg    rcx, [rbx+140h]
0x18000f479  test    rcx, rcx
0x18000f47c  jz      short loc_18000F484
0x18000f47e  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000f484  lea     rcx, [rbx+120h]
0x18000f48b  call    ?reset@?$shared_ptr@VRpcServerRegistration@Broker@@@std@@QEAAXXZ; std::shared_ptr<Broker::RpcServerRegistration>::reset(void)
0x18000f490  mov     qword ptr [rbx+130h], 0
0x18000f49b  mov     rcx, [rbx+138h]; this
0x18000f4a2  mov     qword ptr [rbx+138h], 0
0x18000f4ad  test    rcx, rcx
0x18000f4b0  jz      short loc_18000F4B7
0x18000f4b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f4b7  mov     [rbp+var_20], rbx
0x18000f4bb  mov     rcx, rbx
0x18000f4be  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000f4c4  call    cs:__imp_GetCurrentThreadId
0x18000f4ca  mov     [rbp+var_14], eax
0x18000f4cd  mov     [rbp+var_18], 1
0x18000f4d1  lea     rdi, [rbx+0D0h]
0x18000f4d8  cmp     qword ptr [rdi+8], 0
0x18000f4dd  jnz     short loc_18000F4EE
0x18000f4df  xorps   xmm1, xmm1
0x18000f4e2  movdqu  xmmword ptr [rbp+var_30], xmm1
0x18000f4e7  movq    rcx, xmm1
0x18000f4ec  jmp     short loc_18000F511
0x18000f4ee  mov     rax, [rdi]
0x18000f4f1  mov     rax, [rax]
0x18000f4f4  mov     rcx, [rax+30h]
0x18000f4f8  test    rcx, rcx
0x18000f4fb  jz      short loc_18000F501
0x18000f4fd  lock inc dword ptr [rcx+8]
0x18000f501  mov     rcx, [rax+28h]
0x18000f505  mov     [rbp+var_30], rcx
0x18000f509  mov     rax, [rax+30h]
0x18000f50d  mov     [rbp+var_30+8], rax
0x18000f511  test    rcx, rcx
0x18000f514  jz      short loc_18000F553
0x18000f516  lea     r8, [rbp+var_30]
0x18000f51a  mov     edx, 3
0x18000f51f  mov     rcx, rbx
0x18000f522  call    ?DestroyEvent@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::DestroyEvent(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> &)
0x18000f527  lea     rdx, [rbp+var_10]
0x18000f52b  mov     rcx, rdi
0x18000f52e  call    ?GetFirst@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@XZ; Broker::BrokeredEventTable::GetFirst(void)
0x18000f533  mov     rdx, rax
0x18000f536  lea     rcx, [rbp+var_30]
0x18000f53a  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000f53f  mov     rcx, [rbp+var_8]; this
0x18000f543  test    rcx, rcx
0x18000f546  jz      short loc_18000F54D
0x18000f548  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f54d  mov     rcx, [rbp+var_30]
0x18000f551  jmp     short loc_18000F511
0x18000f553  mov     rcx, [rbp+var_30+8]; this
0x18000f557  test    rcx, rcx
0x18000f55a  jz      short loc_18000F562
0x18000f55c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f561  nop
0x18000f562  mov     rcx, rbx
0x18000f565  mov     rbx, [rsp+50h+arg_0]
0x18000f56a  mov     rdi, [rsp+50h+arg_8]
0x18000f56f  add     rsp, 50h
0x18000f573  pop     rbp
0x18000f574  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
