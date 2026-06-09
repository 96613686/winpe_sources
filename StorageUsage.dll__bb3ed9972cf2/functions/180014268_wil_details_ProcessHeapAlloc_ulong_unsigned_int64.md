# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180014268`
- end: `0x180014306`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011fc0`
- `0x180013f80`
- `0x1800153d4`
- `0x18001576c`
- `0x180027d34`
- `0x18002a5bc`

## callees

- `0x180014268`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800142b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800142b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800142c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800142c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001427c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001427c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001428d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001428d`

## string_xrefs

- `0x1800142aa`: `ntdll.dll`

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
0x180014268  mov     [rsp+arg_0], rbx
0x18001426d  mov     [rsp+arg_8], rsi
0x180014272  push    rdi
0x180014273  sub     rsp, 20h
0x180014277  mov     rbx, rdx
0x18001427a  mov     edi, ecx
0x18001427c  call    cs:__imp_GetProcessHeap
0x180014282  mov     rsi, rax
0x180014285  mov     r8, rbx; dwBytes
0x180014288  mov     edx, edi; dwFlags
0x18001428a  mov     rcx, rax; hHeap
0x18001428d  call    cs:__imp_HeapAlloc
0x180014293  mov     rbx, rax
0x180014296  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001429d  test    rax, rax
0x1800142a0  jnz     short loc_1800142E8
0x1800142a2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800142a8  jnz     short loc_1800142F3
0x1800142aa  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800142b1  call    cs:__imp_GetModuleHandleW
0x1800142b7  test    rax, rax
0x1800142ba  jz      short loc_1800142D5
0x1800142bc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800142c3  mov     rcx, rax; hModule
0x1800142c6  call    cs:__imp_GetProcAddress
0x1800142cc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800142d3  jmp     short loc_1800142DC
0x1800142d5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800142dc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800142e3  test    rax, rax
0x1800142e6  jz      short loc_1800142F3
0x1800142e8  mov     rdx, rbx
0x1800142eb  mov     rcx, rsi
0x1800142ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142f3  mov     rax, rbx
0x1800142f6  mov     rbx, [rsp+28h+arg_0]
0x1800142fb  mov     rsi, [rsp+28h+arg_8]
0x180014300  add     rsp, 20h
0x180014304  pop     rdi
0x180014305  retn
```
