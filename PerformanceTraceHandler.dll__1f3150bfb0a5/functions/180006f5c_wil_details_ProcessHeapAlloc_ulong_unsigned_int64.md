# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006f5c`
- end: `0x180006ffa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005c5c`
- `0x18000698c`
- `0x180006abc`
- `0x180007fe0`
- `0x180008470`
- `0x1800099a4`

## callees

- `0x180006f5c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006fba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006fba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fa5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fa5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006f81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006f81`

## string_xrefs

- `0x180006f9e`: `ntdll.dll`

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
0x180006f5c  mov     [rsp+arg_0], rbx
0x180006f61  mov     [rsp+arg_8], rsi
0x180006f66  push    rdi
0x180006f67  sub     rsp, 20h
0x180006f6b  mov     rbx, rdx
0x180006f6e  mov     edi, ecx
0x180006f70  call    cs:__imp_GetProcessHeap
0x180006f76  mov     rsi, rax
0x180006f79  mov     r8, rbx; dwBytes
0x180006f7c  mov     edx, edi; dwFlags
0x180006f7e  mov     rcx, rax; hHeap
0x180006f81  call    cs:__imp_HeapAlloc
0x180006f87  mov     rbx, rax
0x180006f8a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006f91  test    rax, rax
0x180006f94  jnz     short loc_180006FDC
0x180006f96  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006f9c  jnz     short loc_180006FE7
0x180006f9e  lea     rcx, ModuleName; "ntdll.dll"
0x180006fa5  call    cs:__imp_GetModuleHandleW
0x180006fab  test    rax, rax
0x180006fae  jz      short loc_180006FC9
0x180006fb0  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180006fb7  mov     rcx, rax; hModule
0x180006fba  call    cs:__imp_GetProcAddress
0x180006fc0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006fc7  jmp     short loc_180006FD0
0x180006fc9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006fd0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006fd7  test    rax, rax
0x180006fda  jz      short loc_180006FE7
0x180006fdc  mov     rdx, rbx
0x180006fdf  mov     rcx, rsi
0x180006fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe7  mov     rax, rbx
0x180006fea  mov     rbx, [rsp+28h+arg_0]
0x180006fef  mov     rsi, [rsp+28h+arg_8]
0x180006ff4  add     rsp, 20h
0x180006ff8  pop     rdi
0x180006ff9  retn
```
