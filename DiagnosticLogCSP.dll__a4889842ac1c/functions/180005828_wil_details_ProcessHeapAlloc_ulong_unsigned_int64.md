# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005828`
- end: `0x1800058c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800040e8`
- `0x1800047d0`
- `0x180005b90`

## callees

- `0x180005828`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005871`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005871`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005886`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005886`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000584d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000584d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000583c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000583c`

## string_xrefs

- `0x18000586a`: `ntdll.dll`

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
0x180005828  mov     [rsp+arg_0], rbx
0x18000582d  mov     [rsp+arg_8], rsi
0x180005832  push    rdi
0x180005833  sub     rsp, 20h
0x180005837  mov     rbx, rdx
0x18000583a  mov     edi, ecx
0x18000583c  call    cs:__imp_GetProcessHeap
0x180005842  mov     rsi, rax
0x180005845  mov     r8, rbx; dwBytes
0x180005848  mov     edx, edi; dwFlags
0x18000584a  mov     rcx, rax; hHeap
0x18000584d  call    cs:__imp_HeapAlloc
0x180005853  mov     rbx, rax
0x180005856  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000585d  test    rax, rax
0x180005860  jnz     short loc_1800058A8
0x180005862  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005868  jnz     short loc_1800058B3
0x18000586a  lea     rcx, ModuleName; "ntdll.dll"
0x180005871  call    cs:__imp_GetModuleHandleW
0x180005877  test    rax, rax
0x18000587a  jz      short loc_180005895
0x18000587c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005883  mov     rcx, rax; hModule
0x180005886  call    cs:__imp_GetProcAddress
0x18000588c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005893  jmp     short loc_18000589C
0x180005895  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000589c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800058a3  test    rax, rax
0x1800058a6  jz      short loc_1800058B3
0x1800058a8  mov     rdx, rbx
0x1800058ab  mov     rcx, rsi
0x1800058ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b3  mov     rax, rbx
0x1800058b6  mov     rbx, [rsp+28h+arg_0]
0x1800058bb  mov     rsi, [rsp+28h+arg_8]
0x1800058c0  add     rsp, 20h
0x1800058c4  pop     rdi
0x1800058c5  retn
```
