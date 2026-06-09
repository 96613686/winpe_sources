# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000e6bc`
- end: `0x18000e75a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b848`
- `0x18000bc20`
- `0x18000d030`
- `0x18000d600`
- `0x1800106e4`
- `0x1800122d4`

## callees

- `0x18000e6bc`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e705`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e705`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e71a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e71a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e6e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e6e1`

## string_xrefs

- `0x18000e6fe`: `ntdll.dll`

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
0x18000e6bc  mov     [rsp+arg_0], rbx
0x18000e6c1  mov     [rsp+arg_8], rsi
0x18000e6c6  push    rdi
0x18000e6c7  sub     rsp, 20h
0x18000e6cb  mov     rbx, rdx
0x18000e6ce  mov     edi, ecx
0x18000e6d0  call    cs:__imp_GetProcessHeap
0x18000e6d6  mov     rsi, rax
0x18000e6d9  mov     r8, rbx; dwBytes
0x18000e6dc  mov     edx, edi; dwFlags
0x18000e6de  mov     rcx, rax; hHeap
0x18000e6e1  call    cs:__imp_HeapAlloc
0x18000e6e7  mov     rbx, rax
0x18000e6ea  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e6f1  test    rax, rax
0x18000e6f4  jnz     short loc_18000E73C
0x18000e6f6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e6fc  jnz     short loc_18000E747
0x18000e6fe  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e705  call    cs:__imp_GetModuleHandleW
0x18000e70b  test    rax, rax
0x18000e70e  jz      short loc_18000E729
0x18000e710  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000e717  mov     rcx, rax; hModule
0x18000e71a  call    cs:__imp_GetProcAddress
0x18000e720  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000e727  jmp     short loc_18000E730
0x18000e729  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e730  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e737  test    rax, rax
0x18000e73a  jz      short loc_18000E747
0x18000e73c  mov     rdx, rbx
0x18000e73f  mov     rcx, rsi
0x18000e742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e747  mov     rax, rbx
0x18000e74a  mov     rbx, [rsp+28h+arg_0]
0x18000e74f  mov     rsi, [rsp+28h+arg_8]
0x18000e754  add     rsp, 20h
0x18000e758  pop     rdi
0x18000e759  retn
```
