# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800189d8`
- end: `0x180018a76`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017b0c`
- `0x180018180`
- `0x180018e60`

## callees

- `0x1800189d8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018a36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018a36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018a21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018a21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800189fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800189fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800189ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800189ec`

## string_xrefs

- `0x180018a1a`: `ntdll.dll`

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
0x1800189d8  mov     [rsp+arg_0], rbx
0x1800189dd  mov     [rsp+arg_8], rsi
0x1800189e2  push    rdi
0x1800189e3  sub     rsp, 20h
0x1800189e7  mov     rbx, rdx
0x1800189ea  mov     edi, ecx
0x1800189ec  call    cs:__imp_GetProcessHeap
0x1800189f2  mov     rsi, rax
0x1800189f5  mov     r8, rbx; dwBytes
0x1800189f8  mov     edx, edi; dwFlags
0x1800189fa  mov     rcx, rax; hHeap
0x1800189fd  call    cs:__imp_HeapAlloc
0x180018a03  mov     rbx, rax
0x180018a06  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180018a0d  test    rax, rax
0x180018a10  jnz     short loc_180018A58
0x180018a12  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180018a18  jnz     short loc_180018A63
0x180018a1a  lea     rcx, ModuleName; "ntdll.dll"
0x180018a21  call    cs:__imp_GetModuleHandleW
0x180018a27  test    rax, rax
0x180018a2a  jz      short loc_180018A45
0x180018a2c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180018a33  mov     rcx, rax; hModule
0x180018a36  call    cs:__imp_GetProcAddress
0x180018a3c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180018a43  jmp     short loc_180018A4C
0x180018a45  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180018a4c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180018a53  test    rax, rax
0x180018a56  jz      short loc_180018A63
0x180018a58  mov     rdx, rbx
0x180018a5b  mov     rcx, rsi
0x180018a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a63  mov     rax, rbx
0x180018a66  mov     rbx, [rsp+28h+arg_0]
0x180018a6b  mov     rsi, [rsp+28h+arg_8]
0x180018a70  add     rsp, 20h
0x180018a74  pop     rdi
0x180018a75  retn
```
