# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180010cd0`
- end: `0x180010d64`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010ca8`

## callees

- `0x18000db40`
- `0x180010cd0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010cea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010cea`

## pseudocode

```c
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
    v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    v3->Ptr = 0;
    if ( v5
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
0x180010cd0  mov     [rsp+arg_8], rbx
0x180010cd5  push    rdi
0x180010cd6  sub     rsp, 20h
0x180010cda  mov     eax, [rcx]
0x180010cdc  mov     rdi, rcx
0x180010cdf  test    eax, eax
0x180010ce1  jz      short loc_180010D57
0x180010ce3  lea     rbx, [rcx+8]
0x180010ce7  mov     rcx, rbx; SRWLock
0x180010cea  call    cs:__imp_AcquireSRWLockExclusive
0x180010cf0  mov     [rsp+28h+arg_0], rbx
0x180010cf5  lea     rbx, [rdi+60h]
0x180010cf9  cmp     qword ptr [rbx], 0
0x180010cfd  jz      short loc_180010D05
0x180010cff  mov     ebx, [rdi+1Ch]
0x180010d02  nop
0x180010d03  jmp     short loc_180010D49
0x180010d05  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180010d0c  mov     qword ptr [rbx], 0
0x180010d13  test    rax, rax
0x180010d16  jnz     short loc_180010D24
0x180010d18  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180010d1f  test    rax, rax
0x180010d22  jz      short loc_180010D36
0x180010d24  mov     r8, rdi
0x180010d27  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180010d2e  mov     rcx, rbx
0x180010d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d36  cmp     qword ptr [rbx], 0
0x180010d3a  jnz     short loc_180010D40
0x180010d3c  xor     ebx, ebx
0x180010d3e  jmp     short loc_180010D49
0x180010d40  mov     ebx, 1
0x180010d45  nop
0x180010d46  mov     [rdi+1Ch], ebx
0x180010d49  lea     rcx, [rsp+28h+arg_0]
0x180010d4e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010d53  mov     eax, ebx
0x180010d55  jmp     short loc_180010D59
0x180010d57  xor     eax, eax
0x180010d59  mov     rbx, [rsp+28h+arg_8]
0x180010d5e  add     rsp, 20h
0x180010d62  pop     rdi
0x180010d63  retn
```
