# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007590`
- end: `0x180007626`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006fa8`
- `0x1800070d8`
- `0x180008860`
- `0x180008ce4`
- `0x180009f80`

## callees

- `0x180003f6c`
- `0x180007590`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800075d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800075d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800075b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800075b5`

## string_xrefs

- `0x1800075d2`: `ntdll.dll`

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
0x180007590  mov     [rsp+arg_0], rbx
0x180007595  mov     [rsp+arg_8], rsi
0x18000759a  push    rdi
0x18000759b  sub     rsp, 20h
0x18000759f  mov     rbx, rdx
0x1800075a2  mov     edi, ecx
0x1800075a4  call    cs:__imp_GetProcessHeap
0x1800075aa  mov     rsi, rax
0x1800075ad  mov     r8, rbx; dwBytes
0x1800075b0  mov     edx, edi; dwFlags
0x1800075b2  mov     rcx, rax; hHeap
0x1800075b5  call    cs:__imp_HeapAlloc
0x1800075bb  mov     rbx, rax
0x1800075be  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800075c5  test    rax, rax
0x1800075c8  jnz     short loc_180007608
0x1800075ca  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800075d0  jnz     short loc_180007613
0x1800075d2  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800075d9  call    cs:__imp_GetModuleHandleW
0x1800075df  test    rax, rax
0x1800075e2  jz      short loc_1800075F5
0x1800075e4  mov     rcx, rax
0x1800075e7  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800075ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800075f3  jmp     short loc_1800075FC
0x1800075f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800075fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007603  test    rax, rax
0x180007606  jz      short loc_180007613
0x180007608  mov     rdx, rbx
0x18000760b  mov     rcx, rsi
0x18000760e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007613  mov     rax, rbx
0x180007616  mov     rbx, [rsp+28h+arg_0]
0x18000761b  mov     rsi, [rsp+28h+arg_8]
0x180007620  add     rsp, 20h
0x180007624  pop     rdi
0x180007625  retn
```
