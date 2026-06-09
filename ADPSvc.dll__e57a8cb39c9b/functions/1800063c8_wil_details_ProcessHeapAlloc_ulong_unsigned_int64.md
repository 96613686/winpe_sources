# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800063c8`
- end: `0x180006466`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004ba8`
- `0x180005370`
- `0x180006934`
- `0x180008b94`
- `0x18000b5ac`

## callees

- `0x1800063c8`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006411`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006411`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006426`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006426`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063dc`

## string_xrefs

- `0x18000640a`: `ntdll.dll`

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
0x1800063c8  mov     [rsp+arg_0], rbx
0x1800063cd  mov     [rsp+arg_8], rsi
0x1800063d2  push    rdi
0x1800063d3  sub     rsp, 20h
0x1800063d7  mov     rbx, rdx
0x1800063da  mov     edi, ecx
0x1800063dc  call    cs:__imp_GetProcessHeap
0x1800063e2  mov     rsi, rax
0x1800063e5  mov     r8, rbx; dwBytes
0x1800063e8  mov     edx, edi; dwFlags
0x1800063ea  mov     rcx, rax; hHeap
0x1800063ed  call    cs:__imp_HeapAlloc
0x1800063f3  mov     rbx, rax
0x1800063f6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800063fd  test    rax, rax
0x180006400  jnz     short loc_180006448
0x180006402  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006408  jnz     short loc_180006453
0x18000640a  lea     rcx, ModuleName; "ntdll.dll"
0x180006411  call    cs:__imp_GetModuleHandleW
0x180006417  test    rax, rax
0x18000641a  jz      short loc_180006435
0x18000641c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006423  mov     rcx, rax; hModule
0x180006426  call    cs:__imp_GetProcAddress
0x18000642c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006433  jmp     short loc_18000643C
0x180006435  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000643c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006443  test    rax, rax
0x180006446  jz      short loc_180006453
0x180006448  mov     rdx, rbx
0x18000644b  mov     rcx, rsi
0x18000644e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006453  mov     rax, rbx
0x180006456  mov     rbx, [rsp+28h+arg_0]
0x18000645b  mov     rsi, [rsp+28h+arg_8]
0x180006460  add     rsp, 20h
0x180006464  pop     rdi
0x180006465  retn
```
