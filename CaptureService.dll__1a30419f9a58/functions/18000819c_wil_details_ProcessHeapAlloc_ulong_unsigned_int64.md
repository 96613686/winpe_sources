# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000819c`
- end: `0x180008232`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006e6c`
- `0x180007cf8`
- `0x180007e58`
- `0x180009120`
- `0x1800095b4`
- `0x18000abb0`

## callees

- `0x180004098`
- `0x18000819c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800081e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800081e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800081c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800081c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081b0`

## string_xrefs

- `0x1800081de`: `ntdll.dll`

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
0x18000819c  mov     [rsp+arg_0], rbx
0x1800081a1  mov     [rsp+arg_8], rsi
0x1800081a6  push    rdi
0x1800081a7  sub     rsp, 20h
0x1800081ab  mov     rbx, rdx
0x1800081ae  mov     edi, ecx
0x1800081b0  call    cs:__imp_GetProcessHeap
0x1800081b6  mov     rsi, rax
0x1800081b9  mov     r8, rbx; dwBytes
0x1800081bc  mov     edx, edi; dwFlags
0x1800081be  mov     rcx, rax; hHeap
0x1800081c1  call    cs:__imp_HeapAlloc
0x1800081c7  mov     rbx, rax
0x1800081ca  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800081d1  test    rax, rax
0x1800081d4  jnz     short loc_180008214
0x1800081d6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800081dc  jnz     short loc_18000821F
0x1800081de  lea     rcx, ModuleName; "ntdll.dll"
0x1800081e5  call    cs:__imp_GetModuleHandleW
0x1800081eb  test    rax, rax
0x1800081ee  jz      short loc_180008201
0x1800081f0  mov     rcx, rax
0x1800081f3  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800081f8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800081ff  jmp     short loc_180008208
0x180008201  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008208  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000820f  test    rax, rax
0x180008212  jz      short loc_18000821F
0x180008214  mov     rdx, rbx
0x180008217  mov     rcx, rsi
0x18000821a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000821f  mov     rax, rbx
0x180008222  mov     rbx, [rsp+28h+arg_0]
0x180008227  mov     rsi, [rsp+28h+arg_8]
0x18000822c  add     rsp, 20h
0x180008230  pop     rdi
0x180008231  retn
```
