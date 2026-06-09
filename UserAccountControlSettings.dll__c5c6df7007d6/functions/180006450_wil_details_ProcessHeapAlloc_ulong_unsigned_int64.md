# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006450`
- end: `0x1800064e6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800061a0`
- `0x18000684c`
- `0x1800069c4`

## callees

- `0x180004250`
- `0x180006450`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006499`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006499`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006464`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006464`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006475`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006475`

## string_xrefs

- `0x180006492`: `ntdll.dll`

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
0x180006450  mov     [rsp+arg_0], rbx
0x180006455  mov     [rsp+arg_8], rsi
0x18000645a  push    rdi
0x18000645b  sub     rsp, 20h
0x18000645f  mov     rbx, rdx
0x180006462  mov     edi, ecx
0x180006464  call    cs:__imp_GetProcessHeap
0x18000646a  mov     r8, rbx; dwBytes
0x18000646d  mov     edx, edi; dwFlags
0x18000646f  mov     rcx, rax; hHeap
0x180006472  mov     rsi, rax
0x180006475  call    cs:__imp_HeapAlloc
0x18000647b  mov     rbx, rax
0x18000647e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006485  test    rax, rax
0x180006488  jnz     short loc_1800064C8
0x18000648a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006490  jnz     short loc_1800064D3
0x180006492  lea     rcx, ModuleName; "ntdll.dll"
0x180006499  call    cs:__imp_GetModuleHandleW
0x18000649f  test    rax, rax
0x1800064a2  jz      short loc_1800064B5
0x1800064a4  mov     rcx, rax
0x1800064a7  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800064ac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800064b3  jmp     short loc_1800064BC
0x1800064b5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800064bc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800064c3  test    rax, rax
0x1800064c6  jz      short loc_1800064D3
0x1800064c8  mov     rdx, rbx
0x1800064cb  mov     rcx, rsi
0x1800064ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d3  mov     rsi, [rsp+28h+arg_8]
0x1800064d8  mov     rax, rbx
0x1800064db  mov     rbx, [rsp+28h+arg_0]
0x1800064e0  add     rsp, 20h
0x1800064e4  pop     rdi
0x1800064e5  retn
```
