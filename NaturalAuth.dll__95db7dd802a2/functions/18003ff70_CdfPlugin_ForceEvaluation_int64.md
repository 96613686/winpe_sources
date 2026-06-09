# CdfPlugin::ForceEvaluation(__int64)

- ea: `0x18003ff70`
- end: `0x18004005f`
- name: `?ForceEvaluation@CdfPlugin@@UEAAX_J@Z`
- size: `239`
- prototype: `void __fastcall(CdfPlugin *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a7d0`
- `0x18000b5b0`
- `0x18000b6f0`
- `0x18003ff70`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ff89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ff89`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180040032`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180040032`
- `DeviceCredential!DeviceCredentialMgrCheckPresence` at `0x180040038`
- `DeviceCredential!DeviceCredentialMgrCheckPresence` at `0x180040038`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CdfPlugin::ForceEvaluation(CdfPlugin *this)
{
  RTL_SRWLOCK *v2; // rbx
  char v3; // bl
  struct _FILETIME v4; // rax
  _QWORD *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v7; // [rsp+40h] [rbp+18h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 112);
  AcquireSRWLockExclusive((PSRWLOCK)this + 14);
  v7 = v2;
  if ( !_InterlockedCompareExchange8((volatile signed __int8 *)this + 104, 1, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f58bb35385b7316b81a3583d99bb799e_Traceguids);
    v3 = 0;
    v4 = (struct _FILETIME)**((_QWORD **)this + 6);
    pftDueTime = v4;
    while ( !*(_BYTE *)(*(_QWORD *)&v4 + 25LL) )
    {
      v5 = *(_QWORD **)(*(_QWORD *)&v4 + 40LL);
      if ( *(_QWORD *)(v5[1] + 24LL) )
      {
        v3 = 1;
        (*(void (__fastcall **)(_QWORD *))(*v5 + 40LL))(v5);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,SignalInfo::List>>>,std::_Iterator_base0>::operator++(&pftDueTime);
      v4 = pftDueTime;
    }
    if ( v3 )
    {
      pftDueTime = (struct _FILETIME)-300000000LL;
      SetThreadpoolTimer(*((PTP_TIMER *)this + 12), &pftDueTime, 0, 0);
      DeviceCredentialMgrCheckPresence();
    }
    else
    {
      *((_BYTE *)this + 104) = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
}

```

## disassembly

```asm
0x18003ff70  mov     [rsp+arg_8], rbx
0x18003ff75  mov     [rsp+arg_18], rsi
0x18003ff7a  push    rdi
0x18003ff7b  sub     rsp, 20h
0x18003ff7f  mov     rdi, rcx
0x18003ff82  lea     rbx, [rcx+70h]
0x18003ff86  mov     rcx, rbx; SRWLock
0x18003ff89  call    cs:__imp_AcquireSRWLockExclusive
0x18003ff8f  mov     [rsp+28h+arg_10], rbx
0x18003ff94  mov     esi, 1
0x18003ff99  xor     eax, eax
0x18003ff9b  lock cmpxchg [rdi+68h], sil
0x18003ffa1  jnz     loc_180040045
0x18003ffa7  lea     rax, WPP_GLOBAL_Control
0x18003ffae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ffb5  cmp     rcx, rax
0x18003ffb8  jz      short loc_18003FFD3
0x18003ffba  test    byte ptr [rcx+1Ch], 4
0x18003ffbe  jz      short loc_18003FFD3
0x18003ffc0  lea     edx, [rsi+0Eh]
0x18003ffc3  lea     r8, WPP_f58bb35385b7316b81a3583d99bb799e_Traceguids
0x18003ffca  mov     rcx, [rcx+10h]
0x18003ffce  call    WPP_SF_
0x18003ffd3  xor     bl, bl
0x18003ffd5  mov     rax, [rdi+30h]
0x18003ffd9  mov     rax, [rax]
0x18003ffdc  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18003ffe1  cmp     byte ptr [rax+19h], 0
0x18003ffe5  jnz     short loc_180040016
0x18003ffe7  mov     rcx, [rax+28h]
0x18003ffeb  mov     rax, [rcx+8]
0x18003ffef  cmp     qword ptr [rax+18h], 0
0x18003fff4  jbe     short loc_180040005
0x18003fff6  mov     bl, sil
0x18003fff9  mov     rax, [rcx]
0x18003fffc  mov     rax, [rax+28h]
0x180040000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040005  lea     rcx, [rsp+28h+pftDueTime]
0x18004000a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@UList@SignalInfo@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,SignalInfo::List>>>,std::_Iterator_base0>::operator++(void)
0x18004000f  mov     rax, qword ptr [rsp+28h+pftDueTime.dwLowDateTime]
0x180040014  jmp     short loc_18003FFE1
0x180040016  test    bl, bl
0x180040018  jz      short loc_180040040
0x18004001a  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x180040023  xor     r9d, r9d; msWindowLength
0x180040026  xor     r8d, r8d; msPeriod
0x180040029  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18004002e  mov     rcx, [rdi+60h]; pti
0x180040032  call    cs:__imp_SetThreadpoolTimer
0x180040038  call    cs:__imp_DeviceCredentialMgrCheckPresence
0x18004003e  jmp     short loc_180040045
0x180040040  xor     eax, eax
0x180040042  xchg    al, [rdi+68h]
0x180040045  lea     rcx, [rsp+28h+arg_10]
0x18004004a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004004f  mov     rbx, [rsp+28h+arg_8]
0x180040054  mov     rsi, [rsp+28h+arg_18]
0x180040059  add     rsp, 20h
0x18004005d  pop     rdi
0x18004005e  retn
```
