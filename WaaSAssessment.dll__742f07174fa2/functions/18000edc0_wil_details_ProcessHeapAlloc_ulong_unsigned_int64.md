# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000edc0`
- end: `0x18000ee5e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c450`
- `0x18000f010`
- `0x1800114d8`
- `0x1800162c4`

## callees

- `0x18000edc0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ee1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ee1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ee09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ee09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000edd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000edd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ede5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ede5`

## string_xrefs

- `0x18000ee02`: `ntdll.dll`

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
0x18000edc0  mov     [rsp+arg_0], rbx
0x18000edc5  mov     [rsp+arg_8], rsi
0x18000edca  push    rdi
0x18000edcb  sub     rsp, 20h
0x18000edcf  mov     rbx, rdx
0x18000edd2  mov     edi, ecx
0x18000edd4  call    cs:__imp_GetProcessHeap
0x18000edda  mov     r8, rbx; dwBytes
0x18000eddd  mov     edx, edi; dwFlags
0x18000eddf  mov     rcx, rax; hHeap
0x18000ede2  mov     rsi, rax
0x18000ede5  call    cs:__imp_HeapAlloc
0x18000edeb  mov     rbx, rax
0x18000edee  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000edf5  test    rax, rax
0x18000edf8  jnz     short loc_18000EE40
0x18000edfa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ee00  jnz     short loc_18000EE4B
0x18000ee02  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ee09  call    cs:__imp_GetModuleHandleW
0x18000ee0f  test    rax, rax
0x18000ee12  jz      short loc_18000EE2D
0x18000ee14  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000ee1b  mov     rcx, rax; hModule
0x18000ee1e  call    cs:__imp_GetProcAddress
0x18000ee24  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ee2b  jmp     short loc_18000EE34
0x18000ee2d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ee34  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ee3b  test    rax, rax
0x18000ee3e  jz      short loc_18000EE4B
0x18000ee40  mov     rdx, rbx
0x18000ee43  mov     rcx, rsi
0x18000ee46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee4b  mov     rsi, [rsp+28h+arg_8]
0x18000ee50  mov     rax, rbx
0x18000ee53  mov     rbx, [rsp+28h+arg_0]
0x18000ee58  add     rsp, 20h
0x18000ee5c  pop     rdi
0x18000ee5d  retn
```
