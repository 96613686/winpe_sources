# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000ab00`
- end: `0x18000aba9`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a810`
- `0x18000b0c4`
- `0x18000b478`
- `0x18000c258`
- `0x1800376d0`

## callees

- `0x180007cec`
- `0x18000ab00`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ab55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ab55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ab2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ab2b`

## string_xrefs

- `0x18000ab4e`: `ntdll.dll`

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
0x18000ab00  mov     [rsp+arg_0], rbx
0x18000ab05  mov     [rsp+arg_8], rsi
0x18000ab0a  push    rdi
0x18000ab0b  sub     rsp, 20h
0x18000ab0f  mov     rbx, rdx
0x18000ab12  mov     edi, ecx
0x18000ab14  call    cs:__imp_GetProcessHeap
0x18000ab1b  nop     dword ptr [rax+rax+00h]
0x18000ab20  mov     rsi, rax
0x18000ab23  mov     r8, rbx; dwBytes
0x18000ab26  mov     edx, edi; dwFlags
0x18000ab28  mov     rcx, rax; hHeap
0x18000ab2b  call    cs:__imp_HeapAlloc
0x18000ab32  nop     dword ptr [rax+rax+00h]
0x18000ab37  mov     rbx, rax
0x18000ab3a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ab41  test    rax, rax
0x18000ab44  jnz     short loc_18000AB8A
0x18000ab46  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ab4c  jnz     short loc_18000AB95
0x18000ab4e  lea     rcx, ModuleName; "ntdll.dll"
0x18000ab55  call    cs:__imp_GetModuleHandleW
0x18000ab5c  nop     dword ptr [rax+rax+00h]
0x18000ab61  test    rax, rax
0x18000ab64  jz      short loc_18000AB77
0x18000ab66  mov     rcx, rax
0x18000ab69  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000ab6e  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ab75  jmp     short loc_18000AB7E
0x18000ab77  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ab7e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ab85  test    rax, rax
0x18000ab88  jz      short loc_18000AB95
0x18000ab8a  mov     rdx, rbx
0x18000ab8d  mov     rcx, rsi
0x18000ab90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab95  mov     rax, rbx
0x18000ab98  mov     rbx, [rsp+28h+arg_0]
0x18000ab9d  mov     rsi, [rsp+28h+arg_8]
0x18000aba2  add     rsp, 20h
0x18000aba6  pop     rdi
0x18000aba7  retn
```
