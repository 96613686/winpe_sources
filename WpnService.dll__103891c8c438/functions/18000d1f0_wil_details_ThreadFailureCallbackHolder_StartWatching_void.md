# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000d1f0`
- end: `0x18000d366`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `374`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003590`
- `0x18000b720`
- `0x18000c990`
- `0x18000d36c`
- `0x18000d440`
- `0x1800238ac`

## callees

- `0x18000d1f0`
- `0x1800118ec`
- `0x180026cd0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d353`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d353`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d2cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d2cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d2a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d2a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d295`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d219`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d275`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d219`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d275`

## string_xrefs

- `0x18000d2c6`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // r14
  unsigned __int64 CurrentThreadId; // rbx
  unsigned __int64 v4; // r15
  __int64 i; // rax
  _QWORD *v6; // rcx
  HANDLE ProcessHeap; // rbp
  char *v8; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  signed __int64 v11; // rax
  const struct wil::FailureInfo *v12; // rdx
  _BYTE v13[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v12);
  }
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
    *(_QWORD *)this = v6;
    if ( v6 )
    {
      *((_QWORD *)this + 2) = *v6;
      *v6 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000d1f0  push    rbx
0x18000d1f2  push    rbp
0x18000d1f3  push    rsi
0x18000d1f4  push    rdi
0x18000d1f5  push    r14
0x18000d1f7  push    r15
0x18000d1f9  sub     rsp, 0C8h
0x18000d200  mov     rdi, rcx
0x18000d203  cmp     dword ptr [rcx+18h], 0
0x18000d207  jnz     loc_18000D32C
0x18000d20d  mov     r14, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d214  test    r14, r14
0x18000d217  jz      short loc_18000D28E
0x18000d219  call    cs:__imp_GetCurrentThreadId
0x18000d21f  mov     ebx, eax
0x18000d221  mov     r8d, eax
0x18000d224  shr     r8, 2
0x18000d228  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d232  mul     r8
0x18000d235  shr     rdx, 3
0x18000d239  lea     rcx, [rdx+rdx*4]
0x18000d23d  add     rcx, rcx
0x18000d240  sub     r8, rcx
0x18000d243  lea     r15, ds:0[r8*8]
0x18000d24b  mov     rax, [r15+r14]
0x18000d24f  nop
0x18000d250  test    rax, rax
0x18000d253  jz      short loc_18000D295
0x18000d255  cmp     [rax], ebx
0x18000d257  jz      short loc_18000D25F
0x18000d259  mov     rax, [rax+8]
0x18000d25d  jmp     short loc_18000D250
0x18000d25f  lea     rcx, [rax+10h]
0x18000d263  mov     [rdi], rcx
0x18000d266  test    rcx, rcx
0x18000d269  jz      short loc_18000D27E
0x18000d26b  mov     rax, [rcx]
0x18000d26e  mov     [rdi+10h], rax
0x18000d272  mov     [rcx], rdi
0x18000d275  call    cs:__imp_GetCurrentThreadId
0x18000d27b  mov     [rdi+18h], eax
0x18000d27e  add     rsp, 0C8h
0x18000d285  pop     r15
0x18000d287  pop     r14
0x18000d289  pop     rdi
0x18000d28a  pop     rsi
0x18000d28b  pop     rbp
0x18000d28c  pop     rbx
0x18000d28d  retn
0x18000d28e  xor     eax, eax
0x18000d290  mov     [rcx], rax
0x18000d293  jmp     short loc_18000D27E
0x18000d295  call    cs:__imp_GetProcessHeap
0x18000d29b  mov     rbp, rax
0x18000d29e  xor     edx, edx; dwFlags
0x18000d2a0  mov     r8d, 18h; dwBytes
0x18000d2a6  mov     rcx, rax; hHeap
0x18000d2a9  call    cs:__imp_HeapAlloc
0x18000d2af  mov     rsi, rax
0x18000d2b2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d2b9  test    rax, rax
0x18000d2bc  jnz     short loc_18000D2EB
0x18000d2be  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d2c4  jnz     short loc_18000D2F7
0x18000d2c6  lea     rcx, ModuleName; "ntdll.dll"
0x18000d2cd  call    cs:__imp_GetModuleHandleW
0x18000d2d3  test    rax, rax
0x18000d2d6  jnz     short loc_18000D349
0x18000d2d8  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d2df  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d2e6  test    rax, rax
0x18000d2e9  jz      short loc_18000D2F7
0x18000d2eb  mov     rdx, rsi
0x18000d2ee  mov     rcx, rbp
0x18000d2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2f6  nop
0x18000d2f7  xor     eax, eax
0x18000d2f9  test    rsi, rsi
0x18000d2fc  jz      short loc_18000D324
0x18000d2fe  mov     [rsi], ebx
0x18000d300  mov     [rsi+4], eax
0x18000d303  mov     [rsi+8], rax
0x18000d307  lea     rcx, [rsi+10h]
0x18000d30b  mov     [rcx], rax
0x18000d30e  mov     rax, [r15+r14]
0x18000d312  mov     [rsi+8], rax
0x18000d316  lock cmpxchg [r15+r14], rsi
0x18000d31c  jz      loc_18000D263
0x18000d322  jmp     short loc_18000D30E
0x18000d324  mov     rcx, rax
0x18000d327  jmp     loc_18000D263
0x18000d32c  xor     edx, edx; Val
0x18000d32e  mov     r8d, 98h; Size
0x18000d334  lea     rcx, [rsp+0F8h+var_D8]; void *
0x18000d339  call    memset_0
0x18000d33e  lea     rcx, [rsp+0F8h+var_D8]; this
0x18000d343  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d349  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000d350  mov     rcx, rax; hModule
0x18000d353  call    cs:__imp_GetProcAddress
0x18000d359  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000d360  jmp     loc_18000D2DF
```
