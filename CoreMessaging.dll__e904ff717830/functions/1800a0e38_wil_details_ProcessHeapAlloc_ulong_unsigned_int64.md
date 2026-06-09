# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800a0e38`
- end: `0x1800a0ece`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18009a51c`
- `0x18009a680`
- `0x1800a10c0`
- `0x1800a1458`
- `0x1800bc2e4`

## callees

- `0x18009f298`
- `0x1800a0e38`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a0e81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a0e81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0e5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0e5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0e4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0e4c`

## string_xrefs

- `0x1800a0e7a`: `ntdll.dll`

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
0x1800a0e38  mov     [rsp+arg_0], rbx
0x1800a0e3d  mov     [rsp+arg_8], rsi
0x1800a0e42  push    rdi
0x1800a0e43  sub     rsp, 20h
0x1800a0e47  mov     rbx, rdx
0x1800a0e4a  mov     edi, ecx
0x1800a0e4c  call    cs:__imp_GetProcessHeap
0x1800a0e52  mov     rsi, rax
0x1800a0e55  mov     r8, rbx; dwBytes
0x1800a0e58  mov     edx, edi; dwFlags
0x1800a0e5a  mov     rcx, rax; hHeap
0x1800a0e5d  call    cs:__imp_HeapAlloc
0x1800a0e63  mov     rbx, rax
0x1800a0e66  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800a0e6d  test    rax, rax
0x1800a0e70  jnz     short loc_1800A0EB0
0x1800a0e72  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800a0e78  jnz     short loc_1800A0EBB
0x1800a0e7a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800a0e81  call    cs:__imp_GetModuleHandleW
0x1800a0e87  test    rax, rax
0x1800a0e8a  jz      short loc_1800A0E9D
0x1800a0e8c  mov     rcx, rax
0x1800a0e8f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800a0e94  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800a0e9b  jmp     short loc_1800A0EA4
0x1800a0e9d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800a0ea4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800a0eab  test    rax, rax
0x1800a0eae  jz      short loc_1800A0EBB
0x1800a0eb0  mov     rdx, rbx
0x1800a0eb3  mov     rcx, rsi
0x1800a0eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0ebb  mov     rax, rbx
0x1800a0ebe  mov     rbx, [rsp+28h+arg_0]
0x1800a0ec3  mov     rsi, [rsp+28h+arg_8]
0x1800a0ec8  add     rsp, 20h
0x1800a0ecc  pop     rdi
0x1800a0ecd  retn
```
