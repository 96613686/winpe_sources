# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008acc`
- end: `0x180008b62`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002ab8`
- `0x1800087d8`
- `0x18000923c`
- `0x1800095d4`

## callees

- `0x180005ef4`
- `0x180008acc`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ae0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ae0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008af1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008af1`

## string_xrefs

- `0x180008b0e`: `ntdll.dll`

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
0x180008acc  mov     [rsp+arg_0], rbx
0x180008ad1  mov     [rsp+arg_8], rsi
0x180008ad6  push    rdi
0x180008ad7  sub     rsp, 20h
0x180008adb  mov     rbx, rdx
0x180008ade  mov     edi, ecx
0x180008ae0  call    cs:__imp_GetProcessHeap
0x180008ae6  mov     rsi, rax
0x180008ae9  mov     r8, rbx; dwBytes
0x180008aec  mov     edx, edi; dwFlags
0x180008aee  mov     rcx, rax; hHeap
0x180008af1  call    cs:__imp_HeapAlloc
0x180008af7  mov     rbx, rax
0x180008afa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008b01  test    rax, rax
0x180008b04  jnz     short loc_180008B44
0x180008b06  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008b0c  jnz     short loc_180008B4F
0x180008b0e  lea     rcx, ModuleName; "ntdll.dll"
0x180008b15  call    cs:__imp_GetModuleHandleW
0x180008b1b  test    rax, rax
0x180008b1e  jz      short loc_180008B31
0x180008b20  mov     rcx, rax
0x180008b23  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180008b28  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008b2f  jmp     short loc_180008B38
0x180008b31  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008b38  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008b3f  test    rax, rax
0x180008b42  jz      short loc_180008B4F
0x180008b44  mov     rdx, rbx
0x180008b47  mov     rcx, rsi
0x180008b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b4f  mov     rax, rbx
0x180008b52  mov     rbx, [rsp+28h+arg_0]
0x180008b57  mov     rsi, [rsp+28h+arg_8]
0x180008b5c  add     rsp, 20h
0x180008b60  pop     rdi
0x180008b61  retn
```
