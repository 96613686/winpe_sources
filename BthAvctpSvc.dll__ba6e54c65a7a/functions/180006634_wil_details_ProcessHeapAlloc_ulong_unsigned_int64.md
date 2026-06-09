# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006634`
- end: `0x1800066d2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000604c`
- `0x1800061b0`
- `0x1800075c0`
- `0x180007a50`
- `0x180008c0c`

## callees

- `0x180006634`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000667d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000667d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006692`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006692`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006648`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006648`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006659`

## string_xrefs

- `0x180006676`: `ntdll.dll`

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
0x180006634  mov     [rsp+arg_0], rbx
0x180006639  mov     [rsp+arg_8], rsi
0x18000663e  push    rdi
0x18000663f  sub     rsp, 20h
0x180006643  mov     rbx, rdx
0x180006646  mov     edi, ecx
0x180006648  call    cs:__imp_GetProcessHeap
0x18000664e  mov     rsi, rax
0x180006651  mov     r8, rbx; dwBytes
0x180006654  mov     edx, edi; dwFlags
0x180006656  mov     rcx, rax; hHeap
0x180006659  call    cs:__imp_HeapAlloc
0x18000665f  mov     rbx, rax
0x180006662  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006669  test    rax, rax
0x18000666c  jnz     short loc_1800066B4
0x18000666e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006674  jnz     short loc_1800066BF
0x180006676  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000667d  call    cs:__imp_GetModuleHandleW
0x180006683  test    rax, rax
0x180006686  jz      short loc_1800066A1
0x180006688  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000668f  mov     rcx, rax; hModule
0x180006692  call    cs:__imp_GetProcAddress
0x180006698  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000669f  jmp     short loc_1800066A8
0x1800066a1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800066a8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800066af  test    rax, rax
0x1800066b2  jz      short loc_1800066BF
0x1800066b4  mov     rdx, rbx
0x1800066b7  mov     rcx, rsi
0x1800066ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066bf  mov     rax, rbx
0x1800066c2  mov     rbx, [rsp+28h+arg_0]
0x1800066c7  mov     rsi, [rsp+28h+arg_8]
0x1800066cc  add     rsp, 20h
0x1800066d0  pop     rdi
0x1800066d1  retn
```
