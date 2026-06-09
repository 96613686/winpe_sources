# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000837c`
- end: `0x140008412`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140003f40`
- `0x140008668`
- `0x1400087cc`
- `0x14000c664`
- `0x14000c824`

## callees

- `0x14000837c`
- `0x14000a228`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400083c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400083c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400083a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400083a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008390`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008390`

## string_xrefs

- `0x1400083be`: `ntdll.dll`

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
0x14000837c  mov     [rsp+arg_0], rbx
0x140008381  mov     [rsp+arg_8], rsi
0x140008386  push    rdi
0x140008387  sub     rsp, 20h
0x14000838b  mov     rbx, rdx
0x14000838e  mov     edi, ecx
0x140008390  call    cs:__imp_GetProcessHeap
0x140008396  mov     r8, rbx; dwBytes
0x140008399  mov     edx, edi; dwFlags
0x14000839b  mov     rcx, rax; hHeap
0x14000839e  mov     rsi, rax
0x1400083a1  call    cs:__imp_HeapAlloc
0x1400083a7  mov     rbx, rax
0x1400083aa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400083b1  test    rax, rax
0x1400083b4  jnz     short loc_1400083F4
0x1400083b6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400083bc  jnz     short loc_1400083FF
0x1400083be  lea     rcx, ModuleName; "ntdll.dll"
0x1400083c5  call    cs:__imp_GetModuleHandleW
0x1400083cb  test    rax, rax
0x1400083ce  jz      short loc_1400083E1
0x1400083d0  mov     rcx, rax
0x1400083d3  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1400083d8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400083df  jmp     short loc_1400083E8
0x1400083e1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400083e8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400083ef  test    rax, rax
0x1400083f2  jz      short loc_1400083FF
0x1400083f4  mov     rdx, rbx
0x1400083f7  mov     rcx, rsi
0x1400083fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083ff  mov     rsi, [rsp+28h+arg_8]
0x140008404  mov     rax, rbx
0x140008407  mov     rbx, [rsp+28h+arg_0]
0x14000840c  add     rsp, 20h
0x140008410  pop     rdi
0x140008411  retn
```
