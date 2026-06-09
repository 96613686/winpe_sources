# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007494`
- end: `0x18000753d`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006edc`
- `0x18000703c`
- `0x1800088a4`
- `0x180008d48`
- `0x18000a50c`

## callees

- `0x18000375c`
- `0x180007494`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800074bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800074bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800074a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800074a8`

## string_xrefs

- `0x1800074e2`: `ntdll.dll`

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
0x180007494  mov     [rsp+arg_0], rbx
0x180007499  mov     [rsp+arg_8], rsi
0x18000749e  push    rdi
0x18000749f  sub     rsp, 20h
0x1800074a3  mov     rbx, rdx
0x1800074a6  mov     edi, ecx
0x1800074a8  call    cs:__imp_GetProcessHeap
0x1800074af  nop     dword ptr [rax+rax+00h]
0x1800074b4  mov     rsi, rax
0x1800074b7  mov     r8, rbx; dwBytes
0x1800074ba  mov     edx, edi; dwFlags
0x1800074bc  mov     rcx, rax; hHeap
0x1800074bf  call    cs:__imp_HeapAlloc
0x1800074c6  nop     dword ptr [rax+rax+00h]
0x1800074cb  mov     rbx, rax
0x1800074ce  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800074d5  test    rax, rax
0x1800074d8  jnz     short loc_18000751E
0x1800074da  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800074e0  jnz     short loc_180007529
0x1800074e2  lea     rcx, ModuleName; "ntdll.dll"
0x1800074e9  call    cs:__imp_GetModuleHandleW
0x1800074f0  nop     dword ptr [rax+rax+00h]
0x1800074f5  test    rax, rax
0x1800074f8  jz      short loc_18000750B
0x1800074fa  mov     rcx, rax
0x1800074fd  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180007502  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007509  jmp     short loc_180007512
0x18000750b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007512  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007519  test    rax, rax
0x18000751c  jz      short loc_180007529
0x18000751e  mov     rdx, rbx
0x180007521  mov     rcx, rsi
0x180007524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007529  mov     rax, rbx
0x18000752c  mov     rbx, [rsp+28h+arg_0]
0x180007531  mov     rsi, [rsp+28h+arg_8]
0x180007536  add     rsp, 20h
0x18000753a  pop     rdi
0x18000753b  retn
```
