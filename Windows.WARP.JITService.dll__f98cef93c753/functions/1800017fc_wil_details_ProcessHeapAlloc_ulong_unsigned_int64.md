# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800017fc`
- end: `0x18000189a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003924`
- `0x180003e00`
- `0x180004224`
- `0x180005b00`

## callees

- `0x1800017fc`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001845`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001845`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000185a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000185a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001810`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001810`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001821`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001821`

## string_xrefs

- `0x18000183e`: `ntdll.dll`

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
0x1800017fc  mov     [rsp+arg_0], rbx
0x180001801  mov     [rsp+arg_8], rsi
0x180001806  push    rdi
0x180001807  sub     rsp, 20h
0x18000180b  mov     rbx, rdx
0x18000180e  mov     edi, ecx
0x180001810  call    cs:__imp_GetProcessHeap
0x180001816  mov     rsi, rax
0x180001819  mov     r8, rbx; dwBytes
0x18000181c  mov     edx, edi; dwFlags
0x18000181e  mov     rcx, rax; hHeap
0x180001821  call    cs:__imp_HeapAlloc
0x180001827  mov     rbx, rax
0x18000182a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180001831  test    rax, rax
0x180001834  jnz     short loc_18000187C
0x180001836  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000183c  jnz     short loc_180001887
0x18000183e  lea     rcx, ModuleName; "ntdll.dll"
0x180001845  call    cs:__imp_GetModuleHandleW
0x18000184b  test    rax, rax
0x18000184e  jz      short loc_180001869
0x180001850  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180001857  mov     rcx, rax; hModule
0x18000185a  call    cs:__imp_GetProcAddress
0x180001860  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180001867  jmp     short loc_180001870
0x180001869  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180001870  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180001877  test    rax, rax
0x18000187a  jz      short loc_180001887
0x18000187c  mov     rdx, rbx
0x18000187f  mov     rcx, rsi
0x180001882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001887  mov     rax, rbx
0x18000188a  mov     rbx, [rsp+28h+arg_0]
0x18000188f  mov     rsi, [rsp+28h+arg_8]
0x180001894  add     rsp, 20h
0x180001898  pop     rdi
0x180001899  retn
```
