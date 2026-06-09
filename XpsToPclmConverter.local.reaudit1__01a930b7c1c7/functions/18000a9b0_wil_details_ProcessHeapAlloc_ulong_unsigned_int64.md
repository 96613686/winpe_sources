# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a9b0`
- end: `0x18000aa4e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a54c`
- `0x18000a69c`
- `0x18000b960`
- `0x18000bde8`
- `0x18000cd90`

## callees

- `0x18000a9b0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a9f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a9f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a9d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a9d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9c4`

## string_xrefs

- `0x18000a9f2`: `ntdll.dll`

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
0x18000a9b0  mov     [rsp+arg_0], rbx
0x18000a9b5  mov     [rsp+arg_8], rsi
0x18000a9ba  push    rdi
0x18000a9bb  sub     rsp, 20h
0x18000a9bf  mov     rbx, rdx
0x18000a9c2  mov     edi, ecx
0x18000a9c4  call    cs:__imp_GetProcessHeap
0x18000a9ca  mov     rsi, rax
0x18000a9cd  mov     r8, rbx; dwBytes
0x18000a9d0  mov     edx, edi; dwFlags
0x18000a9d2  mov     rcx, rax; hHeap
0x18000a9d5  call    cs:__imp_HeapAlloc
0x18000a9db  mov     rbx, rax
0x18000a9de  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a9e5  test    rax, rax
0x18000a9e8  jnz     short loc_18000AA30
0x18000a9ea  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a9f0  jnz     short loc_18000AA3B
0x18000a9f2  lea     rcx, ModuleName; "ntdll.dll"
0x18000a9f9  call    cs:__imp_GetModuleHandleW
0x18000a9ff  test    rax, rax
0x18000aa02  jz      short loc_18000AA1D
0x18000aa04  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000aa0b  mov     rcx, rax; hModule
0x18000aa0e  call    cs:__imp_GetProcAddress
0x18000aa14  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000aa1b  jmp     short loc_18000AA24
0x18000aa1d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000aa24  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000aa2b  test    rax, rax
0x18000aa2e  jz      short loc_18000AA3B
0x18000aa30  mov     rdx, rbx
0x18000aa33  mov     rcx, rsi
0x18000aa36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa3b  mov     rax, rbx
0x18000aa3e  mov     rbx, [rsp+28h+arg_0]
0x18000aa43  mov     rsi, [rsp+28h+arg_8]
0x18000aa48  add     rsp, 20h
0x18000aa4c  pop     rdi
0x18000aa4d  retn
```
