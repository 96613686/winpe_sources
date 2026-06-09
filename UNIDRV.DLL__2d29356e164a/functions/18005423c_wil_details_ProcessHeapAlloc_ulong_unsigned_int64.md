# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005423c`
- end: `0x1800542d2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180053a0c`
- `0x180053b30`
- `0x1800554e4`
- `0x18005574c`
- `0x180056770`

## callees

- `0x18005065c`
- `0x18005423c`
- `0x180075010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180054250`
- `KERNEL32!GetProcessHeap` at `0x180054250`
- `KERNEL32!HeapAlloc` at `0x180054261`
- `KERNEL32!HeapAlloc` at `0x180054261`
- `KERNEL32!GetModuleHandleW` at `0x180054285`
- `KERNEL32!GetModuleHandleW` at `0x180054285`

## string_xrefs

- `0x18005427e`: `ntdll.dll`

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
0x18005423c  mov     [rsp+arg_0], rbx
0x180054241  mov     [rsp+arg_8], rsi
0x180054246  push    rdi
0x180054247  sub     rsp, 20h
0x18005424b  mov     rbx, rdx
0x18005424e  mov     edi, ecx
0x180054250  call    cs:__imp_GetProcessHeap
0x180054256  mov     r8, rbx; dwBytes
0x180054259  mov     edx, edi; dwFlags
0x18005425b  mov     rcx, rax; hHeap
0x18005425e  mov     rsi, rax
0x180054261  call    cs:__imp_HeapAlloc
0x180054267  mov     rbx, rax
0x18005426a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180054271  test    rax, rax
0x180054274  jnz     short loc_1800542B4
0x180054276  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18005427c  jnz     short loc_1800542BF
0x18005427e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180054285  call    cs:__imp_GetModuleHandleW
0x18005428b  test    rax, rax
0x18005428e  jz      short loc_1800542A1
0x180054290  mov     rcx, rax
0x180054293  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180054298  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18005429f  jmp     short loc_1800542A8
0x1800542a1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800542a8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800542af  test    rax, rax
0x1800542b2  jz      short loc_1800542BF
0x1800542b4  mov     rdx, rbx
0x1800542b7  mov     rcx, rsi
0x1800542ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542bf  mov     rsi, [rsp+28h+arg_8]
0x1800542c4  mov     rax, rbx
0x1800542c7  mov     rbx, [rsp+28h+arg_0]
0x1800542cc  add     rsp, 20h
0x1800542d0  pop     rdi
0x1800542d1  retn
```
