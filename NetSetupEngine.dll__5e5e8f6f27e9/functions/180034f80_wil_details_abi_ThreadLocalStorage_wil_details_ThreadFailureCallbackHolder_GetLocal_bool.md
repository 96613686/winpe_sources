# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180034f80`
- end: `0x1800350ba`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800662cc`

## callees

- `0x180034f80`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180035046`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180035046`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180035031`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180035031`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003500d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003500d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034ff9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034ff9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034f9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034f9e`

## string_xrefs

- `0x18003502a`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v3; // rdi
  unsigned __int64 CurrentThreadId; // rbx
  unsigned __int64 v5; // rsi
  __int64 i; // rax
  HANDLE ProcessHeap; // rbp
  _DWORD *v9; // r14
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
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
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
0x180034f80  push    rbx
0x180034f82  push    rbp
0x180034f83  push    rsi
0x180034f84  push    rdi
0x180034f85  push    r14
0x180034f87  sub     rsp, 30h
0x180034f8b  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180034f94  movzx   ebp, dl
0x180034f97  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180034f9e  call    cs:__imp_GetCurrentThreadId
0x180034fa4  mov     ebx, eax
0x180034fa6  mov     r8d, eax
0x180034fa9  shr     r8, 2
0x180034fad  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180034fb7  mul     r8
0x180034fba  shr     rdx, 3
0x180034fbe  lea     rcx, [rdx+rdx*4]
0x180034fc2  add     rcx, rcx
0x180034fc5  sub     r8, rcx
0x180034fc8  lea     rsi, ds:0[r8*8]
0x180034fd0  mov     rax, [rsi+rdi]
0x180034fd4  test    rax, rax
0x180034fd7  jz      short loc_180034FF0
0x180034fd9  cmp     [rax], ebx
0x180034fdb  jnz     loc_1800350A7
0x180034fe1  add     rax, 10h
0x180034fe5  add     rsp, 30h
0x180034fe9  pop     r14
0x180034feb  pop     rdi
0x180034fec  pop     rsi
0x180034fed  pop     rbp
0x180034fee  pop     rbx
0x180034fef  retn
0x180034ff0  test    bpl, bpl
0x180034ff3  jz      loc_1800350A0
0x180034ff9  call    cs:__imp_GetProcessHeap
0x180034fff  mov     rbp, rax
0x180035002  xor     edx, edx; dwFlags
0x180035004  mov     r8d, 18h; dwBytes
0x18003500a  mov     rcx, rax; hHeap
0x18003500d  call    cs:__imp_HeapAlloc
0x180035013  mov     r14, rax
0x180035016  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003501d  test    rax, rax
0x180035020  jnz     short loc_18003505F
0x180035022  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180035028  jnz     short loc_18003506B
0x18003502a  lea     rcx, ModuleName; "ntdll.dll"
0x180035031  call    cs:__imp_GetModuleHandleW
0x180035037  test    rax, rax
0x18003503a  jz      short loc_1800350B0
0x18003503c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180035043  mov     rcx, rax; hModule
0x180035046  call    cs:__imp_GetProcAddress
0x18003504c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180035053  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003505a  test    rax, rax
0x18003505d  jz      short loc_18003506B
0x18003505f  mov     rdx, r14
0x180035062  mov     rcx, rbp
0x180035065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003506a  nop
0x18003506b  test    r14, r14
0x18003506e  jz      short loc_1800350A0
0x180035070  mov     [r14], ebx
0x180035073  xor     eax, eax
0x180035075  mov     [r14+4], eax
0x180035079  mov     [r14+8], rax
0x18003507d  mov     [r14+10h], rax
0x180035081  mov     rax, [rsi+rdi]
0x180035085  mov     [r14+8], rax
0x180035089  lock cmpxchg [rsi+rdi], r14
0x18003508f  jnz     short loc_180035081
0x180035091  lea     rax, [r14+10h]
0x180035095  add     rsp, 30h
0x180035099  pop     r14
0x18003509b  pop     rdi
0x18003509c  pop     rsi
0x18003509d  pop     rbp
0x18003509e  pop     rbx
0x18003509f  retn
0x1800350a0  xor     eax, eax
0x1800350a2  jmp     loc_180034FE5
0x1800350a7  mov     rax, [rax+8]
0x1800350ab  jmp     loc_180034FD4
0x1800350b0  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800350b7  jmp     short loc_180035053
```
