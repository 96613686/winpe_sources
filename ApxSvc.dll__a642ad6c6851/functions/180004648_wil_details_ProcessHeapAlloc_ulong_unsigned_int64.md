# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004648`
- end: `0x1800046e6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002f08`
- `0x1800035f0`
- `0x1800049b0`

## callees

- `0x180004648`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004691`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004691`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000466d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000466d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000465c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000465c`

## string_xrefs

- `0x18000468a`: `ntdll.dll`

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
0x180004648  mov     [rsp+arg_0], rbx
0x18000464d  mov     [rsp+arg_8], rsi
0x180004652  push    rdi
0x180004653  sub     rsp, 20h
0x180004657  mov     rbx, rdx
0x18000465a  mov     edi, ecx
0x18000465c  call    cs:__imp_GetProcessHeap
0x180004662  mov     rsi, rax
0x180004665  mov     r8, rbx; dwBytes
0x180004668  mov     edx, edi; dwFlags
0x18000466a  mov     rcx, rax; hHeap
0x18000466d  call    cs:__imp_HeapAlloc
0x180004673  mov     rbx, rax
0x180004676  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000467d  test    rax, rax
0x180004680  jnz     short loc_1800046C8
0x180004682  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004688  jnz     short loc_1800046D3
0x18000468a  lea     rcx, ModuleName; "ntdll.dll"
0x180004691  call    cs:__imp_GetModuleHandleW
0x180004697  test    rax, rax
0x18000469a  jz      short loc_1800046B5
0x18000469c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800046a3  mov     rcx, rax; hModule
0x1800046a6  call    cs:__imp_GetProcAddress
0x1800046ac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800046b3  jmp     short loc_1800046BC
0x1800046b5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800046bc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800046c3  test    rax, rax
0x1800046c6  jz      short loc_1800046D3
0x1800046c8  mov     rdx, rbx
0x1800046cb  mov     rcx, rsi
0x1800046ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d3  mov     rax, rbx
0x1800046d6  mov     rbx, [rsp+28h+arg_0]
0x1800046db  mov     rsi, [rsp+28h+arg_8]
0x1800046e0  add     rsp, 20h
0x1800046e4  pop     rdi
0x1800046e5  retn
```
