# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18002b900`
- end: `0x18002ba24`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003e314`

## callees

- `0x18002b900`
- `0x18005f3b0`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b9ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b9ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b973`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b973`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b987`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b987`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b915`

## string_xrefs

- `0x18002b9e8`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v3; // rbp
  unsigned __int64 CurrentThreadId; // rbx
  unsigned __int64 v5; // r14
  __int64 i; // rax
  HANDLE ProcessHeap; // rsi
  _DWORD *v9; // rdi
  void (__fastcall *ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(HANDLE, _DWORD *); // rax
  signed __int64 v11; // rax
  HMODULE ModuleHandleW; // rax

  v3 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v5 = 8 * ((CurrentThreadId >> 2) % 0xA);
  for ( i = *(_QWORD *)(v5 + v3); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      return (char *)(i + 16);
  }
  if ( !a2 )
    return 0;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 0x18u);
  ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, _DWORD *))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, _DWORD *))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (void (__fastcall *)(HANDLE, _DWORD *))(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, _DWORD *))___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW),
                                                `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z) )
  {
    ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ProcessHeap, v9);
  }
  if ( !v9 )
    return 0;
  *v9 = CurrentThreadId;
  v9[1] = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  do
  {
    v11 = *(_QWORD *)(v5 + v3);
    *((_QWORD *)v9 + 1) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v3), (signed __int64)v9, v11) );
  return (char *)(v9 + 4);
}

```

## disassembly

```asm
0x18002b900  push    rbx
0x18002b902  push    rbp
0x18002b903  push    rsi
0x18002b904  push    rdi
0x18002b905  push    r14
0x18002b907  sub     rsp, 20h
0x18002b90b  movzx   edi, dl
0x18002b90e  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002b915  call    cs:__imp_GetCurrentThreadId
0x18002b91b  mov     ebx, eax
0x18002b91d  mov     r8d, eax
0x18002b920  shr     r8, 2
0x18002b924  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002b92e  mul     r8
0x18002b931  shr     rdx, 3
0x18002b935  lea     rcx, [rdx+rdx*4]
0x18002b939  add     rcx, rcx
0x18002b93c  sub     r8, rcx
0x18002b93f  lea     r14, ds:0[r8*8]
0x18002b947  mov     rax, [r14+rbp]
0x18002b94b  nop     dword ptr [rax+rax+00h]
0x18002b950  test    rax, rax
0x18002b953  jz      short loc_18002B96E
0x18002b955  cmp     [rax], ebx
0x18002b957  jz      short loc_18002B95F
0x18002b959  mov     rax, [rax+8]
0x18002b95d  jmp     short loc_18002B950
0x18002b95f  add     rax, 10h
0x18002b963  add     rsp, 20h
0x18002b967  pop     r14
0x18002b969  pop     rdi
0x18002b96a  pop     rsi
0x18002b96b  pop     rbp
0x18002b96c  pop     rbx
0x18002b96d  retn
0x18002b96e  test    dil, dil
0x18002b971  jz      short loc_18002B9DB
0x18002b973  call    cs:__imp_GetProcessHeap
0x18002b979  mov     rsi, rax
0x18002b97c  xor     edx, edx; dwFlags
0x18002b97e  mov     r8d, 18h; dwBytes
0x18002b984  mov     rcx, rax; hHeap
0x18002b987  call    cs:__imp_HeapAlloc
0x18002b98d  mov     rdi, rax
0x18002b990  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002b997  test    rax, rax
0x18002b99a  jz      short loc_18002B9DF
0x18002b99c  mov     rdx, rdi
0x18002b99f  mov     rcx, rsi
0x18002b9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9a7  nop
0x18002b9a8  test    rdi, rdi
0x18002b9ab  jz      short loc_18002B9DB
0x18002b9ad  mov     [rdi], ebx
0x18002b9af  xor     eax, eax
0x18002b9b1  mov     [rdi+4], eax
0x18002b9b4  mov     [rdi+8], rax
0x18002b9b8  mov     [rdi+10h], rax
0x18002b9bc  mov     rax, [r14+rbp]
0x18002b9c0  mov     [rdi+8], rax
0x18002b9c4  lock cmpxchg [r14+rbp], rdi
0x18002b9ca  jnz     short loc_18002B9BC
0x18002b9cc  lea     rax, [rdi+10h]
0x18002b9d0  add     rsp, 20h
0x18002b9d4  pop     r14
0x18002b9d6  pop     rdi
0x18002b9d7  pop     rsi
0x18002b9d8  pop     rbp
0x18002b9d9  pop     rbx
0x18002b9da  retn
0x18002b9db  xor     eax, eax
0x18002b9dd  jmp     short loc_18002B963
0x18002b9df  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002b9e6  jnz     short loc_18002B9A8
0x18002b9e8  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002b9ef  call    cs:__imp_GetModuleHandleW
0x18002b9f5  test    rax, rax
0x18002b9f8  jz      short loc_18002BA0B
0x18002b9fa  mov     rcx, rax
0x18002b9fd  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18002ba02  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002ba09  jmp     short loc_18002BA12
0x18002ba0b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002ba12  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002ba19  test    rax, rax
0x18002ba1c  jz      short loc_18002B9A8
0x18002ba1e  jmp     loc_18002B99C
```
