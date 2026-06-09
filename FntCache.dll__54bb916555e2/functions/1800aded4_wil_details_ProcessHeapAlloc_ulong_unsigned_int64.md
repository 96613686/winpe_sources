# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800aded4`
- end: `0x1800adf6a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18009e900`
- `0x1800ad9e8`
- `0x1800adb18`
- `0x1800ae800`
- `0x1800aeb98`

## callees

- `0x1800ab7dc`
- `0x1800aded4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800adef9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800adef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800adee8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800adee8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800adf1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800adf1d`

## string_xrefs

- `0x1800adf16`: `ntdll.dll`

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
0x1800aded4  mov     [rsp+arg_0], rbx
0x1800aded9  mov     [rsp+arg_8], rsi
0x1800adede  push    rdi
0x1800adedf  sub     rsp, 20h
0x1800adee3  mov     rbx, rdx
0x1800adee6  mov     edi, ecx
0x1800adee8  call    cs:__imp_GetProcessHeap
0x1800adeee  mov     rsi, rax
0x1800adef1  mov     r8, rbx; dwBytes
0x1800adef4  mov     edx, edi; dwFlags
0x1800adef6  mov     rcx, rax; hHeap
0x1800adef9  call    cs:__imp_HeapAlloc
0x1800adeff  mov     rbx, rax
0x1800adf02  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800adf09  test    rax, rax
0x1800adf0c  jnz     short loc_1800ADF4C
0x1800adf0e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800adf14  jnz     short loc_1800ADF57
0x1800adf16  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800adf1d  call    cs:__imp_GetModuleHandleW
0x1800adf23  test    rax, rax
0x1800adf26  jz      short loc_1800ADF39
0x1800adf28  mov     rcx, rax
0x1800adf2b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800adf30  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800adf37  jmp     short loc_1800ADF40
0x1800adf39  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800adf40  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800adf47  test    rax, rax
0x1800adf4a  jz      short loc_1800ADF57
0x1800adf4c  mov     rdx, rbx
0x1800adf4f  mov     rcx, rsi
0x1800adf52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adf57  mov     rax, rbx
0x1800adf5a  mov     rbx, [rsp+28h+arg_0]
0x1800adf5f  mov     rsi, [rsp+28h+arg_8]
0x1800adf64  add     rsp, 20h
0x1800adf68  pop     rdi
0x1800adf69  retn
```
