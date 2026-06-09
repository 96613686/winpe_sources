# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800057d8`
- end: `0x180005876`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800036f4`
- `0x180003a98`
- `0x180004670`
- `0x180006bd8`
- `0x180007bbc`

## callees

- `0x1800057d8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005821`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005821`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005836`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800057fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800057fd`

## string_xrefs

- `0x18000581a`: `ntdll.dll`

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
0x1800057d8  mov     [rsp+arg_0], rbx
0x1800057dd  mov     [rsp+arg_8], rsi
0x1800057e2  push    rdi
0x1800057e3  sub     rsp, 20h
0x1800057e7  mov     rbx, rdx
0x1800057ea  mov     edi, ecx
0x1800057ec  call    cs:__imp_GetProcessHeap
0x1800057f2  mov     r8, rbx; dwBytes
0x1800057f5  mov     edx, edi; dwFlags
0x1800057f7  mov     rcx, rax; hHeap
0x1800057fa  mov     rsi, rax
0x1800057fd  call    cs:__imp_HeapAlloc
0x180005803  mov     rbx, rax
0x180005806  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000580d  test    rax, rax
0x180005810  jnz     short loc_180005858
0x180005812  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005818  jnz     short loc_180005863
0x18000581a  lea     rcx, ModuleName; "ntdll.dll"
0x180005821  call    cs:__imp_GetModuleHandleW
0x180005827  test    rax, rax
0x18000582a  jz      short loc_180005845
0x18000582c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005833  mov     rcx, rax; hModule
0x180005836  call    cs:__imp_GetProcAddress
0x18000583c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005843  jmp     short loc_18000584C
0x180005845  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000584c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005853  test    rax, rax
0x180005856  jz      short loc_180005863
0x180005858  mov     rdx, rbx
0x18000585b  mov     rcx, rsi
0x18000585e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005863  mov     rsi, [rsp+28h+arg_8]
0x180005868  mov     rax, rbx
0x18000586b  mov     rbx, [rsp+28h+arg_0]
0x180005870  add     rsp, 20h
0x180005874  pop     rdi
0x180005875  retn
```
