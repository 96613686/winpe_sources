# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005518`
- end: `0x1800055b6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003dd8`
- `0x1800044c0`
- `0x180005a10`

## callees

- `0x180005518`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005561`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005561`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005576`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005576`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000552c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000552c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000553d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000553d`

## string_xrefs

- `0x18000555a`: `ntdll.dll`

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
0x180005518  mov     [rsp+arg_0], rbx
0x18000551d  mov     [rsp+arg_8], rsi
0x180005522  push    rdi
0x180005523  sub     rsp, 20h
0x180005527  mov     rbx, rdx
0x18000552a  mov     edi, ecx
0x18000552c  call    cs:__imp_GetProcessHeap
0x180005532  mov     rsi, rax
0x180005535  mov     r8, rbx; dwBytes
0x180005538  mov     edx, edi; dwFlags
0x18000553a  mov     rcx, rax; hHeap
0x18000553d  call    cs:__imp_HeapAlloc
0x180005543  mov     rbx, rax
0x180005546  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000554d  test    rax, rax
0x180005550  jnz     short loc_180005598
0x180005552  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005558  jnz     short loc_1800055A3
0x18000555a  lea     rcx, aNtdllDll; "ntdll.dll"
0x180005561  call    cs:__imp_GetModuleHandleW
0x180005567  test    rax, rax
0x18000556a  jz      short loc_180005585
0x18000556c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005573  mov     rcx, rax; hModule
0x180005576  call    cs:__imp_GetProcAddress
0x18000557c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005583  jmp     short loc_18000558C
0x180005585  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000558c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005593  test    rax, rax
0x180005596  jz      short loc_1800055A3
0x180005598  mov     rdx, rbx
0x18000559b  mov     rcx, rsi
0x18000559e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a3  mov     rax, rbx
0x1800055a6  mov     rbx, [rsp+28h+arg_0]
0x1800055ab  mov     rsi, [rsp+28h+arg_8]
0x1800055b0  add     rsp, 20h
0x1800055b4  pop     rdi
0x1800055b5  retn
```
