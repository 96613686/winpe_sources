# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000d2c8`
- end: `0x18000d40a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `322`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ffd0`

## callees

- `0x18000d2c8`
- `0x1800105e0`
- `0x180010774`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d3e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d3e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d326`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d36c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d36c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d3cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d3cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d387`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d387`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  int Source; // [rsp+20h] [rbp-28h] BYREF
  __int16 v13; // [rsp+24h] [rbp-24h]
  __int16 v14; // [rsp+26h] [rbp-22h]
  int v15; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v14 = 0;
    Source = a2;
    v13 = a3;
    v15 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[29], &Source, 0xCu);
    v8 = (struct _TP_TIMER **)&pv[7];
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !*v8 )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)&pv[7],
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x18000d2c8  mov     [rsp+arg_8], rbx
0x18000d2cd  mov     [rsp+arg_10], rbp
0x18000d2d2  mov     [rsp+arg_18], rsi
0x18000d2d7  push    rdi
0x18000d2d8  push    r14
0x18000d2da  push    r15
0x18000d2dc  sub     rsp, 30h
0x18000d2e0  mov     ebx, r9d
0x18000d2e3  movzx   ebp, r8w
0x18000d2e7  mov     r14d, edx
0x18000d2ea  mov     rdi, rcx
0x18000d2ed  xor     r15d, r15d
0x18000d2f0  cmp     [rcx], r15b
0x18000d2f3  jz      loc_18000D3F0
0x18000d2f9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x18000d300  jnz     loc_18000D3F0
0x18000d306  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d30d  test    rax, rax
0x18000d310  jz      short loc_18000D31F
0x18000d312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d317  test    al, al
0x18000d319  jnz     loc_18000D3F0
0x18000d31f  lea     rsi, [rdi+28h]
0x18000d323  mov     rcx, rsi; SRWLock
0x18000d326  call    cs:__imp_AcquireSRWLockExclusive
0x18000d32d  nop     dword ptr [rax+rax+00h]
0x18000d332  mov     [rsp+48h+var_22], r15w
0x18000d338  mov     [rsp+48h+Source], r14d
0x18000d33d  mov     [rsp+48h+var_24], bp
0x18000d342  mov     [rsp+48h+var_20], ebx
0x18000d346  lea     rcx, [rdi+0E8h]; this
0x18000d34d  mov     r8d, 0Ch; SourceSize
0x18000d353  lea     rdx, [rsp+48h+Source]; Source
0x18000d358  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000d35d  lea     r14, [rdi+38h]
0x18000d361  cmp     [rdi+40h], r15b
0x18000d365  jnz     short loc_18000D3DB
0x18000d367  cmp     [r14], r15
0x18000d36a  jnz     short loc_18000D3AC
0x18000d36c  call    cs:__imp_GetLastError
0x18000d373  nop     dword ptr [rax+rax+00h]
0x18000d378  mov     ebx, eax
0x18000d37a  xor     r8d, r8d; pcbe
0x18000d37d  mov     rdx, rdi; pv
0x18000d380  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000d387  call    cs:__imp_CreateThreadpoolTimer
0x18000d38e  nop     dword ptr [rax+rax+00h]
0x18000d393  mov     rdx, rax
0x18000d396  mov     rcx, r14
0x18000d399  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000d39e  mov     ecx, ebx; dwErrCode
0x18000d3a0  call    cs:__imp_SetLastError
0x18000d3a7  nop     dword ptr [rax+rax+00h]
0x18000d3ac  mov     rcx, [r14]; pti
0x18000d3af  test    rcx, rcx
0x18000d3b2  jz      short loc_18000D3DB
0x18000d3b4  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000d3bd  mov     r9d, 4E2h; msWindowLength
0x18000d3c3  xor     r8d, r8d; msPeriod
0x18000d3c6  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000d3cb  call    cs:__imp_SetThreadpoolTimer
0x18000d3d2  nop     dword ptr [rax+rax+00h]
0x18000d3d7  mov     byte ptr [rdi+40h], 1
0x18000d3db  test    rsi, rsi
0x18000d3de  jz      short loc_18000D3F0
0x18000d3e0  mov     rcx, rsi; SRWLock
0x18000d3e3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d3ea  nop     dword ptr [rax+rax+00h]
0x18000d3ef  nop
0x18000d3f0  mov     rbx, [rsp+48h+arg_8]
0x18000d3f5  mov     rbp, [rsp+48h+arg_10]
0x18000d3fa  mov     rsi, [rsp+48h+arg_18]
0x18000d3ff  add     rsp, 30h
0x18000d403  pop     r15
0x18000d405  pop     r14
0x18000d407  pop     rdi
0x18000d408  retn
```
