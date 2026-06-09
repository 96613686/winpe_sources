# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000d618`
- end: `0x18000d6ae`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000cd94`
- `0x18000ceb8`
- `0x18000f4b8`
- `0x18000f9dc`
- `0x180011184`

## callees

- `0x1800076d4`
- `0x18000d618`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d63d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d63d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d62c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d62c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d661`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d661`

## string_xrefs

- `0x18000d65a`: `ntdll.dll`

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
0x18000d618  mov     [rsp+arg_0], rbx
0x18000d61d  mov     [rsp+arg_8], rsi
0x18000d622  push    rdi
0x18000d623  sub     rsp, 20h
0x18000d627  mov     rbx, rdx
0x18000d62a  mov     edi, ecx
0x18000d62c  call    cs:__imp_GetProcessHeap
0x18000d632  mov     rsi, rax
0x18000d635  mov     r8, rbx; dwBytes
0x18000d638  mov     edx, edi; dwFlags
0x18000d63a  mov     rcx, rax; hHeap
0x18000d63d  call    cs:__imp_HeapAlloc
0x18000d643  mov     rbx, rax
0x18000d646  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d64d  test    rax, rax
0x18000d650  jnz     short loc_18000D690
0x18000d652  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d658  jnz     short loc_18000D69B
0x18000d65a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000d661  call    cs:__imp_GetModuleHandleW
0x18000d667  test    rax, rax
0x18000d66a  jz      short loc_18000D67D
0x18000d66c  mov     rcx, rax
0x18000d66f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000d674  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000d67b  jmp     short loc_18000D684
0x18000d67d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d684  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d68b  test    rax, rax
0x18000d68e  jz      short loc_18000D69B
0x18000d690  mov     rdx, rbx
0x18000d693  mov     rcx, rsi
0x18000d696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d69b  mov     rax, rbx
0x18000d69e  mov     rbx, [rsp+28h+arg_0]
0x18000d6a3  mov     rsi, [rsp+28h+arg_8]
0x18000d6a8  add     rsp, 20h
0x18000d6ac  pop     rdi
0x18000d6ad  retn
```
