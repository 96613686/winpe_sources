# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000d2fc`
- end: `0x14000d392`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000bb8c`
- `0x14000cc98`
- `0x14000e894`
- `0x14000ec2c`
- `0x14001650c`
- `0x140018bc0`

## callees

- `0x140005d98`
- `0x14000d2fc`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d345`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d345`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d310`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d310`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d321`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d321`

## string_xrefs

- `0x14000d33e`: `ntdll.dll`

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
0x14000d2fc  mov     [rsp+arg_0], rbx
0x14000d301  mov     [rsp+arg_8], rsi
0x14000d306  push    rdi
0x14000d307  sub     rsp, 20h
0x14000d30b  mov     rbx, rdx
0x14000d30e  mov     edi, ecx
0x14000d310  call    cs:__imp_GetProcessHeap
0x14000d316  mov     rsi, rax
0x14000d319  mov     r8, rbx; dwBytes
0x14000d31c  mov     edx, edi; dwFlags
0x14000d31e  mov     rcx, rax; hHeap
0x14000d321  call    cs:__imp_HeapAlloc
0x14000d327  mov     rbx, rax
0x14000d32a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000d331  test    rax, rax
0x14000d334  jnz     short loc_14000D374
0x14000d336  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000d33c  jnz     short loc_14000D37F
0x14000d33e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000d345  call    cs:__imp_GetModuleHandleW
0x14000d34b  test    rax, rax
0x14000d34e  jz      short loc_14000D361
0x14000d350  mov     rcx, rax
0x14000d353  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x14000d358  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000d35f  jmp     short loc_14000D368
0x14000d361  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000d368  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000d36f  test    rax, rax
0x14000d372  jz      short loc_14000D37F
0x14000d374  mov     rdx, rbx
0x14000d377  mov     rcx, rsi
0x14000d37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d37f  mov     rax, rbx
0x14000d382  mov     rbx, [rsp+28h+arg_0]
0x14000d387  mov     rsi, [rsp+28h+arg_8]
0x14000d38c  add     rsp, 20h
0x14000d390  pop     rdi
0x14000d391  retn
```
