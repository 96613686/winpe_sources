# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000ac10`
- end: `0x14000acae`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008f9c`
- `0x14000936c`
- `0x14000a3b0`
- `0x14000c1ac`
- `0x14000dd18`

## callees

- `0x14000ac10`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ac6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ac6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ac59`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ac59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ac24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ac24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000ac35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000ac35`

## string_xrefs

- `0x14000ac52`: `ntdll.dll`

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
0x14000ac10  mov     [rsp+arg_0], rbx
0x14000ac15  mov     [rsp+arg_8], rsi
0x14000ac1a  push    rdi
0x14000ac1b  sub     rsp, 20h
0x14000ac1f  mov     rbx, rdx
0x14000ac22  mov     edi, ecx
0x14000ac24  call    cs:__imp_GetProcessHeap
0x14000ac2a  mov     rsi, rax
0x14000ac2d  mov     r8, rbx; dwBytes
0x14000ac30  mov     edx, edi; dwFlags
0x14000ac32  mov     rcx, rax; hHeap
0x14000ac35  call    cs:__imp_HeapAlloc
0x14000ac3b  mov     rbx, rax
0x14000ac3e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000ac45  test    rax, rax
0x14000ac48  jnz     short loc_14000AC90
0x14000ac4a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000ac50  jnz     short loc_14000AC9B
0x14000ac52  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000ac59  call    cs:__imp_GetModuleHandleW
0x14000ac5f  test    rax, rax
0x14000ac62  jz      short loc_14000AC7D
0x14000ac64  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000ac6b  mov     rcx, rax; hModule
0x14000ac6e  call    cs:__imp_GetProcAddress
0x14000ac74  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000ac7b  jmp     short loc_14000AC84
0x14000ac7d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000ac84  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000ac8b  test    rax, rax
0x14000ac8e  jz      short loc_14000AC9B
0x14000ac90  mov     rdx, rbx
0x14000ac93  mov     rcx, rsi
0x14000ac96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac9b  mov     rax, rbx
0x14000ac9e  mov     rbx, [rsp+28h+arg_0]
0x14000aca3  mov     rsi, [rsp+28h+arg_8]
0x14000aca8  add     rsp, 20h
0x14000acac  pop     rdi
0x14000acad  retn
```
