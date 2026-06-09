# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800048f8`
- end: `0x180004996`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003168`
- `0x1800038b0`
- `0x180004de4`
- `0x180007824`
- `0x180009a7c`

## callees

- `0x1800048f8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004941`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004941`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004956`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004956`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000491d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000491d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000490c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000490c`

## string_xrefs

- `0x18000493a`: `ntdll.dll`

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
0x1800048f8  mov     [rsp+arg_0], rbx
0x1800048fd  mov     [rsp+arg_8], rsi
0x180004902  push    rdi
0x180004903  sub     rsp, 20h
0x180004907  mov     rbx, rdx
0x18000490a  mov     edi, ecx
0x18000490c  call    cs:__imp_GetProcessHeap
0x180004912  mov     rsi, rax
0x180004915  mov     r8, rbx; dwBytes
0x180004918  mov     edx, edi; dwFlags
0x18000491a  mov     rcx, rax; hHeap
0x18000491d  call    cs:__imp_HeapAlloc
0x180004923  mov     rbx, rax
0x180004926  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000492d  test    rax, rax
0x180004930  jnz     short loc_180004978
0x180004932  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004938  jnz     short loc_180004983
0x18000493a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180004941  call    cs:__imp_GetModuleHandleW
0x180004947  test    rax, rax
0x18000494a  jz      short loc_180004965
0x18000494c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004953  mov     rcx, rax; hModule
0x180004956  call    cs:__imp_GetProcAddress
0x18000495c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004963  jmp     short loc_18000496C
0x180004965  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000496c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004973  test    rax, rax
0x180004976  jz      short loc_180004983
0x180004978  mov     rdx, rbx
0x18000497b  mov     rcx, rsi
0x18000497e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004983  mov     rax, rbx
0x180004986  mov     rbx, [rsp+28h+arg_0]
0x18000498b  mov     rsi, [rsp+28h+arg_8]
0x180004990  add     rsp, 20h
0x180004994  pop     rdi
0x180004995  retn
```
