# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005cd8`
- end: `0x180005d76`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003bf8`
- `0x180003f9c`
- `0x180004b70`
- `0x1800070f4`
- `0x18000877c`

## callees

- `0x180005cd8`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005d36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005d36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005d21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005d21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005cfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005cfd`

## string_xrefs

- `0x180005d1a`: `ntdll.dll`

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
0x180005cd8  mov     [rsp+arg_0], rbx
0x180005cdd  mov     [rsp+arg_8], rsi
0x180005ce2  push    rdi
0x180005ce3  sub     rsp, 20h
0x180005ce7  mov     rbx, rdx
0x180005cea  mov     edi, ecx
0x180005cec  call    cs:__imp_GetProcessHeap
0x180005cf2  mov     rsi, rax
0x180005cf5  mov     r8, rbx; dwBytes
0x180005cf8  mov     edx, edi; dwFlags
0x180005cfa  mov     rcx, rax; hHeap
0x180005cfd  call    cs:__imp_HeapAlloc
0x180005d03  mov     rbx, rax
0x180005d06  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005d0d  test    rax, rax
0x180005d10  jnz     short loc_180005D58
0x180005d12  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005d18  jnz     short loc_180005D63
0x180005d1a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180005d21  call    cs:__imp_GetModuleHandleW
0x180005d27  test    rax, rax
0x180005d2a  jz      short loc_180005D45
0x180005d2c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005d33  mov     rcx, rax; hModule
0x180005d36  call    cs:__imp_GetProcAddress
0x180005d3c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005d43  jmp     short loc_180005D4C
0x180005d45  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005d4c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005d53  test    rax, rax
0x180005d56  jz      short loc_180005D63
0x180005d58  mov     rdx, rbx
0x180005d5b  mov     rcx, rsi
0x180005d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d63  mov     rax, rbx
0x180005d66  mov     rbx, [rsp+28h+arg_0]
0x180005d6b  mov     rsi, [rsp+28h+arg_8]
0x180005d70  add     rsp, 20h
0x180005d74  pop     rdi
0x180005d75  retn
```
