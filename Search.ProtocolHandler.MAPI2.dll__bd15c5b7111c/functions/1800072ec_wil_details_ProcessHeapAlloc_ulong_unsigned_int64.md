# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800072ec`
- end: `0x180007382`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006d48`
- `0x180006ea8`
- `0x180008400`
- `0x180008888`
- `0x180009d8c`

## callees

- `0x180003a8c`
- `0x1800072ec`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007335`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007335`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007300`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007300`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007311`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007311`

## string_xrefs

- `0x18000732e`: `ntdll.dll`

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
0x1800072ec  mov     [rsp+arg_0], rbx
0x1800072f1  mov     [rsp+arg_8], rsi
0x1800072f6  push    rdi
0x1800072f7  sub     rsp, 20h
0x1800072fb  mov     rbx, rdx
0x1800072fe  mov     edi, ecx
0x180007300  call    cs:__imp_GetProcessHeap
0x180007306  mov     rsi, rax
0x180007309  mov     r8, rbx; dwBytes
0x18000730c  mov     edx, edi; dwFlags
0x18000730e  mov     rcx, rax; hHeap
0x180007311  call    cs:__imp_HeapAlloc
0x180007317  mov     rbx, rax
0x18000731a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007321  test    rax, rax
0x180007324  jnz     short loc_180007364
0x180007326  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000732c  jnz     short loc_18000736F
0x18000732e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180007335  call    cs:__imp_GetModuleHandleW
0x18000733b  test    rax, rax
0x18000733e  jz      short loc_180007351
0x180007340  mov     rcx, rax
0x180007343  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180007348  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000734f  jmp     short loc_180007358
0x180007351  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007358  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000735f  test    rax, rax
0x180007362  jz      short loc_18000736F
0x180007364  mov     rdx, rbx
0x180007367  mov     rcx, rsi
0x18000736a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000736f  mov     rax, rbx
0x180007372  mov     rbx, [rsp+28h+arg_0]
0x180007377  mov     rsi, [rsp+28h+arg_8]
0x18000737c  add     rsp, 20h
0x180007380  pop     rdi
0x180007381  retn
```
