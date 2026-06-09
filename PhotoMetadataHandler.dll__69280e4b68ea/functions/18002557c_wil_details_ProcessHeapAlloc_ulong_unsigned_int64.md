# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002557c`
- end: `0x180025610`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `148`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001595c`
- `0x180015ab4`
- `0x180025ff8`
- `0x18002625c`
- `0x180026ef0`

## callees

- `0x18001768e`
- `0x180017724`
- `0x180017730`
- `0x18002304c`
- `0x18002557c`
- `0x180029010`

## string_xrefs

- `0x1800255bc`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap_0; // rsi
  LPVOID v5; // rbx
  void (__fastcall *ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(HANDLE, LPVOID); // rax
  HMODULE ModuleHandleW_0; // rax

  ProcessHeap_0 = GetProcessHeap_0();
  v5 = HeapAlloc_0(ProcessHeap_0, dwFlags, dwBytes);
  ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW_0 = GetModuleHandleW_0(L"ntdll.dll")) == 0
      ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (void (__fastcall *)(HANDLE, LPVOID))(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW_0),
                                              `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z) )
  {
    ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ProcessHeap_0, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18002557c  mov     [rsp+arg_0], rbx
0x180025581  mov     [rsp+arg_8], rsi
0x180025586  push    rdi
0x180025587  sub     rsp, 20h
0x18002558b  mov     rbx, rdx
0x18002558e  mov     edi, ecx
0x180025590  call    GetProcessHeap_0
0x180025595  mov     r8, rbx; dwBytes
0x180025598  mov     edx, edi; dwFlags
0x18002559a  mov     rcx, rax; hHeap
0x18002559d  mov     rsi, rax
0x1800255a0  call    HeapAlloc_0
0x1800255a5  mov     rbx, rax
0x1800255a8  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800255af  test    rax, rax
0x1800255b2  jnz     short loc_1800255F1
0x1800255b4  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800255ba  jnz     short loc_1800255FC
0x1800255bc  lea     rcx, ModuleName; "ntdll.dll"
0x1800255c3  call    GetModuleHandleW_0
0x1800255c8  test    rax, rax
0x1800255cb  jz      short loc_1800255DE
0x1800255cd  mov     rcx, rax
0x1800255d0  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800255d5  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800255dc  jmp     short loc_1800255E5
0x1800255de  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800255e5  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800255ec  test    rax, rax
0x1800255ef  jz      short loc_1800255FC
0x1800255f1  mov     rdx, rbx
0x1800255f4  mov     rcx, rsi
0x1800255f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255fc  mov     rsi, [rsp+28h+arg_8]
0x180025601  mov     rax, rbx
0x180025604  mov     rbx, [rsp+28h+arg_0]
0x180025609  add     rsp, 20h
0x18002560d  pop     rdi
0x18002560e  retn
```
