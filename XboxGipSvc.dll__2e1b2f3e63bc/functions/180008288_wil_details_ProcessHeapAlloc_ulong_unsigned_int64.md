# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008288`
- end: `0x180008326`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800073b8`
- `0x180007a90`
- `0x180008560`

## callees

- `0x180008288`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800082ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800082ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000829c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000829c`

## string_xrefs

- `0x1800082ca`: `ntdll.dll`

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
0x180008288  mov     [rsp+arg_0], rbx
0x18000828d  mov     [rsp+arg_8], rsi
0x180008292  push    rdi
0x180008293  sub     rsp, 20h
0x180008297  mov     rbx, rdx
0x18000829a  mov     edi, ecx
0x18000829c  call    cs:__imp_GetProcessHeap
0x1800082a2  mov     rsi, rax
0x1800082a5  mov     r8, rbx; dwBytes
0x1800082a8  mov     edx, edi; dwFlags
0x1800082aa  mov     rcx, rax; hHeap
0x1800082ad  call    cs:__imp_HeapAlloc
0x1800082b3  mov     rbx, rax
0x1800082b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800082bd  test    rax, rax
0x1800082c0  jnz     short loc_180008308
0x1800082c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800082c8  jnz     short loc_180008313
0x1800082ca  lea     rcx, ModuleName; "ntdll.dll"
0x1800082d1  call    cs:__imp_GetModuleHandleW
0x1800082d7  test    rax, rax
0x1800082da  jz      short loc_1800082F5
0x1800082dc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800082e3  mov     rcx, rax; hModule
0x1800082e6  call    cs:__imp_GetProcAddress
0x1800082ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800082f3  jmp     short loc_1800082FC
0x1800082f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800082fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008303  test    rax, rax
0x180008306  jz      short loc_180008313
0x180008308  mov     rdx, rbx
0x18000830b  mov     rcx, rsi
0x18000830e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008313  mov     rax, rbx
0x180008316  mov     rbx, [rsp+28h+arg_0]
0x18000831b  mov     rsi, [rsp+28h+arg_8]
0x180008320  add     rsp, 20h
0x180008324  pop     rdi
0x180008325  retn
```
