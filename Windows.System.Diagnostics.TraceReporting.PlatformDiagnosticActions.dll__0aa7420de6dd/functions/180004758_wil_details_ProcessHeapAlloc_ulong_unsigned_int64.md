# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004758`
- end: `0x1800047f6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003018`
- `0x180003700`
- `0x180004c50`

## callees

- `0x180004758`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800047b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800047b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800047a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800047a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000477d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000477d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000476c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000476c`

## string_xrefs

- `0x18000479a`: `ntdll.dll`

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
0x180004758  mov     [rsp+arg_0], rbx
0x18000475d  mov     [rsp+arg_8], rsi
0x180004762  push    rdi
0x180004763  sub     rsp, 20h
0x180004767  mov     rbx, rdx
0x18000476a  mov     edi, ecx
0x18000476c  call    cs:__imp_GetProcessHeap
0x180004772  mov     rsi, rax
0x180004775  mov     r8, rbx; dwBytes
0x180004778  mov     edx, edi; dwFlags
0x18000477a  mov     rcx, rax; hHeap
0x18000477d  call    cs:__imp_HeapAlloc
0x180004783  mov     rbx, rax
0x180004786  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000478d  test    rax, rax
0x180004790  jnz     short loc_1800047D8
0x180004792  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004798  jnz     short loc_1800047E3
0x18000479a  lea     rcx, ModuleName; "ntdll.dll"
0x1800047a1  call    cs:__imp_GetModuleHandleW
0x1800047a7  test    rax, rax
0x1800047aa  jz      short loc_1800047C5
0x1800047ac  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800047b3  mov     rcx, rax; hModule
0x1800047b6  call    cs:__imp_GetProcAddress
0x1800047bc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800047c3  jmp     short loc_1800047CC
0x1800047c5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800047cc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800047d3  test    rax, rax
0x1800047d6  jz      short loc_1800047E3
0x1800047d8  mov     rdx, rbx
0x1800047db  mov     rcx, rsi
0x1800047de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047e3  mov     rax, rbx
0x1800047e6  mov     rbx, [rsp+28h+arg_0]
0x1800047eb  mov     rsi, [rsp+28h+arg_8]
0x1800047f0  add     rsp, 20h
0x1800047f4  pop     rdi
0x1800047f5  retn
```
