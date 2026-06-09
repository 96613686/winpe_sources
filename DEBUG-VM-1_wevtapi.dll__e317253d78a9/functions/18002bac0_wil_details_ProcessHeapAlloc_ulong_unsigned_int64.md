# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002bac0`
- end: `0x18002bb5e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800202a0`
- `0x18002b5e0`
- `0x18002b704`
- `0x18002c450`
- `0x18002c6b4`

## callees

- `0x18002bac0`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bad4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bad4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bae5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bae5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bb1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bb1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bb09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bb09`

## string_xrefs

- `0x18002bb02`: `ntdll.dll`

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
0x18002bac0  mov     [rsp+arg_0], rbx
0x18002bac5  mov     [rsp+arg_8], rsi
0x18002baca  push    rdi
0x18002bacb  sub     rsp, 20h
0x18002bacf  mov     rbx, rdx
0x18002bad2  mov     edi, ecx
0x18002bad4  call    cs:__imp_GetProcessHeap
0x18002bada  mov     rsi, rax
0x18002badd  mov     r8, rbx; dwBytes
0x18002bae0  mov     edx, edi; dwFlags
0x18002bae2  mov     rcx, rax; hHeap
0x18002bae5  call    cs:__imp_HeapAlloc
0x18002baeb  mov     rbx, rax
0x18002baee  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002baf5  test    rax, rax
0x18002baf8  jnz     short loc_18002BB40
0x18002bafa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002bb00  jnz     short loc_18002BB4B
0x18002bb02  lea     rcx, ModuleName; "ntdll.dll"
0x18002bb09  call    cs:__imp_GetModuleHandleW
0x18002bb0f  test    rax, rax
0x18002bb12  jz      short loc_18002BB2D
0x18002bb14  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18002bb1b  mov     rcx, rax; hModule
0x18002bb1e  call    cs:__imp_GetProcAddress
0x18002bb24  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002bb2b  jmp     short loc_18002BB34
0x18002bb2d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002bb34  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002bb3b  test    rax, rax
0x18002bb3e  jz      short loc_18002BB4B
0x18002bb40  mov     rdx, rbx
0x18002bb43  mov     rcx, rsi
0x18002bb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb4b  mov     rax, rbx
0x18002bb4e  mov     rbx, [rsp+28h+arg_0]
0x18002bb53  mov     rsi, [rsp+28h+arg_8]
0x18002bb58  add     rsp, 20h
0x18002bb5c  pop     rdi
0x18002bb5d  retn
```
