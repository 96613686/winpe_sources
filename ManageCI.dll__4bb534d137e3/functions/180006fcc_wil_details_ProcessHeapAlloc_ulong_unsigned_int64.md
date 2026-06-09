# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006fcc`
- end: `0x18000706a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000627c`
- `0x180006c70`
- `0x180007740`
- `0x180007ad8`
- `0x18000bae0`
- `0x18000d5e0`

## callees

- `0x180006fcc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000702a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000702a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007015`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007015`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006fe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006fe0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ff1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ff1`

## string_xrefs

- `0x18000700e`: `ntdll.dll`

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
0x180006fcc  mov     [rsp+arg_0], rbx
0x180006fd1  mov     [rsp+arg_8], rsi
0x180006fd6  push    rdi
0x180006fd7  sub     rsp, 20h
0x180006fdb  mov     rbx, rdx
0x180006fde  mov     edi, ecx
0x180006fe0  call    cs:__imp_GetProcessHeap
0x180006fe6  mov     rsi, rax
0x180006fe9  mov     r8, rbx; dwBytes
0x180006fec  mov     edx, edi; dwFlags
0x180006fee  mov     rcx, rax; hHeap
0x180006ff1  call    cs:__imp_HeapAlloc
0x180006ff7  mov     rbx, rax
0x180006ffa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007001  test    rax, rax
0x180007004  jnz     short loc_18000704C
0x180007006  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000700c  jnz     short loc_180007057
0x18000700e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180007015  call    cs:__imp_GetModuleHandleW
0x18000701b  test    rax, rax
0x18000701e  jz      short loc_180007039
0x180007020  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007027  mov     rcx, rax; hModule
0x18000702a  call    cs:__imp_GetProcAddress
0x180007030  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007037  jmp     short loc_180007040
0x180007039  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007040  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007047  test    rax, rax
0x18000704a  jz      short loc_180007057
0x18000704c  mov     rdx, rbx
0x18000704f  mov     rcx, rsi
0x180007052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007057  mov     rax, rbx
0x18000705a  mov     rbx, [rsp+28h+arg_0]
0x18000705f  mov     rsi, [rsp+28h+arg_8]
0x180007064  add     rsp, 20h
0x180007068  pop     rdi
0x180007069  retn
```
