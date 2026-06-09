# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800ab894`
- end: `0x1800ab933`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800693a8`
- `0x1800ab344`
- `0x1800ab470`
- `0x1800ac800`
- `0x1800acc84`

## callees

- `0x1800ab894`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ab8dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ab8dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab8f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab8f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab8a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab8a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab8b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab8b9`

## string_xrefs

- `0x1800ab8d6`: `ntdll.dll`

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
0x1800ab894  mov     [rsp+arg_0], rbx
0x1800ab899  mov     [rsp+arg_8], rsi
0x1800ab89e  push    rdi
0x1800ab89f  sub     rsp, 20h
0x1800ab8a3  mov     rbx, rdx
0x1800ab8a6  mov     edi, ecx
0x1800ab8a8  call    cs:__imp_GetProcessHeap
0x1800ab8ae  mov     rsi, rax
0x1800ab8b1  mov     r8, rbx; dwBytes
0x1800ab8b4  mov     edx, edi; dwFlags
0x1800ab8b6  mov     rcx, rax; hHeap
0x1800ab8b9  call    cs:__imp_HeapAlloc
0x1800ab8bf  mov     rbx, rax
0x1800ab8c2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800ab8c9  test    rax, rax
0x1800ab8cc  jnz     short loc_1800AB915
0x1800ab8ce  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800ab8d4  jnz     short loc_1800AB920
0x1800ab8d6  lea     rcx, ModuleName; "ntdll.dll"
0x1800ab8dd  call    cs:__imp_GetModuleHandleW
0x1800ab8e3  test    rax, rax
0x1800ab8e6  jz      short loc_1800AB902
0x1800ab8e8  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800ab8ef  mov     rcx, rax; hModule
0x1800ab8f2  call    cs:__imp_GetProcAddress
0x1800ab8f8  nop
0x1800ab8f9  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800ab900  jmp     short loc_1800AB909
0x1800ab902  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800ab909  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800ab910  test    rax, rax
0x1800ab913  jz      short loc_1800AB920
0x1800ab915  mov     rdx, rbx
0x1800ab918  mov     rcx, rsi
0x1800ab91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab920  mov     rax, rbx
0x1800ab923  mov     rbx, [rsp+28h+arg_0]
0x1800ab928  mov     rsi, [rsp+28h+arg_8]
0x1800ab92d  add     rsp, 20h
0x1800ab931  pop     rdi
0x1800ab932  retn
```
