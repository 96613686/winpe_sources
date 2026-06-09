# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000d154`
- end: `0x18000d20b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a82c`
- `0x18000abf0`
- `0x18000ec30`
- `0x18000f49c`
- `0x180010684`

## callees

- `0x18000d154`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d1c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d1c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d1a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d1a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d168`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d168`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d17f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d17f`

## string_xrefs

- `0x18000d1a2`: `ntdll.dll`

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
0x18000d154  mov     [rsp+arg_0], rbx
0x18000d159  mov     [rsp+arg_8], rsi
0x18000d15e  push    rdi
0x18000d15f  sub     rsp, 20h
0x18000d163  mov     rbx, rdx
0x18000d166  mov     edi, ecx
0x18000d168  call    cs:__imp_GetProcessHeap
0x18000d16f  nop     dword ptr [rax+rax+00h]
0x18000d174  mov     rsi, rax
0x18000d177  mov     r8, rbx; dwBytes
0x18000d17a  mov     edx, edi; dwFlags
0x18000d17c  mov     rcx, rax; hHeap
0x18000d17f  call    cs:__imp_HeapAlloc
0x18000d186  nop     dword ptr [rax+rax+00h]
0x18000d18b  mov     rbx, rax
0x18000d18e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d195  test    rax, rax
0x18000d198  jnz     short loc_18000D1EC
0x18000d19a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d1a0  jnz     short loc_18000D1F7
0x18000d1a2  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000d1a9  call    cs:__imp_GetModuleHandleW
0x18000d1b0  nop     dword ptr [rax+rax+00h]
0x18000d1b5  test    rax, rax
0x18000d1b8  jz      short loc_18000D1D9
0x18000d1ba  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000d1c1  mov     rcx, rax; hModule
0x18000d1c4  call    cs:__imp_GetProcAddress
0x18000d1cb  nop     dword ptr [rax+rax+00h]
0x18000d1d0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000d1d7  jmp     short loc_18000D1E0
0x18000d1d9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d1e0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d1e7  test    rax, rax
0x18000d1ea  jz      short loc_18000D1F7
0x18000d1ec  mov     rdx, rbx
0x18000d1ef  mov     rcx, rsi
0x18000d1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1f7  mov     rax, rbx
0x18000d1fa  mov     rbx, [rsp+28h+arg_0]
0x18000d1ff  mov     rsi, [rsp+28h+arg_8]
0x18000d204  add     rsp, 20h
0x18000d208  pop     rdi
0x18000d209  retn
```
