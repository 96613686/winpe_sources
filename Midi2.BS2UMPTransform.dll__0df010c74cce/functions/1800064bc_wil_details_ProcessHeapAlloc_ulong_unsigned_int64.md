# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800064bc`
- end: `0x18000655a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800038e8`
- `0x180004fb0`
- `0x180007740`

## callees

- `0x1800064bc`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006505`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006505`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000651a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000651a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800064e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800064e1`

## string_xrefs

- `0x1800064fe`: `ntdll.dll`

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
0x1800064bc  mov     [rsp+arg_0], rbx
0x1800064c1  mov     [rsp+arg_8], rsi
0x1800064c6  push    rdi
0x1800064c7  sub     rsp, 20h
0x1800064cb  mov     rbx, rdx
0x1800064ce  mov     edi, ecx
0x1800064d0  call    cs:__imp_GetProcessHeap
0x1800064d6  mov     rsi, rax
0x1800064d9  mov     r8, rbx; dwBytes
0x1800064dc  mov     edx, edi; dwFlags
0x1800064de  mov     rcx, rax; hHeap
0x1800064e1  call    cs:__imp_HeapAlloc
0x1800064e7  mov     rbx, rax
0x1800064ea  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800064f1  test    rax, rax
0x1800064f4  jnz     short loc_18000653C
0x1800064f6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800064fc  jnz     short loc_180006547
0x1800064fe  lea     rcx, aNtdllDll; "ntdll.dll"
0x180006505  call    cs:__imp_GetModuleHandleW
0x18000650b  test    rax, rax
0x18000650e  jz      short loc_180006529
0x180006510  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006517  mov     rcx, rax; hModule
0x18000651a  call    cs:__imp_GetProcAddress
0x180006520  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006527  jmp     short loc_180006530
0x180006529  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006530  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006537  test    rax, rax
0x18000653a  jz      short loc_180006547
0x18000653c  mov     rdx, rbx
0x18000653f  mov     rcx, rsi
0x180006542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006547  mov     rax, rbx
0x18000654a  mov     rbx, [rsp+28h+arg_0]
0x18000654f  mov     rsi, [rsp+28h+arg_8]
0x180006554  add     rsp, 20h
0x180006558  pop     rdi
0x180006559  retn
```
