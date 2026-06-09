# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000d114`
- end: `0x18000d1b2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007de8`
- `0x18000a500`
- `0x18000ef78`

## callees

- `0x18000d114`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d15d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d15d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d172`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d172`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d128`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d128`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d139`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d139`

## string_xrefs

- `0x18000d156`: `ntdll.dll`

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
0x18000d114  mov     [rsp+arg_0], rbx
0x18000d119  mov     [rsp+arg_8], rsi
0x18000d11e  push    rdi
0x18000d11f  sub     rsp, 20h
0x18000d123  mov     rbx, rdx
0x18000d126  mov     edi, ecx
0x18000d128  call    cs:__imp_GetProcessHeap
0x18000d12e  mov     r8, rbx; dwBytes
0x18000d131  mov     edx, edi; dwFlags
0x18000d133  mov     rcx, rax; hHeap
0x18000d136  mov     rsi, rax
0x18000d139  call    cs:__imp_HeapAlloc
0x18000d13f  mov     rbx, rax
0x18000d142  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d149  test    rax, rax
0x18000d14c  jnz     short loc_18000D194
0x18000d14e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d154  jnz     short loc_18000D19F
0x18000d156  lea     rcx, ModuleName; "ntdll.dll"
0x18000d15d  call    cs:__imp_GetModuleHandleW
0x18000d163  test    rax, rax
0x18000d166  jz      short loc_18000D181
0x18000d168  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000d16f  mov     rcx, rax; hModule
0x18000d172  call    cs:__imp_GetProcAddress
0x18000d178  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000d17f  jmp     short loc_18000D188
0x18000d181  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d188  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d18f  test    rax, rax
0x18000d192  jz      short loc_18000D19F
0x18000d194  mov     rdx, rbx
0x18000d197  mov     rcx, rsi
0x18000d19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19f  mov     rsi, [rsp+28h+arg_8]
0x18000d1a4  mov     rax, rbx
0x18000d1a7  mov     rbx, [rsp+28h+arg_0]
0x18000d1ac  add     rsp, 20h
0x18000d1b0  pop     rdi
0x18000d1b1  retn
```
