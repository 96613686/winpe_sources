# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180014390`
- end: `0x18001442e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180027634`
- `0x1800279a0`
- `0x180027adc`
- `0x1800295d8`
- `0x18002ac64`

## callees

- `0x180014390`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001441f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001441f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800143d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800143d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800143b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800143b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800143a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800143a4`

## string_xrefs

- `0x1800143d2`: `ntdll.dll`

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
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) != 0
      ? (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress)
      : (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation),
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
0x180014390  mov     [rsp+arg_0], rbx
0x180014395  mov     [rsp+arg_8], rsi
0x18001439a  push    rdi
0x18001439b  sub     rsp, 20h
0x18001439f  mov     rbx, rdx
0x1800143a2  mov     edi, ecx
0x1800143a4  call    cs:__imp_GetProcessHeap
0x1800143aa  mov     rsi, rax
0x1800143ad  mov     r8, rbx; dwBytes
0x1800143b0  mov     edx, edi; dwFlags
0x1800143b2  mov     rcx, rax; hHeap
0x1800143b5  call    cs:__imp_HeapAlloc
0x1800143bb  mov     rbx, rax
0x1800143be  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800143c5  test    rax, rax
0x1800143c8  jnz     short loc_1800143F7
0x1800143ca  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800143d0  jnz     short loc_180014402
0x1800143d2  lea     rcx, ModuleName; "ntdll.dll"
0x1800143d9  call    cs:__imp_GetModuleHandleW
0x1800143df  test    rax, rax
0x1800143e2  jnz     short loc_180014415
0x1800143e4  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800143eb  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800143f2  test    rax, rax
0x1800143f5  jz      short loc_180014402
0x1800143f7  mov     rdx, rbx
0x1800143fa  mov     rcx, rsi
0x1800143fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014402  mov     rax, rbx
0x180014405  mov     rbx, [rsp+28h+arg_0]
0x18001440a  mov     rsi, [rsp+28h+arg_8]
0x18001440f  add     rsp, 20h
0x180014413  pop     rdi
0x180014414  retn
0x180014415  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18001441c  mov     rcx, rax; hModule
0x18001441f  call    cs:__imp_GetProcAddress
0x180014425  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001442c  jmp     short loc_1800143EB
```
