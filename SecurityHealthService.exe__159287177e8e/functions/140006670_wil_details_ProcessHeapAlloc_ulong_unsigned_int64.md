# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140006670`
- end: `0x14000670e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006f10`
- `0x140008718`
- `0x140008ae8`
- `0x1400096d0`
- `0x14000b284`

## callees

- `0x140006670`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400066b9`
- `KERNEL32!GetModuleHandleW` at `0x1400066b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006695`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006695`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006684`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006684`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400066ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400066ce`

## string_xrefs

- `0x1400066b2`: `ntdll.dll`

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
0x140006670  mov     [rsp+arg_0], rbx
0x140006675  mov     [rsp+arg_8], rsi
0x14000667a  push    rdi
0x14000667b  sub     rsp, 20h
0x14000667f  mov     rbx, rdx
0x140006682  mov     edi, ecx
0x140006684  call    cs:__imp_GetProcessHeap
0x14000668a  mov     rsi, rax
0x14000668d  mov     r8, rbx; dwBytes
0x140006690  mov     edx, edi; dwFlags
0x140006692  mov     rcx, rax; hHeap
0x140006695  call    cs:__imp_HeapAlloc
0x14000669b  mov     rbx, rax
0x14000669e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400066a5  test    rax, rax
0x1400066a8  jnz     short loc_1400066F0
0x1400066aa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400066b0  jnz     short loc_1400066FB
0x1400066b2  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1400066b9  call    cs:__imp_GetModuleHandleW
0x1400066bf  test    rax, rax
0x1400066c2  jz      short loc_1400066DD
0x1400066c4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400066cb  mov     rcx, rax; hModule
0x1400066ce  call    cs:__imp_GetProcAddress
0x1400066d4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400066db  jmp     short loc_1400066E4
0x1400066dd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400066e4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400066eb  test    rax, rax
0x1400066ee  jz      short loc_1400066FB
0x1400066f0  mov     rdx, rbx
0x1400066f3  mov     rcx, rsi
0x1400066f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066fb  mov     rax, rbx
0x1400066fe  mov     rbx, [rsp+28h+arg_0]
0x140006703  mov     rsi, [rsp+28h+arg_8]
0x140006708  add     rsp, 20h
0x14000670c  pop     rdi
0x14000670d  retn
```
