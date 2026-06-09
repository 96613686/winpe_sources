# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d5b0`
- end: `0x18000d6dd`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d480`

## callees

- `0x18000d5b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d6cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d6cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d65f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d65f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d63b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d63b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d627`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d627`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d5c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d5c5`

## string_xrefs

- `0x18000d658`: `ntdll.dll`

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
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  signed __int64 v12; // rax

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
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) != 0
      ? (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress)
      : (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, _DWORD *))ProcAddress)(ProcessHeap, v9);
  }
  if ( !v9 )
    return 0;
  *v9 = CurrentThreadId;
  v9[1] = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  do
  {
    v12 = *(_QWORD *)(v5 + v3);
    *((_QWORD *)v9 + 1) = v12;
  }
  while ( v12 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v3), (signed __int64)v9, v12) );
  return (char *)(v9 + 4);
}

```

## disassembly

```asm
0x18000d5b0  push    rbx
0x18000d5b2  push    rbp
0x18000d5b3  push    rsi
0x18000d5b4  push    rdi
0x18000d5b5  push    r14
0x18000d5b7  sub     rsp, 20h
0x18000d5bb  movzx   edi, dl
0x18000d5be  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d5c5  call    cs:__imp_GetCurrentThreadId
0x18000d5cb  mov     ebx, eax
0x18000d5cd  mov     r8d, eax
0x18000d5d0  shr     r8, 2
0x18000d5d4  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d5de  mul     r8
0x18000d5e1  shr     rdx, 3
0x18000d5e5  lea     rcx, [rdx+rdx*4]
0x18000d5e9  add     rcx, rcx
0x18000d5ec  sub     r8, rcx
0x18000d5ef  lea     r14, ds:0[r8*8]
0x18000d5f7  mov     rax, [r14+rbp]
0x18000d5fb  nop     dword ptr [rax+rax+00h]
0x18000d600  test    rax, rax
0x18000d603  jz      short loc_18000D61E
0x18000d605  cmp     [rax], ebx
0x18000d607  jz      short loc_18000D60F
0x18000d609  mov     rax, [rax+8]
0x18000d60d  jmp     short loc_18000D600
0x18000d60f  add     rax, 10h
0x18000d613  add     rsp, 20h
0x18000d617  pop     r14
0x18000d619  pop     rdi
0x18000d61a  pop     rsi
0x18000d61b  pop     rbp
0x18000d61c  pop     rbx
0x18000d61d  retn
0x18000d61e  test    dil, dil
0x18000d621  jz      loc_18000D6BC
0x18000d627  call    cs:__imp_GetProcessHeap
0x18000d62d  mov     rsi, rax
0x18000d630  xor     edx, edx; dwFlags
0x18000d632  mov     r8d, 18h; dwBytes
0x18000d638  mov     rcx, rax; hHeap
0x18000d63b  call    cs:__imp_HeapAlloc
0x18000d641  mov     rdi, rax
0x18000d644  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d64b  test    rax, rax
0x18000d64e  jnz     short loc_18000D67D
0x18000d650  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d656  jnz     short loc_18000D689
0x18000d658  lea     rcx, ModuleName; "ntdll.dll"
0x18000d65f  call    cs:__imp_GetModuleHandleW
0x18000d665  test    rax, rax
0x18000d668  jnz     short loc_18000D6C3
0x18000d66a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d671  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d678  test    rax, rax
0x18000d67b  jz      short loc_18000D689
0x18000d67d  mov     rdx, rdi
0x18000d680  mov     rcx, rsi
0x18000d683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d688  nop
0x18000d689  test    rdi, rdi
0x18000d68c  jz      short loc_18000D6BC
0x18000d68e  mov     [rdi], ebx
0x18000d690  xor     eax, eax
0x18000d692  mov     [rdi+4], eax
0x18000d695  mov     [rdi+8], rax
0x18000d699  mov     [rdi+10h], rax
0x18000d69d  mov     rax, [r14+rbp]
0x18000d6a1  mov     [rdi+8], rax
0x18000d6a5  lock cmpxchg [r14+rbp], rdi
0x18000d6ab  jnz     short loc_18000D69D
0x18000d6ad  lea     rax, [rdi+10h]
0x18000d6b1  add     rsp, 20h
0x18000d6b5  pop     r14
0x18000d6b7  pop     rdi
0x18000d6b8  pop     rsi
0x18000d6b9  pop     rbp
0x18000d6ba  pop     rbx
0x18000d6bb  retn
0x18000d6bc  xor     eax, eax
0x18000d6be  jmp     loc_18000D613
0x18000d6c3  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000d6ca  mov     rcx, rax; hModule
0x18000d6cd  call    cs:__imp_GetProcAddress
0x18000d6d3  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000d6da  jmp     short loc_18000D671
```
