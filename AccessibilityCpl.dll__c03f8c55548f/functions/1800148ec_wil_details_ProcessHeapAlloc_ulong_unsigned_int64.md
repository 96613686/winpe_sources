# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800148ec`
- end: `0x180014982`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012fe8`
- `0x18001314c`
- `0x180017ffc`
- `0x18001844c`
- `0x18001b7e0`

## callees

- `0x180003a38`
- `0x1800148ec`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014911`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014900`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014900`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014935`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014935`

## string_xrefs

- `0x18001492e`: `ntdll.dll`

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
0x1800148ec  mov     [rsp+arg_0], rbx
0x1800148f1  mov     [rsp+arg_8], rsi
0x1800148f6  push    rdi
0x1800148f7  sub     rsp, 20h
0x1800148fb  mov     rbx, rdx
0x1800148fe  mov     edi, ecx
0x180014900  call    cs:__imp_GetProcessHeap
0x180014906  mov     r8, rbx; dwBytes
0x180014909  mov     edx, edi; dwFlags
0x18001490b  mov     rcx, rax; hHeap
0x18001490e  mov     rsi, rax
0x180014911  call    cs:__imp_HeapAlloc
0x180014917  mov     rbx, rax
0x18001491a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014921  test    rax, rax
0x180014924  jnz     short loc_180014964
0x180014926  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001492c  jnz     short loc_18001496F
0x18001492e  lea     rcx, ModuleName; "ntdll.dll"
0x180014935  call    cs:__imp_GetModuleHandleW
0x18001493b  test    rax, rax
0x18001493e  jz      short loc_180014951
0x180014940  mov     rcx, rax
0x180014943  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180014948  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001494f  jmp     short loc_180014958
0x180014951  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014958  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001495f  test    rax, rax
0x180014962  jz      short loc_18001496F
0x180014964  mov     rdx, rbx
0x180014967  mov     rcx, rsi
0x18001496a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001496f  mov     rsi, [rsp+28h+arg_8]
0x180014974  mov     rax, rbx
0x180014977  mov     rbx, [rsp+28h+arg_0]
0x18001497c  add     rsp, 20h
0x180014980  pop     rdi
0x180014981  retn
```
