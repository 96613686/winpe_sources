# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180013538`
- end: `0x1800135ce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `10`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001348c`
- `0x180027060`
- `0x180028340`
- `0x18002846c`
- `0x180028b50`
- `0x180028ee8`
- `0x18002c0d0`
- `0x18002c520`
- `0x18002c950`
- `0x18002cd80`

## callees

- `0x180013538`
- `0x180024400`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013581`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013581`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001355d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001355d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001354c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001354c`

## string_xrefs

- `0x18001357a`: `ntdll.dll`

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
0x180013538  mov     [rsp+arg_0], rbx
0x18001353d  mov     [rsp+arg_8], rsi
0x180013542  push    rdi
0x180013543  sub     rsp, 20h
0x180013547  mov     rbx, rdx
0x18001354a  mov     edi, ecx
0x18001354c  call    cs:__imp_GetProcessHeap
0x180013552  mov     rsi, rax
0x180013555  mov     r8, rbx; dwBytes
0x180013558  mov     edx, edi; dwFlags
0x18001355a  mov     rcx, rax; hHeap
0x18001355d  call    cs:__imp_HeapAlloc
0x180013563  mov     rbx, rax
0x180013566  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001356d  test    rax, rax
0x180013570  jnz     short loc_1800135B0
0x180013572  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180013578  jnz     short loc_1800135BB
0x18001357a  lea     rcx, ModuleName; "ntdll.dll"
0x180013581  call    cs:__imp_GetModuleHandleW
0x180013587  test    rax, rax
0x18001358a  jz      short loc_18001359D
0x18001358c  mov     rcx, rax
0x18001358f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180013594  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001359b  jmp     short loc_1800135A4
0x18001359d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800135a4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800135ab  test    rax, rax
0x1800135ae  jz      short loc_1800135BB
0x1800135b0  mov     rdx, rbx
0x1800135b3  mov     rcx, rsi
0x1800135b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135bb  mov     rax, rbx
0x1800135be  mov     rbx, [rsp+28h+arg_0]
0x1800135c3  mov     rsi, [rsp+28h+arg_8]
0x1800135c8  add     rsp, 20h
0x1800135cc  pop     rdi
0x1800135cd  retn
```
