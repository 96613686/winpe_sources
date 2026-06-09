# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000665c`
- end: `0x1800066fa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003a88`
- `0x180005150`
- `0x1800078f0`

## callees

- `0x18000665c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006670`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006670`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006681`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006681`

## string_xrefs

- `0x18000669e`: `ntdll.dll`

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
0x18000665c  mov     [rsp+arg_0], rbx
0x180006661  mov     [rsp+arg_8], rsi
0x180006666  push    rdi
0x180006667  sub     rsp, 20h
0x18000666b  mov     rbx, rdx
0x18000666e  mov     edi, ecx
0x180006670  call    cs:__imp_GetProcessHeap
0x180006676  mov     rsi, rax
0x180006679  mov     r8, rbx; dwBytes
0x18000667c  mov     edx, edi; dwFlags
0x18000667e  mov     rcx, rax; hHeap
0x180006681  call    cs:__imp_HeapAlloc
0x180006687  mov     rbx, rax
0x18000668a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006691  test    rax, rax
0x180006694  jnz     short loc_1800066DC
0x180006696  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000669c  jnz     short loc_1800066E7
0x18000669e  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800066a5  call    cs:__imp_GetModuleHandleW
0x1800066ab  test    rax, rax
0x1800066ae  jz      short loc_1800066C9
0x1800066b0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800066b7  mov     rcx, rax; hModule
0x1800066ba  call    cs:__imp_GetProcAddress
0x1800066c0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800066c7  jmp     short loc_1800066D0
0x1800066c9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800066d0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800066d7  test    rax, rax
0x1800066da  jz      short loc_1800066E7
0x1800066dc  mov     rdx, rbx
0x1800066df  mov     rcx, rsi
0x1800066e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066e7  mov     rax, rbx
0x1800066ea  mov     rbx, [rsp+28h+arg_0]
0x1800066ef  mov     rsi, [rsp+28h+arg_8]
0x1800066f4  add     rsp, 20h
0x1800066f8  pop     rdi
0x1800066f9  retn
```
