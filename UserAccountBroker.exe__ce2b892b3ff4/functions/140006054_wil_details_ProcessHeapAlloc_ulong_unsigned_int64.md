# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140006054`
- end: `0x1400060f2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400049d0`
- `0x140005120`
- `0x1400063a0`

## callees

- `0x140006054`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000609d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000609d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400060b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400060b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006068`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006068`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006079`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006079`

## string_xrefs

- `0x140006096`: `ntdll.dll`

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
0x140006054  mov     [rsp+arg_0], rbx
0x140006059  mov     [rsp+arg_8], rsi
0x14000605e  push    rdi
0x14000605f  sub     rsp, 20h
0x140006063  mov     rbx, rdx
0x140006066  mov     edi, ecx
0x140006068  call    cs:__imp_GetProcessHeap
0x14000606e  mov     r8, rbx; dwBytes
0x140006071  mov     edx, edi; dwFlags
0x140006073  mov     rcx, rax; hHeap
0x140006076  mov     rsi, rax
0x140006079  call    cs:__imp_HeapAlloc
0x14000607f  mov     rbx, rax
0x140006082  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006089  test    rax, rax
0x14000608c  jnz     short loc_1400060D4
0x14000608e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006094  jnz     short loc_1400060DF
0x140006096  lea     rcx, ModuleName; "ntdll.dll"
0x14000609d  call    cs:__imp_GetModuleHandleW
0x1400060a3  test    rax, rax
0x1400060a6  jz      short loc_1400060C1
0x1400060a8  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1400060af  mov     rcx, rax; hModule
0x1400060b2  call    cs:__imp_GetProcAddress
0x1400060b8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400060bf  jmp     short loc_1400060C8
0x1400060c1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400060c8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400060cf  test    rax, rax
0x1400060d2  jz      short loc_1400060DF
0x1400060d4  mov     rdx, rbx
0x1400060d7  mov     rcx, rsi
0x1400060da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060df  mov     rsi, [rsp+28h+arg_8]
0x1400060e4  mov     rax, rbx
0x1400060e7  mov     rbx, [rsp+28h+arg_0]
0x1400060ec  add     rsp, 20h
0x1400060f0  pop     rdi
0x1400060f1  retn
```
