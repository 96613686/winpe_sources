# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18000496c`
- end: `0x1800049fe`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `146`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004944`

## callees

- `0x180003d78`
- `0x180004650`
- `0x18000496c`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rdi
  unsigned int Ptr_high; // ebx
  void (__fastcall *v4)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF

  if ( !LODWORD(this->Ptr) )
    return 0;
  wil::AcquireSRWLockExclusive(&v6, this + 1);
  v2 = this + 12;
  if ( this[12].Ptr )
  {
    Ptr_high = HIDWORD(this[3].Ptr);
  }
  else
  {
    v2->Ptr = 0;
    v4 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
      || (v4 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
    {
      v4(this + 12, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
    }
    if ( v2->Ptr )
    {
      HIDWORD(this[3].Ptr) = 1;
      Ptr_high = 1;
    }
    else
    {
      Ptr_high = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  return Ptr_high;
}

```

## disassembly

```asm
0x18000496c  mov     [rsp+arg_8], rbx
0x180004971  push    rdi
0x180004972  sub     rsp, 20h
0x180004976  mov     rbx, rcx
0x180004979  mov     eax, [rcx]
0x18000497b  test    eax, eax
0x18000497d  jz      short loc_1800049F1
0x18000497f  lea     rdx, [rcx+8]
0x180004983  lea     rcx, [rsp+28h+arg_0]
0x180004988  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000498d  lea     rdi, [rbx+60h]
0x180004991  cmp     qword ptr [rdi], 0
0x180004995  jz      short loc_18000499D
0x180004997  mov     ebx, [rbx+1Ch]
0x18000499a  nop
0x18000499b  jmp     short loc_1800049E3
0x18000499d  mov     qword ptr [rdi], 0
0x1800049a4  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800049ab  test    rax, rax
0x1800049ae  jnz     short loc_1800049BC
0x1800049b0  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800049b7  test    rax, rax
0x1800049ba  jz      short loc_1800049CE
0x1800049bc  mov     r8, rbx
0x1800049bf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800049c6  mov     rcx, rdi
0x1800049c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ce  cmp     qword ptr [rdi], 0
0x1800049d2  jnz     short loc_1800049D8
0x1800049d4  xor     ebx, ebx
0x1800049d6  jmp     short loc_1800049E3
0x1800049d8  nop
0x1800049d9  mov     eax, 1
0x1800049de  mov     [rbx+1Ch], eax
0x1800049e1  mov     ebx, eax
0x1800049e3  lea     rcx, [rsp+28h+arg_0]
0x1800049e8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800049ed  mov     eax, ebx
0x1800049ef  jmp     short loc_1800049F3
0x1800049f1  xor     eax, eax
0x1800049f3  mov     rbx, [rsp+28h+arg_8]
0x1800049f8  add     rsp, 20h
0x1800049fc  pop     rdi
0x1800049fd  retn
```
