# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000f450`
- end: `0x18000f692`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `578`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18001fe50`

## callees

- `0x18000e5e0`
- `0x18000f450`
- `0x18000f698`
- `0x18000f740`
- `0x180027fdc`
- `0x18002aa62`
- `0x18002aad0`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f546`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f61a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f546`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f61a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f49a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f49a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f52e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f52e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f687`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f687`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f679`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f5a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f605`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f65b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f5a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f605`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f65b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f632`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f647`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f647`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // r9
  size_t v12; // r8
  unsigned __int64 v13; // rdi
  DWORD LastError; // esi
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // r8
  char *v17; // rax
  char *v18; // rdi
  const void *v19; // r8
  rsize_t v20; // r12
  void *v21; // r13
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  DWORD v25; // edi
  PTP_TIMER ThreadpoolTimer; // rax
  HANDLE ProcessHeap; // rax
  __int64 v28; // [rsp+20h] [rbp-58h]

  if ( !*pv
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
  LODWORD(v28) = a2;
  HIDWORD(v28) = a3;
  v8 = *((_QWORD *)pv + 29);
  v9 = *((_QWORD *)pv + 31) - v8;
  if ( *((_QWORD *)pv + 30) - v8 + 12 >= v9 )
  {
    v13 = 12;
    if ( 2 * v9 > 0xC )
      v13 = 2 * v9;
    if ( v9 < v13 )
    {
      LastError = GetLastError();
      v15 = (v13 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v17 = (char *)wil::details::ProcessHeapAlloc(0, v15, v16);
      v18 = v17;
      if ( !v17 )
      {
        SetLastError(LastError);
        goto LABEL_11;
      }
      v19 = (const void *)*((_QWORD *)pv + 29);
      v20 = *((_QWORD *)pv + 30) - (_QWORD)v19;
      memcpy_s_0(v17, v15, v19, v20);
      v21 = (void *)*((_QWORD *)pv + 32);
      *((_QWORD *)pv + 32) = v18;
      if ( v21 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v21);
      }
      *((_QWORD *)pv + 29) = v18;
      *((_QWORD *)pv + 30) = &v18[v20];
      *((_QWORD *)pv + 31) = &v18[v15];
      SetLastError(LastError);
    }
  }
  v10 = *((_QWORD *)pv + 31);
  v11 = *((_QWORD *)pv + 30);
  v12 = 0;
  if ( v11 < v10 )
    v12 = *((_QWORD *)pv + 31) - v11;
  if ( !v11 )
  {
    *(_DWORD *)_o__errno(v10, v9, v12) = 22;
LABEL_16:
    invalid_parameter_noinfo();
    goto LABEL_10;
  }
  if ( v12 < 0xC )
  {
    memset_0(*((void **)pv + 30), 0, v12);
    *(_DWORD *)_o__errno(v23, v22, v24) = 34;
    goto LABEL_16;
  }
  *(_QWORD *)v11 = v28;
  *(_DWORD *)(v11 + 8) = a4;
LABEL_10:
  *((_QWORD *)pv + 30) += 12LL;
LABEL_11:
  if ( !pv[64] )
  {
    if ( !*((_QWORD *)pv + 7) )
    {
      v25 = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        pv + 56,
        ThreadpoolTimer);
      SetLastError(v25);
    }
    wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
  }
  if ( pv != (char *)-40LL )
    ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
}

```

## disassembly

```asm
0x18000f450  push    rbx
0x18000f452  push    rbp
0x18000f453  push    rsi
0x18000f454  push    rdi
0x18000f455  push    r12
0x18000f457  push    r13
0x18000f459  push    r14
0x18000f45b  push    r15
0x18000f45d  sub     rsp, 38h
0x18000f461  mov     r14d, r9d
0x18000f464  movzx   edi, r8w
0x18000f468  mov     esi, edx
0x18000f46a  mov     rbx, rcx
0x18000f46d  cmp     byte ptr [rcx], 0
0x18000f470  jz      loc_18000F535
0x18000f476  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f47d  jnz     loc_18000F535
0x18000f483  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f48a  test    rax, rax
0x18000f48d  jnz     loc_18000F559
0x18000f493  lea     rbp, [rbx+28h]
0x18000f497  mov     rcx, rbp; SRWLock
0x18000f49a  call    cs:__imp_AcquireSRWLockExclusive
0x18000f4a0  xor     eax, eax
0x18000f4a2  mov     word ptr [rsp+78h+var_58+6], ax
0x18000f4a7  mov     dword ptr [rsp+78h+var_58], esi
0x18000f4ab  mov     word ptr [rsp+78h+var_58+4], di
0x18000f4b0  mov     rcx, [rbx+0E8h]
0x18000f4b7  mov     rdx, [rbx+0F8h]
0x18000f4be  sub     rdx, rcx
0x18000f4c1  mov     rax, [rbx+0F0h]
0x18000f4c8  sub     rax, rcx
0x18000f4cb  add     rax, 0Ch
0x18000f4cf  cmp     rax, rdx
0x18000f4d2  jnb     loc_18000F568
0x18000f4d8  mov     rcx, [rbx+0F8h]
0x18000f4df  mov     r9, [rbx+0F0h]
0x18000f4e6  mov     rax, rcx
0x18000f4e9  sub     rax, r9
0x18000f4ec  xor     r8d, r8d
0x18000f4ef  cmp     r9, rcx
0x18000f4f2  cmovb   r8, rax; Size
0x18000f4f6  test    r9, r9
0x18000f4f9  jz      short loc_18000F546
0x18000f4fb  cmp     r8, 0Ch
0x18000f4ff  jb      loc_18000F610
0x18000f505  movsd   xmm0, [rsp+78h+var_58]
0x18000f50b  movsd   qword ptr [r9], xmm0
0x18000f510  mov     [r9+8], r14d
0x18000f514  add     qword ptr [rbx+0F0h], 0Ch
0x18000f51c  cmp     byte ptr [rbx+40h], 0
0x18000f520  jz      loc_18000F62B
0x18000f526  test    rbp, rbp
0x18000f529  jz      short loc_18000F535
0x18000f52b  mov     rcx, rbp; SRWLock
0x18000f52e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f534  nop
0x18000f535  add     rsp, 38h
0x18000f539  pop     r15
0x18000f53b  pop     r14
0x18000f53d  pop     r13
0x18000f53f  pop     r12
0x18000f541  pop     rdi
0x18000f542  pop     rsi
0x18000f543  pop     rbp
0x18000f544  pop     rbx
0x18000f545  retn
0x18000f546  call    cs:__imp__o__errno
0x18000f54c  mov     dword ptr [rax], 16h
0x18000f552  call    _invalid_parameter_noinfo
0x18000f557  jmp     short loc_18000F514
0x18000f559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f55e  test    al, al
0x18000f560  jz      loc_18000F493
0x18000f566  jmp     short loc_18000F535
0x18000f568  lea     rax, [rdx+rdx]
0x18000f56c  mov     edi, 0Ch
0x18000f571  cmp     rax, rdi
0x18000f574  cmova   rdi, rax
0x18000f578  cmp     rdx, rdi
0x18000f57b  jnb     loc_18000F4D8
0x18000f581  call    cs:__imp_GetLastError
0x18000f587  mov     esi, eax
0x18000f589  and     rdi, 0FFFFFFFFFFFFFFC0h
0x18000f58d  lea     r15, [rdi+40h]
0x18000f591  mov     rdx, r15; dwBytes
0x18000f594  xor     ecx, ecx; dwFlags
0x18000f596  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f59b  mov     rdi, rax
0x18000f59e  test    rax, rax
0x18000f5a1  jnz     short loc_18000F5B0
0x18000f5a3  mov     ecx, esi; dwErrCode
0x18000f5a5  call    cs:__imp_SetLastError
0x18000f5ab  jmp     loc_18000F51C
0x18000f5b0  mov     r8, [rbx+0E8h]; Source
0x18000f5b7  mov     r12, [rbx+0F0h]
0x18000f5be  sub     r12, r8
0x18000f5c1  mov     r9, r12; SourceSize
0x18000f5c4  mov     rdx, r15; DestinationSize
0x18000f5c7  mov     rcx, rdi; Destination
0x18000f5ca  call    memcpy_s_0
0x18000f5cf  mov     r13, [rbx+100h]
0x18000f5d6  mov     [rbx+100h], rdi
0x18000f5dd  test    r13, r13
0x18000f5e0  jnz     loc_18000F679
0x18000f5e6  mov     [rbx+0E8h], rdi
0x18000f5ed  lea     rax, [r12+rdi]
0x18000f5f1  mov     [rbx+0F0h], rax
0x18000f5f8  lea     rax, [r15+rdi]
0x18000f5fc  mov     [rbx+0F8h], rax
0x18000f603  mov     ecx, esi; dwErrCode
0x18000f605  call    cs:__imp_SetLastError
0x18000f60b  jmp     loc_18000F4D8
0x18000f610  xor     edx, edx; Val
0x18000f612  mov     rcx, r9; void *
0x18000f615  call    memset_0
0x18000f61a  call    cs:__imp__o__errno
0x18000f620  mov     dword ptr [rax], 22h ; '"'
0x18000f626  jmp     loc_18000F552
0x18000f62b  cmp     qword ptr [rbx+38h], 0
0x18000f630  jnz     short loc_18000F661
0x18000f632  call    cs:__imp_GetLastError
0x18000f638  mov     edi, eax
0x18000f63a  xor     r8d, r8d; pcbe
0x18000f63d  mov     rdx, rbx; pv
0x18000f640  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f647  call    cs:__imp_CreateThreadpoolTimer
0x18000f64d  mov     rdx, rax
0x18000f650  lea     rcx, [rbx+38h]
0x18000f654  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000f659  mov     ecx, edi; dwErrCode
0x18000f65b  call    cs:__imp_SetLastError
0x18000f661  mov     r8d, 1388h
0x18000f667  lea     rdx, [rbx+40h]
0x18000f66b  lea     rcx, [rbx+38h]
0x18000f66f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000f674  jmp     loc_18000F526
0x18000f679  call    cs:__imp_GetProcessHeap
0x18000f67f  mov     rcx, rax; hHeap
0x18000f682  mov     r8, r13; lpMem
0x18000f685  xor     edx, edx; dwFlags
0x18000f687  call    cs:__imp_HeapFree
0x18000f68d  jmp     loc_18000F5E6
```
