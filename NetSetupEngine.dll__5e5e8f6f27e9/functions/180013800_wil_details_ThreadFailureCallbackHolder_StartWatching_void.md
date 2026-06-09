# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180013800`
- end: `0x18001398b`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `395`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010778`
- `0x180011e54`
- `0x1800137bc`
- `0x180013aa4`
- `0x180019d08`

## callees

- `0x180013800`
- `0x180058450`
- `0x1800810a2`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800138f5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800138f5`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800138e0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800138e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800138bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800138bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800138a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800138a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013836`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001388f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013836`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001388f`

## string_xrefs

- `0x1800138d9`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rdi
  unsigned __int64 CurrentThreadId; // rsi
  unsigned __int64 v4; // r14
  __int64 i; // rcx
  _QWORD *v6; // rcx
  HANDLE ProcessHeap; // rbp
  char *v8; // r15
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  signed __int64 v11; // rax
  const struct wil::FailureInfo *v12; // rdx
  _BYTE v13[216]; // [rsp+30h] [rbp-D8h] BYREF

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
        goto LABEL_7;
      }
    }
    ProcessHeap = GetProcessHeap();
    v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
    ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
    if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
      || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
      && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
        ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
        : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                    `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
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
LABEL_7:
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
0x180013800  push    rbx
0x180013802  push    rbp
0x180013803  push    rsi
0x180013804  push    rdi
0x180013805  push    r14
0x180013807  push    r15
0x180013809  sub     rsp, 0D8h
0x180013810  mov     [rsp+108h+var_E8], 0FFFFFFFFFFFFFFFEh
0x180013819  mov     rbx, rcx
0x18001381c  cmp     dword ptr [rcx+18h], 0
0x180013820  jnz     loc_180013962
0x180013826  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001382d  test    rdi, rdi
0x180013830  jz      loc_18001397F
0x180013836  call    cs:__imp_GetCurrentThreadId
0x18001383c  mov     esi, eax
0x18001383e  mov     r8d, eax
0x180013841  shr     r8, 2
0x180013845  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001384f  mul     r8
0x180013852  shr     rdx, 3
0x180013856  lea     rcx, [rdx+rdx*4]
0x18001385a  add     rcx, rcx
0x18001385d  sub     r8, rcx
0x180013860  lea     r14, ds:0[r8*8]
0x180013868  mov     rcx, [r14+rdi]
0x18001386c  test    rcx, rcx
0x18001386f  jz      short loc_1800138A8
0x180013871  cmp     [rcx], esi
0x180013873  jnz     loc_180013949
0x180013879  add     rcx, 10h
0x18001387d  mov     [rbx], rcx
0x180013880  test    rcx, rcx
0x180013883  jz      short loc_180013898
0x180013885  mov     rax, [rcx]
0x180013888  mov     [rbx+10h], rax
0x18001388c  mov     [rcx], rbx
0x18001388f  call    cs:__imp_GetCurrentThreadId
0x180013895  mov     [rbx+18h], eax
0x180013898  add     rsp, 0D8h
0x18001389f  pop     r15
0x1800138a1  pop     r14
0x1800138a3  pop     rdi
0x1800138a4  pop     rsi
0x1800138a5  pop     rbp
0x1800138a6  pop     rbx
0x1800138a7  retn
0x1800138a8  call    cs:__imp_GetProcessHeap
0x1800138ae  mov     rbp, rax
0x1800138b1  xor     edx, edx; dwFlags
0x1800138b3  mov     r8d, 18h; dwBytes
0x1800138b9  mov     rcx, rax; hHeap
0x1800138bc  call    cs:__imp_HeapAlloc
0x1800138c2  mov     r15, rax
0x1800138c5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800138cc  test    rax, rax
0x1800138cf  jnz     short loc_18001390E
0x1800138d1  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800138d7  jnz     short loc_18001391A
0x1800138d9  lea     rcx, ModuleName; "ntdll.dll"
0x1800138e0  call    cs:__imp_GetModuleHandleW
0x1800138e6  test    rax, rax
0x1800138e9  jz      short loc_180013959
0x1800138eb  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800138f2  mov     rcx, rax; hModule
0x1800138f5  call    cs:__imp_GetProcAddress
0x1800138fb  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180013902  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180013909  test    rax, rax
0x18001390c  jz      short loc_18001391A
0x18001390e  mov     rdx, r15
0x180013911  mov     rcx, rbp
0x180013914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013919  nop
0x18001391a  test    r15, r15
0x18001391d  jz      short loc_180013952
0x18001391f  mov     [r15], esi
0x180013922  xor     eax, eax
0x180013924  mov     [r15+4], eax
0x180013928  mov     [r15+8], rax
0x18001392c  lea     rcx, [r15+10h]
0x180013930  mov     [rcx], rax
0x180013933  mov     rax, [r14+rdi]
0x180013937  mov     [r15+8], rax
0x18001393b  lock cmpxchg [r14+rdi], r15
0x180013941  jz      loc_18001387D
0x180013947  jmp     short loc_180013933
0x180013949  mov     rcx, [rcx+8]
0x18001394d  jmp     loc_18001386C
0x180013952  xor     ecx, ecx
0x180013954  jmp     loc_18001387D
0x180013959  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180013960  jmp     short loc_180013902
0x180013962  xor     edx, edx; Val
0x180013964  mov     r8d, 98h; Size
0x18001396a  lea     rcx, [rsp+108h+var_D8]; void *
0x18001396f  call    memset_0
0x180013974  lea     rcx, [rsp+108h+var_D8]; this
0x180013979  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001397f  mov     qword ptr [rcx], 0
0x180013986  jmp     loc_180013898
```
