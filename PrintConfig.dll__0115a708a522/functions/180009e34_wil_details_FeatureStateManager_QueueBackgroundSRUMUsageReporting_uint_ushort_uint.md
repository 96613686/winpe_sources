# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180009e34`
- end: `0x180009f9a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `358`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c900`

## callees

- `0x180009e34`
- `0x18000d09c`
- `0x18000d194`
- `0x18000d538`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180009f1d`
- `KERNEL32!CreateThreadpoolTimer` at `0x180009f1d`
- `KERNEL32!SetThreadpoolTimer` at `0x180009f61`
- `KERNEL32!SetThreadpoolTimer` at `0x180009f61`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009e93`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009e93`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009f79`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009f79`
- `KERNEL32!SetLastError` at `0x180009f36`
- `KERNEL32!SetLastError` at `0x180009f36`
- `KERNEL32!GetLastError` at `0x180009f02`
- `KERNEL32!GetLastError` at `0x180009f02`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  int Source; // [rsp+28h] [rbp-30h] BYREF
  __int16 v13; // [rsp+2Ch] [rbp-2Ch]
  __int16 v14; // [rsp+2Eh] [rbp-2Ah]
  int v15; // [rsp+30h] [rbp-28h]
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv)) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v14 = 0;
    Source = a2;
    v13 = a3;
    v15 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s_0(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      v8 = (struct _TP_TIMER **)&pv[7];
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            (PTP_TIMER_CALLBACK)_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
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
0x180009e34  push    rsi
0x180009e36  push    rdi
0x180009e37  push    r14
0x180009e39  sub     rsp, 40h
0x180009e3d  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180009e46  mov     [rsp+58h+arg_8], rbx
0x180009e4b  mov     [rsp+58h+arg_10], rbp
0x180009e50  mov     ebx, r9d
0x180009e53  movzx   esi, r8w
0x180009e57  mov     r14d, edx
0x180009e5a  mov     rdi, rcx
0x180009e5d  cmp     byte ptr [rcx], 0
0x180009e60  jz      loc_180009F86
0x180009e66  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009e6d  jnz     loc_180009F86
0x180009e73  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009e7a  test    rax, rax
0x180009e7d  jz      short loc_180009E8C
0x180009e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e84  test    al, al
0x180009e86  jnz     loc_180009F86
0x180009e8c  lea     rbp, [rdi+28h]
0x180009e90  mov     rcx, rbp; SRWLock
0x180009e93  call    cs:__imp_AcquireSRWLockExclusive
0x180009e9a  nop     dword ptr [rax+rax+00h]
0x180009e9f  xor     eax, eax
0x180009ea1  mov     [rsp+58h+var_2A], ax
0x180009ea6  mov     [rsp+58h+Source], r14d
0x180009eab  mov     [rsp+58h+var_2C], si
0x180009eb0  mov     [rsp+58h+var_28], ebx
0x180009eb4  lea     rbx, [rdi+0E8h]
0x180009ebb  lea     esi, [rax+0Ch]
0x180009ebe  mov     edx, esi; unsigned __int64
0x180009ec0  mov     rcx, rbx; this
0x180009ec3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009ec8  test    al, al
0x180009eca  jz      short loc_180009EF2
0x180009ecc  mov     rcx, [rbx+8]; Destination
0x180009ed0  mov     rax, [rbx+10h]
0x180009ed4  sub     rax, rcx
0x180009ed7  cmp     rcx, [rbx+10h]
0x180009edb  sbb     rdx, rdx
0x180009ede  and     rdx, rax; DestinationSize
0x180009ee1  mov     r9d, esi; SourceSize
0x180009ee4  lea     r8, [rsp+58h+Source]; Source
0x180009ee9  call    memcpy_s_0
0x180009eee  add     [rbx+8], rsi
0x180009ef2  cmp     byte ptr [rdi+40h], 0
0x180009ef6  jnz     short loc_180009F71
0x180009ef8  lea     rsi, [rdi+38h]
0x180009efc  cmp     qword ptr [rsi], 0
0x180009f00  jnz     short loc_180009F42
0x180009f02  call    cs:__imp_GetLastError
0x180009f09  nop     dword ptr [rax+rax+00h]
0x180009f0e  mov     ebx, eax
0x180009f10  xor     r8d, r8d; pcbe
0x180009f13  mov     rdx, rdi; pv
0x180009f16  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009f1d  call    cs:__imp_CreateThreadpoolTimer
0x180009f24  nop     dword ptr [rax+rax+00h]
0x180009f29  mov     rdx, rax
0x180009f2c  mov     rcx, rsi
0x180009f2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009f34  mov     ecx, ebx; dwErrCode
0x180009f36  call    cs:__imp_SetLastError
0x180009f3d  nop     dword ptr [rax+rax+00h]
0x180009f42  mov     rcx, [rsi]; pti
0x180009f45  test    rcx, rcx
0x180009f48  jz      short loc_180009F71
0x180009f4a  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180009f53  mov     r9d, 4E2h; msWindowLength
0x180009f59  xor     r8d, r8d; msPeriod
0x180009f5c  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180009f61  call    cs:__imp_SetThreadpoolTimer
0x180009f68  nop     dword ptr [rax+rax+00h]
0x180009f6d  mov     byte ptr [rdi+40h], 1
0x180009f71  test    rbp, rbp
0x180009f74  jz      short loc_180009F86
0x180009f76  mov     rcx, rbp; SRWLock
0x180009f79  call    cs:__imp_ReleaseSRWLockExclusive
0x180009f80  nop     dword ptr [rax+rax+00h]
0x180009f85  nop
0x180009f86  mov     rbx, [rsp+58h+arg_8]
0x180009f8b  mov     rbp, [rsp+58h+arg_10]
0x180009f90  add     rsp, 40h
0x180009f94  pop     r14
0x180009f96  pop     rdi
0x180009f97  pop     rsi
0x180009f98  retn
```
