# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000877c`
- end: `0x18000881a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006128`
- `0x180006f30`
- `0x180007710`
- `0x180009634`
- `0x180023de4`
- `0x180025fd4`

## callees

- `0x18000877c`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800087c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800087c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800087da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800087da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800087a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800087a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008790`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008790`

## string_xrefs

- `0x1800087be`: `ntdll.dll`

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
0x18000877c  mov     [rsp+arg_0], rbx
0x180008781  mov     [rsp+arg_8], rsi
0x180008786  push    rdi
0x180008787  sub     rsp, 20h
0x18000878b  mov     rbx, rdx
0x18000878e  mov     edi, ecx
0x180008790  call    cs:__imp_GetProcessHeap
0x180008796  mov     rsi, rax
0x180008799  mov     r8, rbx; dwBytes
0x18000879c  mov     edx, edi; dwFlags
0x18000879e  mov     rcx, rax; hHeap
0x1800087a1  call    cs:__imp_HeapAlloc
0x1800087a7  mov     rbx, rax
0x1800087aa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800087b1  test    rax, rax
0x1800087b4  jnz     short loc_1800087FC
0x1800087b6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800087bc  jnz     short loc_180008807
0x1800087be  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800087c5  call    cs:__imp_GetModuleHandleW
0x1800087cb  test    rax, rax
0x1800087ce  jz      short loc_1800087E9
0x1800087d0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800087d7  mov     rcx, rax; hModule
0x1800087da  call    cs:__imp_GetProcAddress
0x1800087e0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800087e7  jmp     short loc_1800087F0
0x1800087e9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800087f0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800087f7  test    rax, rax
0x1800087fa  jz      short loc_180008807
0x1800087fc  mov     rdx, rbx
0x1800087ff  mov     rcx, rsi
0x180008802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008807  mov     rax, rbx
0x18000880a  mov     rbx, [rsp+28h+arg_0]
0x18000880f  mov     rsi, [rsp+28h+arg_8]
0x180008814  add     rsp, 20h
0x180008818  pop     rdi
0x180008819  retn
```
