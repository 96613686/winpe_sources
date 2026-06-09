# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800065c0`
- end: `0x180006656`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005988`
- `0x1800063b0`
- `0x180006850`
- `0x180006be8`
- `0x180009030`
- `0x18000ad10`

## callees

- `0x180004398`
- `0x1800065c0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006609`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006609`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800065e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800065e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065d4`

## string_xrefs

- `0x180006602`: `ntdll.dll`

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
0x1800065c0  mov     [rsp+arg_0], rbx
0x1800065c5  mov     [rsp+arg_8], rsi
0x1800065ca  push    rdi
0x1800065cb  sub     rsp, 20h
0x1800065cf  mov     rbx, rdx
0x1800065d2  mov     edi, ecx
0x1800065d4  call    cs:__imp_GetProcessHeap
0x1800065da  mov     rsi, rax
0x1800065dd  mov     r8, rbx; dwBytes
0x1800065e0  mov     edx, edi; dwFlags
0x1800065e2  mov     rcx, rax; hHeap
0x1800065e5  call    cs:__imp_HeapAlloc
0x1800065eb  mov     rbx, rax
0x1800065ee  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800065f5  test    rax, rax
0x1800065f8  jnz     short loc_180006638
0x1800065fa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006600  jnz     short loc_180006643
0x180006602  lea     rcx, ModuleName; "ntdll.dll"
0x180006609  call    cs:__imp_GetModuleHandleW
0x18000660f  test    rax, rax
0x180006612  jz      short loc_180006625
0x180006614  mov     rcx, rax
0x180006617  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000661c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006623  jmp     short loc_18000662C
0x180006625  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000662c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006633  test    rax, rax
0x180006636  jz      short loc_180006643
0x180006638  mov     rdx, rbx
0x18000663b  mov     rcx, rsi
0x18000663e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006643  mov     rax, rbx
0x180006646  mov     rbx, [rsp+28h+arg_0]
0x18000664b  mov     rsi, [rsp+28h+arg_8]
0x180006650  add     rsp, 20h
0x180006654  pop     rdi
0x180006655  retn
```
