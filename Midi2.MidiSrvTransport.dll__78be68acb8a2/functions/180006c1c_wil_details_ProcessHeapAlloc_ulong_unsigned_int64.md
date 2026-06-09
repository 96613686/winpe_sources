# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006c1c`
- end: `0x180006cba`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004038`
- `0x180005700`
- `0x180007eb0`
- `0x1800116f4`

## callees

- `0x180006c1c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006c41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006c41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c30`

## string_xrefs

- `0x180006c5e`: `ntdll.dll`

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
0x180006c1c  mov     [rsp+arg_0], rbx
0x180006c21  mov     [rsp+arg_8], rsi
0x180006c26  push    rdi
0x180006c27  sub     rsp, 20h
0x180006c2b  mov     rbx, rdx
0x180006c2e  mov     edi, ecx
0x180006c30  call    cs:__imp_GetProcessHeap
0x180006c36  mov     rsi, rax
0x180006c39  mov     r8, rbx; dwBytes
0x180006c3c  mov     edx, edi; dwFlags
0x180006c3e  mov     rcx, rax; hHeap
0x180006c41  call    cs:__imp_HeapAlloc
0x180006c47  mov     rbx, rax
0x180006c4a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006c51  test    rax, rax
0x180006c54  jnz     short loc_180006C9C
0x180006c56  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006c5c  jnz     short loc_180006CA7
0x180006c5e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180006c65  call    cs:__imp_GetModuleHandleW
0x180006c6b  test    rax, rax
0x180006c6e  jz      short loc_180006C89
0x180006c70  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006c77  mov     rcx, rax; hModule
0x180006c7a  call    cs:__imp_GetProcAddress
0x180006c80  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006c87  jmp     short loc_180006C90
0x180006c89  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006c90  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006c97  test    rax, rax
0x180006c9a  jz      short loc_180006CA7
0x180006c9c  mov     rdx, rbx
0x180006c9f  mov     rcx, rsi
0x180006ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ca7  mov     rax, rbx
0x180006caa  mov     rbx, [rsp+28h+arg_0]
0x180006caf  mov     rsi, [rsp+28h+arg_8]
0x180006cb4  add     rsp, 20h
0x180006cb8  pop     rdi
0x180006cb9  retn
```
