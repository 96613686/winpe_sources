# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180027c58`
- end: `0x180027cee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180027a5c`
- `0x180027edc`
- `0x180028274`

## callees

- `0x180026760`
- `0x180027c58`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027ca1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027ca1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027c6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027c6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027c7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027c7d`

## string_xrefs

- `0x180027c9a`: `ntdll.dll`

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
0x180027c58  mov     [rsp+arg_0], rbx
0x180027c5d  mov     [rsp+arg_8], rsi
0x180027c62  push    rdi
0x180027c63  sub     rsp, 20h
0x180027c67  mov     rbx, rdx
0x180027c6a  mov     edi, ecx
0x180027c6c  call    cs:__imp_GetProcessHeap
0x180027c72  mov     rsi, rax
0x180027c75  mov     r8, rbx; dwBytes
0x180027c78  mov     edx, edi; dwFlags
0x180027c7a  mov     rcx, rax; hHeap
0x180027c7d  call    cs:__imp_HeapAlloc
0x180027c83  mov     rbx, rax
0x180027c86  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180027c8d  test    rax, rax
0x180027c90  jnz     short loc_180027CD0
0x180027c92  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180027c98  jnz     short loc_180027CDB
0x180027c9a  lea     rcx, LibFileName; "ntdll.dll"
0x180027ca1  call    cs:__imp_GetModuleHandleW
0x180027ca7  test    rax, rax
0x180027caa  jz      short loc_180027CBD
0x180027cac  mov     rcx, rax
0x180027caf  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180027cb4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180027cbb  jmp     short loc_180027CC4
0x180027cbd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180027cc4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180027ccb  test    rax, rax
0x180027cce  jz      short loc_180027CDB
0x180027cd0  mov     rdx, rbx
0x180027cd3  mov     rcx, rsi
0x180027cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cdb  mov     rax, rbx
0x180027cde  mov     rbx, [rsp+28h+arg_0]
0x180027ce3  mov     rsi, [rsp+28h+arg_8]
0x180027ce8  add     rsp, 20h
0x180027cec  pop     rdi
0x180027ced  retn
```
