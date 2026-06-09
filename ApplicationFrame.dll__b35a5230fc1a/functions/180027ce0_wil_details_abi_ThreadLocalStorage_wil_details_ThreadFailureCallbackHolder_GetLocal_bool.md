# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180027ce0`
- end: `0x180027e02`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `290`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027c60`
- `0x180039cc0`

## callees

- `0x180027ce0`
- `0x1800472ac`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027dca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027d66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027d66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027d52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027d52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027cf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027cf5`

## string_xrefs

- `0x180027dc3`: `ntdll.dll`

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
0x180027ce0  push    rbx
0x180027ce2  push    rbp
0x180027ce3  push    rsi
0x180027ce4  push    rdi
0x180027ce5  push    r14
0x180027ce7  sub     rsp, 20h
0x180027ceb  movzx   edi, dl
0x180027cee  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180027cf5  call    cs:__imp_GetCurrentThreadId
0x180027cfb  mov     ebx, eax
0x180027cfd  mov     r8d, eax
0x180027d00  shr     r8, 2
0x180027d04  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180027d0e  mul     r8
0x180027d11  shr     rdx, 3
0x180027d15  lea     rcx, [rdx+rdx*4]
0x180027d19  add     rcx, rcx
0x180027d1c  sub     r8, rcx
0x180027d1f  lea     r14, ds:0[r8*8]
0x180027d27  mov     rax, [r14+rbp]
0x180027d2b  test    rax, rax
0x180027d2e  jz      short loc_180027D49
0x180027d30  cmp     [rax], ebx
0x180027d32  jz      short loc_180027D3A
0x180027d34  mov     rax, [rax+8]
0x180027d38  jmp     short loc_180027D2B
0x180027d3a  add     rax, 10h
0x180027d3e  add     rsp, 20h
0x180027d42  pop     r14
0x180027d44  pop     rdi
0x180027d45  pop     rsi
0x180027d46  pop     rbp
0x180027d47  pop     rbx
0x180027d48  retn
0x180027d49  test    dil, dil
0x180027d4c  jz      loc_180027DFB
0x180027d52  call    cs:__imp_GetProcessHeap
0x180027d58  mov     rsi, rax
0x180027d5b  xor     edx, edx; dwFlags
0x180027d5d  mov     r8d, 18h; dwBytes
0x180027d63  mov     rcx, rax; hHeap
0x180027d66  call    cs:__imp_HeapAlloc
0x180027d6c  mov     rdi, rax
0x180027d6f  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180027d76  test    rax, rax
0x180027d79  jz      short loc_180027DBA
0x180027d7b  mov     rdx, rdi
0x180027d7e  mov     rcx, rsi
0x180027d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d86  nop
0x180027d87  test    rdi, rdi
0x180027d8a  jz      short loc_180027DFB
0x180027d8c  mov     [rdi], ebx
0x180027d8e  xor     eax, eax
0x180027d90  mov     [rdi+4], eax
0x180027d93  mov     [rdi+8], rax
0x180027d97  mov     [rdi+10h], rax
0x180027d9b  mov     rax, [r14+rbp]
0x180027d9f  mov     [rdi+8], rax
0x180027da3  lock cmpxchg [r14+rbp], rdi
0x180027da9  jnz     short loc_180027D9B
0x180027dab  lea     rax, [rdi+10h]
0x180027daf  add     rsp, 20h
0x180027db3  pop     r14
0x180027db5  pop     rdi
0x180027db6  pop     rsi
0x180027db7  pop     rbp
0x180027db8  pop     rbx
0x180027db9  retn
0x180027dba  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180027dc1  jnz     short loc_180027D87
0x180027dc3  lea     rcx, ModuleName; "ntdll.dll"
0x180027dca  call    cs:__imp_GetModuleHandleW
0x180027dd0  test    rax, rax
0x180027dd3  jz      short loc_180027DE6
0x180027dd5  mov     rcx, rax
0x180027dd8  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180027ddd  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180027de4  jmp     short loc_180027DED
0x180027de6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180027ded  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180027df4  test    rax, rax
0x180027df7  jz      short loc_180027D87
0x180027df9  jmp     short loc_180027D7B
0x180027dfb  xor     eax, eax
0x180027dfd  jmp     loc_180027D3E
```
