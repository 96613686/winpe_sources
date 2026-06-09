# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400052e0`
- end: `0x140005376`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400050a8`
- `0x140005564`
- `0x1400056dc`
- `0x140007d68`
- `0x14000af40`

## callees

- `0x1400033cc`
- `0x1400052e0`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005329`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005329`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400052f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400052f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005305`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005305`

## string_xrefs

- `0x140005322`: `ntdll.dll`

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
0x1400052e0  mov     [rsp+arg_0], rbx
0x1400052e5  mov     [rsp+arg_8], rsi
0x1400052ea  push    rdi
0x1400052eb  sub     rsp, 20h
0x1400052ef  mov     rbx, rdx
0x1400052f2  mov     edi, ecx
0x1400052f4  call    cs:__imp_GetProcessHeap
0x1400052fa  mov     r8, rbx; dwBytes
0x1400052fd  mov     edx, edi; dwFlags
0x1400052ff  mov     rcx, rax; hHeap
0x140005302  mov     rsi, rax
0x140005305  call    cs:__imp_HeapAlloc
0x14000530b  mov     rbx, rax
0x14000530e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005315  test    rax, rax
0x140005318  jnz     short loc_140005358
0x14000531a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005320  jnz     short loc_140005363
0x140005322  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140005329  call    cs:__imp_GetModuleHandleW
0x14000532f  test    rax, rax
0x140005332  jz      short loc_140005345
0x140005334  mov     rcx, rax
0x140005337  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x14000533c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005343  jmp     short loc_14000534C
0x140005345  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000534c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005353  test    rax, rax
0x140005356  jz      short loc_140005363
0x140005358  mov     rdx, rbx
0x14000535b  mov     rcx, rsi
0x14000535e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005363  mov     rsi, [rsp+28h+arg_8]
0x140005368  mov     rax, rbx
0x14000536b  mov     rbx, [rsp+28h+arg_0]
0x140005370  add     rsp, 20h
0x140005374  pop     rdi
0x140005375  retn
```
