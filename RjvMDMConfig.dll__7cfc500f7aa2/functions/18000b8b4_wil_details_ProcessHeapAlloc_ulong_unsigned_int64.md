# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b8b4`
- end: `0x18000b96b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b36c`
- `0x18000b4d0`
- `0x18000f650`
- `0x18000f94c`
- `0x180011780`

## callees

- `0x18000b8b4`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b924`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b924`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b909`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b909`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b8df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b8df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8c8`

## string_xrefs

- `0x18000b902`: `ntdll.dll`

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
0x18000b8b4  mov     [rsp+arg_0], rbx
0x18000b8b9  mov     [rsp+arg_8], rsi
0x18000b8be  push    rdi
0x18000b8bf  sub     rsp, 20h
0x18000b8c3  mov     rbx, rdx
0x18000b8c6  mov     edi, ecx
0x18000b8c8  call    cs:__imp_GetProcessHeap
0x18000b8cf  nop     dword ptr [rax+rax+00h]
0x18000b8d4  mov     r8, rbx; dwBytes
0x18000b8d7  mov     edx, edi; dwFlags
0x18000b8d9  mov     rcx, rax; hHeap
0x18000b8dc  mov     rsi, rax
0x18000b8df  call    cs:__imp_HeapAlloc
0x18000b8e6  nop     dword ptr [rax+rax+00h]
0x18000b8eb  mov     rbx, rax
0x18000b8ee  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b8f5  test    rax, rax
0x18000b8f8  jnz     short loc_18000B94C
0x18000b8fa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b900  jnz     short loc_18000B957
0x18000b902  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000b909  call    cs:__imp_GetModuleHandleW
0x18000b910  nop     dword ptr [rax+rax+00h]
0x18000b915  test    rax, rax
0x18000b918  jz      short loc_18000B939
0x18000b91a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000b921  mov     rcx, rax; hModule
0x18000b924  call    cs:__imp_GetProcAddress
0x18000b92b  nop     dword ptr [rax+rax+00h]
0x18000b930  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000b937  jmp     short loc_18000B940
0x18000b939  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b940  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b947  test    rax, rax
0x18000b94a  jz      short loc_18000B957
0x18000b94c  mov     rdx, rbx
0x18000b94f  mov     rcx, rsi
0x18000b952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b957  mov     rsi, [rsp+28h+arg_8]
0x18000b95c  mov     rax, rbx
0x18000b95f  mov     rbx, [rsp+28h+arg_0]
0x18000b964  add     rsp, 20h
0x18000b968  pop     rdi
0x18000b969  retn
```
