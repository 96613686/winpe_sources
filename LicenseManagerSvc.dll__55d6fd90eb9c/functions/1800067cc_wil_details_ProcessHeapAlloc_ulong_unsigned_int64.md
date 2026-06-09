# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800067cc`
- end: `0x180006862`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006538`
- `0x180006d40`
- `0x1800070d8`
- `0x1800093e0`
- `0x18000b478`

## callees

- `0x180004350`
- `0x1800067cc`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006815`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006815`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067e0`

## string_xrefs

- `0x18000680e`: `ntdll.dll`

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
0x1800067cc  mov     [rsp+arg_0], rbx
0x1800067d1  mov     [rsp+arg_8], rsi
0x1800067d6  push    rdi
0x1800067d7  sub     rsp, 20h
0x1800067db  mov     rbx, rdx
0x1800067de  mov     edi, ecx
0x1800067e0  call    cs:__imp_GetProcessHeap
0x1800067e6  mov     rsi, rax
0x1800067e9  mov     r8, rbx; dwBytes
0x1800067ec  mov     edx, edi; dwFlags
0x1800067ee  mov     rcx, rax; hHeap
0x1800067f1  call    cs:__imp_HeapAlloc
0x1800067f7  mov     rbx, rax
0x1800067fa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006801  test    rax, rax
0x180006804  jnz     short loc_180006844
0x180006806  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000680c  jnz     short loc_18000684F
0x18000680e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180006815  call    cs:__imp_GetModuleHandleW
0x18000681b  test    rax, rax
0x18000681e  jz      short loc_180006831
0x180006820  mov     rcx, rax
0x180006823  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180006828  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000682f  jmp     short loc_180006838
0x180006831  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006838  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000683f  test    rax, rax
0x180006842  jz      short loc_18000684F
0x180006844  mov     rdx, rbx
0x180006847  mov     rcx, rsi
0x18000684a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000684f  mov     rax, rbx
0x180006852  mov     rbx, [rsp+28h+arg_0]
0x180006857  mov     rsi, [rsp+28h+arg_8]
0x18000685c  add     rsp, 20h
0x180006860  pop     rdi
0x180006861  retn
```
