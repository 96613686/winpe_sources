# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001429c`
- end: `0x18001433a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a498`
- `0x180052a80`
- `0x180052bb8`
- `0x180053f60`
- `0x1800543f0`

## callees

- `0x18001429c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800142fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800142fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800142e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800142e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142b0`

## string_xrefs

- `0x1800142de`: `ntdll.dll`

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
0x18001429c  mov     [rsp+arg_0], rbx
0x1800142a1  mov     [rsp+arg_8], rsi
0x1800142a6  push    rdi
0x1800142a7  sub     rsp, 20h
0x1800142ab  mov     rbx, rdx
0x1800142ae  mov     edi, ecx
0x1800142b0  call    cs:__imp_GetProcessHeap
0x1800142b6  mov     rsi, rax
0x1800142b9  mov     r8, rbx; dwBytes
0x1800142bc  mov     edx, edi; dwFlags
0x1800142be  mov     rcx, rax; hHeap
0x1800142c1  call    cs:__imp_HeapAlloc
0x1800142c7  mov     rbx, rax
0x1800142ca  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800142d1  test    rax, rax
0x1800142d4  jnz     short loc_18001431C
0x1800142d6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800142dc  jnz     short loc_180014327
0x1800142de  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800142e5  call    cs:__imp_GetModuleHandleW
0x1800142eb  test    rax, rax
0x1800142ee  jz      short loc_180014309
0x1800142f0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800142f7  mov     rcx, rax; hModule
0x1800142fa  call    cs:__imp_GetProcAddress
0x180014300  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180014307  jmp     short loc_180014310
0x180014309  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014310  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180014317  test    rax, rax
0x18001431a  jz      short loc_180014327
0x18001431c  mov     rdx, rbx
0x18001431f  mov     rcx, rsi
0x180014322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014327  mov     rax, rbx
0x18001432a  mov     rbx, [rsp+28h+arg_0]
0x18001432f  mov     rsi, [rsp+28h+arg_8]
0x180014334  add     rsp, 20h
0x180014338  pop     rdi
0x180014339  retn
```
