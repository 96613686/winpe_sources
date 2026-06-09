# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18005bd50`
- end: `0x18005bdd9`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `137`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180048ed8`

## callees

- `0x18004aaf8`
- `0x18004bb7c`
- `0x180058af0`
- `0x18005bd50`
- `0x18005cdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005bd77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005bd77`

## pseudocode

```c
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
    if ( *(_DWORD *)this )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details::EnabledStateManager *)((char *)this + 32), Source, v7);
        wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
          (struct _TP_TIMER **)this + 2,
          (_BYTE *)this + 24,
          this);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18005bd50  push    rbx
0x18005bd52  push    rbp
0x18005bd53  push    rsi
0x18005bd54  push    rdi
0x18005bd55  sub     rsp, 38h
0x18005bd59  mov     rsi, r8
0x18005bd5c  mov     ebp, edx
0x18005bd5e  mov     rdi, rcx
0x18005bd61  mov     eax, [rcx]
0x18005bd63  test    eax, eax
0x18005bd65  jz      short loc_18005BDCF
0x18005bd67  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005bd6c  test    al, al
0x18005bd6e  jnz     short loc_18005BDCF
0x18005bd70  lea     rbx, [rdi+8]
0x18005bd74  mov     rcx, rbx; SRWLock
0x18005bd77  call    cs:__imp_AcquireSRWLockExclusive
0x18005bd7e  nop     dword ptr [rax+rax+00h]
0x18005bd83  mov     [rsp+58h+arg_0], rbx
0x18005bd88  mov     eax, [rdi]
0x18005bd8a  test    eax, eax
0x18005bd8c  jz      short loc_18005BDC4
0x18005bd8e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005bd93  test    al, al
0x18005bd95  jnz     short loc_18005BDC4
0x18005bd97  mov     [rsp+58h+Source], ebp
0x18005bd9b  xor     eax, eax
0x18005bd9d  mov     [rsp+58h+var_34], eax
0x18005bda1  mov     [rsp+58h+var_30], rsi
0x18005bda6  lea     rcx, [rdi+20h]; this
0x18005bdaa  lea     rdx, [rsp+58h+Source]; Source
0x18005bdaf  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18005bdb4  lea     rdx, [rdi+18h]
0x18005bdb8  lea     rcx, [rdi+10h]
0x18005bdbc  mov     r8, rdi
0x18005bdbf  call    ??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)
0x18005bdc4  lea     rcx, [rsp+58h+arg_0]
0x18005bdc9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005bdce  nop
0x18005bdcf  add     rsp, 38h
0x18005bdd3  pop     rdi
0x18005bdd4  pop     rsi
0x18005bdd5  pop     rbp
0x18005bdd6  pop     rbx
0x18005bdd7  retn
```
