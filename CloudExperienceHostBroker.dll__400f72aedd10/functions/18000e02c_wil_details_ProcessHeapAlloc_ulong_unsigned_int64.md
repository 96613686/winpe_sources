# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000e02c`
- end: `0x18000e0c2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d4c0`
- `0x18000dd24`
- `0x18000e760`
- `0x18000eaf8`
- `0x180015a3c`
- `0x18001a7c4`

## callees

- `0x18000c060`
- `0x18000e02c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e075`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e075`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e051`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e040`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e040`

## string_xrefs

- `0x18000e06e`: `ntdll.dll`

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
0x18000e02c  mov     [rsp+arg_0], rbx
0x18000e031  mov     [rsp+arg_8], rsi
0x18000e036  push    rdi
0x18000e037  sub     rsp, 20h
0x18000e03b  mov     rbx, rdx
0x18000e03e  mov     edi, ecx
0x18000e040  call    cs:__imp_GetProcessHeap
0x18000e046  mov     rsi, rax
0x18000e049  mov     r8, rbx; dwBytes
0x18000e04c  mov     edx, edi; dwFlags
0x18000e04e  mov     rcx, rax; hHeap
0x18000e051  call    cs:__imp_HeapAlloc
0x18000e057  mov     rbx, rax
0x18000e05a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e061  test    rax, rax
0x18000e064  jnz     short loc_18000E0A4
0x18000e066  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e06c  jnz     short loc_18000E0AF
0x18000e06e  lea     rcx, ModuleName; "ntdll.dll"
0x18000e075  call    cs:__imp_GetModuleHandleW
0x18000e07b  test    rax, rax
0x18000e07e  jz      short loc_18000E091
0x18000e080  mov     rcx, rax
0x18000e083  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000e088  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000e08f  jmp     short loc_18000E098
0x18000e091  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e098  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e09f  test    rax, rax
0x18000e0a2  jz      short loc_18000E0AF
0x18000e0a4  mov     rdx, rbx
0x18000e0a7  mov     rcx, rsi
0x18000e0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0af  mov     rax, rbx
0x18000e0b2  mov     rbx, [rsp+28h+arg_0]
0x18000e0b7  mov     rsi, [rsp+28h+arg_8]
0x18000e0bc  add     rsp, 20h
0x18000e0c0  pop     rdi
0x18000e0c1  retn
```
