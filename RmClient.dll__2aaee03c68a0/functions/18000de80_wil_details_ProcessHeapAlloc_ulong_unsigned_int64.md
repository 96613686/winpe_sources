# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000de80`
- end: `0x18000df1e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800058c0`
- `0x180005cf0`
- `0x180005e60`
- `0x180005fb8`
- `0x180006130`
- `0x18000ba60`
- `0x180016a08`
- `0x180016b4c`
- `0x180017024`
- `0x18001719c`

## callees

- `0x18000de80`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dec9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dec9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dede`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dede`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dea5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dea5`

## string_xrefs

- `0x18000dec2`: `ntdll.dll`

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
0x18000de80  mov     [rsp+arg_0], rbx
0x18000de85  mov     [rsp+arg_8], rsi
0x18000de8a  push    rdi
0x18000de8b  sub     rsp, 20h
0x18000de8f  mov     rbx, rdx
0x18000de92  mov     edi, ecx
0x18000de94  call    cs:__imp_GetProcessHeap
0x18000de9a  mov     r8, rbx; dwBytes
0x18000de9d  mov     edx, edi; dwFlags
0x18000de9f  mov     rcx, rax; hHeap
0x18000dea2  mov     rsi, rax
0x18000dea5  call    cs:__imp_HeapAlloc
0x18000deab  mov     rbx, rax
0x18000deae  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000deb5  test    rax, rax
0x18000deb8  jnz     short loc_18000DEF7
0x18000deba  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000dec0  jnz     short loc_18000DF02
0x18000dec2  lea     rcx, ModuleName; "ntdll.dll"
0x18000dec9  call    cs:__imp_GetModuleHandleW
0x18000decf  test    rax, rax
0x18000ded2  jz      short loc_18000DF15
0x18000ded4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000dedb  mov     rcx, rax; hModule
0x18000dede  call    cs:__imp_GetProcAddress
0x18000dee4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000deeb  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000def2  test    rax, rax
0x18000def5  jz      short loc_18000DF02
0x18000def7  mov     rdx, rbx
0x18000defa  mov     rcx, rsi
0x18000defd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df02  mov     rsi, [rsp+28h+arg_8]
0x18000df07  mov     rax, rbx
0x18000df0a  mov     rbx, [rsp+28h+arg_0]
0x18000df0f  add     rsp, 20h
0x18000df13  pop     rdi
0x18000df14  retn
0x18000df15  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000df1c  jmp     short loc_18000DEEB
```
