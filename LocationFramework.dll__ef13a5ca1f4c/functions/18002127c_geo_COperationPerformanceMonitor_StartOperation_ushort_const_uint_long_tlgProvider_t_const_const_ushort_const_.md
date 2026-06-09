# geo::COperationPerformanceMonitor::StartOperation(ushort const *,uint,long (*)(_tlgProvider_t const * const &,ushort const *,int,ushort const *),_tlgProvider_t const * const &,ushort const *)

- ea: `0x18002127c`
- end: `0x18002143e`
- name: `?StartOperation@COperationPerformanceMonitor@geo@@SA?AV?$shared_ptr@VOperationPerformanceCookie@geo@@@std@@PEBGIP6AJAEBQEBU_tlgProvider_t@@0H0@Z10@Z`
- size: `450`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `20`
- callee_count: `8`
- tags: ``

## callers

- `0x180012590`
- `0x180012800`
- `0x180013000`
- `0x180021064`
- `0x1800210b0`
- `0x1800652f0`
- `0x18006a690`
- `0x18006ad70`
- `0x18006af30`
- `0x18006cce0`
- `0x18006fa20`
- `0x18006fe10`
- `0x180071cc0`
- `0x180082f8c`
- `0x1800a3140`
- `0x1800a3530`
- `0x1800a50e0`
- `0x1800a61d0`
- `0x1800a6b10`
- `0x1800c36f0`

## callees

- `0x18002127c`
- `0x180021450`
- `0x1800456a8`
- `0x18005f304`
- `0x180061f04`
- `0x1800a98c0`
- `0x1800a9910`
- `0x1800a9e0c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002139c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002139c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002135c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002135c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021307`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021307`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall geo::COperationPerformanceMonitor::StartOperation(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  _QWORD *v8; // rax
  struct _FILETIME v9; // rbx
  struct _TP_TIMER *ThreadpoolTimer; // rsi
  struct _TP_TIMER *v11; // rbp
  std::_Ref_count_base *v12; // rcx
  struct _FILETIME *v14; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-38h] BYREF

  *(_OWORD *)a1 = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v8 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v9 = (struct _FILETIME)v8;
  pftDueTime = (struct _FILETIME)v8;
  if ( v8 )
  {
    *v8 = &g_nonPIILocationTraceLoggingId;
    v8[1] = a2;
    v8[2] = a6;
    *((_DWORD *)v8 + 6) = 420000;
    v8[4] = GetTickCount64();
    *(_QWORD *)(*(_QWORD *)&v9 + 40LL) = 0;
    *(_WORD *)(*(_QWORD *)&v9 + 48LL) = 0;
    *(_QWORD *)(*(_QWORD *)&v9 + 56LL) = geo::Details::CSuspectedDeadlockWatchdogDetails::ReportSuspectedDeadlock;
    *(_QWORD *)(*(_QWORD *)&v9 + 64LL) = 0;
    if ( !*(_QWORD *)(*(_QWORD *)&v9 + 16LL) )
      *(_QWORD *)(*(_QWORD *)&v9 + 16LL) = &word_18016FF04;
    if ( !*(_QWORD *)(*(_QWORD *)&v9 + 8LL) )
      *(_QWORD *)(*(_QWORD *)&v9 + 8LL) = &word_18016FF04;
    ThreadpoolTimer = CreateThreadpoolTimer(geo::OperationPerformanceCookie::sTimerCallback, *(PVOID *)&v9, 0);
    v11 = *(struct _TP_TIMER **)(*(_QWORD *)&v9 + 64LL);
    if ( v11 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&pftDueTime);
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&pftDueTime);
    }
    *(_QWORD *)(*(_QWORD *)&v9 + 64LL) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      pftDueTime.dwLowDateTime = 94967296;
      pftDueTime.dwHighDateTime = -1;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0x64u);
    }
  }
  else
  {
    v9 = 0;
  }
  pftDueTime = v9;
  v14 = (struct _FILETIME *)operator new(0x18u);
  *(_OWORD *)&v14->dwLowDateTime = 0;
  v14[1].dwLowDateTime = 1;
  v14[1].dwHighDateTime = 1;
  *v14 = (struct _FILETIME)&std::_Ref_count<geo::OperationPerformanceCookie>::`vftable';
  v14[2] = v9;
  *(struct _FILETIME *)a1 = v9;
  v12 = *(std::_Ref_count_base **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = v14;
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  return a1;
}

```

## disassembly

```asm
0x18002127c  push    rbx
0x18002127e  push    rbp
0x18002127f  push    rsi
0x180021280  push    rdi
0x180021281  sub     rsp, 48h
0x180021285  mov     rax, cs:__security_cookie
0x18002128c  xor     rax, rsp
0x18002128f  mov     [rsp+68h+var_30], rax
0x180021294  mov     rsi, rdx
0x180021297  mov     rdi, rcx
0x18002129a  mov     [rsp+68h+var_40], rcx
0x18002129f  mov     [rsp+68h+var_48], 0
0x1800212a7  xorps   xmm0, xmm0
0x1800212aa  movups  xmmword ptr [rcx], xmm0
0x1800212ad  mov     qword ptr [rcx], 0
0x1800212b4  mov     qword ptr [rcx+8], 0
0x1800212bc  mov     [rsp+68h+var_48], 1
0x1800212c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800212cb  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800212d0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800212d5  mov     rbx, rax
0x1800212d8  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x1800212dd  test    rax, rax
0x1800212e0  jz      loc_180021406
0x1800212e6  lea     rax, g_nonPIILocationTraceLoggingId
0x1800212ed  mov     [rbx], rax
0x1800212f0  mov     [rbx+8], rsi
0x1800212f4  mov     rax, [rsp+68h+arg_28]
0x1800212fc  mov     [rbx+10h], rax
0x180021300  mov     dword ptr [rbx+18h], 668A0h
0x180021307  call    cs:__imp_GetTickCount64
0x18002130d  mov     [rbx+20h], rax
0x180021311  mov     qword ptr [rbx+28h], 0
0x180021319  mov     word ptr [rbx+30h], 0
0x18002131f  lea     rax, ?ReportSuspectedDeadlock@CSuspectedDeadlockWatchdogDetails@Details@geo@@SAJAEBQEBU_tlgProvider_t@@PEBGH1@Z; geo::Details::CSuspectedDeadlockWatchdogDetails::ReportSuspectedDeadlock(_tlgProvider_t const * const &,ushort const *,int,ushort const *)
0x180021326  mov     [rbx+38h], rax
0x18002132a  mov     qword ptr [rbx+40h], 0
0x180021332  lea     rax, word_18016FF04
0x180021339  cmp     qword ptr [rbx+10h], 0
0x18002133e  jz      loc_18002140A
0x180021344  cmp     qword ptr [rbx+8], 0
0x180021349  jz      loc_180021413
0x18002134f  xor     r8d, r8d; pcbe
0x180021352  mov     rdx, rbx; pv
0x180021355  lea     rcx, ?sTimerCallback@OperationPerformanceCookie@geo@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002135c  call    cs:__imp_CreateThreadpoolTimer
0x180021362  mov     rsi, rax
0x180021365  mov     rbp, [rbx+40h]
0x180021369  test    rbp, rbp
0x18002136c  jnz     loc_18002141C
0x180021372  mov     [rbx+40h], rsi
0x180021376  test    rsi, rsi
0x180021379  jz      short loc_1800213A2
0x18002137b  mov     [rsp+68h+pftDueTime.dwLowDateTime], 5A91600h
0x180021383  mov     [rsp+68h+pftDueTime.dwHighDateTime], 0FFFFFFFFh
0x18002138b  mov     r9d, 64h ; 'd'; msWindowLength
0x180021391  xor     r8d, r8d; msPeriod
0x180021394  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180021399  mov     rcx, rsi; pti
0x18002139c  call    cs:__imp_SetThreadpoolTimer
0x1800213a2  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rbx
0x1800213a7  mov     ecx, 18h; Size
0x1800213ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800213b1  mov     [rsp+68h+var_40], rax
0x1800213b6  xorps   xmm0, xmm0
0x1800213b9  movups  xmmword ptr [rax], xmm0
0x1800213bc  mov     dword ptr [rax+8], 1
0x1800213c3  mov     dword ptr [rax+0Ch], 1
0x1800213ca  lea     rcx, ??_7?$_Ref_count@VOperationPerformanceCookie@geo@@@std@@6B@; const std::_Ref_count<geo::OperationPerformanceCookie>::`vftable'
0x1800213d1  mov     [rax], rcx
0x1800213d4  mov     [rax+10h], rbx
0x1800213d8  mov     [rdi], rbx
0x1800213db  mov     rcx, [rdi+8]; this
0x1800213df  mov     [rdi+8], rax
0x1800213e3  test    rcx, rcx
0x1800213e6  jz      short loc_1800213ED
0x1800213e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800213ed  mov     rax, rdi
0x1800213f0  mov     rcx, [rsp+68h+var_30]
0x1800213f5  xor     rcx, rsp; StackCookie
0x1800213f8  call    __security_check_cookie
0x1800213fd  add     rsp, 48h
0x180021401  pop     rdi
0x180021402  pop     rsi
0x180021403  pop     rbp
0x180021404  pop     rbx
0x180021405  retn
0x180021406  xor     ebx, ebx
0x180021408  jmp     short loc_1800213A2
0x18002140a  mov     [rbx+10h], rax
0x18002140e  jmp     loc_180021344
0x180021413  mov     [rbx+8], rax
0x180021417  jmp     loc_18002134F
0x18002141c  lea     rcx, [rsp+68h+pftDueTime]; this
0x180021421  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180021426  mov     rcx, rbp; pti
0x180021429  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002142e  lea     rcx, [rsp+68h+pftDueTime]; this
0x180021433  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180021438  jmp     loc_180021372
```
