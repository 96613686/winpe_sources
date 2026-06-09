# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140008ed8`
- end: `0x140008f78`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `160`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140007be4`
- `0x1400088ec`
- `0x140008a1c`
- `0x140009fec`
- `0x14000a470`
- `0x14000bb60`

## callees

- `0x14000549c`
- `0x140008ed8`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008f2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008f2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008f07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008f07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ef6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ef6`

## string_xrefs

- `0x140008f24`: `ntdll.dll`

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
0x140008ed8  push    rdi
0x140008eda  sub     rsp, 30h
0x140008ede  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140008ee7  mov     [rsp+38h+arg_0], rbx
0x140008eec  mov     [rsp+38h+arg_8], rsi
0x140008ef1  mov     rbx, rdx
0x140008ef4  mov     edi, ecx
0x140008ef6  call    cs:__imp_GetProcessHeap
0x140008efc  mov     rsi, rax
0x140008eff  mov     r8, rbx; dwBytes
0x140008f02  mov     edx, edi; dwFlags
0x140008f04  mov     rcx, rax; hHeap
0x140008f07  call    cs:__imp_HeapAlloc
0x140008f0d  mov     rbx, rax
0x140008f10  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140008f17  test    rax, rax
0x140008f1a  jnz     short loc_140008F5A
0x140008f1c  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008f22  jnz     short loc_140008F65
0x140008f24  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140008f2b  call    cs:__imp_GetModuleHandleW
0x140008f31  test    rax, rax
0x140008f34  jz      short loc_140008F47
0x140008f36  mov     rcx, rax
0x140008f39  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x140008f3e  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140008f45  jmp     short loc_140008F4E
0x140008f47  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140008f4e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008f55  test    rax, rax
0x140008f58  jz      short loc_140008F65
0x140008f5a  mov     rdx, rbx
0x140008f5d  mov     rcx, rsi
0x140008f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f65  mov     rax, rbx
0x140008f68  mov     rbx, [rsp+38h+arg_0]
0x140008f6d  mov     rsi, [rsp+38h+arg_8]
0x140008f72  add     rsp, 30h
0x140008f76  pop     rdi
0x140008f77  retn
```
