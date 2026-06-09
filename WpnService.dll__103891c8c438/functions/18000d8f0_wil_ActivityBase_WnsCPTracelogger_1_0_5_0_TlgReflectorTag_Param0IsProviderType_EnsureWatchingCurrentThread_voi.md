# wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x18000d8f0`
- end: `0x18000da45`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `341`
- prototype: `void __fastcall(__int64)`
- caller_count: `35`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004104`
- `0x180004fc0`
- `0x180005ae0`
- `0x180006820`
- `0x180006b00`
- `0x180007f00`
- `0x180008210`
- `0x180008440`
- `0x18000a600`
- `0x18000b380`
- `0x18000cee0`
- `0x18000e2e0`
- `0x18000f810`
- `0x180016a28`
- `0x180016da4`
- `0x180017a58`
- `0x180018220`
- `0x1800191e0`
- `0x18001c280`
- `0x1800219b0`
- `0x180022380`
- `0x180022500`
- `0x180022d1c`
- `0x18002d6a4`
- `0x18002d73c`
- `0x18002e7e0`
- `0x18002e8c0`
- `0x18002e9e4`
- `0x18002ea84`
- `0x18002eb48`
- `0x180030584`
- `0x180033520`
- `0x180033618`
- `0x1800336fc`
- `0x1800337e0`

## callees

- `0x18000d8f0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000da35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000da35`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d9ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d9ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d9a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d9a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d992`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d992`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d919`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d975`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d919`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d975`

## string_xrefs

- `0x18000d9c3`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rsi
  unsigned __int64 CurrentThreadId; // rbx
  unsigned __int64 v4; // r15
  __int64 i; // rax
  _QWORD *v6; // rcx
  HANDLE ProcessHeap; // rbp
  char *v8; // r14
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  signed __int64 v11; // rax

  if ( !*(_DWORD *)(a1 + 312) )
  {
    v1 = a1 + 288;
    v2 = wil::details::g_pThreadFailureCallbacks;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      CurrentThreadId = GetCurrentThreadId();
      v4 = 8 * ((CurrentThreadId >> 2) % 0xA);
      for ( i = *(_QWORD *)(v4 + v2); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
        {
          v6 = (_QWORD *)(i + 16);
          goto LABEL_8;
        }
      }
      ProcessHeap = GetProcessHeap();
      v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
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
        ((void (__fastcall *)(HANDLE, char *))ProcAddress)(ProcessHeap, v8);
      }
      if ( v8 )
      {
        *(_DWORD *)v8 = CurrentThreadId;
        *((_DWORD *)v8 + 1) = 0;
        *((_QWORD *)v8 + 1) = 0;
        v6 = v8 + 16;
        *((_QWORD *)v8 + 2) = 0;
        do
        {
          v11 = *(_QWORD *)(v4 + v2);
          *((_QWORD *)v8 + 1) = v11;
        }
        while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + v2), (signed __int64)v8, v11) );
      }
      else
      {
        v6 = 0;
      }
LABEL_8:
      *(_QWORD *)v1 = v6;
      if ( v6 )
      {
        *(_QWORD *)(v1 + 16) = *v6;
        *v6 = v1;
        *(_DWORD *)(v1 + 24) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v1 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000d8f0  push    rbx
0x18000d8f2  push    rbp
0x18000d8f3  push    rsi
0x18000d8f4  push    rdi
0x18000d8f5  push    r14
0x18000d8f7  push    r15
0x18000d8f9  sub     rsp, 28h
0x18000d8fd  cmp     dword ptr [rcx+138h], 0
0x18000d904  jnz     short loc_18000D97E
0x18000d906  lea     rdi, [rcx+120h]
0x18000d90d  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d914  test    rsi, rsi
0x18000d917  jz      short loc_18000D98B
0x18000d919  call    cs:__imp_GetCurrentThreadId
0x18000d91f  mov     ebx, eax
0x18000d921  mov     r8d, eax
0x18000d924  shr     r8, 2
0x18000d928  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d932  mul     r8
0x18000d935  shr     rdx, 3
0x18000d939  lea     rcx, [rdx+rdx*4]
0x18000d93d  add     rcx, rcx
0x18000d940  sub     r8, rcx
0x18000d943  lea     r15, ds:0[r8*8]
0x18000d94b  mov     rax, [r15+rsi]
0x18000d94f  nop
0x18000d950  test    rax, rax
0x18000d953  jz      short loc_18000D992
0x18000d955  cmp     [rax], ebx
0x18000d957  jz      short loc_18000D95F
0x18000d959  mov     rax, [rax+8]
0x18000d95d  jmp     short loc_18000D950
0x18000d95f  lea     rcx, [rax+10h]
0x18000d963  mov     [rdi], rcx
0x18000d966  test    rcx, rcx
0x18000d969  jz      short loc_18000D97E
0x18000d96b  mov     rax, [rcx]
0x18000d96e  mov     [rdi+10h], rax
0x18000d972  mov     [rcx], rdi
0x18000d975  call    cs:__imp_GetCurrentThreadId
0x18000d97b  mov     [rdi+18h], eax
0x18000d97e  add     rsp, 28h
0x18000d982  pop     r15
0x18000d984  pop     r14
0x18000d986  pop     rdi
0x18000d987  pop     rsi
0x18000d988  pop     rbp
0x18000d989  pop     rbx
0x18000d98a  retn
0x18000d98b  xor     eax, eax
0x18000d98d  mov     [rdi], rax
0x18000d990  jmp     short loc_18000D97E
0x18000d992  call    cs:__imp_GetProcessHeap
0x18000d998  mov     rbp, rax
0x18000d99b  xor     edx, edx; dwFlags
0x18000d99d  mov     r8d, 18h; dwBytes
0x18000d9a3  mov     rcx, rax; hHeap
0x18000d9a6  call    cs:__imp_HeapAlloc
0x18000d9ac  mov     r14, rax
0x18000d9af  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d9b6  test    rax, rax
0x18000d9b9  jnz     short loc_18000D9E8
0x18000d9bb  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d9c1  jnz     short loc_18000D9F4
0x18000d9c3  lea     rcx, ModuleName; "ntdll.dll"
0x18000d9ca  call    cs:__imp_GetModuleHandleW
0x18000d9d0  test    rax, rax
0x18000d9d3  jnz     short loc_18000DA2B
0x18000d9d5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d9dc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d9e3  test    rax, rax
0x18000d9e6  jz      short loc_18000D9F4
0x18000d9e8  mov     rdx, r14
0x18000d9eb  mov     rcx, rbp
0x18000d9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9f3  nop
0x18000d9f4  xor     eax, eax
0x18000d9f6  test    r14, r14
0x18000d9f9  jz      short loc_18000DA23
0x18000d9fb  mov     [r14], ebx
0x18000d9fe  mov     [r14+4], eax
0x18000da02  mov     [r14+8], rax
0x18000da06  lea     rcx, [r14+10h]
0x18000da0a  mov     [rcx], rax
0x18000da0d  mov     rax, [r15+rsi]
0x18000da11  mov     [r14+8], rax
0x18000da15  lock cmpxchg [r15+rsi], r14
0x18000da1b  jz      loc_18000D963
0x18000da21  jmp     short loc_18000DA0D
0x18000da23  mov     rcx, rax
0x18000da26  jmp     loc_18000D963
0x18000da2b  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000da32  mov     rcx, rax; hModule
0x18000da35  call    cs:__imp_GetProcAddress
0x18000da3b  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000da42  jmp     short loc_18000D9DC
```
