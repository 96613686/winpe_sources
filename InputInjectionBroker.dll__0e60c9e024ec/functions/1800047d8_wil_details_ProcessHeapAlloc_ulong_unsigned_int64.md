# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800047d8`
- end: `0x180004876`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800030a0`
- `0x180004f28`
- `0x180009ed8`
- `0x18000ea2c`

## callees

- `0x1800047d8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004836`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004821`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004821`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047ec`

## string_xrefs

- `0x18000481a`: `ntdll.dll`

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
0x1800047d8  mov     [rsp+arg_0], rbx
0x1800047dd  mov     [rsp+arg_8], rsi
0x1800047e2  push    rdi
0x1800047e3  sub     rsp, 20h
0x1800047e7  mov     rbx, rdx
0x1800047ea  mov     edi, ecx
0x1800047ec  call    cs:__imp_GetProcessHeap
0x1800047f2  mov     rsi, rax
0x1800047f5  mov     r8, rbx; dwBytes
0x1800047f8  mov     edx, edi; dwFlags
0x1800047fa  mov     rcx, rax; hHeap
0x1800047fd  call    cs:__imp_HeapAlloc
0x180004803  mov     rbx, rax
0x180004806  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000480d  test    rax, rax
0x180004810  jnz     short loc_180004858
0x180004812  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004818  jnz     short loc_180004863
0x18000481a  lea     rcx, ModuleName; "ntdll.dll"
0x180004821  call    cs:__imp_GetModuleHandleW
0x180004827  test    rax, rax
0x18000482a  jz      short loc_180004845
0x18000482c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004833  mov     rcx, rax; hModule
0x180004836  call    cs:__imp_GetProcAddress
0x18000483c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004843  jmp     short loc_18000484C
0x180004845  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000484c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004853  test    rax, rax
0x180004856  jz      short loc_180004863
0x180004858  mov     rdx, rbx
0x18000485b  mov     rcx, rsi
0x18000485e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004863  mov     rax, rbx
0x180004866  mov     rbx, [rsp+28h+arg_0]
0x18000486b  mov     rsi, [rsp+28h+arg_8]
0x180004870  add     rsp, 20h
0x180004874  pop     rdi
0x180004875  retn
```
