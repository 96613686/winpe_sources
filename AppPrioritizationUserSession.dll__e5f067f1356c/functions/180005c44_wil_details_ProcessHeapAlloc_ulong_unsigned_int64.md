# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005c44`
- end: `0x180005ce2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800042e8`
- `0x180004b30`
- `0x1800062b0`

## callees

- `0x180005c44`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ca2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ca2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c69`

## string_xrefs

- `0x180005c86`: `ntdll.dll`

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
0x180005c44  mov     [rsp+arg_0], rbx
0x180005c49  mov     [rsp+arg_8], rsi
0x180005c4e  push    rdi
0x180005c4f  sub     rsp, 20h
0x180005c53  mov     rbx, rdx
0x180005c56  mov     edi, ecx
0x180005c58  call    cs:__imp_GetProcessHeap
0x180005c5e  mov     rsi, rax
0x180005c61  mov     r8, rbx; dwBytes
0x180005c64  mov     edx, edi; dwFlags
0x180005c66  mov     rcx, rax; hHeap
0x180005c69  call    cs:__imp_HeapAlloc
0x180005c6f  mov     rbx, rax
0x180005c72  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005c79  test    rax, rax
0x180005c7c  jnz     short loc_180005CC4
0x180005c7e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005c84  jnz     short loc_180005CCF
0x180005c86  lea     rcx, ModuleName; "ntdll.dll"
0x180005c8d  call    cs:__imp_GetModuleHandleW
0x180005c93  test    rax, rax
0x180005c96  jz      short loc_180005CB1
0x180005c98  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005c9f  mov     rcx, rax; hModule
0x180005ca2  call    cs:__imp_GetProcAddress
0x180005ca8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005caf  jmp     short loc_180005CB8
0x180005cb1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005cb8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005cbf  test    rax, rax
0x180005cc2  jz      short loc_180005CCF
0x180005cc4  mov     rdx, rbx
0x180005cc7  mov     rcx, rsi
0x180005cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ccf  mov     rax, rbx
0x180005cd2  mov     rbx, [rsp+28h+arg_0]
0x180005cd7  mov     rsi, [rsp+28h+arg_8]
0x180005cdc  add     rsp, 20h
0x180005ce0  pop     rdi
0x180005ce1  retn
```
