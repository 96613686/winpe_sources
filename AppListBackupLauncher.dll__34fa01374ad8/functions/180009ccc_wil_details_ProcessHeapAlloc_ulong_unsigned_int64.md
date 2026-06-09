# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009ccc`
- end: `0x180009d6a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800068a8`
- `0x180006c4c`
- `0x1800081c0`
- `0x180008988`
- `0x18000c0a4`
- `0x18000eb4c`

## callees

- `0x180009ccc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009cf1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009cf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ce0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ce0`

## string_xrefs

- `0x180009d0e`: `ntdll.dll`

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
0x180009ccc  mov     [rsp+arg_0], rbx
0x180009cd1  mov     [rsp+arg_8], rsi
0x180009cd6  push    rdi
0x180009cd7  sub     rsp, 20h
0x180009cdb  mov     rbx, rdx
0x180009cde  mov     edi, ecx
0x180009ce0  call    cs:__imp_GetProcessHeap
0x180009ce6  mov     rsi, rax
0x180009ce9  mov     r8, rbx; dwBytes
0x180009cec  mov     edx, edi; dwFlags
0x180009cee  mov     rcx, rax; hHeap
0x180009cf1  call    cs:__imp_HeapAlloc
0x180009cf7  mov     rbx, rax
0x180009cfa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009d01  test    rax, rax
0x180009d04  jnz     short loc_180009D4C
0x180009d06  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009d0c  jnz     short loc_180009D57
0x180009d0e  lea     rcx, ModuleName; "ntdll.dll"
0x180009d15  call    cs:__imp_GetModuleHandleW
0x180009d1b  test    rax, rax
0x180009d1e  jz      short loc_180009D39
0x180009d20  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180009d27  mov     rcx, rax; hModule
0x180009d2a  call    cs:__imp_GetProcAddress
0x180009d30  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180009d37  jmp     short loc_180009D40
0x180009d39  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009d40  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009d47  test    rax, rax
0x180009d4a  jz      short loc_180009D57
0x180009d4c  mov     rdx, rbx
0x180009d4f  mov     rcx, rsi
0x180009d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d57  mov     rax, rbx
0x180009d5a  mov     rbx, [rsp+28h+arg_0]
0x180009d5f  mov     rsi, [rsp+28h+arg_8]
0x180009d64  add     rsp, 20h
0x180009d68  pop     rdi
0x180009d69  retn
```
