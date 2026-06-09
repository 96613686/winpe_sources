# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007104`
- end: `0x18000719a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005dec`
- `0x180006b14`
- `0x180006c78`
- `0x180008050`
- `0x1800084e0`
- `0x1800097ac`

## callees

- `0x180003c94`
- `0x180007104`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000714d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000714d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007118`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007118`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007129`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007129`

## string_xrefs

- `0x180007146`: `ntdll.dll`

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
0x180007104  mov     [rsp+arg_0], rbx
0x180007109  mov     [rsp+arg_8], rsi
0x18000710e  push    rdi
0x18000710f  sub     rsp, 20h
0x180007113  mov     rbx, rdx
0x180007116  mov     edi, ecx
0x180007118  call    cs:__imp_GetProcessHeap
0x18000711e  mov     rsi, rax
0x180007121  mov     r8, rbx; dwBytes
0x180007124  mov     edx, edi; dwFlags
0x180007126  mov     rcx, rax; hHeap
0x180007129  call    cs:__imp_HeapAlloc
0x18000712f  mov     rbx, rax
0x180007132  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007139  test    rax, rax
0x18000713c  jnz     short loc_18000717C
0x18000713e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007144  jnz     short loc_180007187
0x180007146  lea     rcx, ModuleName; "ntdll.dll"
0x18000714d  call    cs:__imp_GetModuleHandleW
0x180007153  test    rax, rax
0x180007156  jz      short loc_180007169
0x180007158  mov     rcx, rax
0x18000715b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180007160  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007167  jmp     short loc_180007170
0x180007169  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007170  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007177  test    rax, rax
0x18000717a  jz      short loc_180007187
0x18000717c  mov     rdx, rbx
0x18000717f  mov     rcx, rsi
0x180007182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007187  mov     rax, rbx
0x18000718a  mov     rbx, [rsp+28h+arg_0]
0x18000718f  mov     rsi, [rsp+28h+arg_8]
0x180007194  add     rsp, 20h
0x180007198  pop     rdi
0x180007199  retn
```
