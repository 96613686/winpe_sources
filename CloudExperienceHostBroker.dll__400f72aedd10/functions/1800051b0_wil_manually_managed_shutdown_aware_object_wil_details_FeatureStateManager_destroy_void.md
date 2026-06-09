# wil::manually_managed_shutdown_aware_object<wil::details::FeatureStateManager>::destroy(void)

- ea: `0x1800051b0`
- end: `0x180005375`
- name: `?destroy@?$manually_managed_shutdown_aware_object@VFeatureStateManager@details@wil@@@wil@@QEAAXXZ`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180037150`

## callees

- `0x1800051b0`
- `0x18000858c`
- `0x180016ed4`
- `0x180018774`
- `0x18001c4d0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005245`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005276`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005245`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005276`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005310`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005333`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005356`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005310`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005333`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005356`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005302`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005325`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005348`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005302`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005325`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005348`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::manually_managed_shutdown_aware_object<wil::details::FeatureStateManager>::destroy(
        __int64 a1,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  struct _TP_TIMER *v4; // rsi
  void *v5; // rdi
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rcx
  void *v7; // rsi
  void *v8; // rsi
  struct _TP_TIMER *v9; // rcx
  struct _TP_TIMER *v10; // rcx
  void *v11; // rcx
  DWORD LastError; // edi
  DWORD v13; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    *(_BYTE *)a1 = 0;
    v11 = *(void **)(a1 + 16);
    if ( v11 )
LABEL_25:
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v11);
  }
  else
  {
    *(_BYTE *)a1 = 0;
    v3 = *(struct _TP_TIMER **)(a1 + 48);
    if ( v3 )
    {
      LastError = GetLastError();
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v3);
      SetLastError(LastError);
    }
    *(_QWORD *)(a1 + 48) = 0;
    v4 = *(struct _TP_TIMER **)(a1 + 56);
    if ( v4 )
    {
      v13 = GetLastError();
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
      SetLastError(v13);
    }
    *(_QWORD *)(a1 + 56) = 0;
    v5 = *(void **)(a1 + 256);
    *(_QWORD *)(a1 + 256) = 0;
    if ( v5 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
    v6 = *(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **)(a1 + 224);
    if ( v6 )
      wil::details::UnsubscribeProcessWideUsageFlush(v6, a2);
    v7 = *(void **)(a1 + 216);
    *(_QWORD *)(a1 + 216) = 0;
    if ( v7 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v7);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
    if ( *(_QWORD *)(a1 + 144) )
      wil_details_RtlUnregisterFeatureConfigurationChangeNotification();
    v8 = *(void **)(a1 + 136);
    *(_QWORD *)(a1 + 136) = 0;
    if ( v8 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v8);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
    v9 = *(struct _TP_TIMER **)(a1 + 56);
    if ( v9 )
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v9);
    v10 = *(struct _TP_TIMER **)(a1 + 48);
    if ( v10 )
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v10);
    v11 = *(void **)(a1 + 16);
    if ( v11 )
      goto LABEL_25;
  }
}

```

## disassembly

```asm
0x1800051b0  push    rbx
0x1800051b2  push    rbp
0x1800051b3  push    rsi
0x1800051b4  push    rdi
0x1800051b5  sub     rsp, 28h
0x1800051b9  mov     rbx, rcx
0x1800051bc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800051c3  jnz     loc_1800052B5
0x1800051c9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800051d0  test    rax, rax
0x1800051d3  jnz     loc_1800052A8
0x1800051d9  mov     byte ptr [rbx], 0
0x1800051dc  mov     rsi, [rbx+30h]
0x1800051e0  test    rsi, rsi
0x1800051e3  jnz     loc_1800052C8
0x1800051e9  xor     ebp, ebp
0x1800051eb  mov     [rbx+30h], rbp
0x1800051ef  mov     rsi, [rbx+38h]
0x1800051f3  test    rsi, rsi
0x1800051f6  jnz     loc_1800052E5
0x1800051fc  mov     [rbx+38h], rbp
0x180005200  mov     rdi, [rbx+100h]
0x180005207  mov     [rbx+100h], rbp
0x18000520e  test    rdi, rdi
0x180005211  jnz     loc_180005302
0x180005217  mov     rcx, [rbx+0E0h]; this
0x18000521e  test    rcx, rcx
0x180005221  jnz     loc_18000531B
0x180005227  mov     rsi, [rbx+0D8h]
0x18000522e  mov     [rbx+0D8h], rbp
0x180005235  test    rsi, rsi
0x180005238  jnz     loc_180005325
0x18000523e  lea     rcx, [rbx+98h]; lpCriticalSection
0x180005245  call    cs:__imp_DeleteCriticalSection
0x18000524b  mov     rcx, [rbx+90h]
0x180005252  test    rcx, rcx
0x180005255  jnz     loc_18000533E
0x18000525b  mov     rsi, [rbx+88h]
0x180005262  mov     [rbx+88h], rbp
0x180005269  test    rsi, rsi
0x18000526c  jnz     loc_180005348
0x180005272  lea     rcx, [rbx+48h]; lpCriticalSection
0x180005276  call    cs:__imp_DeleteCriticalSection
0x18000527c  mov     rcx, [rbx+38h]; pti
0x180005280  test    rcx, rcx
0x180005283  jnz     loc_180005361
0x180005289  mov     rcx, [rbx+30h]; pti
0x18000528d  test    rcx, rcx
0x180005290  jnz     loc_18000536B
0x180005296  mov     rcx, [rbx+10h]
0x18000529a  test    rcx, rcx
0x18000529d  jnz     short loc_1800052C1
0x18000529f  add     rsp, 28h
0x1800052a3  pop     rdi
0x1800052a4  pop     rsi
0x1800052a5  pop     rbp
0x1800052a6  pop     rbx
0x1800052a7  retn
0x1800052a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ad  test    al, al
0x1800052af  jz      loc_1800051D9
0x1800052b5  mov     byte ptr [rbx], 0
0x1800052b8  mov     rcx, [rbx+10h]; lpMem
0x1800052bc  test    rcx, rcx
0x1800052bf  jz      short loc_18000529F
0x1800052c1  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800052c6  jmp     short loc_18000529F
0x1800052c8  call    cs:__imp_GetLastError
0x1800052ce  mov     edi, eax
0x1800052d0  mov     rcx, rsi; pti
0x1800052d3  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800052d8  mov     ecx, edi; dwErrCode
0x1800052da  call    cs:__imp_SetLastError
0x1800052e0  jmp     loc_1800051E9
0x1800052e5  call    cs:__imp_GetLastError
0x1800052eb  mov     edi, eax
0x1800052ed  mov     rcx, rsi; pti
0x1800052f0  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800052f5  mov     ecx, edi; dwErrCode
0x1800052f7  call    cs:__imp_SetLastError
0x1800052fd  jmp     loc_1800051FC
0x180005302  call    cs:__imp_GetProcessHeap
0x180005308  mov     rcx, rax; hHeap
0x18000530b  mov     r8, rdi; lpMem
0x18000530e  xor     edx, edx; dwFlags
0x180005310  call    cs:__imp_HeapFree
0x180005316  jmp     loc_180005217
0x18000531b  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180005320  jmp     loc_180005227
0x180005325  call    cs:__imp_GetProcessHeap
0x18000532b  mov     rcx, rax; hHeap
0x18000532e  mov     r8, rsi; lpMem
0x180005331  xor     edx, edx; dwFlags
0x180005333  call    cs:__imp_HeapFree
0x180005339  jmp     loc_18000523E
0x18000533e  call    wil_details_RtlUnregisterFeatureConfigurationChangeNotification
0x180005343  jmp     loc_18000525B
0x180005348  call    cs:__imp_GetProcessHeap
0x18000534e  mov     rcx, rax; hHeap
0x180005351  mov     r8, rsi; lpMem
0x180005354  xor     edx, edx; dwFlags
0x180005356  call    cs:__imp_HeapFree
0x18000535c  jmp     loc_180005272
0x180005361  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180005366  jmp     loc_180005289
0x18000536b  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180005370  jmp     loc_180005296
```
