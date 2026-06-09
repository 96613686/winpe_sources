# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008ee8`
- end: `0x180008f7e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000783c`
- `0x1800078e0`
- `0x18000880c`
- `0x180008970`
- `0x18000a5d4`
- `0x18000aa64`
- `0x18000bdcc`

## callees

- `0x180004a84`
- `0x180008ee8`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008efc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008efc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f0d`

## string_xrefs

- `0x180008f2a`: `ntdll.dll`

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
0x180008ee8  mov     [rsp+arg_0], rbx
0x180008eed  mov     [rsp+arg_8], rsi
0x180008ef2  push    rdi
0x180008ef3  sub     rsp, 20h
0x180008ef7  mov     rbx, rdx
0x180008efa  mov     edi, ecx
0x180008efc  call    cs:__imp_GetProcessHeap
0x180008f02  mov     rsi, rax
0x180008f05  mov     r8, rbx; dwBytes
0x180008f08  mov     edx, edi; dwFlags
0x180008f0a  mov     rcx, rax; hHeap
0x180008f0d  call    cs:__imp_HeapAlloc
0x180008f13  mov     rbx, rax
0x180008f16  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008f1d  test    rax, rax
0x180008f20  jnz     short loc_180008F60
0x180008f22  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008f28  jnz     short loc_180008F6B
0x180008f2a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008f31  call    cs:__imp_GetModuleHandleW
0x180008f37  test    rax, rax
0x180008f3a  jz      short loc_180008F4D
0x180008f3c  mov     rcx, rax
0x180008f3f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180008f44  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008f4b  jmp     short loc_180008F54
0x180008f4d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008f54  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008f5b  test    rax, rax
0x180008f5e  jz      short loc_180008F6B
0x180008f60  mov     rdx, rbx
0x180008f63  mov     rcx, rsi
0x180008f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f6b  mov     rax, rbx
0x180008f6e  mov     rbx, [rsp+28h+arg_0]
0x180008f73  mov     rsi, [rsp+28h+arg_8]
0x180008f78  add     rsp, 20h
0x180008f7c  pop     rdi
0x180008f7d  retn
```
