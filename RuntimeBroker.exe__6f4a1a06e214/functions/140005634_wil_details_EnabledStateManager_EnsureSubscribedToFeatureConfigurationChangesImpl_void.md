# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x140005634`
- end: `0x1400056c8`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140005578`

## callees

- `0x140005634`
- `0x1400085c4`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000564e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000564e`

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
0x140005634  mov     [rsp+arg_8], rbx
0x140005639  push    rdi
0x14000563a  sub     rsp, 20h
0x14000563e  mov     eax, [rcx]
0x140005640  mov     rdi, rcx
0x140005643  test    eax, eax
0x140005645  jz      short loc_1400056BB
0x140005647  lea     rbx, [rcx+8]
0x14000564b  mov     rcx, rbx; SRWLock
0x14000564e  call    cs:__imp_AcquireSRWLockExclusive
0x140005654  mov     [rsp+28h+arg_0], rbx
0x140005659  lea     rbx, [rdi+60h]
0x14000565d  cmp     qword ptr [rbx], 0
0x140005661  jz      short loc_140005669
0x140005663  mov     ebx, [rdi+1Ch]
0x140005666  nop
0x140005667  jmp     short loc_1400056AD
0x140005669  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140005670  mov     qword ptr [rbx], 0
0x140005677  test    rax, rax
0x14000567a  jnz     short loc_140005688
0x14000567c  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140005683  test    rax, rax
0x140005686  jz      short loc_14000569A
0x140005688  mov     r8, rdi
0x14000568b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140005692  mov     rcx, rbx
0x140005695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000569a  cmp     qword ptr [rbx], 0
0x14000569e  jnz     short loc_1400056A4
0x1400056a0  xor     ebx, ebx
0x1400056a2  jmp     short loc_1400056AD
0x1400056a4  mov     ebx, 1
0x1400056a9  nop
0x1400056aa  mov     [rdi+1Ch], ebx
0x1400056ad  lea     rcx, [rsp+28h+arg_0]
0x1400056b2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400056b7  mov     eax, ebx
0x1400056b9  jmp     short loc_1400056BD
0x1400056bb  xor     eax, eax
0x1400056bd  mov     rbx, [rsp+28h+arg_8]
0x1400056c2  add     rsp, 20h
0x1400056c6  pop     rdi
0x1400056c7  retn
```
