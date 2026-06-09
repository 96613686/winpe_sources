# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b030`
- end: `0x18000b0ce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000966c`
- `0x18000a914`
- `0x18000aa78`
- `0x18000c698`
- `0x18000cb28`
- `0x18000e660`

## callees

- `0x18000b030`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b08e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b08e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b079`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b079`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b044`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b044`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b055`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b055`

## string_xrefs

- `0x18000b072`: `ntdll.dll`

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
0x18000b030  mov     [rsp+arg_0], rbx
0x18000b035  mov     [rsp+arg_8], rsi
0x18000b03a  push    rdi
0x18000b03b  sub     rsp, 20h
0x18000b03f  mov     rbx, rdx
0x18000b042  mov     edi, ecx
0x18000b044  call    cs:__imp_GetProcessHeap
0x18000b04a  mov     rsi, rax
0x18000b04d  mov     r8, rbx; dwBytes
0x18000b050  mov     edx, edi; dwFlags
0x18000b052  mov     rcx, rax; hHeap
0x18000b055  call    cs:__imp_HeapAlloc
0x18000b05b  mov     rbx, rax
0x18000b05e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b065  test    rax, rax
0x18000b068  jnz     short loc_18000B0B0
0x18000b06a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b070  jnz     short loc_18000B0BB
0x18000b072  lea     rcx, ModuleName; "ntdll.dll"
0x18000b079  call    cs:__imp_GetModuleHandleW
0x18000b07f  test    rax, rax
0x18000b082  jz      short loc_18000B09D
0x18000b084  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000b08b  mov     rcx, rax; hModule
0x18000b08e  call    cs:__imp_GetProcAddress
0x18000b094  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000b09b  jmp     short loc_18000B0A4
0x18000b09d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b0a4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b0ab  test    rax, rax
0x18000b0ae  jz      short loc_18000B0BB
0x18000b0b0  mov     rdx, rbx
0x18000b0b3  mov     rcx, rsi
0x18000b0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0bb  mov     rax, rbx
0x18000b0be  mov     rbx, [rsp+28h+arg_0]
0x18000b0c3  mov     rsi, [rsp+28h+arg_8]
0x18000b0c8  add     rsp, 20h
0x18000b0cc  pop     rdi
0x18000b0cd  retn
```
