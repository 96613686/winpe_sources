# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001eff0`
- end: `0x18001f0d2`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `226`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002a9d0`

## callees

- `0x180015a10`
- `0x180016790`
- `0x1800176d4`
- `0x180017708`
- `0x1800178c4`
- `0x18001eff0`
- `0x18001f344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f02c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f02c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f0b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f0b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f083`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f083`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  int Source; // [rsp+20h] [rbp-28h] BYREF
  __int16 v10; // [rsp+24h] [rbp-24h]
  __int16 v11; // [rsp+26h] [rbp-22h]
  int v12; // [rsp+28h] [rbp-20h]
  char v13; // [rsp+50h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v11 = 0;
    Source = a2;
    v10 = a3;
    v12 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &Source, 0xCu);
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
0x18001eff0  mov     [rsp+arg_8], rbx
0x18001eff5  mov     [rsp+arg_10], rbp
0x18001effa  push    rsi
0x18001effb  push    rdi
0x18001effc  push    r14
0x18001effe  sub     rsp, 30h
0x18001f002  mov     edi, r9d
0x18001f005  movzx   ebp, r8w
0x18001f009  mov     r14d, edx
0x18001f00c  mov     rbx, rcx
0x18001f00f  cmp     byte ptr [rcx], 0
0x18001f012  jz      loc_18001F0BF
0x18001f018  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001f01d  test    al, al
0x18001f01f  jnz     loc_18001F0BF
0x18001f025  lea     rsi, [rbx+28h]
0x18001f029  mov     rcx, rsi; SRWLock
0x18001f02c  call    cs:__imp_AcquireSRWLockExclusive
0x18001f032  xor     eax, eax
0x18001f034  mov     [rsp+48h+var_22], ax
0x18001f039  mov     [rsp+48h+Source], r14d
0x18001f03e  mov     [rsp+48h+var_24], bp
0x18001f043  mov     [rsp+48h+var_20], edi
0x18001f047  lea     rcx, [rbx+0E8h]; this
0x18001f04e  lea     r8d, [rax+0Ch]; SourceSize
0x18001f052  lea     rdx, [rsp+48h+Source]; Source
0x18001f057  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001f05c  cmp     byte ptr [rbx+40h], 0
0x18001f060  jnz     short loc_18001F0B0
0x18001f062  lea     rdi, [rbx+38h]
0x18001f066  cmp     qword ptr [rdi], 0
0x18001f06a  jnz     short loc_18001F09E
0x18001f06c  lea     rcx, [rsp+48h+arg_0]; this
0x18001f071  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001f076  xor     r8d, r8d; pcbe
0x18001f079  mov     rdx, rbx; pv
0x18001f07c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001f083  call    cs:__imp_CreateThreadpoolTimer
0x18001f089  mov     rdx, rax
0x18001f08c  mov     rcx, rdi
0x18001f08f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001f094  lea     rcx, [rsp+48h+arg_0]; this
0x18001f099  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001f09e  mov     r8d, 1388h
0x18001f0a4  lea     rdx, [rbx+40h]
0x18001f0a8  mov     rcx, rdi
0x18001f0ab  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001f0b0  test    rsi, rsi
0x18001f0b3  jz      short loc_18001F0BF
0x18001f0b5  mov     rcx, rsi; SRWLock
0x18001f0b8  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f0be  nop
0x18001f0bf  mov     rbx, [rsp+48h+arg_8]
0x18001f0c4  mov     rbp, [rsp+48h+arg_10]
0x18001f0c9  add     rsp, 30h
0x18001f0cd  pop     r14
0x18001f0cf  pop     rdi
0x18001f0d0  pop     rsi
0x18001f0d1  retn
```
