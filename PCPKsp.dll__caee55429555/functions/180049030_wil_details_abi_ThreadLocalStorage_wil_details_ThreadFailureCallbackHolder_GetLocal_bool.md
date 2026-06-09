# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180049030`
- end: `0x180049178`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006abc0`

## callees

- `0x180049030`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049162`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049162`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800490ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800490ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800490a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800490a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800490c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800490c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049045`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049045`

## string_xrefs

- `0x1800490e6`: `ntdll.dll`

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
0x180049030  push    rbx
0x180049032  push    rbp
0x180049033  push    rsi
0x180049034  push    rdi
0x180049035  push    r14
0x180049037  sub     rsp, 20h
0x18004903b  movzx   edi, dl
0x18004903e  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180049045  call    cs:__imp_GetCurrentThreadId
0x18004904c  nop     dword ptr [rax+rax+00h]
0x180049051  mov     ebx, eax
0x180049053  mov     r8d, eax
0x180049056  shr     r8, 2
0x18004905a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180049064  mul     r8
0x180049067  shr     rdx, 3
0x18004906b  lea     rcx, [rdx+rdx*4]
0x18004906f  add     rcx, rcx
0x180049072  sub     r8, rcx
0x180049075  lea     r14, ds:0[r8*8]
0x18004907d  mov     rax, [r14+rbp]
0x180049081  test    rax, rax
0x180049084  jz      short loc_1800490A0
0x180049086  cmp     [rax], ebx
0x180049088  jz      short loc_180049090
0x18004908a  mov     rax, [rax+8]
0x18004908e  jmp     short loc_180049081
0x180049090  add     rax, 10h
0x180049094  add     rsp, 20h
0x180049098  pop     r14
0x18004909a  pop     rdi
0x18004909b  pop     rsi
0x18004909c  pop     rbp
0x18004909d  pop     rbx
0x18004909e  retn
0x1800490a0  test    dil, dil
0x1800490a3  jz      loc_180049151
0x1800490a9  call    cs:__imp_GetProcessHeap
0x1800490b0  nop     dword ptr [rax+rax+00h]
0x1800490b5  mov     rsi, rax
0x1800490b8  xor     edx, edx; dwFlags
0x1800490ba  mov     r8d, 18h; dwBytes
0x1800490c0  mov     rcx, rax; hHeap
0x1800490c3  call    cs:__imp_HeapAlloc
0x1800490ca  nop     dword ptr [rax+rax+00h]
0x1800490cf  mov     rdi, rax
0x1800490d2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800490d9  test    rax, rax
0x1800490dc  jnz     short loc_180049111
0x1800490de  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800490e4  jnz     short loc_18004911D
0x1800490e6  lea     rcx, ModuleName; "ntdll.dll"
0x1800490ed  call    cs:__imp_GetModuleHandleW
0x1800490f4  nop     dword ptr [rax+rax+00h]
0x1800490f9  test    rax, rax
0x1800490fc  jnz     short loc_180049158
0x1800490fe  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180049105  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004910c  test    rax, rax
0x18004910f  jz      short loc_18004911D
0x180049111  mov     rdx, rdi
0x180049114  mov     rcx, rsi
0x180049117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004911c  nop
0x18004911d  test    rdi, rdi
0x180049120  jz      short loc_180049151
0x180049122  mov     [rdi], ebx
0x180049124  xor     eax, eax
0x180049126  mov     [rdi+4], eax
0x180049129  mov     [rdi+8], rax
0x18004912d  mov     [rdi+10h], rax
0x180049131  mov     rax, [r14+rbp]
0x180049135  mov     [rdi+8], rax
0x180049139  lock cmpxchg [r14+rbp], rdi
0x18004913f  jnz     short loc_180049131
0x180049141  lea     rax, [rdi+10h]
0x180049145  add     rsp, 20h
0x180049149  pop     r14
0x18004914b  pop     rdi
0x18004914c  pop     rsi
0x18004914d  pop     rbp
0x18004914e  pop     rbx
0x18004914f  retn
0x180049151  xor     eax, eax
0x180049153  jmp     loc_180049094
0x180049158  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18004915f  mov     rcx, rax; hModule
0x180049162  call    cs:__imp_GetProcAddress
0x180049169  nop     dword ptr [rax+rax+00h]
0x18004916e  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180049175  jmp     short loc_180049105
```
