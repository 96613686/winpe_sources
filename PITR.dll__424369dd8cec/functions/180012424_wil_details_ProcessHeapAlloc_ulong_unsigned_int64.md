# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180012424`
- end: `0x1800124c2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007610`
- `0x1800079b4`
- `0x18001baf0`
- `0x18001e26c`

## callees

- `0x180012424`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001246d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001246d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012482`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012482`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012438`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012438`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012449`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012449`

## string_xrefs

- `0x180012466`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180012424  mov     [rsp+arg_0], rbx
0x180012429  mov     [rsp+arg_8], rsi
0x18001242e  push    rdi
0x18001242f  sub     rsp, 20h
0x180012433  mov     rbx, rdx
0x180012436  mov     edi, ecx
0x180012438  call    cs:__imp_GetProcessHeap
0x18001243e  mov     rsi, rax
0x180012441  mov     r8, rbx; dwBytes
0x180012444  mov     edx, edi; dwFlags
0x180012446  mov     rcx, rax; hHeap
0x180012449  call    cs:__imp_HeapAlloc
0x18001244f  mov     rbx, rax
0x180012452  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012459  test    rax, rax
0x18001245c  jnz     short loc_1800124A4
0x18001245e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012464  jnz     short loc_1800124AF
0x180012466  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x18001246d  call    cs:__imp_GetModuleHandleW
0x180012473  test    rax, rax
0x180012476  jz      short loc_180012491
0x180012478  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001247f  mov     rcx, rax; hModule
0x180012482  call    cs:__imp_GetProcAddress
0x180012488  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001248f  jmp     short loc_180012498
0x180012491  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012498  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001249f  test    rax, rax
0x1800124a2  jz      short loc_1800124AF
0x1800124a4  mov     rdx, rbx
0x1800124a7  mov     rcx, rsi
0x1800124aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124af  mov     rax, rbx
0x1800124b2  mov     rbx, [rsp+28h+arg_0]
0x1800124b7  mov     rsi, [rsp+28h+arg_8]
0x1800124bc  add     rsp, 20h
0x1800124c0  pop     rdi
0x1800124c1  retn
```
