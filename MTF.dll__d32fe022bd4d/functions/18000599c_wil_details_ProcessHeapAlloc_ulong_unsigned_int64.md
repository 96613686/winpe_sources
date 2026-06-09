# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000599c`
- end: `0x180005a3a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004010`
- `0x180004d20`
- `0x180006568`
- `0x180009988`
- `0x18000d2e4`

## callees

- `0x18000599c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800059fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800059fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800059c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800059c1`

## string_xrefs

- `0x1800059de`: `ntdll.dll`

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
0x18000599c  mov     [rsp+arg_0], rbx
0x1800059a1  mov     [rsp+arg_8], rsi
0x1800059a6  push    rdi
0x1800059a7  sub     rsp, 20h
0x1800059ab  mov     rbx, rdx
0x1800059ae  mov     edi, ecx
0x1800059b0  call    cs:__imp_GetProcessHeap
0x1800059b6  mov     rsi, rax
0x1800059b9  mov     r8, rbx; dwBytes
0x1800059bc  mov     edx, edi; dwFlags
0x1800059be  mov     rcx, rax; hHeap
0x1800059c1  call    cs:__imp_HeapAlloc
0x1800059c7  mov     rbx, rax
0x1800059ca  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800059d1  test    rax, rax
0x1800059d4  jnz     short loc_180005A1C
0x1800059d6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800059dc  jnz     short loc_180005A27
0x1800059de  lea     rcx, ModuleName; "ntdll.dll"
0x1800059e5  call    cs:__imp_GetModuleHandleW
0x1800059eb  test    rax, rax
0x1800059ee  jz      short loc_180005A09
0x1800059f0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800059f7  mov     rcx, rax; hModule
0x1800059fa  call    cs:__imp_GetProcAddress
0x180005a00  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005a07  jmp     short loc_180005A10
0x180005a09  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005a10  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005a17  test    rax, rax
0x180005a1a  jz      short loc_180005A27
0x180005a1c  mov     rdx, rbx
0x180005a1f  mov     rcx, rsi
0x180005a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a27  mov     rax, rbx
0x180005a2a  mov     rbx, [rsp+28h+arg_0]
0x180005a2f  mov     rsi, [rsp+28h+arg_8]
0x180005a34  add     rsp, 20h
0x180005a38  pop     rdi
0x180005a39  retn
```
