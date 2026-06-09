# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180063494`
- end: `0x180063565`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `209`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000bf8c`
- `0x180025220`

## callees

- `0x18000b290`
- `0x18000ba40`
- `0x18000ba60`
- `0x18000baa4`
- `0x18000bac8`
- `0x180043c64`
- `0x180063494`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180063520`
- `KERNEL32!CreateThreadpoolTimer` at `0x180063520`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180063555`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180063555`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800634c3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800634c3`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  char v10; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x180063494  push    rbx
0x180063496  push    rbp
0x180063497  push    rsi
0x180063498  push    rdi
0x180063499  sub     rsp, 38h
0x18006349d  mov     rsi, r8
0x1800634a0  mov     ebp, edx
0x1800634a2  mov     rbx, rcx
0x1800634a5  mov     eax, [rcx]
0x1800634a7  test    eax, eax
0x1800634a9  jz      loc_18006355C
0x1800634af  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800634b4  test    al, al
0x1800634b6  jnz     loc_18006355C
0x1800634bc  lea     rdi, [rbx+8]
0x1800634c0  mov     rcx, rdi; SRWLock
0x1800634c3  call    cs:__imp_AcquireSRWLockExclusive
0x1800634c9  mov     eax, [rbx]
0x1800634cb  test    eax, eax
0x1800634cd  jz      short loc_18006354D
0x1800634cf  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800634d4  test    al, al
0x1800634d6  jnz     short loc_18006354D
0x1800634d8  mov     [rsp+58h+var_38], ebp
0x1800634dc  xor     eax, eax
0x1800634de  mov     [rsp+58h+var_34], eax
0x1800634e2  mov     [rsp+58h+var_30], rsi
0x1800634e7  lea     rcx, [rbx+20h]; this
0x1800634eb  lea     r8d, [rax+10h]; unsigned __int64
0x1800634ef  lea     rdx, [rsp+58h+var_38]; void *
0x1800634f4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800634f9  cmp     byte ptr [rbx+18h], 0
0x1800634fd  jnz     short loc_18006354D
0x1800634ff  lea     rsi, [rbx+10h]
0x180063503  cmp     qword ptr [rsi], 0
0x180063507  jnz     short loc_18006353B
0x180063509  lea     rcx, [rsp+58h+arg_0]; this
0x18006350e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180063513  xor     r8d, r8d; pcbe
0x180063516  mov     rdx, rbx; pv
0x180063519  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180063520  call    cs:__imp_CreateThreadpoolTimer
0x180063526  mov     rdx, rax
0x180063529  mov     rcx, rsi
0x18006352c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180063531  lea     rcx, [rsp+58h+arg_0]; this
0x180063536  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006353b  mov     r8d, 493E0h
0x180063541  lea     rdx, [rbx+18h]
0x180063545  mov     rcx, rsi
0x180063548  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18006354d  test    rdi, rdi
0x180063550  jz      short loc_18006355C
0x180063552  mov     rcx, rdi; SRWLock
0x180063555  call    cs:__imp_ReleaseSRWLockExclusive
0x18006355b  nop
0x18006355c  add     rsp, 38h
0x180063560  pop     rdi
0x180063561  pop     rsi
0x180063562  pop     rbp
0x180063563  pop     rbx
0x180063564  retn
```
