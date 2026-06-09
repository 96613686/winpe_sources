# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000db6c`
- end: `0x18000dc02`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000c8dc`
- `0x18000d600`
- `0x18000d730`
- `0x18000eb70`
- `0x18000eff4`
- `0x1800102cc`

## callees

- `0x18000a60c`
- `0x18000db6c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dbb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dbb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db80`

## string_xrefs

- `0x18000dbae`: `ntdll.dll`

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
0x18000db6c  mov     [rsp+arg_0], rbx
0x18000db71  mov     [rsp+arg_8], rsi
0x18000db76  push    rdi
0x18000db77  sub     rsp, 20h
0x18000db7b  mov     rbx, rdx
0x18000db7e  mov     edi, ecx
0x18000db80  call    cs:__imp_GetProcessHeap
0x18000db86  mov     rsi, rax
0x18000db89  mov     r8, rbx; dwBytes
0x18000db8c  mov     edx, edi; dwFlags
0x18000db8e  mov     rcx, rax; hHeap
0x18000db91  call    cs:__imp_HeapAlloc
0x18000db97  mov     rbx, rax
0x18000db9a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000dba1  test    rax, rax
0x18000dba4  jnz     short loc_18000DBE4
0x18000dba6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000dbac  jnz     short loc_18000DBEF
0x18000dbae  lea     rcx, ModuleName; "ntdll.dll"
0x18000dbb5  call    cs:__imp_GetModuleHandleW
0x18000dbbb  test    rax, rax
0x18000dbbe  jz      short loc_18000DBD1
0x18000dbc0  mov     rcx, rax
0x18000dbc3  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000dbc8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000dbcf  jmp     short loc_18000DBD8
0x18000dbd1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000dbd8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000dbdf  test    rax, rax
0x18000dbe2  jz      short loc_18000DBEF
0x18000dbe4  mov     rdx, rbx
0x18000dbe7  mov     rcx, rsi
0x18000dbea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbef  mov     rax, rbx
0x18000dbf2  mov     rbx, [rsp+28h+arg_0]
0x18000dbf7  mov     rsi, [rsp+28h+arg_8]
0x18000dbfc  add     rsp, 20h
0x18000dc00  pop     rdi
0x18000dc01  retn
```
