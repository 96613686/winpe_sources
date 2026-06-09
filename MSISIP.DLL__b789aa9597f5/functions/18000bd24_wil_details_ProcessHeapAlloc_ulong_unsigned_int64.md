# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000bd24`
- end: `0x18000bdc4`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `160`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000983c`
- `0x180009990`
- `0x18000c39c`
- `0x18000c734`
- `0x18000cc9c`

## callees

- `0x18000a5c0`
- `0x18000bd24`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000bd77`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000bd77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bd53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bd53`

## string_xrefs

- `0x18000bd70`: `ntdll.dll`

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
0x18000bd24  push    rdi
0x18000bd26  sub     rsp, 30h
0x18000bd2a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000bd33  mov     [rsp+38h+arg_0], rbx
0x18000bd38  mov     [rsp+38h+arg_8], rsi
0x18000bd3d  mov     rbx, rdx
0x18000bd40  mov     edi, ecx
0x18000bd42  call    cs:__imp_GetProcessHeap
0x18000bd48  mov     rsi, rax
0x18000bd4b  mov     r8, rbx; dwBytes
0x18000bd4e  mov     edx, edi; dwFlags
0x18000bd50  mov     rcx, rax; hHeap
0x18000bd53  call    cs:__imp_HeapAlloc
0x18000bd59  mov     rbx, rax
0x18000bd5c  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000bd63  test    rax, rax
0x18000bd66  jnz     short loc_18000BDA6
0x18000bd68  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000bd6e  jnz     short loc_18000BDB1
0x18000bd70  lea     rcx, ModuleName; "ntdll.dll"
0x18000bd77  call    cs:__imp_GetModuleHandleW
0x18000bd7d  test    rax, rax
0x18000bd80  jz      short loc_18000BD93
0x18000bd82  mov     rcx, rax
0x18000bd85  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000bd8a  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000bd91  jmp     short loc_18000BD9A
0x18000bd93  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000bd9a  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000bda1  test    rax, rax
0x18000bda4  jz      short loc_18000BDB1
0x18000bda6  mov     rdx, rbx
0x18000bda9  mov     rcx, rsi
0x18000bdac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb1  mov     rax, rbx
0x18000bdb4  mov     rbx, [rsp+38h+arg_0]
0x18000bdb9  mov     rsi, [rsp+38h+arg_8]
0x18000bdbe  add     rsp, 30h
0x18000bdc2  pop     rdi
0x18000bdc3  retn
```
