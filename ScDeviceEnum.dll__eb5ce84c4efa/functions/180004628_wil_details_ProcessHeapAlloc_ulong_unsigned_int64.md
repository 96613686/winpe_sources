# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004628`
- end: `0x1800046c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800043b4`
- `0x180004aac`
- `0x180004e44`

## callees

- `0x180004628`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004671`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004671`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004686`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000463c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000463c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000464d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000464d`

## string_xrefs

- `0x18000466a`: `ntdll.dll`

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
0x180004628  mov     [rsp+arg_0], rbx
0x18000462d  mov     [rsp+arg_8], rsi
0x180004632  push    rdi
0x180004633  sub     rsp, 20h
0x180004637  mov     rbx, rdx
0x18000463a  mov     edi, ecx
0x18000463c  call    cs:__imp_GetProcessHeap
0x180004642  mov     rsi, rax
0x180004645  mov     r8, rbx; dwBytes
0x180004648  mov     edx, edi; dwFlags
0x18000464a  mov     rcx, rax; hHeap
0x18000464d  call    cs:__imp_HeapAlloc
0x180004653  mov     rbx, rax
0x180004656  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000465d  test    rax, rax
0x180004660  jnz     short loc_1800046A8
0x180004662  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004668  jnz     short loc_1800046B3
0x18000466a  lea     rcx, ModuleName; "ntdll.dll"
0x180004671  call    cs:__imp_GetModuleHandleW
0x180004677  test    rax, rax
0x18000467a  jz      short loc_180004695
0x18000467c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180004683  mov     rcx, rax; hModule
0x180004686  call    cs:__imp_GetProcAddress
0x18000468c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004693  jmp     short loc_18000469C
0x180004695  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000469c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800046a3  test    rax, rax
0x1800046a6  jz      short loc_1800046B3
0x1800046a8  mov     rdx, rbx
0x1800046ab  mov     rcx, rsi
0x1800046ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b3  mov     rax, rbx
0x1800046b6  mov     rbx, [rsp+28h+arg_0]
0x1800046bb  mov     rsi, [rsp+28h+arg_8]
0x1800046c0  add     rsp, 20h
0x1800046c4  pop     rdi
0x1800046c5  retn
```
