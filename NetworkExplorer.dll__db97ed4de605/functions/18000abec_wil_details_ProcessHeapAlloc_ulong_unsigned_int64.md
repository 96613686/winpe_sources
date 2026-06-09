# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000abec`
- end: `0x18000ac82`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009b54`
- `0x18000a60c`
- `0x18000b3cc`
- `0x18000b78c`

## callees

- `0x180007ffc`
- `0x18000abec`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ac11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ac11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac00`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ac35`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ac35`

## string_xrefs

- `0x18000ac2e`: `ntdll.dll`

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
0x18000abec  mov     [rsp+arg_0], rbx
0x18000abf1  mov     [rsp+arg_8], rsi
0x18000abf6  push    rdi
0x18000abf7  sub     rsp, 20h
0x18000abfb  mov     rbx, rdx
0x18000abfe  mov     edi, ecx
0x18000ac00  call    cs:__imp_GetProcessHeap
0x18000ac06  mov     rsi, rax
0x18000ac09  mov     r8, rbx; dwBytes
0x18000ac0c  mov     edx, edi; dwFlags
0x18000ac0e  mov     rcx, rax; hHeap
0x18000ac11  call    cs:__imp_HeapAlloc
0x18000ac17  mov     rbx, rax
0x18000ac1a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ac21  test    rax, rax
0x18000ac24  jnz     short loc_18000AC64
0x18000ac26  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ac2c  jnz     short loc_18000AC6F
0x18000ac2e  lea     rcx, ModuleName; "ntdll.dll"
0x18000ac35  call    cs:__imp_GetModuleHandleW
0x18000ac3b  test    rax, rax
0x18000ac3e  jz      short loc_18000AC51
0x18000ac40  mov     rcx, rax
0x18000ac43  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000ac48  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ac4f  jmp     short loc_18000AC58
0x18000ac51  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ac58  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ac5f  test    rax, rax
0x18000ac62  jz      short loc_18000AC6F
0x18000ac64  mov     rdx, rbx
0x18000ac67  mov     rcx, rsi
0x18000ac6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac6f  mov     rax, rbx
0x18000ac72  mov     rbx, [rsp+28h+arg_0]
0x18000ac77  mov     rsi, [rsp+28h+arg_8]
0x18000ac7c  add     rsp, 20h
0x18000ac80  pop     rdi
0x18000ac81  retn
```
