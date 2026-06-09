# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006778`
- end: `0x18000680e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005a2c`
- `0x180005ad0`
- `0x1800064ec`
- `0x180006bf4`
- `0x180006f8c`
- `0x180024fc0`
- `0x1800297fc`

## callees

- `0x1800043e8`
- `0x180006778`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800067c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800067c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000678c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000678c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000679d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000679d`

## string_xrefs

- `0x1800067ba`: `ntdll.dll`

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
0x180006778  mov     [rsp+arg_0], rbx
0x18000677d  mov     [rsp+arg_8], rsi
0x180006782  push    rdi
0x180006783  sub     rsp, 20h
0x180006787  mov     rbx, rdx
0x18000678a  mov     edi, ecx
0x18000678c  call    cs:__imp_GetProcessHeap
0x180006792  mov     rsi, rax
0x180006795  mov     r8, rbx; dwBytes
0x180006798  mov     edx, edi; dwFlags
0x18000679a  mov     rcx, rax; hHeap
0x18000679d  call    cs:__imp_HeapAlloc
0x1800067a3  mov     rbx, rax
0x1800067a6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800067ad  test    rax, rax
0x1800067b0  jnz     short loc_1800067F0
0x1800067b2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800067b8  jnz     short loc_1800067FB
0x1800067ba  lea     rcx, ModuleName; "ntdll.dll"
0x1800067c1  call    cs:__imp_GetModuleHandleW
0x1800067c7  test    rax, rax
0x1800067ca  jz      short loc_1800067DD
0x1800067cc  mov     rcx, rax
0x1800067cf  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800067d4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800067db  jmp     short loc_1800067E4
0x1800067dd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800067e4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800067eb  test    rax, rax
0x1800067ee  jz      short loc_1800067FB
0x1800067f0  mov     rdx, rbx
0x1800067f3  mov     rcx, rsi
0x1800067f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067fb  mov     rax, rbx
0x1800067fe  mov     rbx, [rsp+28h+arg_0]
0x180006803  mov     rsi, [rsp+28h+arg_8]
0x180006808  add     rsp, 20h
0x18000680c  pop     rdi
0x18000680d  retn
```
