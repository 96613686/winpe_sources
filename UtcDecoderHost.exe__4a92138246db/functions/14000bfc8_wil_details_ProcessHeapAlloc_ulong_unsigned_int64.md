# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000bfc8`
- end: `0x14000c066`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000aac8`
- `0x14000b270`
- `0x14000c524`
- `0x14001373c`
- `0x1400162b4`

## callees

- `0x14000bfc8`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c011`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c011`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c026`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c026`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bfed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bfed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bfdc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bfdc`

## string_xrefs

- `0x14000c00a`: `ntdll.dll`

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
0x14000bfc8  mov     [rsp+arg_0], rbx
0x14000bfcd  mov     [rsp+arg_8], rsi
0x14000bfd2  push    rdi
0x14000bfd3  sub     rsp, 20h
0x14000bfd7  mov     rbx, rdx
0x14000bfda  mov     edi, ecx
0x14000bfdc  call    cs:__imp_GetProcessHeap
0x14000bfe2  mov     rsi, rax
0x14000bfe5  mov     r8, rbx; dwBytes
0x14000bfe8  mov     edx, edi; dwFlags
0x14000bfea  mov     rcx, rax; hHeap
0x14000bfed  call    cs:__imp_HeapAlloc
0x14000bff3  mov     rbx, rax
0x14000bff6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000bffd  test    rax, rax
0x14000c000  jnz     short loc_14000C048
0x14000c002  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000c008  jnz     short loc_14000C053
0x14000c00a  lea     rcx, ModuleName; "ntdll.dll"
0x14000c011  call    cs:__imp_GetModuleHandleW
0x14000c017  test    rax, rax
0x14000c01a  jz      short loc_14000C035
0x14000c01c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000c023  mov     rcx, rax; hModule
0x14000c026  call    cs:__imp_GetProcAddress
0x14000c02c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000c033  jmp     short loc_14000C03C
0x14000c035  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000c03c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000c043  test    rax, rax
0x14000c046  jz      short loc_14000C053
0x14000c048  mov     rdx, rbx
0x14000c04b  mov     rcx, rsi
0x14000c04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c053  mov     rax, rbx
0x14000c056  mov     rbx, [rsp+28h+arg_0]
0x14000c05b  mov     rsi, [rsp+28h+arg_8]
0x14000c060  add     rsp, 20h
0x14000c064  pop     rdi
0x14000c065  retn
```
