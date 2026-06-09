# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180055d40`
- end: `0x180055de9`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18005549c`
- `0x1800555c0`
- `0x180057068`
- `0x1800572dc`
- `0x1800581cc`

## callees

- `0x180051dfc`
- `0x180055d40`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180055d54`
- `KERNEL32!GetProcessHeap` at `0x180055d54`
- `KERNEL32!HeapAlloc` at `0x180055d6b`
- `KERNEL32!HeapAlloc` at `0x180055d6b`
- `KERNEL32!GetModuleHandleW` at `0x180055d95`
- `KERNEL32!GetModuleHandleW` at `0x180055d95`

## string_xrefs

- `0x180055d8e`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  FARPROC ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z; // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = ___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z) )
  {
    ((void (__fastcall *)(HANDLE, LPVOID))ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(
      ProcessHeap,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180055d40  mov     [rsp+arg_0], rbx
0x180055d45  mov     [rsp+arg_8], rsi
0x180055d4a  push    rdi
0x180055d4b  sub     rsp, 20h
0x180055d4f  mov     rbx, rdx
0x180055d52  mov     edi, ecx
0x180055d54  call    cs:__imp_GetProcessHeap
0x180055d5b  nop     dword ptr [rax+rax+00h]
0x180055d60  mov     r8, rbx; dwBytes
0x180055d63  mov     edx, edi; dwFlags
0x180055d65  mov     rcx, rax; hHeap
0x180055d68  mov     rsi, rax
0x180055d6b  call    cs:__imp_HeapAlloc
0x180055d72  nop     dword ptr [rax+rax+00h]
0x180055d77  mov     rbx, rax
0x180055d7a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180055d81  test    rax, rax
0x180055d84  jnz     short loc_180055DCA
0x180055d86  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180055d8c  jnz     short loc_180055DD5
0x180055d8e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180055d95  call    cs:__imp_GetModuleHandleW
0x180055d9c  nop     dword ptr [rax+rax+00h]
0x180055da1  test    rax, rax
0x180055da4  jz      short loc_180055DB7
0x180055da6  mov     rcx, rax
0x180055da9  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180055dae  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180055db5  jmp     short loc_180055DBE
0x180055db7  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180055dbe  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180055dc5  test    rax, rax
0x180055dc8  jz      short loc_180055DD5
0x180055dca  mov     rdx, rbx
0x180055dcd  mov     rcx, rsi
0x180055dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055dd5  mov     rsi, [rsp+28h+arg_8]
0x180055dda  mov     rax, rbx
0x180055ddd  mov     rbx, [rsp+28h+arg_0]
0x180055de2  add     rsp, 20h
0x180055de6  pop     rdi
0x180055de7  retn
```
