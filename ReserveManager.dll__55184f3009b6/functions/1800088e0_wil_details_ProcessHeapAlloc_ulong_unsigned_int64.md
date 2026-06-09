# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800088e0`
- end: `0x180008988`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800061c8`
- `0x180006598`
- `0x180007390`
- `0x180007990`
- `0x18000a210`
- `0x18000c0cc`

## callees

- `0x1800088e0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180008933`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180008933`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180008948`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180008948`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000890f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000890f`

## string_xrefs

- `0x18000892c`: `ntdll.dll`

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
0x1800088e0  push    rdi
0x1800088e2  sub     rsp, 30h
0x1800088e6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800088ef  mov     [rsp+38h+arg_0], rbx
0x1800088f4  mov     [rsp+38h+arg_8], rsi
0x1800088f9  mov     rbx, rdx
0x1800088fc  mov     edi, ecx
0x1800088fe  call    cs:__imp_GetProcessHeap
0x180008904  mov     rsi, rax
0x180008907  mov     r8, rbx; dwBytes
0x18000890a  mov     edx, edi; dwFlags
0x18000890c  mov     rcx, rax; hHeap
0x18000890f  call    cs:__imp_HeapAlloc
0x180008915  mov     rbx, rax
0x180008918  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000891f  test    rax, rax
0x180008922  jnz     short loc_18000896A
0x180008924  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000892a  jnz     short loc_180008975
0x18000892c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008933  call    cs:__imp_GetModuleHandleW
0x180008939  test    rax, rax
0x18000893c  jz      short loc_180008957
0x18000893e  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008945  mov     rcx, rax; hModule
0x180008948  call    cs:__imp_GetProcAddress
0x18000894e  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008955  jmp     short loc_18000895E
0x180008957  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000895e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008965  test    rax, rax
0x180008968  jz      short loc_180008975
0x18000896a  mov     rdx, rbx
0x18000896d  mov     rcx, rsi
0x180008970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008975  mov     rax, rbx
0x180008978  mov     rbx, [rsp+38h+arg_0]
0x18000897d  mov     rsi, [rsp+38h+arg_8]
0x180008982  add     rsp, 30h
0x180008986  pop     rdi
0x180008987  retn
```
