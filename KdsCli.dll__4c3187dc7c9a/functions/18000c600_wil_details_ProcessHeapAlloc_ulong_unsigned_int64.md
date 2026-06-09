# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c600`
- end: `0x18000c69e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d284`
- `0x18001223c`
- `0x1800125e0`
- `0x1800131c0`
- `0x180015728`

## callees

- `0x18000c600`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c649`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c649`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c65e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c65e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c625`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c625`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c614`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c614`

## string_xrefs

- `0x18000c642`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
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
    ((void (__fastcall *)(HANDLE, LPVOID))ProcAddress)(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18000c600  mov     [rsp+arg_0], rbx
0x18000c605  mov     [rsp+arg_8], rsi
0x18000c60a  push    rdi
0x18000c60b  sub     rsp, 20h
0x18000c60f  mov     rbx, rdx
0x18000c612  mov     edi, ecx
0x18000c614  call    cs:__imp_GetProcessHeap
0x18000c61a  mov     r8, rbx; dwBytes
0x18000c61d  mov     edx, edi; dwFlags
0x18000c61f  mov     rcx, rax; hHeap
0x18000c622  mov     rsi, rax
0x18000c625  call    cs:__imp_HeapAlloc
0x18000c62b  mov     rbx, rax
0x18000c62e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c635  test    rax, rax
0x18000c638  jnz     short loc_18000C680
0x18000c63a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c640  jnz     short loc_18000C68B
0x18000c642  lea     rcx, ModuleName; "ntdll.dll"
0x18000c649  call    cs:__imp_GetModuleHandleW
0x18000c64f  test    rax, rax
0x18000c652  jz      short loc_18000C66D
0x18000c654  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000c65b  mov     rcx, rax; hModule
0x18000c65e  call    cs:__imp_GetProcAddress
0x18000c664  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000c66b  jmp     short loc_18000C674
0x18000c66d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c674  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c67b  test    rax, rax
0x18000c67e  jz      short loc_18000C68B
0x18000c680  mov     rdx, rbx
0x18000c683  mov     rcx, rsi
0x18000c686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c68b  mov     rsi, [rsp+28h+arg_8]
0x18000c690  mov     rax, rbx
0x18000c693  mov     rbx, [rsp+28h+arg_0]
0x18000c698  add     rsp, 20h
0x18000c69c  pop     rdi
0x18000c69d  retn
```
