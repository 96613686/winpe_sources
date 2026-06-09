# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180018eb4`
- end: `0x180018f6b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018b4c`
- `0x180019808`

## callees

- `0x180018eb4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018f24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018f24`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018f09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018f09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018edf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018edf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018ec8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018ec8`

## string_xrefs

- `0x180018f02`: `ntdll.dll`

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
0x180018eb4  mov     [rsp+arg_0], rbx
0x180018eb9  mov     [rsp+arg_8], rsi
0x180018ebe  push    rdi
0x180018ebf  sub     rsp, 20h
0x180018ec3  mov     rbx, rdx
0x180018ec6  mov     edi, ecx
0x180018ec8  call    cs:__imp_GetProcessHeap
0x180018ecf  nop     dword ptr [rax+rax+00h]
0x180018ed4  mov     rsi, rax
0x180018ed7  mov     r8, rbx; dwBytes
0x180018eda  mov     edx, edi; dwFlags
0x180018edc  mov     rcx, rax; hHeap
0x180018edf  call    cs:__imp_HeapAlloc
0x180018ee6  nop     dword ptr [rax+rax+00h]
0x180018eeb  mov     rbx, rax
0x180018eee  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180018ef5  test    rax, rax
0x180018ef8  jnz     short loc_180018F4C
0x180018efa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180018f00  jnz     short loc_180018F57
0x180018f02  lea     rcx, ModuleName; "ntdll.dll"
0x180018f09  call    cs:__imp_GetModuleHandleW
0x180018f10  nop     dword ptr [rax+rax+00h]
0x180018f15  test    rax, rax
0x180018f18  jz      short loc_180018F39
0x180018f1a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180018f21  mov     rcx, rax; hModule
0x180018f24  call    cs:__imp_GetProcAddress
0x180018f2b  nop     dword ptr [rax+rax+00h]
0x180018f30  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180018f37  jmp     short loc_180018F40
0x180018f39  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180018f40  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180018f47  test    rax, rax
0x180018f4a  jz      short loc_180018F57
0x180018f4c  mov     rdx, rbx
0x180018f4f  mov     rcx, rsi
0x180018f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f57  mov     rax, rbx
0x180018f5a  mov     rbx, [rsp+28h+arg_0]
0x180018f5f  mov     rsi, [rsp+28h+arg_8]
0x180018f64  add     rsp, 20h
0x180018f68  pop     rdi
0x180018f69  retn
```
