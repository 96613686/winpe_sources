# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x140005294`
- end: `0x140005328`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000526c`

## callees

- `0x140004604`
- `0x140005294`
- `0x140020010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400052ae`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400052ae`

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
0x140005294  mov     [rsp+arg_8], rbx
0x140005299  push    rdi
0x14000529a  sub     rsp, 20h
0x14000529e  mov     eax, [rcx]
0x1400052a0  mov     rdi, rcx
0x1400052a3  test    eax, eax
0x1400052a5  jz      short loc_14000531B
0x1400052a7  lea     rbx, [rcx+8]
0x1400052ab  mov     rcx, rbx; SRWLock
0x1400052ae  call    cs:__imp_AcquireSRWLockExclusive
0x1400052b4  mov     [rsp+28h+arg_0], rbx
0x1400052b9  lea     rbx, [rdi+60h]
0x1400052bd  cmp     qword ptr [rbx], 0
0x1400052c1  jz      short loc_1400052C9
0x1400052c3  mov     ebx, [rdi+1Ch]
0x1400052c6  nop
0x1400052c7  jmp     short loc_14000530D
0x1400052c9  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400052d0  mov     qword ptr [rbx], 0
0x1400052d7  test    rax, rax
0x1400052da  jnz     short loc_1400052E8
0x1400052dc  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1400052e3  test    rax, rax
0x1400052e6  jz      short loc_1400052FA
0x1400052e8  mov     r8, rdi
0x1400052eb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1400052f2  mov     rcx, rbx
0x1400052f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052fa  cmp     qword ptr [rbx], 0
0x1400052fe  jnz     short loc_140005304
0x140005300  xor     ebx, ebx
0x140005302  jmp     short loc_14000530D
0x140005304  mov     ebx, 1
0x140005309  nop
0x14000530a  mov     [rdi+1Ch], ebx
0x14000530d  lea     rcx, [rsp+28h+arg_0]
0x140005312  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140005317  mov     eax, ebx
0x140005319  jmp     short loc_14000531D
0x14000531b  xor     eax, eax
0x14000531d  mov     rbx, [rsp+28h+arg_8]
0x140005322  add     rsp, 20h
0x140005326  pop     rdi
0x140005327  retn
```
