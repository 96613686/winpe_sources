# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000cac0`
- end: `0x18000cb5e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a1f8`
- `0x18000a59c`
- `0x18000b720`
- `0x18000e444`
- `0x18000fcc0`

## callees

- `0x18000cac0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cb09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cb09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb1e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cae5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cae5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cad4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cad4`

## string_xrefs

- `0x18000cb02`: `ntdll.dll`

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
0x18000cac0  mov     [rsp+arg_0], rbx
0x18000cac5  mov     [rsp+arg_8], rsi
0x18000caca  push    rdi
0x18000cacb  sub     rsp, 20h
0x18000cacf  mov     rbx, rdx
0x18000cad2  mov     edi, ecx
0x18000cad4  call    cs:__imp_GetProcessHeap
0x18000cada  mov     rsi, rax
0x18000cadd  mov     r8, rbx; dwBytes
0x18000cae0  mov     edx, edi; dwFlags
0x18000cae2  mov     rcx, rax; hHeap
0x18000cae5  call    cs:__imp_HeapAlloc
0x18000caeb  mov     rbx, rax
0x18000caee  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000caf5  test    rax, rax
0x18000caf8  jnz     short loc_18000CB40
0x18000cafa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000cb00  jnz     short loc_18000CB4B
0x18000cb02  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000cb09  call    cs:__imp_GetModuleHandleW
0x18000cb0f  test    rax, rax
0x18000cb12  jz      short loc_18000CB2D
0x18000cb14  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000cb1b  mov     rcx, rax; hModule
0x18000cb1e  call    cs:__imp_GetProcAddress
0x18000cb24  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000cb2b  jmp     short loc_18000CB34
0x18000cb2d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000cb34  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000cb3b  test    rax, rax
0x18000cb3e  jz      short loc_18000CB4B
0x18000cb40  mov     rdx, rbx
0x18000cb43  mov     rcx, rsi
0x18000cb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb4b  mov     rax, rbx
0x18000cb4e  mov     rbx, [rsp+28h+arg_0]
0x18000cb53  mov     rsi, [rsp+28h+arg_8]
0x18000cb58  add     rsp, 20h
0x18000cb5c  pop     rdi
0x18000cb5d  retn
```
