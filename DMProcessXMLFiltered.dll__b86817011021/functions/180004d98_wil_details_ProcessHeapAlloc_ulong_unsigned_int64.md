# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004d98`
- end: `0x180004e36`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800034b8`
- `0x180003d40`
- `0x1800052b0`

## callees

- `0x180004d98`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004df6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004df6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004de1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004de1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004dbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004dbd`

## string_xrefs

- `0x180004dda`: `ntdll.dll`

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
0x180004d98  mov     [rsp+arg_0], rbx
0x180004d9d  mov     [rsp+arg_8], rsi
0x180004da2  push    rdi
0x180004da3  sub     rsp, 20h
0x180004da7  mov     rbx, rdx
0x180004daa  mov     edi, ecx
0x180004dac  call    cs:__imp_GetProcessHeap
0x180004db2  mov     rsi, rax
0x180004db5  mov     r8, rbx; dwBytes
0x180004db8  mov     edx, edi; dwFlags
0x180004dba  mov     rcx, rax; hHeap
0x180004dbd  call    cs:__imp_HeapAlloc
0x180004dc3  mov     rbx, rax
0x180004dc6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004dcd  test    rax, rax
0x180004dd0  jnz     short loc_180004E18
0x180004dd2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004dd8  jnz     short loc_180004E23
0x180004dda  lea     rcx, ModuleName; "ntdll.dll"
0x180004de1  call    cs:__imp_GetModuleHandleW
0x180004de7  test    rax, rax
0x180004dea  jz      short loc_180004E05
0x180004dec  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004df3  mov     rcx, rax; hModule
0x180004df6  call    cs:__imp_GetProcAddress
0x180004dfc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004e03  jmp     short loc_180004E0C
0x180004e05  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004e0c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004e13  test    rax, rax
0x180004e16  jz      short loc_180004E23
0x180004e18  mov     rdx, rbx
0x180004e1b  mov     rcx, rsi
0x180004e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e23  mov     rax, rbx
0x180004e26  mov     rbx, [rsp+28h+arg_0]
0x180004e2b  mov     rsi, [rsp+28h+arg_8]
0x180004e30  add     rsp, 20h
0x180004e34  pop     rdi
0x180004e35  retn
```
