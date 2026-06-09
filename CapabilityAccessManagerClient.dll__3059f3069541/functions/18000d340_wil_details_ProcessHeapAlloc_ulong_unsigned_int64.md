# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000d340`
- end: `0x18000d3d6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000bf9c`
- `0x18000cd5c`
- `0x18000cec0`
- `0x18000e2c0`
- `0x18000e750`
- `0x18000fca4`

## callees

- `0x1800098b0`
- `0x18000d340`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d389`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d389`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d365`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d365`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d354`

## string_xrefs

- `0x18000d382`: `ntdll.dll`

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
0x18000d340  mov     [rsp+arg_0], rbx
0x18000d345  mov     [rsp+arg_8], rsi
0x18000d34a  push    rdi
0x18000d34b  sub     rsp, 20h
0x18000d34f  mov     rbx, rdx
0x18000d352  mov     edi, ecx
0x18000d354  call    cs:__imp_GetProcessHeap
0x18000d35a  mov     rsi, rax
0x18000d35d  mov     r8, rbx; dwBytes
0x18000d360  mov     edx, edi; dwFlags
0x18000d362  mov     rcx, rax; hHeap
0x18000d365  call    cs:__imp_HeapAlloc
0x18000d36b  mov     rbx, rax
0x18000d36e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d375  test    rax, rax
0x18000d378  jnz     short loc_18000D3B8
0x18000d37a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d380  jnz     short loc_18000D3C3
0x18000d382  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000d389  call    cs:__imp_GetModuleHandleW
0x18000d38f  test    rax, rax
0x18000d392  jz      short loc_18000D3A5
0x18000d394  mov     rcx, rax
0x18000d397  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000d39c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000d3a3  jmp     short loc_18000D3AC
0x18000d3a5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d3ac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d3b3  test    rax, rax
0x18000d3b6  jz      short loc_18000D3C3
0x18000d3b8  mov     rdx, rbx
0x18000d3bb  mov     rcx, rsi
0x18000d3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c3  mov     rax, rbx
0x18000d3c6  mov     rbx, [rsp+28h+arg_0]
0x18000d3cb  mov     rsi, [rsp+28h+arg_8]
0x18000d3d0  add     rsp, 20h
0x18000d3d4  pop     rdi
0x18000d3d5  retn
```
