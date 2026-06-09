# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000e730`
- end: `0x18000e7ce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000df7c`
- `0x18000e0cc`
- `0x180010cb0`
- `0x180011138`
- `0x180012c0c`

## callees

- `0x18000e730`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e779`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e779`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e78e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e78e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e744`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e755`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e755`

## string_xrefs

- `0x18000e772`: `ntdll.dll`

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
0x18000e730  mov     [rsp+arg_0], rbx
0x18000e735  mov     [rsp+arg_8], rsi
0x18000e73a  push    rdi
0x18000e73b  sub     rsp, 20h
0x18000e73f  mov     rbx, rdx
0x18000e742  mov     edi, ecx
0x18000e744  call    cs:__imp_GetProcessHeap
0x18000e74a  mov     rsi, rax
0x18000e74d  mov     r8, rbx; dwBytes
0x18000e750  mov     edx, edi; dwFlags
0x18000e752  mov     rcx, rax; hHeap
0x18000e755  call    cs:__imp_HeapAlloc
0x18000e75b  mov     rbx, rax
0x18000e75e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e765  test    rax, rax
0x18000e768  jnz     short loc_18000E7B0
0x18000e76a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e770  jnz     short loc_18000E7BB
0x18000e772  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e779  call    cs:__imp_GetModuleHandleW
0x18000e77f  test    rax, rax
0x18000e782  jz      short loc_18000E79D
0x18000e784  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000e78b  mov     rcx, rax; hModule
0x18000e78e  call    cs:__imp_GetProcAddress
0x18000e794  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000e79b  jmp     short loc_18000E7A4
0x18000e79d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e7a4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e7ab  test    rax, rax
0x18000e7ae  jz      short loc_18000E7BB
0x18000e7b0  mov     rdx, rbx
0x18000e7b3  mov     rcx, rsi
0x18000e7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7bb  mov     rax, rbx
0x18000e7be  mov     rbx, [rsp+28h+arg_0]
0x18000e7c3  mov     rsi, [rsp+28h+arg_8]
0x18000e7c8  add     rsp, 20h
0x18000e7cc  pop     rdi
0x18000e7cd  retn
```
