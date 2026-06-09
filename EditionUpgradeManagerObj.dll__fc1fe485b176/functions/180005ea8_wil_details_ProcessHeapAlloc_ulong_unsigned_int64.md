# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005ea8`
- end: `0x180005f46`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003bc4`
- `0x180003f94`
- `0x180004c80`
- `0x180007528`
- `0x18000877c`

## callees

- `0x180005ea8`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f06`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ef1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ef1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ecd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ecd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ebc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ebc`

## string_xrefs

- `0x180005eea`: `ntdll.dll`

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
0x180005ea8  mov     [rsp+arg_0], rbx
0x180005ead  mov     [rsp+arg_8], rsi
0x180005eb2  push    rdi
0x180005eb3  sub     rsp, 20h
0x180005eb7  mov     rbx, rdx
0x180005eba  mov     edi, ecx
0x180005ebc  call    cs:__imp_GetProcessHeap
0x180005ec2  mov     r8, rbx; dwBytes
0x180005ec5  mov     edx, edi; dwFlags
0x180005ec7  mov     rcx, rax; hHeap
0x180005eca  mov     rsi, rax
0x180005ecd  call    cs:__imp_HeapAlloc
0x180005ed3  mov     rbx, rax
0x180005ed6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005edd  test    rax, rax
0x180005ee0  jnz     short loc_180005F28
0x180005ee2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005ee8  jnz     short loc_180005F33
0x180005eea  lea     rcx, ModuleName; "ntdll.dll"
0x180005ef1  call    cs:__imp_GetModuleHandleW
0x180005ef7  test    rax, rax
0x180005efa  jz      short loc_180005F15
0x180005efc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005f03  mov     rcx, rax; hModule
0x180005f06  call    cs:__imp_GetProcAddress
0x180005f0c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005f13  jmp     short loc_180005F1C
0x180005f15  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005f1c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005f23  test    rax, rax
0x180005f26  jz      short loc_180005F33
0x180005f28  mov     rdx, rbx
0x180005f2b  mov     rcx, rsi
0x180005f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f33  mov     rsi, [rsp+28h+arg_8]
0x180005f38  mov     rax, rbx
0x180005f3b  mov     rbx, [rsp+28h+arg_0]
0x180005f40  add     rsp, 20h
0x180005f44  pop     rdi
0x180005f45  retn
```
