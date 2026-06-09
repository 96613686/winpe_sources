# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b32c`
- end: `0x18000b3ca`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ae10`
- `0x18000af70`
- `0x18000d130`
- `0x18000d5b8`
- `0x18000e760`

## callees

- `0x18000b32c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b38a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b38a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b375`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b375`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b351`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b351`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b340`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b340`

## string_xrefs

- `0x18000b36e`: `ntdll.dll`

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
0x18000b32c  mov     [rsp+arg_0], rbx
0x18000b331  mov     [rsp+arg_8], rsi
0x18000b336  push    rdi
0x18000b337  sub     rsp, 20h
0x18000b33b  mov     rbx, rdx
0x18000b33e  mov     edi, ecx
0x18000b340  call    cs:__imp_GetProcessHeap
0x18000b346  mov     rsi, rax
0x18000b349  mov     r8, rbx; dwBytes
0x18000b34c  mov     edx, edi; dwFlags
0x18000b34e  mov     rcx, rax; hHeap
0x18000b351  call    cs:__imp_HeapAlloc
0x18000b357  mov     rbx, rax
0x18000b35a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b361  test    rax, rax
0x18000b364  jnz     short loc_18000B3AC
0x18000b366  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b36c  jnz     short loc_18000B3B7
0x18000b36e  lea     rcx, ModuleName; "ntdll.dll"
0x18000b375  call    cs:__imp_GetModuleHandleW
0x18000b37b  test    rax, rax
0x18000b37e  jz      short loc_18000B399
0x18000b380  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000b387  mov     rcx, rax; hModule
0x18000b38a  call    cs:__imp_GetProcAddress
0x18000b390  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000b397  jmp     short loc_18000B3A0
0x18000b399  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b3a0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b3a7  test    rax, rax
0x18000b3aa  jz      short loc_18000B3B7
0x18000b3ac  mov     rdx, rbx
0x18000b3af  mov     rcx, rsi
0x18000b3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3b7  mov     rax, rbx
0x18000b3ba  mov     rbx, [rsp+28h+arg_0]
0x18000b3bf  mov     rsi, [rsp+28h+arg_8]
0x18000b3c4  add     rsp, 20h
0x18000b3c8  pop     rdi
0x18000b3c9  retn
```
