# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180049520`
- end: `0x1800496c4`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `420`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001edb0`

## callees

- `0x180049520`
- `0x180058464`
- `0x18007704c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800496a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800496a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180049620`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180049620`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800495dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800495dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800495f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800495f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004954d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800495b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004954d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800495b5`

## string_xrefs

- `0x180049619`: `ntdll.dll`

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
0x180049520  push    rbx
0x180049522  push    rbp
0x180049523  push    rsi
0x180049524  push    rdi
0x180049525  push    r14
0x180049527  push    r15
0x180049529  sub     rsp, 0C8h
0x180049530  mov     rdi, rcx
0x180049533  cmp     dword ptr [rcx+18h], 0
0x180049537  jnz     loc_18004967D
0x18004953d  mov     r14, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180049544  test    r14, r14
0x180049547  jz      loc_1800495D5
0x18004954d  call    cs:__imp_GetCurrentThreadId
0x180049554  nop     dword ptr [rax+rax+00h]
0x180049559  mov     ebx, eax
0x18004955b  mov     r8d, eax
0x18004955e  shr     r8, 2
0x180049562  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18004956c  mul     r8
0x18004956f  shr     rdx, 3
0x180049573  lea     rcx, [rdx+rdx*4]
0x180049577  add     rcx, rcx
0x18004957a  sub     r8, rcx
0x18004957d  lea     r15, ds:0[r8*8]
0x180049585  mov     rax, [r15+r14]
0x180049589  nop     dword ptr [rax+00000000h]
0x180049590  test    rax, rax
0x180049593  jz      short loc_1800495DC
0x180049595  cmp     [rax], ebx
0x180049597  jz      short loc_18004959F
0x180049599  mov     rax, [rax+8]
0x18004959d  jmp     short loc_180049590
0x18004959f  lea     rcx, [rax+10h]
0x1800495a3  mov     [rdi], rcx
0x1800495a6  test    rcx, rcx
0x1800495a9  jz      short loc_1800495C4
0x1800495ab  mov     rax, [rcx]
0x1800495ae  mov     [rdi+10h], rax
0x1800495b2  mov     [rcx], rdi
0x1800495b5  call    cs:__imp_GetCurrentThreadId
0x1800495bc  nop     dword ptr [rax+rax+00h]
0x1800495c1  mov     [rdi+18h], eax
0x1800495c4  add     rsp, 0C8h
0x1800495cb  pop     r15
0x1800495cd  pop     r14
0x1800495cf  pop     rdi
0x1800495d0  pop     rsi
0x1800495d1  pop     rbp
0x1800495d2  pop     rbx
0x1800495d3  retn
0x1800495d5  xor     eax, eax
0x1800495d7  mov     [rcx], rax
0x1800495da  jmp     short loc_1800495C4
0x1800495dc  call    cs:__imp_GetProcessHeap
0x1800495e3  nop     dword ptr [rax+rax+00h]
0x1800495e8  mov     rbp, rax
0x1800495eb  xor     edx, edx; dwFlags
0x1800495ed  mov     r8d, 18h; dwBytes
0x1800495f3  mov     rcx, rax; hHeap
0x1800495f6  call    cs:__imp_HeapAlloc
0x1800495fd  nop     dword ptr [rax+rax+00h]
0x180049602  mov     rsi, rax
0x180049605  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004960c  test    rax, rax
0x18004960f  jnz     short loc_180049644
0x180049611  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180049617  jnz     short loc_180049650
0x180049619  lea     rcx, ModuleName; "ntdll.dll"
0x180049620  call    cs:__imp_GetModuleHandleW
0x180049627  nop     dword ptr [rax+rax+00h]
0x18004962c  test    rax, rax
0x18004962f  jnz     short loc_18004969A
0x180049631  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180049638  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004963f  test    rax, rax
0x180049642  jz      short loc_180049650
0x180049644  mov     rdx, rsi
0x180049647  mov     rcx, rbp
0x18004964a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004964f  nop
0x180049650  xor     eax, eax
0x180049652  test    rsi, rsi
0x180049655  jz      short loc_1800496BC
0x180049657  mov     [rsi], ebx
0x180049659  mov     [rsi+4], eax
0x18004965c  mov     [rsi+8], rax
0x180049660  lea     rcx, [rsi+10h]
0x180049664  mov     [rcx], rax
0x180049667  mov     rax, [r15+r14]
0x18004966b  mov     [rsi+8], rax
0x18004966f  lock cmpxchg [r15+r14], rsi
0x180049675  jz      loc_1800495A3
0x18004967b  jmp     short loc_180049667
0x18004967d  xor     edx, edx; Val
0x18004967f  mov     r8d, 98h; Size
0x180049685  lea     rcx, [rsp+0F8h+var_D8]; void *
0x18004968a  call    memset_0
0x18004968f  lea     rcx, [rsp+0F8h+var_D8]; this
0x180049694  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18004969a  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800496a1  mov     rcx, rax; hModule
0x1800496a4  call    cs:__imp_GetProcAddress
0x1800496ab  nop     dword ptr [rax+rax+00h]
0x1800496b0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800496b7  jmp     loc_180049638
0x1800496bc  mov     rcx, rax
0x1800496bf  jmp     loc_1800495A3
```
