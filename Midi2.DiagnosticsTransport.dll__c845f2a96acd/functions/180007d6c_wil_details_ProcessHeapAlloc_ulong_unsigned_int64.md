# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007d6c`
- end: `0x180007e0a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005198`
- `0x180006860`
- `0x180008ff0`
- `0x180010588`

## callees

- `0x180007d6c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007db5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007db5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d80`

## string_xrefs

- `0x180007dae`: `ntdll.dll`

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
0x180007d6c  mov     [rsp+arg_0], rbx
0x180007d71  mov     [rsp+arg_8], rsi
0x180007d76  push    rdi
0x180007d77  sub     rsp, 20h
0x180007d7b  mov     rbx, rdx
0x180007d7e  mov     edi, ecx
0x180007d80  call    cs:__imp_GetProcessHeap
0x180007d86  mov     rsi, rax
0x180007d89  mov     r8, rbx; dwBytes
0x180007d8c  mov     edx, edi; dwFlags
0x180007d8e  mov     rcx, rax; hHeap
0x180007d91  call    cs:__imp_HeapAlloc
0x180007d97  mov     rbx, rax
0x180007d9a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007da1  test    rax, rax
0x180007da4  jnz     short loc_180007DEC
0x180007da6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007dac  jnz     short loc_180007DF7
0x180007dae  lea     rcx, aNtdllDll; "ntdll.dll"
0x180007db5  call    cs:__imp_GetModuleHandleW
0x180007dbb  test    rax, rax
0x180007dbe  jz      short loc_180007DD9
0x180007dc0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007dc7  mov     rcx, rax; hModule
0x180007dca  call    cs:__imp_GetProcAddress
0x180007dd0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007dd7  jmp     short loc_180007DE0
0x180007dd9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007de0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007de7  test    rax, rax
0x180007dea  jz      short loc_180007DF7
0x180007dec  mov     rdx, rbx
0x180007def  mov     rcx, rsi
0x180007df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007df7  mov     rax, rbx
0x180007dfa  mov     rbx, [rsp+28h+arg_0]
0x180007dff  mov     rsi, [rsp+28h+arg_8]
0x180007e04  add     rsp, 20h
0x180007e08  pop     rdi
0x180007e09  retn
```
