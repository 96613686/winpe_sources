# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800056bc`
- end: `0x18000575a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003648`
- `0x1800046ac`
- `0x1800063a8`

## callees

- `0x1800056bc`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000571a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000571a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005705`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005705`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800056e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800056e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d0`

## string_xrefs

- `0x1800056fe`: `ntdll.dll`

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
0x1800056bc  mov     [rsp+arg_0], rbx
0x1800056c1  mov     [rsp+arg_8], rsi
0x1800056c6  push    rdi
0x1800056c7  sub     rsp, 20h
0x1800056cb  mov     rbx, rdx
0x1800056ce  mov     edi, ecx
0x1800056d0  call    cs:__imp_GetProcessHeap
0x1800056d6  mov     r8, rbx; dwBytes
0x1800056d9  mov     edx, edi; dwFlags
0x1800056db  mov     rcx, rax; hHeap
0x1800056de  mov     rsi, rax
0x1800056e1  call    cs:__imp_HeapAlloc
0x1800056e7  mov     rbx, rax
0x1800056ea  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800056f1  test    rax, rax
0x1800056f4  jnz     short loc_18000573C
0x1800056f6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800056fc  jnz     short loc_180005747
0x1800056fe  lea     rcx, ModuleName; "ntdll.dll"
0x180005705  call    cs:__imp_GetModuleHandleW
0x18000570b  test    rax, rax
0x18000570e  jz      short loc_180005729
0x180005710  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005717  mov     rcx, rax; hModule
0x18000571a  call    cs:__imp_GetProcAddress
0x180005720  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005727  jmp     short loc_180005730
0x180005729  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005730  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005737  test    rax, rax
0x18000573a  jz      short loc_180005747
0x18000573c  mov     rdx, rbx
0x18000573f  mov     rcx, rsi
0x180005742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005747  mov     rsi, [rsp+28h+arg_8]
0x18000574c  mov     rax, rbx
0x18000574f  mov     rbx, [rsp+28h+arg_0]
0x180005754  add     rsp, 20h
0x180005758  pop     rdi
0x180005759  retn
```
