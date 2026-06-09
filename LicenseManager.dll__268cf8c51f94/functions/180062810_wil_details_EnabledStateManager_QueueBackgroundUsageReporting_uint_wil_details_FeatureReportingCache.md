# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180062810`
- end: `0x1800628e9`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800428a4`

## callees

- `0x18003bdc4`
- `0x18003bdf8`
- `0x18003be18`
- `0x180062810`
- `0x1800629dc`
- `0x1800629fc`
- `0x180062a40`
- `0x180069ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062842`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062842`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800628a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800628a4`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v11 = pv + 1;
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
    PendingRequestManager::~PendingRequestManager((PendingRequestManager *)&v11);
  }
}

```

## disassembly

```asm
0x180062810  mov     [rsp+arg_8], rbx
0x180062815  push    rbp
0x180062816  push    rsi
0x180062817  push    rdi
0x180062818  sub     rsp, 30h
0x18006281c  mov     rsi, r8
0x18006281f  mov     ebp, edx
0x180062821  mov     rdi, rcx
0x180062824  mov     eax, [rcx]
0x180062826  test    eax, eax
0x180062828  jz      loc_1800628DC
0x18006282e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180062833  test    al, al
0x180062835  jnz     loc_1800628DC
0x18006283b  lea     rbx, [rdi+8]
0x18006283f  mov     rcx, rbx; SRWLock
0x180062842  call    cs:__imp_AcquireSRWLockExclusive
0x180062848  mov     [rsp+48h+arg_18], rbx
0x18006284d  mov     eax, [rdi]
0x18006284f  test    eax, eax
0x180062851  jz      short loc_1800628D1
0x180062853  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180062858  test    al, al
0x18006285a  jnz     short loc_1800628D1
0x18006285c  mov     [rsp+48h+var_28], ebp
0x180062860  xor     eax, eax
0x180062862  mov     [rsp+48h+var_24], eax
0x180062866  mov     [rsp+48h+var_20], rsi
0x18006286b  lea     rcx, [rdi+20h]; this
0x18006286f  lea     r8d, [rax+10h]; unsigned __int64
0x180062873  lea     rdx, [rsp+48h+var_28]; void *
0x180062878  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18006287d  cmp     byte ptr [rdi+18h], 0
0x180062881  jnz     short loc_1800628D1
0x180062883  lea     rbx, [rdi+10h]
0x180062887  cmp     qword ptr [rbx], 0
0x18006288b  jnz     short loc_1800628BF
0x18006288d  lea     rcx, [rsp+48h+arg_0]; this
0x180062892  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180062897  xor     r8d, r8d; pcbe
0x18006289a  mov     rdx, rdi; pv
0x18006289d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800628a4  call    cs:__imp_CreateThreadpoolTimer
0x1800628aa  mov     rdx, rax
0x1800628ad  mov     rcx, rbx
0x1800628b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800628b5  lea     rcx, [rsp+48h+arg_0]; this
0x1800628ba  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800628bf  mov     r8d, 493E0h
0x1800628c5  lea     rdx, [rdi+18h]
0x1800628c9  mov     rcx, rbx
0x1800628cc  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800628d1  lea     rcx, [rsp+48h+arg_18]; this
0x1800628d6  call    ??1PendingRequestManager@@QEAA@XZ; PendingRequestManager::~PendingRequestManager(void)
0x1800628db  nop
0x1800628dc  mov     rbx, [rsp+48h+arg_8]
0x1800628e1  add     rsp, 30h
0x1800628e5  pop     rdi
0x1800628e6  pop     rsi
0x1800628e7  pop     rbp
0x1800628e8  retn
```
