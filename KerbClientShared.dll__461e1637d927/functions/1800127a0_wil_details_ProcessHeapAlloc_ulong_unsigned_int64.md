# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800127a0`
- end: `0x180012836`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d884`
- `0x1800122b8`
- `0x1800123dc`
- `0x1800131a4`
- `0x180013408`

## callees

- `0x18000fa7c`
- `0x1800127a0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800127e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800127e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800127b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800127b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800127c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800127c5`

## string_xrefs

- `0x1800127e2`: `ntdll.dll`

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
0x1800127a0  mov     [rsp+arg_0], rbx
0x1800127a5  mov     [rsp+arg_8], rsi
0x1800127aa  push    rdi
0x1800127ab  sub     rsp, 20h
0x1800127af  mov     rbx, rdx
0x1800127b2  mov     edi, ecx
0x1800127b4  call    cs:__imp_GetProcessHeap
0x1800127ba  mov     r8, rbx; dwBytes
0x1800127bd  mov     edx, edi; dwFlags
0x1800127bf  mov     rcx, rax; hHeap
0x1800127c2  mov     rsi, rax
0x1800127c5  call    cs:__imp_HeapAlloc
0x1800127cb  mov     rbx, rax
0x1800127ce  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800127d5  test    rax, rax
0x1800127d8  jnz     short loc_180012818
0x1800127da  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800127e0  jnz     short loc_180012823
0x1800127e2  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800127e9  call    cs:__imp_GetModuleHandleW
0x1800127ef  test    rax, rax
0x1800127f2  jz      short loc_180012805
0x1800127f4  mov     rcx, rax
0x1800127f7  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800127fc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180012803  jmp     short loc_18001280C
0x180012805  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001280c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012813  test    rax, rax
0x180012816  jz      short loc_180012823
0x180012818  mov     rdx, rbx
0x18001281b  mov     rcx, rsi
0x18001281e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012823  mov     rsi, [rsp+28h+arg_8]
0x180012828  mov     rax, rbx
0x18001282b  mov     rbx, [rsp+28h+arg_0]
0x180012830  add     rsp, 20h
0x180012834  pop     rdi
0x180012835  retn
```
