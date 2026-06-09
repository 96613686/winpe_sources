# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006c98`
- end: `0x180006d2e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800060ec`
- `0x180006a8c`
- `0x180006f30`
- `0x1800072c8`
- `0x18000a0e8`
- `0x18000c37c`

## callees

- `0x180004b98`
- `0x180006c98`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ce1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ce1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006cbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006cbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cac`

## string_xrefs

- `0x180006cda`: `ntdll.dll`

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
0x180006c98  mov     [rsp+arg_0], rbx
0x180006c9d  mov     [rsp+arg_8], rsi
0x180006ca2  push    rdi
0x180006ca3  sub     rsp, 20h
0x180006ca7  mov     rbx, rdx
0x180006caa  mov     edi, ecx
0x180006cac  call    cs:__imp_GetProcessHeap
0x180006cb2  mov     rsi, rax
0x180006cb5  mov     r8, rbx; dwBytes
0x180006cb8  mov     edx, edi; dwFlags
0x180006cba  mov     rcx, rax; hHeap
0x180006cbd  call    cs:__imp_HeapAlloc
0x180006cc3  mov     rbx, rax
0x180006cc6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006ccd  test    rax, rax
0x180006cd0  jnz     short loc_180006D10
0x180006cd2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006cd8  jnz     short loc_180006D1B
0x180006cda  lea     rcx, ModuleName; "ntdll.dll"
0x180006ce1  call    cs:__imp_GetModuleHandleW
0x180006ce7  test    rax, rax
0x180006cea  jz      short loc_180006CFD
0x180006cec  mov     rcx, rax
0x180006cef  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180006cf4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006cfb  jmp     short loc_180006D04
0x180006cfd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006d04  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006d0b  test    rax, rax
0x180006d0e  jz      short loc_180006D1B
0x180006d10  mov     rdx, rbx
0x180006d13  mov     rcx, rsi
0x180006d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1b  mov     rax, rbx
0x180006d1e  mov     rbx, [rsp+28h+arg_0]
0x180006d23  mov     rsi, [rsp+28h+arg_8]
0x180006d28  add     rsp, 20h
0x180006d2c  pop     rdi
0x180006d2d  retn
```
