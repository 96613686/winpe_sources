# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000f698`
- end: `0x18000f731`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `153`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005700`
- `0x18000e49c`
- `0x18000e9b8`
- `0x18000ef30`
- `0x18000f0e0`
- `0x18000f340`
- `0x18000f450`
- `0x180023f80`
- `0x18002c7f0`

## callees

- `0x18000f698`
- `0x18002bcec`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f700`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f700`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f6bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f6bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6ac`

## string_xrefs

- `0x18000f6f9`: `ntdll.dll`

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
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) != 0
      ? (void (__fastcall *)(HANDLE, LPVOID))(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW),
                                              `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)
      : (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation),
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
0x18000f698  mov     [rsp+arg_0], rbx
0x18000f69d  mov     [rsp+arg_8], rsi
0x18000f6a2  push    rdi
0x18000f6a3  sub     rsp, 20h
0x18000f6a7  mov     rbx, rdx
0x18000f6aa  mov     edi, ecx
0x18000f6ac  call    cs:__imp_GetProcessHeap
0x18000f6b2  mov     rsi, rax
0x18000f6b5  mov     r8, rbx; dwBytes
0x18000f6b8  mov     edx, edi; dwFlags
0x18000f6ba  mov     rcx, rax; hHeap
0x18000f6bd  call    cs:__imp_HeapAlloc
0x18000f6c3  mov     rbx, rax
0x18000f6c6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f6cd  test    rax, rax
0x18000f6d0  jz      short loc_18000F6F0
0x18000f6d2  mov     rdx, rbx
0x18000f6d5  mov     rcx, rsi
0x18000f6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6dd  mov     rax, rbx
0x18000f6e0  mov     rbx, [rsp+28h+arg_0]
0x18000f6e5  mov     rsi, [rsp+28h+arg_8]
0x18000f6ea  add     rsp, 20h
0x18000f6ee  pop     rdi
0x18000f6ef  retn
0x18000f6f0  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f6f7  jnz     short loc_18000F6DD
0x18000f6f9  lea     rcx, ModuleName; "ntdll.dll"
0x18000f700  call    cs:__imp_GetModuleHandleW
0x18000f706  test    rax, rax
0x18000f709  jnz     short loc_18000F720
0x18000f70b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f712  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f719  test    rax, rax
0x18000f71c  jnz     short loc_18000F6D2
0x18000f71e  jmp     short loc_18000F6DD
0x18000f720  mov     rcx, rax
0x18000f723  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000f728  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000f72f  jmp     short loc_18000F712
```
