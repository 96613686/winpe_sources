# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400051f0`
- end: `0x140005286`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140004fb8`
- `0x140005474`
- `0x1400055ec`
- `0x14000b6cc`
- `0x14000d2c0`

## callees

- `0x140003308`
- `0x1400051f0`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005239`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005239`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005215`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005215`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005204`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005204`

## string_xrefs

- `0x140005232`: `ntdll.dll`

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
0x1400051f0  mov     [rsp+arg_0], rbx
0x1400051f5  mov     [rsp+arg_8], rsi
0x1400051fa  push    rdi
0x1400051fb  sub     rsp, 20h
0x1400051ff  mov     rbx, rdx
0x140005202  mov     edi, ecx
0x140005204  call    cs:__imp_GetProcessHeap
0x14000520a  mov     r8, rbx; dwBytes
0x14000520d  mov     edx, edi; dwFlags
0x14000520f  mov     rcx, rax; hHeap
0x140005212  mov     rsi, rax
0x140005215  call    cs:__imp_HeapAlloc
0x14000521b  mov     rbx, rax
0x14000521e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005225  test    rax, rax
0x140005228  jnz     short loc_140005268
0x14000522a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005230  jnz     short loc_140005273
0x140005232  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140005239  call    cs:__imp_GetModuleHandleW
0x14000523f  test    rax, rax
0x140005242  jz      short loc_140005255
0x140005244  mov     rcx, rax
0x140005247  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x14000524c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005253  jmp     short loc_14000525C
0x140005255  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000525c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005263  test    rax, rax
0x140005266  jz      short loc_140005273
0x140005268  mov     rdx, rbx
0x14000526b  mov     rcx, rsi
0x14000526e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005273  mov     rsi, [rsp+28h+arg_8]
0x140005278  mov     rax, rbx
0x14000527b  mov     rbx, [rsp+28h+arg_0]
0x140005280  add     rsp, 20h
0x140005284  pop     rdi
0x140005285  retn
```
