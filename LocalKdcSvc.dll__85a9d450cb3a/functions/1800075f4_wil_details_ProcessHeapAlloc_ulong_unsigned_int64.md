# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800075f4`
- end: `0x18000768a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007120`
- `0x180007244`
- `0x180008390`
- `0x180008814`
- `0x1800099cc`

## callees

- `0x180004254`
- `0x1800075f4`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000763d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000763d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007619`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007619`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007608`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007608`

## string_xrefs

- `0x180007636`: `ntdll.dll`

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
0x1800075f4  mov     [rsp+arg_0], rbx
0x1800075f9  mov     [rsp+arg_8], rsi
0x1800075fe  push    rdi
0x1800075ff  sub     rsp, 20h
0x180007603  mov     rbx, rdx
0x180007606  mov     edi, ecx
0x180007608  call    cs:__imp_GetProcessHeap
0x18000760e  mov     rsi, rax
0x180007611  mov     r8, rbx; dwBytes
0x180007614  mov     edx, edi; dwFlags
0x180007616  mov     rcx, rax; hHeap
0x180007619  call    cs:__imp_HeapAlloc
0x18000761f  mov     rbx, rax
0x180007622  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007629  test    rax, rax
0x18000762c  jnz     short loc_18000766C
0x18000762e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007634  jnz     short loc_180007677
0x180007636  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000763d  call    cs:__imp_GetModuleHandleW
0x180007643  test    rax, rax
0x180007646  jz      short loc_180007659
0x180007648  mov     rcx, rax
0x18000764b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180007650  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007657  jmp     short loc_180007660
0x180007659  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007660  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007667  test    rax, rax
0x18000766a  jz      short loc_180007677
0x18000766c  mov     rdx, rbx
0x18000766f  mov     rcx, rsi
0x180007672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007677  mov     rax, rbx
0x18000767a  mov     rbx, [rsp+28h+arg_0]
0x18000767f  mov     rsi, [rsp+28h+arg_8]
0x180007684  add     rsp, 20h
0x180007688  pop     rdi
0x180007689  retn
```
