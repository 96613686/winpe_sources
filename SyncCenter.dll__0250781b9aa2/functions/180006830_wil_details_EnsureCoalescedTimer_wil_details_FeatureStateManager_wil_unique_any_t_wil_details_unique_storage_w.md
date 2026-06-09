# wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x180006830`
- end: `0x180006913`
- name: `??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z`
- size: `227`
- prototype: `void __fastcall(struct _TP_TIMER **, _BYTE *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800067b0`

## callees

- `0x180006830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000688a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000688a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800068b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800068b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000689d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006902`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000689d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006902`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006879`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006879`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068ab`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(
        struct _TP_TIMER **a1,
        _BYTE *a2,
        void *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v8; // rbp
  struct _TP_TIMER *v9; // r15
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp+10h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, a3, 0);
      v8 = *a1;
      v9 = ThreadpoolTimer;
      if ( *a1 )
      {
        v10 = GetLastError();
        SetThreadpoolTimer(v8, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v8, 1);
        CloseThreadpoolTimer(v8);
        SetLastError(v10);
      }
      *a1 = v9;
      SetLastError(LastError);
    }
    v11 = *a1;
    if ( *a1 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
      *a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x180006830  push    rbx
0x180006832  push    rsi
0x180006833  push    rdi
0x180006834  sub     rsp, 20h
0x180006838  cmp     byte ptr [rdx], 0
0x18000683b  mov     rbx, r8
0x18000683e  mov     rsi, rdx
0x180006841  mov     rdi, rcx
0x180006844  jnz     loc_18000690B
0x18000684a  cmp     qword ptr [rcx], 0
0x18000684e  jnz     loc_1800068DD
0x180006854  mov     [rsp+38h+arg_0], rbp
0x180006859  mov     [rsp+38h+arg_10], r14
0x18000685e  mov     [rsp+38h+arg_18], r15
0x180006863  call    cs:__imp_GetLastError
0x180006869  xor     r8d, r8d; pcbe
0x18000686c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006873  mov     rdx, rbx; pv
0x180006876  mov     r14d, eax
0x180006879  call    cs:__imp_CreateThreadpoolTimer
0x18000687f  mov     rbp, [rdi]
0x180006882  mov     r15, rax
0x180006885  test    rbp, rbp
0x180006888  jz      short loc_1800068C2
0x18000688a  call    cs:__imp_GetLastError
0x180006890  xor     r9d, r9d; msWindowLength
0x180006893  xor     r8d, r8d; msPeriod
0x180006896  xor     edx, edx; pftDueTime
0x180006898  mov     rcx, rbp; pti
0x18000689b  mov     ebx, eax
0x18000689d  call    cs:__imp_SetThreadpoolTimer
0x1800068a3  mov     edx, 1; fCancelPendingCallbacks
0x1800068a8  mov     rcx, rbp; pti
0x1800068ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800068b1  mov     rcx, rbp; pti
0x1800068b4  call    cs:__imp_CloseThreadpoolTimer
0x1800068ba  mov     ecx, ebx; dwErrCode
0x1800068bc  call    cs:__imp_SetLastError
0x1800068c2  mov     ecx, r14d; dwErrCode
0x1800068c5  mov     [rdi], r15
0x1800068c8  call    cs:__imp_SetLastError
0x1800068ce  mov     r15, [rsp+38h+arg_18]
0x1800068d3  mov     r14, [rsp+38h+arg_10]
0x1800068d8  mov     rbp, [rsp+38h+arg_0]
0x1800068dd  mov     rcx, [rdi]; pti
0x1800068e0  test    rcx, rcx
0x1800068e3  jz      short loc_18000690B
0x1800068e5  mov     rax, 0FFFFFFFF4D2FA200h
0x1800068ef  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800068f4  mov     r9d, 124F8h; msWindowLength
0x1800068fa  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800068ff  xor     r8d, r8d; msPeriod
0x180006902  call    cs:__imp_SetThreadpoolTimer
0x180006908  mov     byte ptr [rsi], 1
0x18000690b  add     rsp, 20h
0x18000690f  pop     rdi
0x180006910  pop     rsi
0x180006911  pop     rbx
0x180006912  retn
```
