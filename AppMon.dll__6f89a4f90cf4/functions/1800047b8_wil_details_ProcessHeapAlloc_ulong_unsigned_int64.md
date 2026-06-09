# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800047b8`
- end: `0x180004856`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004508`
- `0x180004c3c`
- `0x180004fd4`

## callees

- `0x1800047b8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004801`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004801`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004816`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004816`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047cc`

## string_xrefs

- `0x1800047fa`: `ntdll.dll`

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
0x1800047b8  mov     [rsp+arg_0], rbx
0x1800047bd  mov     [rsp+arg_8], rsi
0x1800047c2  push    rdi
0x1800047c3  sub     rsp, 20h
0x1800047c7  mov     rbx, rdx
0x1800047ca  mov     edi, ecx
0x1800047cc  call    cs:__imp_GetProcessHeap
0x1800047d2  mov     rsi, rax
0x1800047d5  mov     r8, rbx; dwBytes
0x1800047d8  mov     edx, edi; dwFlags
0x1800047da  mov     rcx, rax; hHeap
0x1800047dd  call    cs:__imp_HeapAlloc
0x1800047e3  mov     rbx, rax
0x1800047e6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800047ed  test    rax, rax
0x1800047f0  jnz     short loc_180004838
0x1800047f2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800047f8  jnz     short loc_180004843
0x1800047fa  lea     rcx, aNtdllDll; "ntdll.dll"
0x180004801  call    cs:__imp_GetModuleHandleW
0x180004807  test    rax, rax
0x18000480a  jz      short loc_180004825
0x18000480c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004813  mov     rcx, rax; hModule
0x180004816  call    cs:__imp_GetProcAddress
0x18000481c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004823  jmp     short loc_18000482C
0x180004825  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000482c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004833  test    rax, rax
0x180004836  jz      short loc_180004843
0x180004838  mov     rdx, rbx
0x18000483b  mov     rcx, rsi
0x18000483e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004843  mov     rax, rbx
0x180004846  mov     rbx, [rsp+28h+arg_0]
0x18000484b  mov     rsi, [rsp+28h+arg_8]
0x180004850  add     rsp, 20h
0x180004854  pop     rdi
0x180004855  retn
```
