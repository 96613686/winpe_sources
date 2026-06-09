# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800268b0`
- end: `0x1800269a9`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `249`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800264d8`

## callees

- `0x1800268b0`
- `0x1800282b4`
- `0x18003161c`
- `0x180031920`
- `0x180031a18`
- `0x180031bfc`
- `0x18003491c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800268e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800268e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026988`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026988`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026948`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026948`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  unsigned __int64 v8; // r8
  struct _TP_TIMER **v9; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  _DWORD v12[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v13; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v15; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v15 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v12[0] = a2;
        v12[1] = 0;
        v13 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v12, v8);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          v9 = (struct _TP_TIMER **)&pv[2];
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&pftDueTime);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&pftDueTime);
          }
          v11 = *v9;
          if ( *v9 )
          {
            pftDueTime = (struct _FILETIME)-3000000000LL;
            SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
            LOBYTE(pv[3].Ptr) = 1;
          }
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  }
}

```

## disassembly

```asm
0x1800268b0  mov     [rsp+arg_8], rbx
0x1800268b5  push    rbp
0x1800268b6  push    rsi
0x1800268b7  push    rdi
0x1800268b8  sub     rsp, 30h
0x1800268bc  mov     eax, [rcx]
0x1800268be  mov     rsi, r8
0x1800268c1  mov     ebp, edx
0x1800268c3  mov     rdi, rcx
0x1800268c6  test    eax, eax
0x1800268c8  jz      loc_18002699C
0x1800268ce  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800268d3  test    al, al
0x1800268d5  jnz     loc_18002699C
0x1800268db  lea     rbx, [rdi+8]
0x1800268df  mov     rcx, rbx; SRWLock
0x1800268e2  call    cs:__imp_AcquireSRWLockExclusive
0x1800268e8  mov     eax, [rdi]
0x1800268ea  mov     [rsp+48h+arg_18], rbx
0x1800268ef  test    eax, eax
0x1800268f1  jz      loc_180026992
0x1800268f7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800268fc  test    al, al
0x1800268fe  jnz     loc_180026992
0x180026904  xor     eax, eax
0x180026906  mov     [rsp+48h+var_28], ebp
0x18002690a  lea     rcx, [rdi+20h]; this
0x18002690e  mov     [rsp+48h+var_24], eax
0x180026912  lea     rdx, [rsp+48h+var_28]; void *
0x180026917  mov     [rsp+48h+var_20], rsi
0x18002691c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026921  cmp     byte ptr [rdi+18h], 0
0x180026925  jnz     short loc_180026992
0x180026927  lea     rbx, [rdi+10h]
0x18002692b  cmp     qword ptr [rbx], 0
0x18002692f  jnz     short loc_180026963
0x180026931  lea     rcx, [rsp+48h+pftDueTime]; this
0x180026936  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002693b  xor     r8d, r8d; pcbe
0x18002693e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180026945  mov     rdx, rdi; pv
0x180026948  call    cs:__imp_CreateThreadpoolTimer
0x18002694e  mov     rdx, rax
0x180026951  mov     rcx, rbx
0x180026954  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180026959  lea     rcx, [rsp+48h+pftDueTime]; this
0x18002695e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180026963  mov     rcx, [rbx]; pti
0x180026966  test    rcx, rcx
0x180026969  jz      short loc_180026992
0x18002696b  mov     rax, 0FFFFFFFF4D2FA200h
0x180026975  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18002697a  mov     r9d, 124F8h; msWindowLength
0x180026980  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180026985  xor     r8d, r8d; msPeriod
0x180026988  call    cs:__imp_SetThreadpoolTimer
0x18002698e  mov     byte ptr [rdi+18h], 1
0x180026992  lea     rcx, [rsp+48h+arg_18]
0x180026997  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002699c  mov     rbx, [rsp+48h+arg_8]
0x1800269a1  add     rsp, 30h
0x1800269a5  pop     rdi
0x1800269a6  pop     rsi
0x1800269a7  pop     rbp
0x1800269a8  retn
```
