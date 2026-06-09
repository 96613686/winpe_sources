# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800726e4`
- end: `0x1800727c5`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `225`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180049b44`

## callees

- `0x180043ea4`
- `0x180044324`
- `0x18004a270`
- `0x18004a2d0`
- `0x18004a3e4`
- `0x1800539fc`
- `0x1800726e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800727b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800727b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007271e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007271e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007277c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007277c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v7[7]; // [rsp+20h] [rbp-38h] BYREF

  v7[2] = -2;
  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v7[0] = 60440628;
        v7[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v7, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v7);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v7);
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
0x1800726e4  push    rbp
0x1800726e6  push    rsi
0x1800726e7  push    rdi
0x1800726e8  sub     rsp, 40h
0x1800726ec  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800726f5  mov     [rsp+58h+arg_8], rbx
0x1800726fa  mov     rsi, r8
0x1800726fd  mov     rbx, rcx
0x180072700  mov     eax, [rcx]
0x180072702  test    eax, eax
0x180072704  jz      loc_1800727B8
0x18007270a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18007270f  test    al, al
0x180072711  jnz     loc_1800727B8
0x180072717  lea     rdi, [rbx+8]
0x18007271b  mov     rcx, rdi; SRWLock
0x18007271e  call    cs:__imp_AcquireSRWLockExclusive
0x180072724  mov     eax, [rbx]
0x180072726  test    eax, eax
0x180072728  jz      short loc_1800727A9
0x18007272a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18007272f  test    al, al
0x180072731  jnz     short loc_1800727A9
0x180072733  mov     [rsp+58h+var_38], 39A4034h
0x18007273c  mov     [rsp+58h+var_30], rsi
0x180072741  lea     rcx, [rbx+20h]; this
0x180072745  mov     r8d, 10h; unsigned __int64
0x18007274b  lea     rdx, [rsp+58h+var_38]; void *
0x180072750  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180072755  cmp     byte ptr [rbx+18h], 0
0x180072759  jnz     short loc_1800727A9
0x18007275b  lea     rsi, [rbx+10h]
0x18007275f  cmp     qword ptr [rsi], 0
0x180072763  jnz     short loc_180072797
0x180072765  lea     rcx, [rsp+58h+var_38]; this
0x18007276a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007276f  xor     r8d, r8d; pcbe
0x180072772  mov     rdx, rbx; pv
0x180072775  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18007277c  call    cs:__imp_CreateThreadpoolTimer
0x180072782  mov     rdx, rax
0x180072785  mov     rcx, rsi
0x180072788  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18007278d  lea     rcx, [rsp+58h+var_38]; this
0x180072792  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180072797  mov     r8d, 493E0h
0x18007279d  lea     rdx, [rbx+18h]
0x1800727a1  mov     rcx, rsi
0x1800727a4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800727a9  test    rdi, rdi
0x1800727ac  jz      short loc_1800727B8
0x1800727ae  mov     rcx, rdi; SRWLock
0x1800727b1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800727b7  nop
0x1800727b8  mov     rbx, [rsp+58h+arg_8]
0x1800727bd  add     rsp, 40h
0x1800727c1  pop     rdi
0x1800727c2  pop     rsi
0x1800727c3  pop     rbp
0x1800727c4  retn
```
