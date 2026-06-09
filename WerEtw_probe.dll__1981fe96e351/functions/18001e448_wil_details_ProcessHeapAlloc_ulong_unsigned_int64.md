# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001e448`
- end: `0x18001e4e6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001be2c`
- `0x18001ca30`
- `0x18001e7d0`

## callees

- `0x18001e448`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e491`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e491`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e4a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e4a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e46d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e46d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e45c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e45c`

## string_xrefs

- `0x18001e48a`: `ntdll.dll`

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
0x18001e448  mov     [rsp+arg_0], rbx
0x18001e44d  mov     [rsp+arg_8], rsi
0x18001e452  push    rdi
0x18001e453  sub     rsp, 20h
0x18001e457  mov     rbx, rdx
0x18001e45a  mov     edi, ecx
0x18001e45c  call    cs:__imp_GetProcessHeap
0x18001e462  mov     rsi, rax
0x18001e465  mov     r8, rbx; dwBytes
0x18001e468  mov     edx, edi; dwFlags
0x18001e46a  mov     rcx, rax; hHeap
0x18001e46d  call    cs:__imp_HeapAlloc
0x18001e473  mov     rbx, rax
0x18001e476  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001e47d  test    rax, rax
0x18001e480  jnz     short loc_18001E4C8
0x18001e482  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001e488  jnz     short loc_18001E4D3
0x18001e48a  lea     rcx, LibFileName; "ntdll.dll"
0x18001e491  call    cs:__imp_GetModuleHandleW
0x18001e497  test    rax, rax
0x18001e49a  jz      short loc_18001E4B5
0x18001e49c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001e4a3  mov     rcx, rax; hModule
0x18001e4a6  call    cs:__imp_GetProcAddress
0x18001e4ac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001e4b3  jmp     short loc_18001E4BC
0x18001e4b5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001e4bc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001e4c3  test    rax, rax
0x18001e4c6  jz      short loc_18001E4D3
0x18001e4c8  mov     rdx, rbx
0x18001e4cb  mov     rcx, rsi
0x18001e4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4d3  mov     rax, rbx
0x18001e4d6  mov     rbx, [rsp+28h+arg_0]
0x18001e4db  mov     rsi, [rsp+28h+arg_8]
0x18001e4e0  add     rsp, 20h
0x18001e4e4  pop     rdi
0x18001e4e5  retn
```
