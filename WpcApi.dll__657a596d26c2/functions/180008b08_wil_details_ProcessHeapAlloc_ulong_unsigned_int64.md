# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008b08`
- end: `0x180008ba6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800064a8`
- `0x180007490`
- `0x180007af0`
- `0x180009524`
- `0x18000fa9c`
- `0x180014824`

## callees

- `0x180008b08`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b2d`

## string_xrefs

- `0x180008b4a`: `ntdll.dll`

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
0x180008b08  mov     [rsp+arg_0], rbx
0x180008b0d  mov     [rsp+arg_8], rsi
0x180008b12  push    rdi
0x180008b13  sub     rsp, 20h
0x180008b17  mov     rbx, rdx
0x180008b1a  mov     edi, ecx
0x180008b1c  call    cs:__imp_GetProcessHeap
0x180008b22  mov     rsi, rax
0x180008b25  mov     r8, rbx; dwBytes
0x180008b28  mov     edx, edi; dwFlags
0x180008b2a  mov     rcx, rax; hHeap
0x180008b2d  call    cs:__imp_HeapAlloc
0x180008b33  mov     rbx, rax
0x180008b36  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008b3d  test    rax, rax
0x180008b40  jnz     short loc_180008B88
0x180008b42  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008b48  jnz     short loc_180008B93
0x180008b4a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008b51  call    cs:__imp_GetModuleHandleW
0x180008b57  test    rax, rax
0x180008b5a  jz      short loc_180008B75
0x180008b5c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008b63  mov     rcx, rax; hModule
0x180008b66  call    cs:__imp_GetProcAddress
0x180008b6c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008b73  jmp     short loc_180008B7C
0x180008b75  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008b7c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008b83  test    rax, rax
0x180008b86  jz      short loc_180008B93
0x180008b88  mov     rdx, rbx
0x180008b8b  mov     rcx, rsi
0x180008b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b93  mov     rax, rbx
0x180008b96  mov     rbx, [rsp+28h+arg_0]
0x180008b9b  mov     rsi, [rsp+28h+arg_8]
0x180008ba0  add     rsp, 20h
0x180008ba4  pop     rdi
0x180008ba5  retn
```
