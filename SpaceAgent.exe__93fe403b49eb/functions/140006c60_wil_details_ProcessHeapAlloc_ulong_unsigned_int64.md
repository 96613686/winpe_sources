# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140006c60`
- end: `0x140006cf6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140006748`
- `0x14000686c`
- `0x140007a74`
- `0x140007cd8`
- `0x140009500`

## callees

- `0x14000387c`
- `0x140006c60`
- `0x140020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140006c85`
- `KERNEL32!HeapAlloc` at `0x140006c85`
- `KERNEL32!GetProcessHeap` at `0x140006c74`
- `KERNEL32!GetProcessHeap` at `0x140006c74`
- `KERNEL32!GetModuleHandleW` at `0x140006ca9`
- `KERNEL32!GetModuleHandleW` at `0x140006ca9`

## string_xrefs

- `0x140006ca2`: `ntdll.dll`

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
0x140006c60  mov     [rsp+arg_0], rbx
0x140006c65  mov     [rsp+arg_8], rsi
0x140006c6a  push    rdi
0x140006c6b  sub     rsp, 20h
0x140006c6f  mov     rbx, rdx
0x140006c72  mov     edi, ecx
0x140006c74  call    cs:__imp_GetProcessHeap
0x140006c7a  mov     r8, rbx; dwBytes
0x140006c7d  mov     edx, edi; dwFlags
0x140006c7f  mov     rcx, rax; hHeap
0x140006c82  mov     rsi, rax
0x140006c85  call    cs:__imp_HeapAlloc
0x140006c8b  mov     rbx, rax
0x140006c8e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006c95  test    rax, rax
0x140006c98  jnz     short loc_140006CD8
0x140006c9a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006ca0  jnz     short loc_140006CE3
0x140006ca2  lea     rcx, ModuleName; "ntdll.dll"
0x140006ca9  call    cs:__imp_GetModuleHandleW
0x140006caf  test    rax, rax
0x140006cb2  jz      short loc_140006CC5
0x140006cb4  mov     rcx, rax
0x140006cb7  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x140006cbc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140006cc3  jmp     short loc_140006CCC
0x140006cc5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006ccc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006cd3  test    rax, rax
0x140006cd6  jz      short loc_140006CE3
0x140006cd8  mov     rdx, rbx
0x140006cdb  mov     rcx, rsi
0x140006cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ce3  mov     rsi, [rsp+28h+arg_8]
0x140006ce8  mov     rax, rbx
0x140006ceb  mov     rbx, [rsp+28h+arg_0]
0x140006cf0  add     rsp, 20h
0x140006cf4  pop     rdi
0x140006cf5  retn
```
