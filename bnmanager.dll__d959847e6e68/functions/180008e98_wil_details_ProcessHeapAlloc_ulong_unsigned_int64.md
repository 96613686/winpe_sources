# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008e98`
- end: `0x180008f36`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005ad8`
- `0x180005e7c`
- `0x180007c00`
- `0x18000a624`
- `0x18000bd0c`

## callees

- `0x180008e98`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008ebd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008ebd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008eac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008eac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ef6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ef6`

## string_xrefs

- `0x180008eda`: `ntdll.dll`

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
0x180008e98  mov     [rsp+arg_0], rbx
0x180008e9d  mov     [rsp+arg_8], rsi
0x180008ea2  push    rdi
0x180008ea3  sub     rsp, 20h
0x180008ea7  mov     rbx, rdx
0x180008eaa  mov     edi, ecx
0x180008eac  call    cs:__imp_GetProcessHeap
0x180008eb2  mov     rsi, rax
0x180008eb5  mov     r8, rbx; dwBytes
0x180008eb8  mov     edx, edi; dwFlags
0x180008eba  mov     rcx, rax; hHeap
0x180008ebd  call    cs:__imp_HeapAlloc
0x180008ec3  mov     rbx, rax
0x180008ec6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008ecd  test    rax, rax
0x180008ed0  jnz     short loc_180008F18
0x180008ed2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008ed8  jnz     short loc_180008F23
0x180008eda  lea     rcx, ModuleName; "ntdll.dll"
0x180008ee1  call    cs:__imp_GetModuleHandleW
0x180008ee7  test    rax, rax
0x180008eea  jz      short loc_180008F05
0x180008eec  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008ef3  mov     rcx, rax; hModule
0x180008ef6  call    cs:__imp_GetProcAddress
0x180008efc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008f03  jmp     short loc_180008F0C
0x180008f05  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008f0c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008f13  test    rax, rax
0x180008f16  jz      short loc_180008F23
0x180008f18  mov     rdx, rbx
0x180008f1b  mov     rcx, rsi
0x180008f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f23  mov     rax, rbx
0x180008f26  mov     rbx, [rsp+28h+arg_0]
0x180008f2b  mov     rsi, [rsp+28h+arg_8]
0x180008f30  add     rsp, 20h
0x180008f34  pop     rdi
0x180008f35  retn
```
