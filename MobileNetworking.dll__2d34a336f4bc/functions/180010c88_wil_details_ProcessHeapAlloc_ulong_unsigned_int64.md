# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010c88`
- end: `0x180010d26`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010b38`
- `0x180010f0c`
- `0x180011084`

## callees

- `0x180010c88`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010cd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010cd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010ce6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010ce6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010cad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010cad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c9c`

## string_xrefs

- `0x180010cca`: `ntdll.dll`

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
0x180010c88  mov     [rsp+arg_0], rbx
0x180010c8d  mov     [rsp+arg_8], rsi
0x180010c92  push    rdi
0x180010c93  sub     rsp, 20h
0x180010c97  mov     rbx, rdx
0x180010c9a  mov     edi, ecx
0x180010c9c  call    cs:__imp_GetProcessHeap
0x180010ca2  mov     r8, rbx; dwBytes
0x180010ca5  mov     edx, edi; dwFlags
0x180010ca7  mov     rcx, rax; hHeap
0x180010caa  mov     rsi, rax
0x180010cad  call    cs:__imp_HeapAlloc
0x180010cb3  mov     rbx, rax
0x180010cb6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010cbd  test    rax, rax
0x180010cc0  jnz     short loc_180010D08
0x180010cc2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180010cc8  jnz     short loc_180010D13
0x180010cca  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180010cd1  call    cs:__imp_GetModuleHandleW
0x180010cd7  test    rax, rax
0x180010cda  jz      short loc_180010CF5
0x180010cdc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180010ce3  mov     rcx, rax; hModule
0x180010ce6  call    cs:__imp_GetProcAddress
0x180010cec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180010cf3  jmp     short loc_180010CFC
0x180010cf5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010cfc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180010d03  test    rax, rax
0x180010d06  jz      short loc_180010D13
0x180010d08  mov     rdx, rbx
0x180010d0b  mov     rcx, rsi
0x180010d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d13  mov     rsi, [rsp+28h+arg_8]
0x180010d18  mov     rax, rbx
0x180010d1b  mov     rbx, [rsp+28h+arg_0]
0x180010d20  add     rsp, 20h
0x180010d24  pop     rdi
0x180010d25  retn
```
