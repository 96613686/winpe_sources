# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005b7c`
- end: `0x180005c1a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004e7c`
- `0x1800058fc`
- `0x180006314`
- `0x180006450`
- `0x180008dbc`
- `0x18000a9e4`

## callees

- `0x180005b7c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005bc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005bc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005bda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005bda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ba1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ba1`

## string_xrefs

- `0x180005bbe`: `ntdll.dll`

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
0x180005b7c  mov     [rsp+arg_0], rbx
0x180005b81  mov     [rsp+arg_8], rsi
0x180005b86  push    rdi
0x180005b87  sub     rsp, 20h
0x180005b8b  mov     rbx, rdx
0x180005b8e  mov     edi, ecx
0x180005b90  call    cs:__imp_GetProcessHeap
0x180005b96  mov     r8, rbx; dwBytes
0x180005b99  mov     edx, edi; dwFlags
0x180005b9b  mov     rcx, rax; hHeap
0x180005b9e  mov     rsi, rax
0x180005ba1  call    cs:__imp_HeapAlloc
0x180005ba7  mov     rbx, rax
0x180005baa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005bb1  test    rax, rax
0x180005bb4  jnz     short loc_180005BFC
0x180005bb6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005bbc  jnz     short loc_180005C07
0x180005bbe  lea     rcx, ModuleName; "ntdll.dll"
0x180005bc5  call    cs:__imp_GetModuleHandleW
0x180005bcb  test    rax, rax
0x180005bce  jz      short loc_180005BE9
0x180005bd0  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180005bd7  mov     rcx, rax; hModule
0x180005bda  call    cs:__imp_GetProcAddress
0x180005be0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005be7  jmp     short loc_180005BF0
0x180005be9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005bf0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005bf7  test    rax, rax
0x180005bfa  jz      short loc_180005C07
0x180005bfc  mov     rdx, rbx
0x180005bff  mov     rcx, rsi
0x180005c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c07  mov     rsi, [rsp+28h+arg_8]
0x180005c0c  mov     rax, rbx
0x180005c0f  mov     rbx, [rsp+28h+arg_0]
0x180005c14  add     rsp, 20h
0x180005c18  pop     rdi
0x180005c19  retn
```
