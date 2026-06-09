# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180014c7c`
- end: `0x180014d0c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `144`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014ed8`

## callees

- `0x1800075a4`
- `0x180008720`
- `0x18000b850`
- `0x18000d968`
- `0x180014c7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ca3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ca3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        wil::details::EnabledStateManager *this,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  unsigned __int64 v7; // r8
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  char *v10; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)this && !wil::ProcessShutdownInProgress(this) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 1);
    v10 = (char *)this + 8;
    if ( !*(_DWORD *)this || wil::ProcessShutdownInProgress(v6) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    }
    else
    {
      Source[0] = a2;
      Source[1] = 0;
      v9 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details::EnabledStateManager *)((char *)this + 32), Source, v7);
      wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
        (struct _TP_TIMER **)this + 2,
        (_BYTE *)this + 24,
        this);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    }
  }
}

```

## disassembly

```asm
0x180014c7c  push    rbx
0x180014c7e  push    rbp
0x180014c7f  push    rsi
0x180014c80  push    rdi
0x180014c81  sub     rsp, 38h
0x180014c85  mov     rsi, r8
0x180014c88  mov     ebp, edx
0x180014c8a  mov     rdi, rcx
0x180014c8d  mov     eax, [rcx]
0x180014c8f  test    eax, eax
0x180014c91  jz      short loc_180014D03
0x180014c93  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180014c98  test    al, al
0x180014c9a  jnz     short loc_180014D03
0x180014c9c  lea     rbx, [rdi+8]
0x180014ca0  mov     rcx, rbx; SRWLock
0x180014ca3  call    cs:__imp_AcquireSRWLockExclusive
0x180014ca9  mov     [rsp+58h+arg_0], rbx
0x180014cae  mov     eax, [rdi]
0x180014cb0  test    eax, eax
0x180014cb2  jz      short loc_180014CF8
0x180014cb4  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180014cb9  test    al, al
0x180014cbb  jnz     short loc_180014CF8
0x180014cbd  mov     [rsp+58h+Source], ebp
0x180014cc1  xor     eax, eax
0x180014cc3  mov     [rsp+58h+var_34], eax
0x180014cc7  mov     [rsp+58h+var_30], rsi
0x180014ccc  lea     rcx, [rdi+20h]; this
0x180014cd0  lea     rdx, [rsp+58h+Source]; Source
0x180014cd5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014cda  lea     rdx, [rdi+18h]
0x180014cde  lea     rcx, [rdi+10h]
0x180014ce2  mov     r8, rdi
0x180014ce5  call    ??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)
0x180014cea  nop
0x180014ceb  lea     rcx, [rsp+58h+arg_0]
0x180014cf0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014cf5  nop
0x180014cf6  jmp     short loc_180014D03
0x180014cf8  lea     rcx, [rsp+58h+arg_0]
0x180014cfd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014d02  nop
0x180014d03  add     rsp, 38h
0x180014d07  pop     rdi
0x180014d08  pop     rsi
0x180014d09  pop     rbp
0x180014d0a  pop     rbx
0x180014d0b  retn
```
