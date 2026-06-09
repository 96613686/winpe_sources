# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005258`
- end: `0x1400052ee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140004e38`
- `0x140004f68`
- `0x140006070`
- `0x1400064f8`
- `0x14000740c`

## callees

- `0x14000222c`
- `0x140005258`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400052a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400052a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000526c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000526c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000527d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000527d`

## string_xrefs

- `0x14000529a`: `ntdll.dll`

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
0x140005258  mov     [rsp+arg_0], rbx
0x14000525d  mov     [rsp+arg_8], rsi
0x140005262  push    rdi
0x140005263  sub     rsp, 20h
0x140005267  mov     rbx, rdx
0x14000526a  mov     edi, ecx
0x14000526c  call    cs:__imp_GetProcessHeap
0x140005272  mov     rsi, rax
0x140005275  mov     r8, rbx; dwBytes
0x140005278  mov     edx, edi; dwFlags
0x14000527a  mov     rcx, rax; hHeap
0x14000527d  call    cs:__imp_HeapAlloc
0x140005283  mov     rbx, rax
0x140005286  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000528d  test    rax, rax
0x140005290  jnz     short loc_1400052D0
0x140005292  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005298  jnz     short loc_1400052DB
0x14000529a  lea     rcx, ModuleName; "ntdll.dll"
0x1400052a1  call    cs:__imp_GetModuleHandleW
0x1400052a7  test    rax, rax
0x1400052aa  jz      short loc_1400052BD
0x1400052ac  mov     rcx, rax
0x1400052af  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1400052b4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400052bb  jmp     short loc_1400052C4
0x1400052bd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400052c4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400052cb  test    rax, rax
0x1400052ce  jz      short loc_1400052DB
0x1400052d0  mov     rdx, rbx
0x1400052d3  mov     rcx, rsi
0x1400052d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052db  mov     rax, rbx
0x1400052de  mov     rbx, [rsp+28h+arg_0]
0x1400052e3  mov     rsi, [rsp+28h+arg_8]
0x1400052e8  add     rsp, 20h
0x1400052ec  pop     rdi
0x1400052ed  retn
```
