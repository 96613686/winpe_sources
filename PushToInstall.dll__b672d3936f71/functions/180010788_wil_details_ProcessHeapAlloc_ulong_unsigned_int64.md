# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010788`
- end: `0x180010826`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ef68`
- `0x18000f730`
- `0x180010c74`
- `0x180012814`
- `0x1800159cc`

## callees

- `0x180010788`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800107d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800107d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800107ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800107ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001079c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001079c`

## string_xrefs

- `0x1800107ca`: `ntdll.dll`

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
0x180010788  mov     [rsp+arg_0], rbx
0x18001078d  mov     [rsp+arg_8], rsi
0x180010792  push    rdi
0x180010793  sub     rsp, 20h
0x180010797  mov     rbx, rdx
0x18001079a  mov     edi, ecx
0x18001079c  call    cs:__imp_GetProcessHeap
0x1800107a2  mov     rsi, rax
0x1800107a5  mov     r8, rbx; dwBytes
0x1800107a8  mov     edx, edi; dwFlags
0x1800107aa  mov     rcx, rax; hHeap
0x1800107ad  call    cs:__imp_HeapAlloc
0x1800107b3  mov     rbx, rax
0x1800107b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800107bd  test    rax, rax
0x1800107c0  jnz     short loc_180010808
0x1800107c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800107c8  jnz     short loc_180010813
0x1800107ca  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800107d1  call    cs:__imp_GetModuleHandleW
0x1800107d7  test    rax, rax
0x1800107da  jz      short loc_1800107F5
0x1800107dc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800107e3  mov     rcx, rax; hModule
0x1800107e6  call    cs:__imp_GetProcAddress
0x1800107ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800107f3  jmp     short loc_1800107FC
0x1800107f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800107fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180010803  test    rax, rax
0x180010806  jz      short loc_180010813
0x180010808  mov     rdx, rbx
0x18001080b  mov     rcx, rsi
0x18001080e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010813  mov     rax, rbx
0x180010816  mov     rbx, [rsp+28h+arg_0]
0x18001081b  mov     rsi, [rsp+28h+arg_8]
0x180010820  add     rsp, 20h
0x180010824  pop     rdi
0x180010825  retn
```
