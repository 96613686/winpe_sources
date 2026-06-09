# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180014c4c`
- end: `0x180014cea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800109f4`
- `0x180018294`
- `0x18001c7b4`
- `0x18001cb70`
- `0x18001d044`

## callees

- `0x180014c4c`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014c60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014c60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014c71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014c71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014caa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014caa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c95`

## string_xrefs

- `0x180014c8e`: `ntdll.dll`

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
0x180014c4c  mov     [rsp+arg_0], rbx
0x180014c51  mov     [rsp+arg_8], rsi
0x180014c56  push    rdi
0x180014c57  sub     rsp, 20h
0x180014c5b  mov     rbx, rdx
0x180014c5e  mov     edi, ecx
0x180014c60  call    cs:__imp_GetProcessHeap
0x180014c66  mov     r8, rbx; dwBytes
0x180014c69  mov     edx, edi; dwFlags
0x180014c6b  mov     rcx, rax; hHeap
0x180014c6e  mov     rsi, rax
0x180014c71  call    cs:__imp_HeapAlloc
0x180014c77  mov     rbx, rax
0x180014c7a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014c81  test    rax, rax
0x180014c84  jnz     short loc_180014CCC
0x180014c86  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180014c8c  jnz     short loc_180014CD7
0x180014c8e  lea     rcx, ModuleName; "ntdll.dll"
0x180014c95  call    cs:__imp_GetModuleHandleW
0x180014c9b  test    rax, rax
0x180014c9e  jz      short loc_180014CB9
0x180014ca0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180014ca7  mov     rcx, rax; hModule
0x180014caa  call    cs:__imp_GetProcAddress
0x180014cb0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180014cb7  jmp     short loc_180014CC0
0x180014cb9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014cc0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180014cc7  test    rax, rax
0x180014cca  jz      short loc_180014CD7
0x180014ccc  mov     rdx, rbx
0x180014ccf  mov     rcx, rsi
0x180014cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cd7  mov     rsi, [rsp+28h+arg_8]
0x180014cdc  mov     rax, rbx
0x180014cdf  mov     rbx, [rsp+28h+arg_0]
0x180014ce4  add     rsp, 20h
0x180014ce8  pop     rdi
0x180014ce9  retn
```
