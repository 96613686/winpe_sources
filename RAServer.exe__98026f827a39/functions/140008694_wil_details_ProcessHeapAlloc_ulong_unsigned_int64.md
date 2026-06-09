# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140008694`
- end: `0x140008732`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007d8c`
- `0x140007ee0`
- `0x14000a288`
- `0x14000a70c`
- `0x14000c274`

## callees

- `0x140008694`
- `0x140017010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400086b9`
- `KERNEL32!HeapAlloc` at `0x1400086b9`
- `KERNEL32!GetProcAddress` at `0x1400086f2`
- `KERNEL32!GetProcAddress` at `0x1400086f2`
- `KERNEL32!GetProcessHeap` at `0x1400086a8`
- `KERNEL32!GetProcessHeap` at `0x1400086a8`
- `KERNEL32!GetModuleHandleW` at `0x1400086dd`
- `KERNEL32!GetModuleHandleW` at `0x1400086dd`

## string_xrefs

- `0x1400086d6`: `ntdll.dll`

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
0x140008694  mov     [rsp+arg_0], rbx
0x140008699  mov     [rsp+arg_8], rsi
0x14000869e  push    rdi
0x14000869f  sub     rsp, 20h
0x1400086a3  mov     rbx, rdx
0x1400086a6  mov     edi, ecx
0x1400086a8  call    cs:__imp_GetProcessHeap
0x1400086ae  mov     rsi, rax
0x1400086b1  mov     r8, rbx; dwBytes
0x1400086b4  mov     edx, edi; dwFlags
0x1400086b6  mov     rcx, rax; hHeap
0x1400086b9  call    cs:__imp_HeapAlloc
0x1400086bf  mov     rbx, rax
0x1400086c2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400086c9  test    rax, rax
0x1400086cc  jnz     short loc_140008714
0x1400086ce  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400086d4  jnz     short loc_14000871F
0x1400086d6  lea     rcx, aNtdllDll; "ntdll.dll"
0x1400086dd  call    cs:__imp_GetModuleHandleW
0x1400086e3  test    rax, rax
0x1400086e6  jz      short loc_140008701
0x1400086e8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400086ef  mov     rcx, rax; hModule
0x1400086f2  call    cs:__imp_GetProcAddress
0x1400086f8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400086ff  jmp     short loc_140008708
0x140008701  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140008708  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000870f  test    rax, rax
0x140008712  jz      short loc_14000871F
0x140008714  mov     rdx, rbx
0x140008717  mov     rcx, rsi
0x14000871a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000871f  mov     rax, rbx
0x140008722  mov     rbx, [rsp+28h+arg_0]
0x140008727  mov     rsi, [rsp+28h+arg_8]
0x14000872c  add     rsp, 20h
0x140008730  pop     rdi
0x140008731  retn
```
