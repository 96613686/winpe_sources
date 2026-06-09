# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800196c4`
- end: `0x1800197a6`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `226`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000a720`

## callees

- `0x18000a3f0`
- `0x18000a52c`
- `0x1800196c4`
- `0x180019938`
- `0x180019958`
- `0x18001999c`
- `0x18002b2e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019700`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019700`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001978c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001978c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019757`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019757`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  int v9; // [rsp+20h] [rbp-28h] BYREF
  __int16 v10; // [rsp+24h] [rbp-24h]
  __int16 v11; // [rsp+26h] [rbp-22h]
  int v12; // [rsp+28h] [rbp-20h]
  char v13; // [rsp+50h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v11 = 0;
    v9 = a2;
    v10 = a3;
    v12 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v9, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x1800196c4  mov     [rsp+arg_8], rbx
0x1800196c9  mov     [rsp+arg_10], rbp
0x1800196ce  push    rsi
0x1800196cf  push    rdi
0x1800196d0  push    r14
0x1800196d2  sub     rsp, 30h
0x1800196d6  mov     edi, r9d
0x1800196d9  movzx   ebp, r8w
0x1800196dd  mov     r14d, edx
0x1800196e0  mov     rbx, rcx
0x1800196e3  cmp     byte ptr [rcx], 0
0x1800196e6  jz      loc_180019793
0x1800196ec  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800196f1  test    al, al
0x1800196f3  jnz     loc_180019793
0x1800196f9  lea     rsi, [rbx+28h]
0x1800196fd  mov     rcx, rsi; SRWLock
0x180019700  call    cs:__imp_AcquireSRWLockExclusive
0x180019706  xor     eax, eax
0x180019708  mov     [rsp+48h+var_22], ax
0x18001970d  mov     [rsp+48h+var_28], r14d
0x180019712  mov     [rsp+48h+var_24], bp
0x180019717  mov     [rsp+48h+var_20], edi
0x18001971b  lea     rcx, [rbx+0E8h]; this
0x180019722  lea     r8d, [rax+0Ch]; unsigned __int64
0x180019726  lea     rdx, [rsp+48h+var_28]; void *
0x18001972b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180019730  cmp     byte ptr [rbx+40h], 0
0x180019734  jnz     short loc_180019784
0x180019736  lea     rdi, [rbx+38h]
0x18001973a  cmp     qword ptr [rdi], 0
0x18001973e  jnz     short loc_180019772
0x180019740  lea     rcx, [rsp+48h+arg_0]; this
0x180019745  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001974a  xor     r8d, r8d; pcbe
0x18001974d  mov     rdx, rbx; pv
0x180019750  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019757  call    cs:__imp_CreateThreadpoolTimer
0x18001975d  mov     rdx, rax
0x180019760  mov     rcx, rdi
0x180019763  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180019768  lea     rcx, [rsp+48h+arg_0]; this
0x18001976d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019772  mov     r8d, 1388h
0x180019778  lea     rdx, [rbx+40h]
0x18001977c  mov     rcx, rdi
0x18001977f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180019784  test    rsi, rsi
0x180019787  jz      short loc_180019793
0x180019789  mov     rcx, rsi; SRWLock
0x18001978c  call    cs:__imp_ReleaseSRWLockExclusive
0x180019792  nop
0x180019793  mov     rbx, [rsp+48h+arg_8]
0x180019798  mov     rbp, [rsp+48h+arg_10]
0x18001979d  add     rsp, 30h
0x1800197a1  pop     r14
0x1800197a3  pop     rdi
0x1800197a4  pop     rsi
0x1800197a5  retn
```
