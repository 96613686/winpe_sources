# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x14000b394`
- end: `0x14000b428`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000b36c`

## callees

- `0x1400092f0`
- `0x14000b394`
- `0x14001c010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b3ae`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b3ae`

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
0x14000b394  mov     [rsp+arg_8], rbx
0x14000b399  push    rdi
0x14000b39a  sub     rsp, 20h
0x14000b39e  mov     rdi, rcx
0x14000b3a1  mov     eax, [rcx]
0x14000b3a3  test    eax, eax
0x14000b3a5  jz      short loc_14000B41B
0x14000b3a7  lea     rbx, [rcx+8]
0x14000b3ab  mov     rcx, rbx; SRWLock
0x14000b3ae  call    cs:__imp_AcquireSRWLockExclusive
0x14000b3b4  mov     [rsp+28h+arg_0], rbx
0x14000b3b9  lea     rbx, [rdi+60h]
0x14000b3bd  cmp     qword ptr [rbx], 0
0x14000b3c1  jz      short loc_14000B3C9
0x14000b3c3  mov     ebx, [rdi+1Ch]
0x14000b3c6  nop
0x14000b3c7  jmp     short loc_14000B40D
0x14000b3c9  mov     qword ptr [rbx], 0
0x14000b3d0  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000b3d7  test    rax, rax
0x14000b3da  jnz     short loc_14000B3E8
0x14000b3dc  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x14000b3e3  test    rax, rax
0x14000b3e6  jz      short loc_14000B3FA
0x14000b3e8  mov     r8, rdi
0x14000b3eb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x14000b3f2  mov     rcx, rbx
0x14000b3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b3fa  cmp     qword ptr [rbx], 0
0x14000b3fe  jnz     short loc_14000B404
0x14000b400  xor     ebx, ebx
0x14000b402  jmp     short loc_14000B40D
0x14000b404  nop
0x14000b405  mov     ebx, 1
0x14000b40a  mov     [rdi+1Ch], ebx
0x14000b40d  lea     rcx, [rsp+28h+arg_0]
0x14000b412  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000b417  mov     eax, ebx
0x14000b419  jmp     short loc_14000B41D
0x14000b41b  xor     eax, eax
0x14000b41d  mov     rbx, [rsp+28h+arg_8]
0x14000b422  add     rsp, 20h
0x14000b426  pop     rdi
0x14000b427  retn
```
