# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c6b4`
- end: `0x18000c752`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(unsigned int flags, unsigned __int64 size)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800063ec`
- `0x18000b560`
- `0x18000c244`
- `0x18000c374`
- `0x18000d464`
- `0x18000d698`

## callees

- `0x18000c6b4`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c6fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c6fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c712`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c712`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c6c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c6c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c6d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c6d9`

## string_xrefs

- `0x18000c6f6`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD flags, SIZE_T size)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, flags, size);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (int (__fastcall *)(void *, void *))ProcAddress),
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
0x18000c6b4  mov     [rsp+arg_0], rbx
0x18000c6b9  mov     [rsp+arg_8], rsi
0x18000c6be  push    rdi
0x18000c6bf  sub     rsp, 20h
0x18000c6c3  mov     rbx, size
0x18000c6c6  mov     edi, flags
0x18000c6c8  call    cs:__imp_GetProcessHeap
0x18000c6ce  mov     r8, rbx; dwBytes
0x18000c6d1  mov     edx, edi; dwFlags
0x18000c6d3  mov     rcx, rax; hHeap
0x18000c6d6  mov     rsi, rax
0x18000c6d9  call    cs:__imp_HeapAlloc
0x18000c6df  mov     rbx, rax
0x18000c6e2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c6e9  test    rax, rax
0x18000c6ec  jnz     short loc_18000C734
0x18000c6ee  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c6f4  jnz     short loc_18000C73F
0x18000c6f6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000c6fd  call    cs:__imp_GetModuleHandleW
0x18000c703  test    rax, rax
0x18000c706  jz      short loc_18000C721
0x18000c708  lea     size, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000c70f  mov     rcx, rax; hModule
0x18000c712  call    cs:__imp_GetProcAddress
0x18000c718  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000c71f  jmp     short loc_18000C728
0x18000c721  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c728  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c72f  test    rax, rax
0x18000c732  jz      short loc_18000C73F
0x18000c734  mov     size, rbx
0x18000c737  mov     rcx, rsi
0x18000c73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c73f  mov     rsi, [rsp+28h+arg_8]
0x18000c744  mov     rax, rbx
0x18000c747  mov     rbx, [rsp+28h+arg_0]
0x18000c74c  add     rsp, 20h
0x18000c750  pop     rdi
0x18000c751  retn
```
