# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000577c`
- end: `0x18000581a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003ff8`
- `0x180004690`
- `0x180005e50`

## callees

- `0x18000577c`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800057a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800057a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005790`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005790`

## string_xrefs

- `0x1800057be`: `ntdll.dll`

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
0x18000577c  mov     [rsp+arg_0], rbx
0x180005781  mov     [rsp+arg_8], rsi
0x180005786  push    rdi
0x180005787  sub     rsp, 20h
0x18000578b  mov     rbx, rdx
0x18000578e  mov     edi, ecx
0x180005790  call    cs:__imp_GetProcessHeap
0x180005796  mov     rsi, rax
0x180005799  mov     r8, rbx; dwBytes
0x18000579c  mov     edx, edi; dwFlags
0x18000579e  mov     rcx, rax; hHeap
0x1800057a1  call    cs:__imp_HeapAlloc
0x1800057a7  mov     rbx, rax
0x1800057aa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800057b1  test    rax, rax
0x1800057b4  jnz     short loc_1800057FC
0x1800057b6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800057bc  jnz     short loc_180005807
0x1800057be  lea     rcx, ModuleName; "ntdll.dll"
0x1800057c5  call    cs:__imp_GetModuleHandleW
0x1800057cb  test    rax, rax
0x1800057ce  jz      short loc_1800057E9
0x1800057d0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800057d7  mov     rcx, rax; hModule
0x1800057da  call    cs:__imp_GetProcAddress
0x1800057e0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800057e7  jmp     short loc_1800057F0
0x1800057e9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800057f0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800057f7  test    rax, rax
0x1800057fa  jz      short loc_180005807
0x1800057fc  mov     rdx, rbx
0x1800057ff  mov     rcx, rsi
0x180005802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005807  mov     rax, rbx
0x18000580a  mov     rbx, [rsp+28h+arg_0]
0x18000580f  mov     rsi, [rsp+28h+arg_8]
0x180005814  add     rsp, 20h
0x180005818  pop     rdi
0x180005819  retn
```
