# Broker::BrokerEvent::~BrokerEvent(void)

- ea: `0x18000f7fc`
- end: `0x18000f87f`
- name: `??1BrokerEvent@Broker@@UEAA@XZ`
- size: `131`
- prototype: `void __fastcall(Broker::BrokerEvent *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f7c0`

## callees

- `0x180004ae0`
- `0x18000f7fc`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18000f860`
- `ntdll!NtDeleteWnfStateName` at `0x18000f860`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f834`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f834`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f84b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f84b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f83a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f83a`

## pseudocode

```c
void __fastcall Broker::BrokerEvent::~BrokerEvent(Broker::BrokerEvent *this)
{
  __int64 v1; // rbp
  __int64 v2; // r14
  int v4; // ebx
  std::_Ref_count_base *v5; // rcx

  v1 = *((_QWORD *)this + 6);
  v2 = *((unsigned int *)this + 7);
  *(_QWORD *)this = &Broker::BrokerEvent::`vftable';
  if ( *(_DWORD *)(*(_QWORD *)(v1 + 88) + 4 * v2) != -1 )
  {
    v4 = *((_DWORD *)this + 8);
    RtlAcquireSRWLockExclusive(v1 + 144);
    GetCurrentThreadId();
    *(_DWORD *)(*(_QWORD *)(v1 + 112) + 4 * v2) -= v4;
    RtlReleaseSRWLockExclusive(v1 + 144);
  }
  if ( *((_DWORD *)this + 16) || *((_DWORD *)this + 17) )
    NtDeleteWnfStateName();
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 7);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x18000f7fc  push    rbx
0x18000f7fe  push    rbp
0x18000f7ff  push    rsi
0x18000f800  push    rdi
0x18000f801  push    r14
0x18000f803  sub     rsp, 20h
0x18000f807  mov     rbp, [rcx+30h]
0x18000f80b  lea     rax, ??_7BrokerEvent@Broker@@6B@; const Broker::BrokerEvent::`vftable'
0x18000f812  mov     r14d, [rcx+1Ch]
0x18000f816  mov     rsi, rcx
0x18000f819  mov     [rcx], rax
0x18000f81c  mov     rax, [rbp+58h]
0x18000f820  cmp     dword ptr [rax+r14*4], 0FFFFFFFFh
0x18000f825  jz      short loc_18000F851
0x18000f827  mov     ebx, [rcx+20h]
0x18000f82a  lea     rdi, [rbp+90h]
0x18000f831  mov     rcx, rdi
0x18000f834  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000f83a  call    cs:__imp_GetCurrentThreadId
0x18000f840  mov     rax, [rbp+70h]
0x18000f844  mov     rcx, rdi
0x18000f847  sub     [rax+r14*4], ebx
0x18000f84b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000f851  lea     rcx, [rsi+40h]
0x18000f855  cmp     dword ptr [rcx], 0
0x18000f858  jnz     short loc_18000F860
0x18000f85a  cmp     dword ptr [rsi+44h], 0
0x18000f85e  jz      short loc_18000F866
0x18000f860  call    cs:__imp_NtDeleteWnfStateName
0x18000f866  mov     rcx, [rsi+38h]; this
0x18000f86a  test    rcx, rcx
0x18000f86d  jz      short loc_18000F874
0x18000f86f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f874  add     rsp, 20h
0x18000f878  pop     r14
0x18000f87a  pop     rdi
0x18000f87b  pop     rsi
0x18000f87c  pop     rbp
0x18000f87d  pop     rbx
0x18000f87e  retn
```
