# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140008e60`
- end: `0x140008fbc`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c280`

## callees

- `0x140008e60`
- `0x14000cc9c`
- `0x14000cec8`
- `0x14000d6b8`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008eb5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008eb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008f9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008f24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008f58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008f58`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008f3f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008f3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008f83`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008f83`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  int Source; // [rsp+20h] [rbp-28h] BYREF
  __int16 v13; // [rsp+24h] [rbp-24h]
  __int16 v14; // [rsp+26h] [rbp-22h]
  int v15; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( *pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v14 = 0;
    Source = a2;
    v13 = a3;
    v15 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 232), 0xCu) )
    {
      memcpy_s(
        *((void *const *)pv + 30),
        (*((_QWORD *)pv + 31) - *((_QWORD *)pv + 30)) & -(__int64)(*((_QWORD *)pv + 30) < *((_QWORD *)pv + 31)),
        &Source,
        0xCu);
      *((_QWORD *)pv + 30) += 12LL;
    }
    if ( !pv[64] )
    {
      v8 = (struct _TP_TIMER **)(pv + 56);
      if ( !*((_QWORD *)pv + 7) )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)pv + 7,
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        pv[64] = 1;
      }
    }
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x140008e60  mov     [rsp+arg_8], rbx
0x140008e65  mov     [rsp+arg_10], rbp
0x140008e6a  push    rsi
0x140008e6b  push    rdi
0x140008e6c  push    r14
0x140008e6e  sub     rsp, 30h
0x140008e72  mov     ebx, r9d
0x140008e75  movzx   esi, r8w
0x140008e79  mov     r14d, edx
0x140008e7c  mov     rdi, rcx
0x140008e7f  cmp     byte ptr [rcx], 0
0x140008e82  jz      loc_140008FA8
0x140008e88  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008e8f  jnz     loc_140008FA8
0x140008e95  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008e9c  test    rax, rax
0x140008e9f  jz      short loc_140008EAE
0x140008ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ea6  test    al, al
0x140008ea8  jnz     loc_140008FA8
0x140008eae  lea     rbp, [rdi+28h]
0x140008eb2  mov     rcx, rbp; SRWLock
0x140008eb5  call    cs:__imp_AcquireSRWLockExclusive
0x140008ebc  nop     dword ptr [rax+rax+00h]
0x140008ec1  xor     eax, eax
0x140008ec3  mov     [rsp+48h+var_22], ax
0x140008ec8  mov     [rsp+48h+Source], r14d
0x140008ecd  mov     [rsp+48h+var_24], si
0x140008ed2  mov     [rsp+48h+var_20], ebx
0x140008ed6  lea     rbx, [rdi+0E8h]
0x140008edd  lea     esi, [rax+0Ch]
0x140008ee0  mov     edx, esi; unsigned __int64
0x140008ee2  mov     rcx, rbx; this
0x140008ee5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008eea  test    al, al
0x140008eec  jz      short loc_140008F14
0x140008eee  mov     rcx, [rbx+8]; Destination
0x140008ef2  mov     rax, [rbx+10h]
0x140008ef6  sub     rax, rcx
0x140008ef9  cmp     rcx, [rbx+10h]
0x140008efd  sbb     rdx, rdx
0x140008f00  and     rdx, rax; DestinationSize
0x140008f03  mov     r9d, esi; SourceSize
0x140008f06  lea     r8, [rsp+48h+Source]; Source
0x140008f0b  call    memcpy_s
0x140008f10  add     [rbx+8], rsi
0x140008f14  cmp     byte ptr [rdi+40h], 0
0x140008f18  jnz     short loc_140008F93
0x140008f1a  lea     rsi, [rdi+38h]
0x140008f1e  cmp     qword ptr [rsi], 0
0x140008f22  jnz     short loc_140008F64
0x140008f24  call    cs:__imp_GetLastError
0x140008f2b  nop     dword ptr [rax+rax+00h]
0x140008f30  mov     ebx, eax
0x140008f32  xor     r8d, r8d; pcbe
0x140008f35  mov     rdx, rdi; pv
0x140008f38  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140008f3f  call    cs:__imp_CreateThreadpoolTimer
0x140008f46  nop     dword ptr [rax+rax+00h]
0x140008f4b  mov     rdx, rax
0x140008f4e  mov     rcx, rsi
0x140008f51  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140008f56  mov     ecx, ebx; dwErrCode
0x140008f58  call    cs:__imp_SetLastError
0x140008f5f  nop     dword ptr [rax+rax+00h]
0x140008f64  mov     rcx, [rsi]; pti
0x140008f67  test    rcx, rcx
0x140008f6a  jz      short loc_140008F93
0x140008f6c  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140008f75  mov     r9d, 4E2h; msWindowLength
0x140008f7b  xor     r8d, r8d; msPeriod
0x140008f7e  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x140008f83  call    cs:__imp_SetThreadpoolTimer
0x140008f8a  nop     dword ptr [rax+rax+00h]
0x140008f8f  mov     byte ptr [rdi+40h], 1
0x140008f93  test    rbp, rbp
0x140008f96  jz      short loc_140008FA8
0x140008f98  mov     rcx, rbp; SRWLock
0x140008f9b  call    cs:__imp_ReleaseSRWLockExclusive
0x140008fa2  nop     dword ptr [rax+rax+00h]
0x140008fa7  nop
0x140008fa8  mov     rbx, [rsp+48h+arg_8]
0x140008fad  mov     rbp, [rsp+48h+arg_10]
0x140008fb2  add     rsp, 30h
0x140008fb6  pop     r14
0x140008fb8  pop     rdi
0x140008fb9  pop     rsi
0x140008fba  retn
```
