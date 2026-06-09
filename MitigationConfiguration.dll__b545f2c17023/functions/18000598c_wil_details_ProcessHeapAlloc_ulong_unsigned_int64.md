# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000598c`
- end: `0x180005a2a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800038c8`
- `0x180004900`
- `0x180005e40`

## callees

- `0x18000598c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800059ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800059ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800059b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800059b1`

## string_xrefs

- `0x1800059ce`: `ntdll.dll`

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
0x18000598c  mov     [rsp+arg_0], rbx
0x180005991  mov     [rsp+arg_8], rsi
0x180005996  push    rdi
0x180005997  sub     rsp, 20h
0x18000599b  mov     rbx, rdx
0x18000599e  mov     edi, ecx
0x1800059a0  call    cs:__imp_GetProcessHeap
0x1800059a6  mov     rsi, rax
0x1800059a9  mov     r8, rbx; dwBytes
0x1800059ac  mov     edx, edi; dwFlags
0x1800059ae  mov     rcx, rax; hHeap
0x1800059b1  call    cs:__imp_HeapAlloc
0x1800059b7  mov     rbx, rax
0x1800059ba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800059c1  test    rax, rax
0x1800059c4  jnz     short loc_180005A0C
0x1800059c6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800059cc  jnz     short loc_180005A17
0x1800059ce  lea     rcx, ModuleName; "ntdll.dll"
0x1800059d5  call    cs:__imp_GetModuleHandleW
0x1800059db  test    rax, rax
0x1800059de  jz      short loc_1800059F9
0x1800059e0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800059e7  mov     rcx, rax; hModule
0x1800059ea  call    cs:__imp_GetProcAddress
0x1800059f0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800059f7  jmp     short loc_180005A00
0x1800059f9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005a00  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005a07  test    rax, rax
0x180005a0a  jz      short loc_180005A17
0x180005a0c  mov     rdx, rbx
0x180005a0f  mov     rcx, rsi
0x180005a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a17  mov     rax, rbx
0x180005a1a  mov     rbx, [rsp+28h+arg_0]
0x180005a1f  mov     rsi, [rsp+28h+arg_8]
0x180005a24  add     rsp, 20h
0x180005a28  pop     rdi
0x180005a29  retn
```
