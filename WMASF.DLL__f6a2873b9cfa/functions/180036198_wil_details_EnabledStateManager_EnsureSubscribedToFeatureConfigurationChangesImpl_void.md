# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180036198`
- end: `0x18003622c`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180036170`

## callees

- `0x18003368c`
- `0x180036198`
- `0x180040010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800361b2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800361b2`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  unsigned int Ptr_high; // ebx
  void (__fastcall *v5)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax
  RTL_SRWLOCK *v7; // [rsp+20h] [rbp-18h] BYREF

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
0x180036198  mov     [rsp+arg_8], rbx
0x18003619d  push    rdi
0x18003619e  sub     rsp, 30h
0x1800361a2  mov     eax, [rcx]
0x1800361a4  mov     rdi, rcx
0x1800361a7  test    eax, eax
0x1800361a9  jz      short loc_18003621F
0x1800361ab  lea     rbx, [rcx+8]
0x1800361af  mov     rcx, rbx; SRWLock
0x1800361b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800361b8  mov     [rsp+38h+var_18], rbx
0x1800361bd  lea     rbx, [rdi+60h]
0x1800361c1  cmp     qword ptr [rbx], 0
0x1800361c5  jz      short loc_1800361CD
0x1800361c7  mov     ebx, [rdi+1Ch]
0x1800361ca  nop
0x1800361cb  jmp     short loc_180036211
0x1800361cd  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800361d4  mov     qword ptr [rbx], 0
0x1800361db  test    rax, rax
0x1800361de  jnz     short loc_1800361EC
0x1800361e0  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800361e7  test    rax, rax
0x1800361ea  jz      short loc_1800361FE
0x1800361ec  mov     r8, rdi
0x1800361ef  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800361f6  mov     rcx, rbx
0x1800361f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361fe  cmp     qword ptr [rbx], 0
0x180036202  jnz     short loc_180036208
0x180036204  xor     ebx, ebx
0x180036206  jmp     short loc_180036211
0x180036208  mov     ebx, 1
0x18003620d  nop
0x18003620e  mov     [rdi+1Ch], ebx
0x180036211  lea     rcx, [rsp+38h+var_18]
0x180036216  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003621b  mov     eax, ebx
0x18003621d  jmp     short loc_180036221
0x18003621f  xor     eax, eax
0x180036221  mov     rbx, [rsp+38h+arg_8]
0x180036226  add     rsp, 30h
0x18003622a  pop     rdi
0x18003622b  retn
```
