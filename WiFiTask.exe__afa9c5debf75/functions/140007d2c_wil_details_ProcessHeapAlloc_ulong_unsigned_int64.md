# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140007d2c`
- end: `0x140007dca`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003e78`
- `0x14000421c`
- `0x140005980`
- `0x140009b4c`
- `0x14000b92c`

## callees

- `0x140007d2c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007d75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007d75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007d8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007d8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007d40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007d40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007d51`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007d51`

## string_xrefs

- `0x140007d6e`: `ntdll.dll`

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
0x140007d2c  mov     [rsp+arg_0], rbx
0x140007d31  mov     [rsp+arg_8], rsi
0x140007d36  push    rdi
0x140007d37  sub     rsp, 20h
0x140007d3b  mov     rbx, rdx
0x140007d3e  mov     edi, ecx
0x140007d40  call    cs:__imp_GetProcessHeap
0x140007d46  mov     rsi, rax
0x140007d49  mov     r8, rbx; dwBytes
0x140007d4c  mov     edx, edi; dwFlags
0x140007d4e  mov     rcx, rax; hHeap
0x140007d51  call    cs:__imp_HeapAlloc
0x140007d57  mov     rbx, rax
0x140007d5a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140007d61  test    rax, rax
0x140007d64  jnz     short loc_140007DAC
0x140007d66  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140007d6c  jnz     short loc_140007DB7
0x140007d6e  lea     rcx, ModuleName; "ntdll.dll"
0x140007d75  call    cs:__imp_GetModuleHandleW
0x140007d7b  test    rax, rax
0x140007d7e  jz      short loc_140007D99
0x140007d80  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140007d87  mov     rcx, rax; hModule
0x140007d8a  call    cs:__imp_GetProcAddress
0x140007d90  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140007d97  jmp     short loc_140007DA0
0x140007d99  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140007da0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140007da7  test    rax, rax
0x140007daa  jz      short loc_140007DB7
0x140007dac  mov     rdx, rbx
0x140007daf  mov     rcx, rsi
0x140007db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007db7  mov     rax, rbx
0x140007dba  mov     rbx, [rsp+28h+arg_0]
0x140007dbf  mov     rsi, [rsp+28h+arg_8]
0x140007dc4  add     rsp, 20h
0x140007dc8  pop     rdi
0x140007dc9  retn
```
