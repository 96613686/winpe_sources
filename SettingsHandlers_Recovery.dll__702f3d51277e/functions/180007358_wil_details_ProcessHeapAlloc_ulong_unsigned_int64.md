# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007358`
- end: `0x1800073f6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004e58`
- `0x18000522c`
- `0x1800060b0`
- `0x180008d14`
- `0x18000a5e0`

## callees

- `0x180007358`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800073b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800073b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800073a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800073a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000736c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000736c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000737d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000737d`

## string_xrefs

- `0x18000739a`: `ntdll.dll`

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
0x180007358  mov     [rsp+arg_0], rbx
0x18000735d  mov     [rsp+arg_8], rsi
0x180007362  push    rdi
0x180007363  sub     rsp, 20h
0x180007367  mov     rbx, rdx
0x18000736a  mov     edi, ecx
0x18000736c  call    cs:__imp_GetProcessHeap
0x180007372  mov     rsi, rax
0x180007375  mov     r8, rbx; dwBytes
0x180007378  mov     edx, edi; dwFlags
0x18000737a  mov     rcx, rax; hHeap
0x18000737d  call    cs:__imp_HeapAlloc
0x180007383  mov     rbx, rax
0x180007386  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000738d  test    rax, rax
0x180007390  jnz     short loc_1800073D8
0x180007392  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007398  jnz     short loc_1800073E3
0x18000739a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800073a1  call    cs:__imp_GetModuleHandleW
0x1800073a7  test    rax, rax
0x1800073aa  jz      short loc_1800073C5
0x1800073ac  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800073b3  mov     rcx, rax; hModule
0x1800073b6  call    cs:__imp_GetProcAddress
0x1800073bc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800073c3  jmp     short loc_1800073CC
0x1800073c5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800073cc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800073d3  test    rax, rax
0x1800073d6  jz      short loc_1800073E3
0x1800073d8  mov     rdx, rbx
0x1800073db  mov     rcx, rsi
0x1800073de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073e3  mov     rax, rbx
0x1800073e6  mov     rbx, [rsp+28h+arg_0]
0x1800073eb  mov     rsi, [rsp+28h+arg_8]
0x1800073f0  add     rsp, 20h
0x1800073f4  pop     rdi
0x1800073f5  retn
```
