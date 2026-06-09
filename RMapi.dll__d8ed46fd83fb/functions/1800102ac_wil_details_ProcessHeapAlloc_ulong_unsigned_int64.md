# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800102ac`
- end: `0x180010342`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010140`
- `0x18001048c`
- `0x1800105c8`
- `0x180013abc`
- `0x180016c6c`

## callees

- `0x18000f088`
- `0x1800102ac`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800102f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800102f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800102c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800102c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800102d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800102d1`

## string_xrefs

- `0x1800102ee`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  void (__fastcall *ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(HANDLE, LPVOID); // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (void (__fastcall *)(HANDLE, LPVOID))(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW),
                                              `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z) )
  {
    ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1800102ac  mov     [rsp+arg_0], rbx
0x1800102b1  mov     [rsp+arg_8], rsi
0x1800102b6  push    rdi
0x1800102b7  sub     rsp, 20h
0x1800102bb  mov     rbx, rdx
0x1800102be  mov     edi, ecx
0x1800102c0  call    cs:__imp_GetProcessHeap
0x1800102c6  mov     rsi, rax
0x1800102c9  mov     r8, rbx; dwBytes
0x1800102cc  mov     edx, edi; dwFlags
0x1800102ce  mov     rcx, rax; hHeap
0x1800102d1  call    cs:__imp_HeapAlloc
0x1800102d7  mov     rbx, rax
0x1800102da  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800102e1  test    rax, rax
0x1800102e4  jnz     short loc_180010324
0x1800102e6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800102ec  jnz     short loc_18001032F
0x1800102ee  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800102f5  call    cs:__imp_GetModuleHandleW
0x1800102fb  test    rax, rax
0x1800102fe  jz      short loc_180010311
0x180010300  mov     rcx, rax
0x180010303  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180010308  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001030f  jmp     short loc_180010318
0x180010311  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010318  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001031f  test    rax, rax
0x180010322  jz      short loc_18001032F
0x180010324  mov     rdx, rbx
0x180010327  mov     rcx, rsi
0x18001032a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001032f  mov     rax, rbx
0x180010332  mov     rbx, [rsp+28h+arg_0]
0x180010337  mov     rsi, [rsp+28h+arg_8]
0x18001033c  add     rsp, 20h
0x180010340  pop     rdi
0x180010341  retn
```
