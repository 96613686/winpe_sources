# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000decc`
- end: `0x18000df6a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dba0`
- `0x18000e7a8`
- `0x18000e92c`
- `0x18001323c`
- `0x180014f00`

## callees

- `0x18000decc`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000df2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000df2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dee0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dee0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000def1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000def1`

## string_xrefs

- `0x18000df0e`: `ntdll.dll`

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
0x18000decc  mov     [rsp+arg_0], rbx
0x18000ded1  mov     [rsp+arg_8], rsi
0x18000ded6  push    rdi
0x18000ded7  sub     rsp, 20h
0x18000dedb  mov     rbx, rdx
0x18000dede  mov     edi, ecx
0x18000dee0  call    cs:__imp_GetProcessHeap
0x18000dee6  mov     rsi, rax
0x18000dee9  mov     r8, rbx; dwBytes
0x18000deec  mov     edx, edi; dwFlags
0x18000deee  mov     rcx, rax; hHeap
0x18000def1  call    cs:__imp_HeapAlloc
0x18000def7  mov     rbx, rax
0x18000defa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000df01  test    rax, rax
0x18000df04  jnz     short loc_18000DF4C
0x18000df06  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000df0c  jnz     short loc_18000DF57
0x18000df0e  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000df15  call    cs:__imp_GetModuleHandleW
0x18000df1b  test    rax, rax
0x18000df1e  jz      short loc_18000DF39
0x18000df20  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000df27  mov     rcx, rax; hModule
0x18000df2a  call    cs:__imp_GetProcAddress
0x18000df30  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000df37  jmp     short loc_18000DF40
0x18000df39  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000df40  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000df47  test    rax, rax
0x18000df4a  jz      short loc_18000DF57
0x18000df4c  mov     rdx, rbx
0x18000df4f  mov     rcx, rsi
0x18000df52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df57  mov     rax, rbx
0x18000df5a  mov     rbx, [rsp+28h+arg_0]
0x18000df5f  mov     rsi, [rsp+28h+arg_8]
0x18000df64  add     rsp, 20h
0x18000df68  pop     rdi
0x18000df69  retn
```
