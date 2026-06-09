# _anonymous_namespace_::ServiceLifetimeManager::_ServiceLifetimeManager

- ea: `0x140005a10`
- end: `0x140005add`
- name: `_anonymous_namespace_::ServiceLifetimeManager::_ServiceLifetimeManager`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140005ae0`
- `0x140015be0`

## callees

- `0x140001fac`
- `0x140005a10`
- `0x140010a04`
- `0x14001382c`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x140005aa7`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005aa7`
- `KERNEL32!IsThreadpoolTimerSet` at `0x140005a78`
- `KERNEL32!IsThreadpoolTimerSet` at `0x140005a78`
- `KERNEL32!SetThreadpoolTimer` at `0x140005a8e`
- `KERNEL32!SetThreadpoolTimer` at `0x140005a8e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005a9d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005a9d`

## pseudocode

```c
void **__fastcall anonymous_namespace_::ServiceLifetimeManager::_ServiceLifetimeManager(__int64 a1)
{
  _QWORD **v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx
  struct _TP_TIMER *v5; // rcx
  void **result; // rax

  DiagHubCommon::ProcessLifetimeMonitor::~ProcessLifetimeMonitor((DiagHubCommon::ProcessLifetimeMonitor *)(a1 + 112));
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(a1 + 72);
  v2 = *(_QWORD ***)(a1 + 56);
  *v2[1] = 0;
  v3 = *v2;
  if ( *v2 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      operator delete(v3);
      v3 = v4;
    }
    while ( v4 );
  }
  operator delete(*(void **)(a1 + 56));
  if ( *(_BYTE *)(a1 + 32) )
  {
    v5 = *(struct _TP_TIMER **)(a1 + 24);
    if ( v5 )
    {
      if ( IsThreadpoolTimerSet(v5) )
      {
        SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 24), 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(a1 + 24), 1);
      }
      CloseThreadpoolTimer(*(PTP_TIMER *)(a1 + 24));
      *(_QWORD *)(a1 + 24) = 0;
    }
  }
  *(_QWORD *)(a1 + 8) = &CModuleRefCount::`vftable';
  result = &CRefCount::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef);
  *(_QWORD *)(a1 + 8) = &CRefCount::`vftable';
  return result;
}

```

## disassembly

```asm
0x140005a10  mov     [rsp+arg_8], rbx
0x140005a15  push    rdi
0x140005a16  sub     rsp, 20h
0x140005a1a  mov     rdi, rcx
0x140005a1d  add     rcx, 70h ; 'p'; this
0x140005a21  call    ??1ProcessLifetimeMonitor@DiagHubCommon@@QEAA@XZ; DiagHubCommon::ProcessLifetimeMonitor::~ProcessLifetimeMonitor(void)
0x140005a26  lea     rcx, [rdi+48h]
0x140005a2a  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(void)
0x140005a2f  mov     rdx, [rdi+38h]
0x140005a33  mov     rax, [rdx+8]
0x140005a37  mov     qword ptr [rax], 0
0x140005a3e  mov     rcx, [rdx]; Block
0x140005a41  test    rcx, rcx
0x140005a44  jz      short loc_140005A5B
0x140005a46  mov     rbx, [rcx]
0x140005a49  mov     edx, 20h ; ' '
0x140005a4e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005a53  mov     rcx, rbx
0x140005a56  test    rbx, rbx
0x140005a59  jnz     short loc_140005A46
0x140005a5b  mov     rcx, [rdi+38h]; Block
0x140005a5f  mov     edx, 20h ; ' '
0x140005a64  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005a69  cmp     byte ptr [rdi+20h], 0
0x140005a6d  jz      short loc_140005AB5
0x140005a6f  mov     rcx, [rdi+18h]; pti
0x140005a73  test    rcx, rcx
0x140005a76  jz      short loc_140005AB5
0x140005a78  call    cs:__imp_IsThreadpoolTimerSet
0x140005a7e  test    eax, eax
0x140005a80  jz      short loc_140005AA3
0x140005a82  mov     rcx, [rdi+18h]; pti
0x140005a86  xor     r9d, r9d; msWindowLength
0x140005a89  xor     r8d, r8d; msPeriod
0x140005a8c  xor     edx, edx; pftDueTime
0x140005a8e  call    cs:__imp_SetThreadpoolTimer
0x140005a94  mov     rcx, [rdi+18h]; pti
0x140005a98  mov     edx, 1; fCancelPendingCallbacks
0x140005a9d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005aa3  mov     rcx, [rdi+18h]; pti
0x140005aa7  call    cs:__imp_CloseThreadpoolTimer
0x140005aad  mov     qword ptr [rdi+18h], 0
0x140005ab5  mov     rbx, [rsp+28h+arg_8]
0x140005aba  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x140005ac1  mov     [rdi+8], rax
0x140005ac5  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x140005acc  lock dec cs:?s_ulcModuleRef@CModuleRefCount@@0KA; ulong CModuleRefCount::s_ulcModuleRef
0x140005ad3  mov     [rdi+8], rax
0x140005ad7  add     rsp, 20h
0x140005adb  pop     rdi
0x140005adc  retn
```
