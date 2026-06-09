# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006538`
- end: `0x1800065d6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800062c4`
- `0x1800069bc`
- `0x180006d54`

## callees

- `0x180006538`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006581`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006581`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006596`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006596`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000655d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000655d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000654c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000654c`

## string_xrefs

- `0x18000657a`: `ntdll.dll`

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
0x180006538  mov     [rsp+arg_0], rbx
0x18000653d  mov     [rsp+arg_8], rsi
0x180006542  push    rdi
0x180006543  sub     rsp, 20h
0x180006547  mov     rbx, rdx
0x18000654a  mov     edi, ecx
0x18000654c  call    cs:__imp_GetProcessHeap
0x180006552  mov     rsi, rax
0x180006555  mov     r8, rbx; dwBytes
0x180006558  mov     edx, edi; dwFlags
0x18000655a  mov     rcx, rax; hHeap
0x18000655d  call    cs:__imp_HeapAlloc
0x180006563  mov     rbx, rax
0x180006566  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000656d  test    rax, rax
0x180006570  jnz     short loc_1800065B8
0x180006572  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006578  jnz     short loc_1800065C3
0x18000657a  lea     rcx, ModuleName; "ntdll.dll"
0x180006581  call    cs:__imp_GetModuleHandleW
0x180006587  test    rax, rax
0x18000658a  jz      short loc_1800065A5
0x18000658c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180006593  mov     rcx, rax; hModule
0x180006596  call    cs:__imp_GetProcAddress
0x18000659c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800065a3  jmp     short loc_1800065AC
0x1800065a5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800065ac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800065b3  test    rax, rax
0x1800065b6  jz      short loc_1800065C3
0x1800065b8  mov     rdx, rbx
0x1800065bb  mov     rcx, rsi
0x1800065be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065c3  mov     rax, rbx
0x1800065c6  mov     rbx, [rsp+28h+arg_0]
0x1800065cb  mov     rsi, [rsp+28h+arg_8]
0x1800065d0  add     rsp, 20h
0x1800065d4  pop     rdi
0x1800065d5  retn
```
