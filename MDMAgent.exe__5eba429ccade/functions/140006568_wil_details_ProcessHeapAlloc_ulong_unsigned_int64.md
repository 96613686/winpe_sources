# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140006568`
- end: `0x140006606`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400056fc`
- `0x1400062e8`
- `0x140006a50`
- `0x140006de8`
- `0x14000bc54`
- `0x1400114dc`

## callees

- `0x140006568`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400065b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400065b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400065c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400065c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000657c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000657c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000658d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000658d`

## string_xrefs

- `0x1400065aa`: `ntdll.dll`

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
0x140006568  mov     [rsp+arg_0], rbx
0x14000656d  mov     [rsp+arg_8], rsi
0x140006572  push    rdi
0x140006573  sub     rsp, 20h
0x140006577  mov     rbx, rdx
0x14000657a  mov     edi, ecx
0x14000657c  call    cs:__imp_GetProcessHeap
0x140006582  mov     rsi, rax
0x140006585  mov     r8, rbx; dwBytes
0x140006588  mov     edx, edi; dwFlags
0x14000658a  mov     rcx, rax; hHeap
0x14000658d  call    cs:__imp_HeapAlloc
0x140006593  mov     rbx, rax
0x140006596  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000659d  test    rax, rax
0x1400065a0  jnz     short loc_1400065E8
0x1400065a2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400065a8  jnz     short loc_1400065F3
0x1400065aa  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1400065b1  call    cs:__imp_GetModuleHandleW
0x1400065b7  test    rax, rax
0x1400065ba  jz      short loc_1400065D5
0x1400065bc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400065c3  mov     rcx, rax; hModule
0x1400065c6  call    cs:__imp_GetProcAddress
0x1400065cc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400065d3  jmp     short loc_1400065DC
0x1400065d5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400065dc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400065e3  test    rax, rax
0x1400065e6  jz      short loc_1400065F3
0x1400065e8  mov     rdx, rbx
0x1400065eb  mov     rcx, rsi
0x1400065ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065f3  mov     rax, rbx
0x1400065f6  mov     rbx, [rsp+28h+arg_0]
0x1400065fb  mov     rsi, [rsp+28h+arg_8]
0x140006600  add     rsp, 20h
0x140006604  pop     rdi
0x140006605  retn
```
