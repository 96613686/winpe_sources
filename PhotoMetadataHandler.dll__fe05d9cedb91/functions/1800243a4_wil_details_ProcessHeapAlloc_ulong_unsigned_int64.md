# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800243a4`
- end: `0x180024437`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `147`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180014f50`
- `0x1800150a4`
- `0x180024de4`
- `0x180025044`
- `0x180025cb0`

## callees

- `0x180016c3e`
- `0x180016cd4`
- `0x180016ce0`
- `0x180021f48`
- `0x1800243a4`
- `0x180028010`

## string_xrefs

- `0x1800243e4`: `ntdll.dll`

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
0x1800243a4  mov     [rsp+arg_0], rbx
0x1800243a9  mov     [rsp+arg_8], rsi
0x1800243ae  push    rdi
0x1800243af  sub     rsp, 20h
0x1800243b3  mov     rbx, rdx
0x1800243b6  mov     edi, ecx
0x1800243b8  call    GetProcessHeap_0
0x1800243bd  mov     r8, rbx; dwBytes
0x1800243c0  mov     edx, edi; dwFlags
0x1800243c2  mov     rcx, rax; hHeap
0x1800243c5  mov     rsi, rax
0x1800243c8  call    HeapAlloc_0
0x1800243cd  mov     rbx, rax
0x1800243d0  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800243d7  test    rax, rax
0x1800243da  jnz     short loc_180024419
0x1800243dc  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800243e2  jnz     short loc_180024424
0x1800243e4  lea     rcx, ModuleName; "ntdll.dll"
0x1800243eb  call    GetModuleHandleW_0
0x1800243f0  test    rax, rax
0x1800243f3  jz      short loc_180024406
0x1800243f5  mov     rcx, rax
0x1800243f8  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800243fd  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180024404  jmp     short loc_18002440D
0x180024406  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002440d  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180024414  test    rax, rax
0x180024417  jz      short loc_180024424
0x180024419  mov     rdx, rbx
0x18002441c  mov     rcx, rsi
0x18002441f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024424  mov     rsi, [rsp+28h+arg_8]
0x180024429  mov     rax, rbx
0x18002442c  mov     rbx, [rsp+28h+arg_0]
0x180024431  add     rsp, 20h
0x180024435  pop     rdi
0x180024436  retn
```
