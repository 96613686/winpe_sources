# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180005aa4`
- end: `0x180005b38`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005a7c`

## callees

- `0x180004e64`
- `0x180005aa4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005abe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005abe`

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
0x180005aa4  mov     [rsp+arg_8], rbx
0x180005aa9  push    rdi
0x180005aaa  sub     rsp, 20h
0x180005aae  mov     rdi, rcx
0x180005ab1  mov     eax, [rcx]
0x180005ab3  test    eax, eax
0x180005ab5  jz      short loc_180005B2B
0x180005ab7  lea     rbx, [rcx+8]
0x180005abb  mov     rcx, rbx; SRWLock
0x180005abe  call    cs:__imp_AcquireSRWLockExclusive
0x180005ac4  mov     [rsp+28h+arg_0], rbx
0x180005ac9  lea     rbx, [rdi+60h]
0x180005acd  cmp     qword ptr [rbx], 0
0x180005ad1  jz      short loc_180005AD9
0x180005ad3  mov     ebx, [rdi+1Ch]
0x180005ad6  nop
0x180005ad7  jmp     short loc_180005B1D
0x180005ad9  mov     qword ptr [rbx], 0
0x180005ae0  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005ae7  test    rax, rax
0x180005aea  jnz     short loc_180005AF8
0x180005aec  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005af3  test    rax, rax
0x180005af6  jz      short loc_180005B0A
0x180005af8  mov     r8, rdi
0x180005afb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005b02  mov     rcx, rbx
0x180005b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b0a  cmp     qword ptr [rbx], 0
0x180005b0e  jnz     short loc_180005B14
0x180005b10  xor     ebx, ebx
0x180005b12  jmp     short loc_180005B1D
0x180005b14  nop
0x180005b15  mov     ebx, 1
0x180005b1a  mov     [rdi+1Ch], ebx
0x180005b1d  lea     rcx, [rsp+28h+arg_0]
0x180005b22  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180005b27  mov     eax, ebx
0x180005b29  jmp     short loc_180005B2D
0x180005b2b  xor     eax, eax
0x180005b2d  mov     rbx, [rsp+28h+arg_8]
0x180005b32  add     rsp, 20h
0x180005b36  pop     rdi
0x180005b37  retn
```
