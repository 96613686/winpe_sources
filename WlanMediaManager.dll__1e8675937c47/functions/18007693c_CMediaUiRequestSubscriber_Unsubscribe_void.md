# CMediaUiRequestSubscriber::Unsubscribe(void)

- ea: `0x18007693c`
- end: `0x180076a22`
- name: `?Unsubscribe@CMediaUiRequestSubscriber@@QEAAJXZ`
- size: `230`
- prototype: `__int64 __fastcall(CMediaUiRequestSubscriber *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ca40`
- `0x1800762ec`

## callees

- `0x1800761c8`
- `0x18007693c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007698c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076a07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007698c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076a07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076970`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076970`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769f7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800769a6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800769ec`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800769a6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800769ec`

## pseudocode

```c
__int64 __fastcall CMediaUiRequestSubscriber::Unsubscribe(CMediaUiRequestSubscriber *this)
{
  unsigned int v2; // esi
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  __int64 v5; // rcx
  __int64 *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rbp
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 5, 1, 0) )
  {
    return (unsigned int)-2147019873;
  }
  else
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    v4 = v3;
    if ( *((_BYTE *)this + 16) )
    {
      v2 = 0;
      LeaveCriticalSection(v3);
      v5 = *((_QWORD *)this + 1);
      *((_QWORD *)this + 9) = _scrt_stub_for_is_c_termination_complete;
      if ( v5 )
      {
        ((void (*)(void))RtlUnsubscribeWnfNotificationWaitForCompletion)();
        *((_QWORD *)this + 1) = 0;
      }
      while ( 1 )
      {
        EnterCriticalSection(v3);
        v6 = (__int64 *)*((_QWORD *)this + 12);
        v7 = *v6;
        if ( (__int64 *)*v6 == v6 )
        {
          v8 = 0;
        }
        else
        {
          v8 = *(_QWORD *)(v7 + 40);
          std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,_WNF_USER_SUBSCRIPTION *,WnfStateNameCompare,std::allocator<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>>>,0>(
            (__int64)this + 96,
            &v10,
            v7);
        }
        LeaveCriticalSection(v3);
        if ( !v8 )
          break;
        RtlUnsubscribeWnfNotificationWaitForCompletion(v8);
      }
      EnterCriticalSection(v3);
      *((_BYTE *)this + 16) = 0;
      v4 = v3;
      *((_DWORD *)this + 5) = 0;
    }
    else
    {
      *((_BYTE *)this + 16) = 1;
      v2 = -2147019873;
    }
    LeaveCriticalSection(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18007693c  mov     [rsp+arg_8], rbx
0x180076941  mov     [rsp+arg_10], rbp
0x180076946  push    rsi
0x180076947  push    rdi
0x180076948  push    r14
0x18007694a  sub     rsp, 20h
0x18007694e  mov     rbx, rcx
0x180076951  mov     esi, 1
0x180076956  xor     eax, eax
0x180076958  lock cmpxchg [rcx+14h], esi
0x18007695d  jz      short loc_180076969
0x18007695f  mov     esi, 8007139Fh
0x180076964  jmp     loc_180076A0D
0x180076969  lea     rdi, [rcx+20h]
0x18007696d  mov     rcx, rdi; lpCriticalSection
0x180076970  call    cs:__imp_EnterCriticalSection
0x180076976  cmp     byte ptr [rbx+10h], 0
0x18007697a  mov     rcx, rdi; lpCriticalSection
0x18007697d  jnz     short loc_18007698A
0x18007697f  mov     [rbx+10h], sil
0x180076983  mov     esi, 8007139Fh
0x180076988  jmp     short loc_180076A07
0x18007698a  xor     esi, esi
0x18007698c  call    cs:__imp_LeaveCriticalSection
0x180076992  mov     rcx, [rbx+8]
0x180076996  lea     rax, __scrt_stub_for_is_c_termination_complete
0x18007699d  mov     [rbx+48h], rax
0x1800769a1  test    rcx, rcx
0x1800769a4  jz      short loc_1800769B0
0x1800769a6  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800769ac  mov     [rbx+8], rsi
0x1800769b0  mov     rcx, rdi; lpCriticalSection
0x1800769b3  call    cs:__imp_EnterCriticalSection
0x1800769b9  mov     rax, [rbx+60h]
0x1800769bd  mov     r8, [rax]
0x1800769c0  cmp     r8, rax
0x1800769c3  jnz     short loc_1800769C9
0x1800769c5  xor     ebp, ebp
0x1800769c7  jmp     short loc_1800769DB
0x1800769c9  mov     rbp, [r8+28h]
0x1800769cd  lea     rdx, [rsp+38h+arg_0]
0x1800769d2  lea     rcx, [rbx+60h]
0x1800769d6  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@UWnfStateNameCompare@@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,_WNF_USER_SUBSCRIPTION *,WnfStateNameCompare,std::allocator<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>>>)
0x1800769db  mov     rcx, rdi; lpCriticalSection
0x1800769de  call    cs:__imp_LeaveCriticalSection
0x1800769e4  test    rbp, rbp
0x1800769e7  jz      short loc_1800769F4
0x1800769e9  mov     rcx, rbp
0x1800769ec  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800769f2  jmp     short loc_1800769B0
0x1800769f4  mov     rcx, rdi; lpCriticalSection
0x1800769f7  call    cs:__imp_EnterCriticalSection
0x1800769fd  mov     [rbx+10h], sil
0x180076a01  mov     rcx, rdi; lpCriticalSection
0x180076a04  mov     [rbx+14h], esi
0x180076a07  call    cs:__imp_LeaveCriticalSection
0x180076a0d  mov     rbx, [rsp+38h+arg_8]
0x180076a12  mov     eax, esi
0x180076a14  mov     rbp, [rsp+38h+arg_10]
0x180076a19  add     rsp, 20h
0x180076a1d  pop     r14
0x180076a1f  pop     rdi
0x180076a20  pop     rsi
0x180076a21  retn
```
