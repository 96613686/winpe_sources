# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005e58`
- end: `0x180005ef6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800045b8`
- `0x180004d60`
- `0x180005330`
- `0x180006334`
- `0x18000896c`
- `0x18000cef4`

## callees

- `0x180005e58`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ea1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ea1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005eb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005eb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005e7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005e7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e6c`

## string_xrefs

- `0x180005e9a`: `ntdll.dll`

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
0x180005e58  mov     [rsp+arg_0], rbx
0x180005e5d  mov     [rsp+arg_8], rsi
0x180005e62  push    rdi
0x180005e63  sub     rsp, 20h
0x180005e67  mov     rbx, rdx
0x180005e6a  mov     edi, ecx
0x180005e6c  call    cs:__imp_GetProcessHeap
0x180005e72  mov     rsi, rax
0x180005e75  mov     r8, rbx; dwBytes
0x180005e78  mov     edx, edi; dwFlags
0x180005e7a  mov     rcx, rax; hHeap
0x180005e7d  call    cs:__imp_HeapAlloc
0x180005e83  mov     rbx, rax
0x180005e86  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005e8d  test    rax, rax
0x180005e90  jnz     short loc_180005ED8
0x180005e92  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005e98  jnz     short loc_180005EE3
0x180005e9a  lea     rcx, ModuleName; "ntdll.dll"
0x180005ea1  call    cs:__imp_GetModuleHandleW
0x180005ea7  test    rax, rax
0x180005eaa  jz      short loc_180005EC5
0x180005eac  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005eb3  mov     rcx, rax; hModule
0x180005eb6  call    cs:__imp_GetProcAddress
0x180005ebc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005ec3  jmp     short loc_180005ECC
0x180005ec5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005ecc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005ed3  test    rax, rax
0x180005ed6  jz      short loc_180005EE3
0x180005ed8  mov     rdx, rbx
0x180005edb  mov     rcx, rsi
0x180005ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee3  mov     rax, rbx
0x180005ee6  mov     rbx, [rsp+28h+arg_0]
0x180005eeb  mov     rsi, [rsp+28h+arg_8]
0x180005ef0  add     rsp, 20h
0x180005ef4  pop     rdi
0x180005ef5  retn
```
