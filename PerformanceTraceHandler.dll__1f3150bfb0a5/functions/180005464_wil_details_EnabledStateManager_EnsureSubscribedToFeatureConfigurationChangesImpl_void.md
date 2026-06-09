# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180005464`
- end: `0x1800054f8`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000543c`

## callees

- `0x18000490c`
- `0x180005464`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000547e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000547e`

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
0x180005464  mov     [rsp+arg_8], rbx
0x180005469  push    rdi
0x18000546a  sub     rsp, 20h
0x18000546e  mov     rdi, rcx
0x180005471  mov     eax, [rcx]
0x180005473  test    eax, eax
0x180005475  jz      short loc_1800054EB
0x180005477  lea     rbx, [rcx+8]
0x18000547b  mov     rcx, rbx; SRWLock
0x18000547e  call    cs:__imp_AcquireSRWLockExclusive
0x180005484  mov     [rsp+28h+arg_0], rbx
0x180005489  lea     rbx, [rdi+60h]
0x18000548d  cmp     qword ptr [rbx], 0
0x180005491  jz      short loc_180005499
0x180005493  mov     ebx, [rdi+1Ch]
0x180005496  nop
0x180005497  jmp     short loc_1800054DD
0x180005499  mov     qword ptr [rbx], 0
0x1800054a0  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800054a7  test    rax, rax
0x1800054aa  jnz     short loc_1800054B8
0x1800054ac  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800054b3  test    rax, rax
0x1800054b6  jz      short loc_1800054CA
0x1800054b8  mov     r8, rdi
0x1800054bb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800054c2  mov     rcx, rbx
0x1800054c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ca  cmp     qword ptr [rbx], 0
0x1800054ce  jnz     short loc_1800054D4
0x1800054d0  xor     ebx, ebx
0x1800054d2  jmp     short loc_1800054DD
0x1800054d4  nop
0x1800054d5  mov     ebx, 1
0x1800054da  mov     [rdi+1Ch], ebx
0x1800054dd  lea     rcx, [rsp+28h+arg_0]
0x1800054e2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800054e7  mov     eax, ebx
0x1800054e9  jmp     short loc_1800054ED
0x1800054eb  xor     eax, eax
0x1800054ed  mov     rbx, [rsp+28h+arg_8]
0x1800054f2  add     rsp, 20h
0x1800054f6  pop     rdi
0x1800054f7  retn
```
