# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009368`
- end: `0x180009406`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800066b8`
- `0x180007e40`
- `0x18000a8a0`
- `0x18000bbec`

## callees

- `0x180009368`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800093b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800093b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800093c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800093c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000937c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000937c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000938d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000938d`

## string_xrefs

- `0x1800093aa`: `ntdll.dll`

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
0x180009368  mov     [rsp+arg_0], rbx
0x18000936d  mov     [rsp+arg_8], rsi
0x180009372  push    rdi
0x180009373  sub     rsp, 20h
0x180009377  mov     rbx, rdx
0x18000937a  mov     edi, ecx
0x18000937c  call    cs:__imp_GetProcessHeap
0x180009382  mov     rsi, rax
0x180009385  mov     r8, rbx; dwBytes
0x180009388  mov     edx, edi; dwFlags
0x18000938a  mov     rcx, rax; hHeap
0x18000938d  call    cs:__imp_HeapAlloc
0x180009393  mov     rbx, rax
0x180009396  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000939d  test    rax, rax
0x1800093a0  jnz     short loc_1800093E8
0x1800093a2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800093a8  jnz     short loc_1800093F3
0x1800093aa  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800093b1  call    cs:__imp_GetModuleHandleW
0x1800093b7  test    rax, rax
0x1800093ba  jz      short loc_1800093D5
0x1800093bc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800093c3  mov     rcx, rax; hModule
0x1800093c6  call    cs:__imp_GetProcAddress
0x1800093cc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800093d3  jmp     short loc_1800093DC
0x1800093d5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800093dc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800093e3  test    rax, rax
0x1800093e6  jz      short loc_1800093F3
0x1800093e8  mov     rdx, rbx
0x1800093eb  mov     rcx, rsi
0x1800093ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f3  mov     rax, rbx
0x1800093f6  mov     rbx, [rsp+28h+arg_0]
0x1800093fb  mov     rsi, [rsp+28h+arg_8]
0x180009400  add     rsp, 20h
0x180009404  pop     rdi
0x180009405  retn
```
