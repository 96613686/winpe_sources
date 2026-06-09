# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18000bcf4`
- end: `0x18000bd88`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000bccc`

## callees

- `0x18000b850`
- `0x18000bcf4`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bd0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bd0e`

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
0x18000bcf4  mov     [rsp+arg_8], rbx
0x18000bcf9  push    rdi
0x18000bcfa  sub     rsp, 20h
0x18000bcfe  mov     rdi, rcx
0x18000bd01  mov     eax, [rcx]
0x18000bd03  test    eax, eax
0x18000bd05  jz      short loc_18000BD7B
0x18000bd07  lea     rbx, [rcx+8]
0x18000bd0b  mov     rcx, rbx; SRWLock
0x18000bd0e  call    cs:__imp_AcquireSRWLockExclusive
0x18000bd14  mov     [rsp+28h+arg_0], rbx
0x18000bd19  lea     rbx, [rdi+60h]
0x18000bd1d  cmp     qword ptr [rbx], 0
0x18000bd21  jz      short loc_18000BD29
0x18000bd23  mov     ebx, [rdi+1Ch]
0x18000bd26  nop
0x18000bd27  jmp     short loc_18000BD6D
0x18000bd29  mov     qword ptr [rbx], 0
0x18000bd30  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000bd37  test    rax, rax
0x18000bd3a  jnz     short loc_18000BD48
0x18000bd3c  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000bd43  test    rax, rax
0x18000bd46  jz      short loc_18000BD5A
0x18000bd48  mov     r8, rdi
0x18000bd4b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000bd52  mov     rcx, rbx
0x18000bd55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd5a  cmp     qword ptr [rbx], 0
0x18000bd5e  jnz     short loc_18000BD64
0x18000bd60  xor     ebx, ebx
0x18000bd62  jmp     short loc_18000BD6D
0x18000bd64  nop
0x18000bd65  mov     ebx, 1
0x18000bd6a  mov     [rdi+1Ch], ebx
0x18000bd6d  lea     rcx, [rsp+28h+arg_0]
0x18000bd72  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bd77  mov     eax, ebx
0x18000bd79  jmp     short loc_18000BD7D
0x18000bd7b  xor     eax, eax
0x18000bd7d  mov     rbx, [rsp+28h+arg_8]
0x18000bd82  add     rsp, 20h
0x18000bd86  pop     rdi
0x18000bd87  retn
```
