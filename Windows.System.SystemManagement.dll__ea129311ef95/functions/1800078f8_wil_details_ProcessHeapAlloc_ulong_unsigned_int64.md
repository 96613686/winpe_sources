# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800078f8`
- end: `0x18000798e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006b3c`
- `0x18000760c`
- `0x180007e20`
- `0x1800081b8`
- `0x180011344`
- `0x180012dbc`

## callees

- `0x180004028`
- `0x1800078f8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007941`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000790c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000790c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000791d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000791d`

## string_xrefs

- `0x18000793a`: `ntdll.dll`

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
0x1800078f8  mov     [rsp+arg_0], rbx
0x1800078fd  mov     [rsp+arg_8], rsi
0x180007902  push    rdi
0x180007903  sub     rsp, 20h
0x180007907  mov     rbx, rdx
0x18000790a  mov     edi, ecx
0x18000790c  call    cs:__imp_GetProcessHeap
0x180007912  mov     rsi, rax
0x180007915  mov     r8, rbx; dwBytes
0x180007918  mov     edx, edi; dwFlags
0x18000791a  mov     rcx, rax; hHeap
0x18000791d  call    cs:__imp_HeapAlloc
0x180007923  mov     rbx, rax
0x180007926  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000792d  test    rax, rax
0x180007930  jnz     short loc_180007970
0x180007932  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007938  jnz     short loc_18000797B
0x18000793a  lea     rcx, ModuleName; "ntdll.dll"
0x180007941  call    cs:__imp_GetModuleHandleW
0x180007947  test    rax, rax
0x18000794a  jz      short loc_18000795D
0x18000794c  mov     rcx, rax
0x18000794f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180007954  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000795b  jmp     short loc_180007964
0x18000795d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007964  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000796b  test    rax, rax
0x18000796e  jz      short loc_18000797B
0x180007970  mov     rdx, rbx
0x180007973  mov     rcx, rsi
0x180007976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000797b  mov     rax, rbx
0x18000797e  mov     rbx, [rsp+28h+arg_0]
0x180007983  mov     rsi, [rsp+28h+arg_8]
0x180007988  add     rsp, 20h
0x18000798c  pop     rdi
0x18000798d  retn
```
