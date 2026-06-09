# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c3d4`
- end: `0x18000c46a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000bc98`
- `0x18000bdc8`
- `0x18000de78`
- `0x18000e32c`
- `0x180010c4c`

## callees

- `0x180004da8`
- `0x18000c3d4`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c41d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c41d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c3f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c3f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c3e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c3e8`

## string_xrefs

- `0x18000c416`: `ntdll.dll`

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
0x18000c3d4  mov     [rsp+arg_0], rbx
0x18000c3d9  mov     [rsp+arg_8], rsi
0x18000c3de  push    rdi
0x18000c3df  sub     rsp, 20h
0x18000c3e3  mov     rbx, rdx
0x18000c3e6  mov     edi, ecx
0x18000c3e8  call    cs:__imp_GetProcessHeap
0x18000c3ee  mov     rsi, rax
0x18000c3f1  mov     r8, rbx; dwBytes
0x18000c3f4  mov     edx, edi; dwFlags
0x18000c3f6  mov     rcx, rax; hHeap
0x18000c3f9  call    cs:__imp_HeapAlloc
0x18000c3ff  mov     rbx, rax
0x18000c402  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c409  test    rax, rax
0x18000c40c  jnz     short loc_18000C44C
0x18000c40e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c414  jnz     short loc_18000C457
0x18000c416  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000c41d  call    cs:__imp_GetModuleHandleW
0x18000c423  test    rax, rax
0x18000c426  jz      short loc_18000C439
0x18000c428  mov     rcx, rax
0x18000c42b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000c430  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000c437  jmp     short loc_18000C440
0x18000c439  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c440  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c447  test    rax, rax
0x18000c44a  jz      short loc_18000C457
0x18000c44c  mov     rdx, rbx
0x18000c44f  mov     rcx, rsi
0x18000c452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c457  mov     rax, rbx
0x18000c45a  mov     rbx, [rsp+28h+arg_0]
0x18000c45f  mov     rsi, [rsp+28h+arg_8]
0x18000c464  add     rsp, 20h
0x18000c468  pop     rdi
0x18000c469  retn
```
