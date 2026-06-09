# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004bd14`
- end: `0x18004bdb2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004b914`
- `0x18004ba3c`
- `0x18004ce74`
- `0x18004d0a0`
- `0x18004eef4`

## callees

- `0x18004bd14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bd72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bd72`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004bd5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004bd5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bd28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bd28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004bd39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004bd39`

## string_xrefs

- `0x18004bd56`: `ntdll.dll`

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
0x18004bd14  mov     [rsp+arg_0], rbx
0x18004bd19  mov     [rsp+arg_8], rsi
0x18004bd1e  push    rdi
0x18004bd1f  sub     rsp, 20h
0x18004bd23  mov     rbx, rdx
0x18004bd26  mov     edi, ecx
0x18004bd28  call    cs:__imp_GetProcessHeap
0x18004bd2e  mov     rsi, rax
0x18004bd31  mov     r8, rbx; dwBytes
0x18004bd34  mov     edx, edi; dwFlags
0x18004bd36  mov     rcx, rax; hHeap
0x18004bd39  call    cs:__imp_HeapAlloc
0x18004bd3f  mov     rbx, rax
0x18004bd42  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004bd49  test    rax, rax
0x18004bd4c  jnz     short loc_18004BD94
0x18004bd4e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004bd54  jnz     short loc_18004BD9F
0x18004bd56  lea     rcx, ModuleName; "ntdll.dll"
0x18004bd5d  call    cs:__imp_GetModuleHandleW
0x18004bd63  test    rax, rax
0x18004bd66  jz      short loc_18004BD81
0x18004bd68  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18004bd6f  mov     rcx, rax; hModule
0x18004bd72  call    cs:__imp_GetProcAddress
0x18004bd78  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18004bd7f  jmp     short loc_18004BD88
0x18004bd81  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004bd88  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004bd8f  test    rax, rax
0x18004bd92  jz      short loc_18004BD9F
0x18004bd94  mov     rdx, rbx
0x18004bd97  mov     rcx, rsi
0x18004bd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd9f  mov     rax, rbx
0x18004bda2  mov     rbx, [rsp+28h+arg_0]
0x18004bda7  mov     rsi, [rsp+28h+arg_8]
0x18004bdac  add     rsp, 20h
0x18004bdb0  pop     rdi
0x18004bdb1  retn
```
