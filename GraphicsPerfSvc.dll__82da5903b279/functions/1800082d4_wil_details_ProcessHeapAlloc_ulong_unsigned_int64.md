# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800082d4`
- end: `0x180008372`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006f6c`
- `0x180007cf0`
- `0x180007e54`
- `0x180009260`
- `0x1800096e4`
- `0x18000a9cc`

## callees

- `0x1800082d4`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008332`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008332`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000831d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000831d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800082f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800082f9`

## string_xrefs

- `0x180008316`: `ntdll.dll`

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
0x1800082d4  mov     [rsp+arg_0], rbx
0x1800082d9  mov     [rsp+arg_8], rsi
0x1800082de  push    rdi
0x1800082df  sub     rsp, 20h
0x1800082e3  mov     rbx, rdx
0x1800082e6  mov     edi, ecx
0x1800082e8  call    cs:__imp_GetProcessHeap
0x1800082ee  mov     rsi, rax
0x1800082f1  mov     r8, rbx; dwBytes
0x1800082f4  mov     edx, edi; dwFlags
0x1800082f6  mov     rcx, rax; hHeap
0x1800082f9  call    cs:__imp_HeapAlloc
0x1800082ff  mov     rbx, rax
0x180008302  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008309  test    rax, rax
0x18000830c  jnz     short loc_180008354
0x18000830e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008314  jnz     short loc_18000835F
0x180008316  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000831d  call    cs:__imp_GetModuleHandleW
0x180008323  test    rax, rax
0x180008326  jz      short loc_180008341
0x180008328  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000832f  mov     rcx, rax; hModule
0x180008332  call    cs:__imp_GetProcAddress
0x180008338  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000833f  jmp     short loc_180008348
0x180008341  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008348  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000834f  test    rax, rax
0x180008352  jz      short loc_18000835F
0x180008354  mov     rdx, rbx
0x180008357  mov     rcx, rsi
0x18000835a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000835f  mov     rax, rbx
0x180008362  mov     rbx, [rsp+28h+arg_0]
0x180008367  mov     rsi, [rsp+28h+arg_8]
0x18000836c  add     rsp, 20h
0x180008370  pop     rdi
0x180008371  retn
```
