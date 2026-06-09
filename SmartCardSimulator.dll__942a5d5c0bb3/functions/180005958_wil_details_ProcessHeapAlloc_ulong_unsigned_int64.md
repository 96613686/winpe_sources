# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005958`
- end: `0x1800059f6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800056e4`
- `0x180005ddc`
- `0x180006174`

## callees

- `0x180005958`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800059b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800059b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000596c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000596c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000597d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000597d`

## string_xrefs

- `0x18000599a`: `ntdll.dll`

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
0x180005958  mov     [rsp+arg_0], rbx
0x18000595d  mov     [rsp+arg_8], rsi
0x180005962  push    rdi
0x180005963  sub     rsp, 20h
0x180005967  mov     rbx, rdx
0x18000596a  mov     edi, ecx
0x18000596c  call    cs:__imp_GetProcessHeap
0x180005972  mov     rsi, rax
0x180005975  mov     r8, rbx; dwBytes
0x180005978  mov     edx, edi; dwFlags
0x18000597a  mov     rcx, rax; hHeap
0x18000597d  call    cs:__imp_HeapAlloc
0x180005983  mov     rbx, rax
0x180005986  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000598d  test    rax, rax
0x180005990  jnz     short loc_1800059D8
0x180005992  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005998  jnz     short loc_1800059E3
0x18000599a  lea     rcx, ModuleName; "ntdll.dll"
0x1800059a1  call    cs:__imp_GetModuleHandleW
0x1800059a7  test    rax, rax
0x1800059aa  jz      short loc_1800059C5
0x1800059ac  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800059b3  mov     rcx, rax; hModule
0x1800059b6  call    cs:__imp_GetProcAddress
0x1800059bc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800059c3  jmp     short loc_1800059CC
0x1800059c5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800059cc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800059d3  test    rax, rax
0x1800059d6  jz      short loc_1800059E3
0x1800059d8  mov     rdx, rbx
0x1800059db  mov     rcx, rsi
0x1800059de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e3  mov     rax, rbx
0x1800059e6  mov     rbx, [rsp+28h+arg_0]
0x1800059eb  mov     rsi, [rsp+28h+arg_8]
0x1800059f0  add     rsp, 20h
0x1800059f4  pop     rdi
0x1800059f5  retn
```
