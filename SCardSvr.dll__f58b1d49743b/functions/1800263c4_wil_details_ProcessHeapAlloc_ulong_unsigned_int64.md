# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800263c4`
- end: `0x18002645a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015790`
- `0x18001bbb4`
- `0x18001bd18`
- `0x180027080`
- `0x180027504`
- `0x180028530`

## callees

- `0x180023534`
- `0x1800263c4`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002640d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002640d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800263e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800263e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800263d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800263d8`

## string_xrefs

- `0x180026406`: `ntdll.dll`

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
0x1800263c4  mov     [rsp+arg_0], rbx
0x1800263c9  mov     [rsp+arg_8], rsi
0x1800263ce  push    rdi
0x1800263cf  sub     rsp, 20h
0x1800263d3  mov     rbx, rdx
0x1800263d6  mov     edi, ecx
0x1800263d8  call    cs:__imp_GetProcessHeap
0x1800263de  mov     rsi, rax
0x1800263e1  mov     r8, rbx; dwBytes
0x1800263e4  mov     edx, edi; dwFlags
0x1800263e6  mov     rcx, rax; hHeap
0x1800263e9  call    cs:__imp_HeapAlloc
0x1800263ef  mov     rbx, rax
0x1800263f2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800263f9  test    rax, rax
0x1800263fc  jnz     short loc_18002643C
0x1800263fe  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180026404  jnz     short loc_180026447
0x180026406  lea     rcx, ModuleName; "ntdll.dll"
0x18002640d  call    cs:__imp_GetModuleHandleW
0x180026413  test    rax, rax
0x180026416  jz      short loc_180026429
0x180026418  mov     rcx, rax
0x18002641b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180026420  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180026427  jmp     short loc_180026430
0x180026429  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180026430  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180026437  test    rax, rax
0x18002643a  jz      short loc_180026447
0x18002643c  mov     rdx, rbx
0x18002643f  mov     rcx, rsi
0x180026442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026447  mov     rax, rbx
0x18002644a  mov     rbx, [rsp+28h+arg_0]
0x18002644f  mov     rsi, [rsp+28h+arg_8]
0x180026454  add     rsp, 20h
0x180026458  pop     rdi
0x180026459  retn
```
