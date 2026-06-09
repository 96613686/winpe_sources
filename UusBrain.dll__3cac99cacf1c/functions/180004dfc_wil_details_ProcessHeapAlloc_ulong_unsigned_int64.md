# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004dfc`
- end: `0x180004e9a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006864`
- `0x180006cc0`
- `0x180007ef8`

## callees

- `0x180004dfc`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e45`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e10`

## string_xrefs

- `0x180004e3e`: `ntdll.dll`

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
0x180004dfc  mov     [rsp+arg_0], rbx
0x180004e01  mov     [rsp+arg_8], rsi
0x180004e06  push    rdi
0x180004e07  sub     rsp, 20h
0x180004e0b  mov     rbx, rdx
0x180004e0e  mov     edi, ecx
0x180004e10  call    cs:__imp_GetProcessHeap
0x180004e16  mov     rsi, rax
0x180004e19  mov     r8, rbx; dwBytes
0x180004e1c  mov     edx, edi; dwFlags
0x180004e1e  mov     rcx, rax; hHeap
0x180004e21  call    cs:__imp_HeapAlloc
0x180004e27  mov     rbx, rax
0x180004e2a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004e31  test    rax, rax
0x180004e34  jnz     short loc_180004E7C
0x180004e36  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004e3c  jnz     short loc_180004E87
0x180004e3e  lea     rcx, ModuleName; "ntdll.dll"
0x180004e45  call    cs:__imp_GetModuleHandleW
0x180004e4b  test    rax, rax
0x180004e4e  jz      short loc_180004E69
0x180004e50  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180004e57  mov     rcx, rax; hModule
0x180004e5a  call    cs:__imp_GetProcAddress
0x180004e60  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004e67  jmp     short loc_180004E70
0x180004e69  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004e70  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004e77  test    rax, rax
0x180004e7a  jz      short loc_180004E87
0x180004e7c  mov     rdx, rbx
0x180004e7f  mov     rcx, rsi
0x180004e82  call    _guard_dispatch_icall
0x180004e87  mov     rax, rbx
0x180004e8a  mov     rbx, [rsp+28h+arg_0]
0x180004e8f  mov     rsi, [rsp+28h+arg_8]
0x180004e94  add     rsp, 20h
0x180004e98  pop     rdi
0x180004e99  retn
```
