# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140007370`
- end: `0x140007406`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140006e0c`
- `0x140006f70`
- `0x1400083f0`
- `0x140008864`
- `0x140009814`

## callees

- `0x140004348`
- `0x140007370`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400073b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400073b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007395`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007395`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007384`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007384`

## string_xrefs

- `0x1400073b2`: `ntdll.dll`

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
0x140007370  mov     [rsp+arg_0], rbx
0x140007375  mov     [rsp+arg_8], rsi
0x14000737a  push    rdi
0x14000737b  sub     rsp, 20h
0x14000737f  mov     rbx, rdx
0x140007382  mov     edi, ecx
0x140007384  call    cs:__imp_GetProcessHeap
0x14000738a  mov     rsi, rax
0x14000738d  mov     r8, rbx; dwBytes
0x140007390  mov     edx, edi; dwFlags
0x140007392  mov     rcx, rax; hHeap
0x140007395  call    cs:__imp_HeapAlloc
0x14000739b  mov     rbx, rax
0x14000739e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400073a5  test    rax, rax
0x1400073a8  jnz     short loc_1400073E8
0x1400073aa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400073b0  jnz     short loc_1400073F3
0x1400073b2  lea     rcx, ModuleName; "ntdll.dll"
0x1400073b9  call    cs:__imp_GetModuleHandleW
0x1400073bf  test    rax, rax
0x1400073c2  jz      short loc_1400073D5
0x1400073c4  mov     rcx, rax
0x1400073c7  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1400073cc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400073d3  jmp     short loc_1400073DC
0x1400073d5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400073dc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400073e3  test    rax, rax
0x1400073e6  jz      short loc_1400073F3
0x1400073e8  mov     rdx, rbx
0x1400073eb  mov     rcx, rsi
0x1400073ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073f3  mov     rax, rbx
0x1400073f6  mov     rbx, [rsp+28h+arg_0]
0x1400073fb  mov     rsi, [rsp+28h+arg_8]
0x140007400  add     rsp, 20h
0x140007404  pop     rdi
0x140007405  retn
```
