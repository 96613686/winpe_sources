# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800a7090`
- end: `0x1800a712e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800a6f5c`
- `0x1800a7370`
- `0x1800a74ac`

## callees

- `0x1800a7090`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a70d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a70d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a70ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a70ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a70a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a70a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a70b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a70b5`

## string_xrefs

- `0x1800a70d2`: `ntdll.dll`

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
0x1800a7090  mov     [rsp+arg_0], rbx
0x1800a7095  mov     [rsp+arg_8], rsi
0x1800a709a  push    rdi
0x1800a709b  sub     rsp, 20h
0x1800a709f  mov     rbx, rdx
0x1800a70a2  mov     edi, ecx
0x1800a70a4  call    cs:__imp_GetProcessHeap
0x1800a70aa  mov     rsi, rax
0x1800a70ad  mov     r8, rbx; dwBytes
0x1800a70b0  mov     edx, edi; dwFlags
0x1800a70b2  mov     rcx, rax; hHeap
0x1800a70b5  call    cs:__imp_HeapAlloc
0x1800a70bb  mov     rbx, rax
0x1800a70be  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800a70c5  test    rax, rax
0x1800a70c8  jnz     short loc_1800A7110
0x1800a70ca  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800a70d0  jnz     short loc_1800A711B
0x1800a70d2  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800a70d9  call    cs:__imp_GetModuleHandleW
0x1800a70df  test    rax, rax
0x1800a70e2  jz      short loc_1800A70FD
0x1800a70e4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800a70eb  mov     rcx, rax; hModule
0x1800a70ee  call    cs:__imp_GetProcAddress
0x1800a70f4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800a70fb  jmp     short loc_1800A7104
0x1800a70fd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800a7104  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800a710b  test    rax, rax
0x1800a710e  jz      short loc_1800A711B
0x1800a7110  mov     rdx, rbx
0x1800a7113  mov     rcx, rsi
0x1800a7116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a711b  mov     rax, rbx
0x1800a711e  mov     rbx, [rsp+28h+arg_0]
0x1800a7123  mov     rsi, [rsp+28h+arg_8]
0x1800a7128  add     rsp, 20h
0x1800a712c  pop     rdi
0x1800a712d  retn
```
