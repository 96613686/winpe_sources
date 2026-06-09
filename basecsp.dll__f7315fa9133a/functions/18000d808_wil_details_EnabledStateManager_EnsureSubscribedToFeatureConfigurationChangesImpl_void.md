# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18000d808`
- end: `0x18000d89c`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000d7e0`

## callees

- `0x18000bc80`
- `0x18000d808`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d822`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d822`

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
0x18000d808  mov     [rsp+arg_8], rbx
0x18000d80d  push    rdi
0x18000d80e  sub     rsp, 20h
0x18000d812  mov     rdi, rcx
0x18000d815  mov     eax, [rcx]
0x18000d817  test    eax, eax
0x18000d819  jz      short loc_18000D88F
0x18000d81b  lea     rbx, [rcx+8]
0x18000d81f  mov     rcx, rbx; SRWLock
0x18000d822  call    cs:__imp_AcquireSRWLockExclusive
0x18000d828  mov     [rsp+28h+arg_0], rbx
0x18000d82d  lea     rbx, [rdi+60h]
0x18000d831  cmp     qword ptr [rbx], 0
0x18000d835  jz      short loc_18000D83D
0x18000d837  mov     ebx, [rdi+1Ch]
0x18000d83a  nop
0x18000d83b  jmp     short loc_18000D881
0x18000d83d  mov     qword ptr [rbx], 0
0x18000d844  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000d84b  test    rax, rax
0x18000d84e  jnz     short loc_18000D85C
0x18000d850  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000d857  test    rax, rax
0x18000d85a  jz      short loc_18000D86E
0x18000d85c  mov     r8, rdi
0x18000d85f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000d866  mov     rcx, rbx
0x18000d869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d86e  cmp     qword ptr [rbx], 0
0x18000d872  jnz     short loc_18000D878
0x18000d874  xor     ebx, ebx
0x18000d876  jmp     short loc_18000D881
0x18000d878  nop
0x18000d879  mov     ebx, 1
0x18000d87e  mov     [rdi+1Ch], ebx
0x18000d881  lea     rcx, [rsp+28h+arg_0]
0x18000d886  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d88b  mov     eax, ebx
0x18000d88d  jmp     short loc_18000D891
0x18000d88f  xor     eax, eax
0x18000d891  mov     rbx, [rsp+28h+arg_8]
0x18000d896  add     rsp, 20h
0x18000d89a  pop     rdi
0x18000d89b  retn
```
