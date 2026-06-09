# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010bf8`
- end: `0x180010c96`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010784`
- `0x1800108d4`
- `0x180011510`
- `0x180011984`
- `0x1800129f4`

## callees

- `0x180010bf8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010c41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010c41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010c56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010c56`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010c1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010c1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c0c`

## string_xrefs

- `0x180010c3a`: `ntdll.dll`

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
0x180010bf8  mov     [rsp+arg_0], rbx
0x180010bfd  mov     [rsp+arg_8], rsi
0x180010c02  push    rdi
0x180010c03  sub     rsp, 20h
0x180010c07  mov     rbx, rdx
0x180010c0a  mov     edi, ecx
0x180010c0c  call    cs:__imp_GetProcessHeap
0x180010c12  mov     rsi, rax
0x180010c15  mov     r8, rbx; dwBytes
0x180010c18  mov     edx, edi; dwFlags
0x180010c1a  mov     rcx, rax; hHeap
0x180010c1d  call    cs:__imp_HeapAlloc
0x180010c23  mov     rbx, rax
0x180010c26  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010c2d  test    rax, rax
0x180010c30  jnz     short loc_180010C78
0x180010c32  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180010c38  jnz     short loc_180010C83
0x180010c3a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180010c41  call    cs:__imp_GetModuleHandleW
0x180010c47  test    rax, rax
0x180010c4a  jz      short loc_180010C65
0x180010c4c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180010c53  mov     rcx, rax; hModule
0x180010c56  call    cs:__imp_GetProcAddress
0x180010c5c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180010c63  jmp     short loc_180010C6C
0x180010c65  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010c6c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180010c73  test    rax, rax
0x180010c76  jz      short loc_180010C83
0x180010c78  mov     rdx, rbx
0x180010c7b  mov     rcx, rsi
0x180010c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c83  mov     rax, rbx
0x180010c86  mov     rbx, [rsp+28h+arg_0]
0x180010c8b  mov     rsi, [rsp+28h+arg_8]
0x180010c90  add     rsp, 20h
0x180010c94  pop     rdi
0x180010c95  retn
```
