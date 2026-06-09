# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800058f8`
- end: `0x180005996`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003818`
- `0x180003bbc`
- `0x180004790`
- `0x180006ea4`
- `0x18000854c`

## callees

- `0x1800058f8`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005956`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005956`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005941`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005941`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000591d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000591d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000590c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000590c`

## string_xrefs

- `0x18000593a`: `ntdll.dll`

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
0x1800058f8  mov     [rsp+arg_0], rbx
0x1800058fd  mov     [rsp+arg_8], rsi
0x180005902  push    rdi
0x180005903  sub     rsp, 20h
0x180005907  mov     rbx, rdx
0x18000590a  mov     edi, ecx
0x18000590c  call    cs:__imp_GetProcessHeap
0x180005912  mov     rsi, rax
0x180005915  mov     r8, rbx; dwBytes
0x180005918  mov     edx, edi; dwFlags
0x18000591a  mov     rcx, rax; hHeap
0x18000591d  call    cs:__imp_HeapAlloc
0x180005923  mov     rbx, rax
0x180005926  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000592d  test    rax, rax
0x180005930  jnz     short loc_180005978
0x180005932  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005938  jnz     short loc_180005983
0x18000593a  lea     rcx, ModuleName; "ntdll.dll"
0x180005941  call    cs:__imp_GetModuleHandleW
0x180005947  test    rax, rax
0x18000594a  jz      short loc_180005965
0x18000594c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005953  mov     rcx, rax; hModule
0x180005956  call    cs:__imp_GetProcAddress
0x18000595c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005963  jmp     short loc_18000596C
0x180005965  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000596c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005973  test    rax, rax
0x180005976  jz      short loc_180005983
0x180005978  mov     rdx, rbx
0x18000597b  mov     rcx, rsi
0x18000597e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005983  mov     rax, rbx
0x180005986  mov     rbx, [rsp+28h+arg_0]
0x18000598b  mov     rsi, [rsp+28h+arg_8]
0x180005990  add     rsp, 20h
0x180005994  pop     rdi
0x180005995  retn
```
