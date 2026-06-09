# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004958`
- end: `0x1400049ee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400046d4`
- `0x140004ddc`
- `0x140005174`

## callees

- `0x140002778`
- `0x140004958`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400049a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400049a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000497d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000497d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000496c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000496c`

## string_xrefs

- `0x14000499a`: `ntdll.dll`

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
0x140004958  mov     [rsp+arg_0], rbx
0x14000495d  mov     [rsp+arg_8], rsi
0x140004962  push    rdi
0x140004963  sub     rsp, 20h
0x140004967  mov     rbx, rdx
0x14000496a  mov     edi, ecx
0x14000496c  call    cs:__imp_GetProcessHeap
0x140004972  mov     rsi, rax
0x140004975  mov     r8, rbx; dwBytes
0x140004978  mov     edx, edi; dwFlags
0x14000497a  mov     rcx, rax; hHeap
0x14000497d  call    cs:__imp_HeapAlloc
0x140004983  mov     rbx, rax
0x140004986  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000498d  test    rax, rax
0x140004990  jnz     short loc_1400049D0
0x140004992  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004998  jnz     short loc_1400049DB
0x14000499a  lea     rcx, ModuleName; "ntdll.dll"
0x1400049a1  call    cs:__imp_GetModuleHandleW
0x1400049a7  test    rax, rax
0x1400049aa  jz      short loc_1400049BD
0x1400049ac  mov     rcx, rax
0x1400049af  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1400049b4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400049bb  jmp     short loc_1400049C4
0x1400049bd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400049c4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400049cb  test    rax, rax
0x1400049ce  jz      short loc_1400049DB
0x1400049d0  mov     rdx, rbx
0x1400049d3  mov     rcx, rsi
0x1400049d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049db  mov     rax, rbx
0x1400049de  mov     rbx, [rsp+28h+arg_0]
0x1400049e3  mov     rsi, [rsp+28h+arg_8]
0x1400049e8  add     rsp, 20h
0x1400049ec  pop     rdi
0x1400049ed  retn
```
