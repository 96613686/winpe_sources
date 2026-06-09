# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006c38`
- end: `0x180006cd6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004988`
- `0x180004d38`
- `0x1800059e0`
- `0x1800084a4`
- `0x180009d1c`

## callees

- `0x180006c38`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006c5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006c5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c96`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c81`

## string_xrefs

- `0x180006c7a`: `ntdll.dll`

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
0x180006c38  mov     [rsp+arg_0], rbx
0x180006c3d  mov     [rsp+arg_8], rsi
0x180006c42  push    rdi
0x180006c43  sub     rsp, 20h
0x180006c47  mov     rbx, rdx
0x180006c4a  mov     edi, ecx
0x180006c4c  call    cs:__imp_GetProcessHeap
0x180006c52  mov     rsi, rax
0x180006c55  mov     r8, rbx; dwBytes
0x180006c58  mov     edx, edi; dwFlags
0x180006c5a  mov     rcx, rax; hHeap
0x180006c5d  call    cs:__imp_HeapAlloc
0x180006c63  mov     rbx, rax
0x180006c66  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006c6d  test    rax, rax
0x180006c70  jnz     short loc_180006CB8
0x180006c72  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006c78  jnz     short loc_180006CC3
0x180006c7a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180006c81  call    cs:__imp_GetModuleHandleW
0x180006c87  test    rax, rax
0x180006c8a  jz      short loc_180006CA5
0x180006c8c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006c93  mov     rcx, rax; hModule
0x180006c96  call    cs:__imp_GetProcAddress
0x180006c9c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006ca3  jmp     short loc_180006CAC
0x180006ca5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006cac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006cb3  test    rax, rax
0x180006cb6  jz      short loc_180006CC3
0x180006cb8  mov     rdx, rbx
0x180006cbb  mov     rcx, rsi
0x180006cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc3  mov     rax, rbx
0x180006cc6  mov     rbx, [rsp+28h+arg_0]
0x180006ccb  mov     rsi, [rsp+28h+arg_8]
0x180006cd0  add     rsp, 20h
0x180006cd4  pop     rdi
0x180006cd5  retn
```
