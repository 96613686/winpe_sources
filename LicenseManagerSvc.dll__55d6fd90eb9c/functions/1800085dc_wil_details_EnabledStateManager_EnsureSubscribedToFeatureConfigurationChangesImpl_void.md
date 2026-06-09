# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1800085dc`
- end: `0x180008670`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800085b4`

## callees

- `0x180007f88`
- `0x1800085dc`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800085f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800085f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  unsigned int Ptr_high; // ebx
  void (__fastcall *v5)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax
  RTL_SRWLOCK *v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !LODWORD(this->Ptr) )
    return 0;
  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v7 = v2;
  v3 = this + 12;
  if ( this[12].Ptr )
  {
    Ptr_high = HIDWORD(this[3].Ptr);
  }
  else
  {
    v3->Ptr = 0;
    v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
      || (v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
    {
      v5(this + 12, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
    }
    if ( v3->Ptr )
    {
      Ptr_high = 1;
      HIDWORD(this[3].Ptr) = 1;
    }
    else
    {
      Ptr_high = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  return Ptr_high;
}

```

## disassembly

```asm
0x1800085dc  mov     [rsp+arg_8], rbx
0x1800085e1  push    rdi
0x1800085e2  sub     rsp, 20h
0x1800085e6  mov     rdi, rcx
0x1800085e9  mov     eax, [rcx]
0x1800085eb  test    eax, eax
0x1800085ed  jz      short loc_180008663
0x1800085ef  lea     rbx, [rcx+8]
0x1800085f3  mov     rcx, rbx; SRWLock
0x1800085f6  call    cs:__imp_AcquireSRWLockExclusive
0x1800085fc  mov     [rsp+28h+arg_0], rbx
0x180008601  lea     rbx, [rdi+60h]
0x180008605  cmp     qword ptr [rbx], 0
0x180008609  jz      short loc_180008611
0x18000860b  mov     ebx, [rdi+1Ch]
0x18000860e  nop
0x18000860f  jmp     short loc_180008655
0x180008611  mov     qword ptr [rbx], 0
0x180008618  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000861f  test    rax, rax
0x180008622  jnz     short loc_180008630
0x180008624  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000862b  test    rax, rax
0x18000862e  jz      short loc_180008642
0x180008630  mov     r8, rdi
0x180008633  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000863a  mov     rcx, rbx
0x18000863d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008642  cmp     qword ptr [rbx], 0
0x180008646  jnz     short loc_18000864C
0x180008648  xor     ebx, ebx
0x18000864a  jmp     short loc_180008655
0x18000864c  nop
0x18000864d  mov     ebx, 1
0x180008652  mov     [rdi+1Ch], ebx
0x180008655  lea     rcx, [rsp+28h+arg_0]
0x18000865a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000865f  mov     eax, ebx
0x180008661  jmp     short loc_180008665
0x180008663  xor     eax, eax
0x180008665  mov     rbx, [rsp+28h+arg_8]
0x18000866a  add     rsp, 20h
0x18000866e  pop     rdi
0x18000866f  retn
```
