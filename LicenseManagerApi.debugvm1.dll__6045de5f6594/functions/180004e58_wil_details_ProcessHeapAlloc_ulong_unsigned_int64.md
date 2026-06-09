# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004e58`
- end: `0x180004ef6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800037a8`
- `0x180003e20`
- `0x180005340`

## callees

- `0x180004e58`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004eb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004eb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ea1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ea1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e7d`

## string_xrefs

- `0x180004e9a`: `ntdll.dll`

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
0x180004e58  mov     [rsp+arg_0], rbx
0x180004e5d  mov     [rsp+arg_8], rsi
0x180004e62  push    rdi
0x180004e63  sub     rsp, 20h
0x180004e67  mov     rbx, rdx
0x180004e6a  mov     edi, ecx
0x180004e6c  call    cs:__imp_GetProcessHeap
0x180004e72  mov     rsi, rax
0x180004e75  mov     r8, rbx; dwBytes
0x180004e78  mov     edx, edi; dwFlags
0x180004e7a  mov     rcx, rax; hHeap
0x180004e7d  call    cs:__imp_HeapAlloc
0x180004e83  mov     rbx, rax
0x180004e86  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004e8d  test    rax, rax
0x180004e90  jnz     short loc_180004ED8
0x180004e92  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004e98  jnz     short loc_180004EE3
0x180004e9a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180004ea1  call    cs:__imp_GetModuleHandleW
0x180004ea7  test    rax, rax
0x180004eaa  jz      short loc_180004EC5
0x180004eac  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004eb3  mov     rcx, rax; hModule
0x180004eb6  call    cs:__imp_GetProcAddress
0x180004ebc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004ec3  jmp     short loc_180004ECC
0x180004ec5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004ecc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004ed3  test    rax, rax
0x180004ed6  jz      short loc_180004EE3
0x180004ed8  mov     rdx, rbx
0x180004edb  mov     rcx, rsi
0x180004ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee3  mov     rax, rbx
0x180004ee6  mov     rbx, [rsp+28h+arg_0]
0x180004eeb  mov     rsi, [rsp+28h+arg_8]
0x180004ef0  add     rsp, 20h
0x180004ef4  pop     rdi
0x180004ef5  retn
```
