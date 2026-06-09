# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800043f8`
- end: `0x180004496`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002d18`
- `0x1800033b0`
- `0x180004760`

## callees

- `0x1800043f8`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004441`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004441`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004456`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004456`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000440c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000440c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000441d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000441d`

## string_xrefs

- `0x18000443a`: `ntdll.dll`

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
0x1800043f8  mov     [rsp+arg_0], rbx
0x1800043fd  mov     [rsp+arg_8], rsi
0x180004402  push    rdi
0x180004403  sub     rsp, 20h
0x180004407  mov     rbx, rdx
0x18000440a  mov     edi, ecx
0x18000440c  call    cs:__imp_GetProcessHeap
0x180004412  mov     rsi, rax
0x180004415  mov     r8, rbx; dwBytes
0x180004418  mov     edx, edi; dwFlags
0x18000441a  mov     rcx, rax; hHeap
0x18000441d  call    cs:__imp_HeapAlloc
0x180004423  mov     rbx, rax
0x180004426  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000442d  test    rax, rax
0x180004430  jnz     short loc_180004478
0x180004432  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004438  jnz     short loc_180004483
0x18000443a  lea     rcx, ModuleName; "ntdll.dll"
0x180004441  call    cs:__imp_GetModuleHandleW
0x180004447  test    rax, rax
0x18000444a  jz      short loc_180004465
0x18000444c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004453  mov     rcx, rax; hModule
0x180004456  call    cs:__imp_GetProcAddress
0x18000445c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004463  jmp     short loc_18000446C
0x180004465  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000446c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004473  test    rax, rax
0x180004476  jz      short loc_180004483
0x180004478  mov     rdx, rbx
0x18000447b  mov     rcx, rsi
0x18000447e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004483  mov     rax, rbx
0x180004486  mov     rbx, [rsp+28h+arg_0]
0x18000448b  mov     rsi, [rsp+28h+arg_8]
0x180004490  add     rsp, 20h
0x180004494  pop     rdi
0x180004495  retn
```
