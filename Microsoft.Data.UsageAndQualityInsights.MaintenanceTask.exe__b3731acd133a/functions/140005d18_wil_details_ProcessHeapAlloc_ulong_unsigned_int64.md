# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005d18`
- end: `0x140005db6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003a78`
- `0x140003e1c`
- `0x140004ac0`
- `0x1400073d4`
- `0x140008c3c`

## callees

- `0x140005d18`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005d61`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005d61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005d76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005d76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005d3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005d3d`

## string_xrefs

- `0x140005d5a`: `ntdll.dll`

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
0x140005d18  mov     [rsp+arg_0], rbx
0x140005d1d  mov     [rsp+arg_8], rsi
0x140005d22  push    rdi
0x140005d23  sub     rsp, 20h
0x140005d27  mov     rbx, rdx
0x140005d2a  mov     edi, ecx
0x140005d2c  call    cs:__imp_GetProcessHeap
0x140005d32  mov     rsi, rax
0x140005d35  mov     r8, rbx; dwBytes
0x140005d38  mov     edx, edi; dwFlags
0x140005d3a  mov     rcx, rax; hHeap
0x140005d3d  call    cs:__imp_HeapAlloc
0x140005d43  mov     rbx, rax
0x140005d46  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005d4d  test    rax, rax
0x140005d50  jnz     short loc_140005D98
0x140005d52  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005d58  jnz     short loc_140005DA3
0x140005d5a  lea     rcx, ModuleName; "ntdll.dll"
0x140005d61  call    cs:__imp_GetModuleHandleW
0x140005d67  test    rax, rax
0x140005d6a  jz      short loc_140005D85
0x140005d6c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140005d73  mov     rcx, rax; hModule
0x140005d76  call    cs:__imp_GetProcAddress
0x140005d7c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005d83  jmp     short loc_140005D8C
0x140005d85  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005d8c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005d93  test    rax, rax
0x140005d96  jz      short loc_140005DA3
0x140005d98  mov     rdx, rbx
0x140005d9b  mov     rcx, rsi
0x140005d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005da3  mov     rax, rbx
0x140005da6  mov     rbx, [rsp+28h+arg_0]
0x140005dab  mov     rsi, [rsp+28h+arg_8]
0x140005db0  add     rsp, 20h
0x140005db4  pop     rdi
0x140005db5  retn
```
