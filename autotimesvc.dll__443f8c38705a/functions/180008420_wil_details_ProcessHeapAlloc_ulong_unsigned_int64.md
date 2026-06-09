# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008420`
- end: `0x1800084be`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007e70`
- `0x180009240`
- `0x1800095d8`

## callees

- `0x180008420`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008469`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008469`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000847e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000847e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008445`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008434`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008434`

## string_xrefs

- `0x180008462`: `ntdll.dll`

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
0x180008420  mov     [rsp+arg_0], rbx
0x180008425  mov     [rsp+arg_8], rsi
0x18000842a  push    rdi
0x18000842b  sub     rsp, 20h
0x18000842f  mov     rbx, rdx
0x180008432  mov     edi, ecx
0x180008434  call    cs:__imp_GetProcessHeap
0x18000843a  mov     rsi, rax
0x18000843d  mov     r8, rbx; dwBytes
0x180008440  mov     edx, edi; dwFlags
0x180008442  mov     rcx, rax; hHeap
0x180008445  call    cs:__imp_HeapAlloc
0x18000844b  mov     rbx, rax
0x18000844e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008455  test    rax, rax
0x180008458  jnz     short loc_1800084A0
0x18000845a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008460  jnz     short loc_1800084AB
0x180008462  lea     rcx, ModuleName; "ntdll.dll"
0x180008469  call    cs:__imp_GetModuleHandleW
0x18000846f  test    rax, rax
0x180008472  jz      short loc_18000848D
0x180008474  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000847b  mov     rcx, rax; hModule
0x18000847e  call    cs:__imp_GetProcAddress
0x180008484  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000848b  jmp     short loc_180008494
0x18000848d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008494  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000849b  test    rax, rax
0x18000849e  jz      short loc_1800084AB
0x1800084a0  mov     rdx, rbx
0x1800084a3  mov     rcx, rsi
0x1800084a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ab  mov     rax, rbx
0x1800084ae  mov     rbx, [rsp+28h+arg_0]
0x1800084b3  mov     rsi, [rsp+28h+arg_8]
0x1800084b8  add     rsp, 20h
0x1800084bc  pop     rdi
0x1800084bd  retn
```
