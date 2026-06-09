# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000af64`
- end: `0x18000affa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a19c`
- `0x18000a9f4`
- `0x18000ab58`
- `0x18000c06c`
- `0x18000c2a0`
- `0x18000d20c`

## callees

- `0x180008688`
- `0x18000af64`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000afad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000afad`

## string_xrefs

- `0x18000afa6`: `ntdll.dll`

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
0x18000af64  mov     [rsp+arg_0], rbx
0x18000af69  mov     [rsp+arg_8], rsi
0x18000af6e  push    rdi
0x18000af6f  sub     rsp, 20h
0x18000af73  mov     rbx, rdx
0x18000af76  mov     edi, ecx
0x18000af78  call    cs:__imp_GetProcessHeap
0x18000af7e  mov     rsi, rax
0x18000af81  mov     r8, rbx; dwBytes
0x18000af84  mov     edx, edi; dwFlags
0x18000af86  mov     rcx, rax; hHeap
0x18000af89  call    cs:__imp_HeapAlloc
0x18000af8f  mov     rbx, rax
0x18000af92  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000af99  test    rax, rax
0x18000af9c  jnz     short loc_18000AFDC
0x18000af9e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000afa4  jnz     short loc_18000AFE7
0x18000afa6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000afad  call    cs:__imp_GetModuleHandleW
0x18000afb3  test    rax, rax
0x18000afb6  jz      short loc_18000AFC9
0x18000afb8  mov     rcx, rax
0x18000afbb  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000afc0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000afc7  jmp     short loc_18000AFD0
0x18000afc9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000afd0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000afd7  test    rax, rax
0x18000afda  jz      short loc_18000AFE7
0x18000afdc  mov     rdx, rbx
0x18000afdf  mov     rcx, rsi
0x18000afe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afe7  mov     rax, rbx
0x18000afea  mov     rbx, [rsp+28h+arg_0]
0x18000afef  mov     rsi, [rsp+28h+arg_8]
0x18000aff4  add     rsp, 20h
0x18000aff8  pop     rdi
0x18000aff9  retn
```
