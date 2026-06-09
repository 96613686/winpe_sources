# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004508`
- end: `0x1400045a6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002d18`
- `0x1400034b0`
- `0x140004854`
- `0x140006064`
- `0x1400082dc`

## callees

- `0x140004508`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004551`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004551`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004566`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004566`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000451c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000451c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000452d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000452d`

## string_xrefs

- `0x14000454a`: `ntdll.dll`

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
0x140004508  mov     [rsp+arg_0], rbx
0x14000450d  mov     [rsp+arg_8], rsi
0x140004512  push    rdi
0x140004513  sub     rsp, 20h
0x140004517  mov     rbx, rdx
0x14000451a  mov     edi, ecx
0x14000451c  call    cs:__imp_GetProcessHeap
0x140004522  mov     rsi, rax
0x140004525  mov     r8, rbx; dwBytes
0x140004528  mov     edx, edi; dwFlags
0x14000452a  mov     rcx, rax; hHeap
0x14000452d  call    cs:__imp_HeapAlloc
0x140004533  mov     rbx, rax
0x140004536  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000453d  test    rax, rax
0x140004540  jnz     short loc_140004588
0x140004542  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004548  jnz     short loc_140004593
0x14000454a  lea     rcx, ModuleName; "ntdll.dll"
0x140004551  call    cs:__imp_GetModuleHandleW
0x140004557  test    rax, rax
0x14000455a  jz      short loc_140004575
0x14000455c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140004563  mov     rcx, rax; hModule
0x140004566  call    cs:__imp_GetProcAddress
0x14000456c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140004573  jmp     short loc_14000457C
0x140004575  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000457c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004583  test    rax, rax
0x140004586  jz      short loc_140004593
0x140004588  mov     rdx, rbx
0x14000458b  mov     rcx, rsi
0x14000458e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004593  mov     rax, rbx
0x140004596  mov     rbx, [rsp+28h+arg_0]
0x14000459b  mov     rsi, [rsp+28h+arg_8]
0x1400045a0  add     rsp, 20h
0x1400045a4  pop     rdi
0x1400045a5  retn
```
