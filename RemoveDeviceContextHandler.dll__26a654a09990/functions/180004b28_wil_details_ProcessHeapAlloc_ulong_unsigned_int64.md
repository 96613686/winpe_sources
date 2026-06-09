# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004b28`
- end: `0x180004bc6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003758`
- `0x1800042fc`
- `0x180004e50`

## callees

- `0x180004b28`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b86`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004b71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004b71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b4d`

## string_xrefs

- `0x180004b6a`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, LPVOID))ProcAddress)(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180004b28  mov     [rsp+arg_0], rbx
0x180004b2d  mov     [rsp+arg_8], rsi
0x180004b32  push    rdi
0x180004b33  sub     rsp, 20h
0x180004b37  mov     rbx, rdx
0x180004b3a  mov     edi, ecx
0x180004b3c  call    cs:__imp_GetProcessHeap
0x180004b42  mov     r8, rbx; dwBytes
0x180004b45  mov     edx, edi; dwFlags
0x180004b47  mov     rcx, rax; hHeap
0x180004b4a  mov     rsi, rax
0x180004b4d  call    cs:__imp_HeapAlloc
0x180004b53  mov     rbx, rax
0x180004b56  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004b5d  test    rax, rax
0x180004b60  jnz     short loc_180004BA8
0x180004b62  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004b68  jnz     short loc_180004BB3
0x180004b6a  lea     rcx, ModuleName; "ntdll.dll"
0x180004b71  call    cs:__imp_GetModuleHandleW
0x180004b77  test    rax, rax
0x180004b7a  jz      short loc_180004B95
0x180004b7c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004b83  mov     rcx, rax; hModule
0x180004b86  call    cs:__imp_GetProcAddress
0x180004b8c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004b93  jmp     short loc_180004B9C
0x180004b95  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004b9c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004ba3  test    rax, rax
0x180004ba6  jz      short loc_180004BB3
0x180004ba8  mov     rdx, rbx
0x180004bab  mov     rcx, rsi
0x180004bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb3  mov     rsi, [rsp+28h+arg_8]
0x180004bb8  mov     rax, rbx
0x180004bbb  mov     rbx, [rsp+28h+arg_0]
0x180004bc0  add     rsp, 20h
0x180004bc4  pop     rdi
0x180004bc5  retn
```
