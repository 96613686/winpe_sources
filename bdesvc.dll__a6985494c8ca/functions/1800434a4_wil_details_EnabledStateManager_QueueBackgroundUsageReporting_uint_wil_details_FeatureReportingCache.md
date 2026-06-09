# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800434a4`
- end: `0x18004358e`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001a6c0`
- `0x18001e320`

## callees

- `0x18001d670`
- `0x1800276f8`
- `0x18002791c`
- `0x18002be48`
- `0x18002be6c`
- `0x18002bed0`
- `0x18002bffc`
- `0x1800434a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800434d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800434d6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180043542`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180043542`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v10; // [rsp+30h] [rbp-28h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v10 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Source, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)Source);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)Source);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x1800434a4  mov     [rsp+arg_18], rbx
0x1800434a9  push    rbp
0x1800434aa  push    rsi
0x1800434ab  push    rdi
0x1800434ac  sub     rsp, 40h
0x1800434b0  mov     rbp, r8
0x1800434b3  mov     esi, edx
0x1800434b5  mov     rdi, rcx
0x1800434b8  mov     eax, [rcx]
0x1800434ba  test    eax, eax
0x1800434bc  jz      loc_180043580
0x1800434c2  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800434c7  test    al, al
0x1800434c9  jnz     loc_180043580
0x1800434cf  lea     rbx, [rdi+8]
0x1800434d3  mov     rcx, rbx; SRWLock
0x1800434d6  call    cs:__imp_AcquireSRWLockExclusive
0x1800434dd  nop     dword ptr [rax+rax+00h]
0x1800434e2  mov     [rsp+58h+var_28], rbx
0x1800434e7  mov     eax, [rdi]
0x1800434e9  test    eax, eax
0x1800434eb  jz      loc_180043575
0x1800434f1  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800434f6  test    al, al
0x1800434f8  jnz     short loc_180043575
0x1800434fa  mov     [rsp+58h+Source], esi
0x1800434fe  xor     eax, eax
0x180043500  mov     [rsp+58h+var_34], eax
0x180043504  mov     [rsp+58h+var_30], rbp
0x180043509  lea     rcx, [rdi+20h]; this
0x18004350d  lea     r8d, [rax+10h]; SourceSize
0x180043511  lea     rdx, [rsp+58h+Source]; Source
0x180043516  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18004351b  cmp     byte ptr [rdi+18h], 0
0x18004351f  jnz     short loc_180043575
0x180043521  lea     rbx, [rdi+10h]
0x180043525  cmp     qword ptr [rbx], 0
0x180043529  jnz     short loc_180043563
0x18004352b  lea     rcx, [rsp+58h+Source]; this
0x180043530  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180043535  xor     r8d, r8d; pcbe
0x180043538  mov     rdx, rdi; pv
0x18004353b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180043542  call    cs:__imp_CreateThreadpoolTimer
0x180043549  nop     dword ptr [rax+rax+00h]
0x18004354e  mov     rdx, rax
0x180043551  mov     rcx, rbx
0x180043554  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180043559  lea     rcx, [rsp+58h+Source]; this
0x18004355e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180043563  mov     r8d, 493E0h
0x180043569  lea     rdx, [rdi+18h]
0x18004356d  mov     rcx, rbx
0x180043570  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180043575  lea     rcx, [rsp+58h+var_28]
0x18004357a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004357f  nop
0x180043580  mov     rbx, [rsp+58h+arg_18]
0x180043585  add     rsp, 40h
0x180043589  pop     rdi
0x18004358a  pop     rsi
0x18004358b  pop     rbp
0x18004358c  retn
```
