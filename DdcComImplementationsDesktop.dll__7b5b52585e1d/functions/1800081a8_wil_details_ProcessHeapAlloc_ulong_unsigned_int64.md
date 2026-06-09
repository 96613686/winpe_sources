# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800081a8`
- end: `0x180008246`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800060bc`
- `0x180006460`
- `0x180007040`
- `0x1800095c4`
- `0x18000ac4c`

## callees

- `0x1800081a8`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008206`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008206`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800081f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800081f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800081cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800081cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081bc`

## string_xrefs

- `0x1800081ea`: `ntdll.dll`

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
0x1800081a8  mov     [rsp+arg_0], rbx
0x1800081ad  mov     [rsp+arg_8], rsi
0x1800081b2  push    rdi
0x1800081b3  sub     rsp, 20h
0x1800081b7  mov     rbx, rdx
0x1800081ba  mov     edi, ecx
0x1800081bc  call    cs:__imp_GetProcessHeap
0x1800081c2  mov     rsi, rax
0x1800081c5  mov     r8, rbx; dwBytes
0x1800081c8  mov     edx, edi; dwFlags
0x1800081ca  mov     rcx, rax; hHeap
0x1800081cd  call    cs:__imp_HeapAlloc
0x1800081d3  mov     rbx, rax
0x1800081d6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800081dd  test    rax, rax
0x1800081e0  jnz     short loc_180008228
0x1800081e2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800081e8  jnz     short loc_180008233
0x1800081ea  lea     rcx, ModuleName; "ntdll.dll"
0x1800081f1  call    cs:__imp_GetModuleHandleW
0x1800081f7  test    rax, rax
0x1800081fa  jz      short loc_180008215
0x1800081fc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008203  mov     rcx, rax; hModule
0x180008206  call    cs:__imp_GetProcAddress
0x18000820c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008213  jmp     short loc_18000821C
0x180008215  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000821c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008223  test    rax, rax
0x180008226  jz      short loc_180008233
0x180008228  mov     rdx, rbx
0x18000822b  mov     rcx, rsi
0x18000822e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008233  mov     rax, rbx
0x180008236  mov     rbx, [rsp+28h+arg_0]
0x18000823b  mov     rsi, [rsp+28h+arg_8]
0x180008240  add     rsp, 20h
0x180008244  pop     rdi
0x180008245  retn
```
