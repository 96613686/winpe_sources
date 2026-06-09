# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008bc0`
- end: `0x180008c56`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003430`
- `0x1800089b0`
- `0x1800091a0`
- `0x180009538`
- `0x18000c01c`

## callees

- `0x180005e28`
- `0x180008bc0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008be5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008bd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008bd4`

## string_xrefs

- `0x180008c02`: `ntdll.dll`

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
0x180008bc0  mov     [rsp+arg_0], rbx
0x180008bc5  mov     [rsp+arg_8], rsi
0x180008bca  push    rdi
0x180008bcb  sub     rsp, 20h
0x180008bcf  mov     rbx, rdx
0x180008bd2  mov     edi, ecx
0x180008bd4  call    cs:__imp_GetProcessHeap
0x180008bda  mov     rsi, rax
0x180008bdd  mov     r8, rbx; dwBytes
0x180008be0  mov     edx, edi; dwFlags
0x180008be2  mov     rcx, rax; hHeap
0x180008be5  call    cs:__imp_HeapAlloc
0x180008beb  mov     rbx, rax
0x180008bee  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008bf5  test    rax, rax
0x180008bf8  jnz     short loc_180008C38
0x180008bfa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008c00  jnz     short loc_180008C43
0x180008c02  lea     rcx, ModuleName; "ntdll.dll"
0x180008c09  call    cs:__imp_GetModuleHandleW
0x180008c0f  test    rax, rax
0x180008c12  jz      short loc_180008C25
0x180008c14  mov     rcx, rax
0x180008c17  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180008c1c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008c23  jmp     short loc_180008C2C
0x180008c25  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008c2c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008c33  test    rax, rax
0x180008c36  jz      short loc_180008C43
0x180008c38  mov     rdx, rbx
0x180008c3b  mov     rcx, rsi
0x180008c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c43  mov     rax, rbx
0x180008c46  mov     rbx, [rsp+28h+arg_0]
0x180008c4b  mov     rsi, [rsp+28h+arg_8]
0x180008c50  add     rsp, 20h
0x180008c54  pop     rdi
0x180008c55  retn
```
