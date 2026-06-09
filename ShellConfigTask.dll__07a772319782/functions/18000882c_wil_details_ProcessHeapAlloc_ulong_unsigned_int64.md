# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000882c`
- end: `0x1800088ca`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005a58`
- `0x180005e38`
- `0x1800076c0`
- `0x18000ac04`
- `0x18000c6e0`

## callees

- `0x18000882c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008851`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008851`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008840`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008840`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008875`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008875`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000888a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000888a`

## string_xrefs

- `0x18000886e`: `ntdll.dll`

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
0x18000882c  mov     [rsp+arg_0], rbx
0x180008831  mov     [rsp+arg_8], rsi
0x180008836  push    rdi
0x180008837  sub     rsp, 20h
0x18000883b  mov     rbx, rdx
0x18000883e  mov     edi, ecx
0x180008840  call    cs:__imp_GetProcessHeap
0x180008846  mov     rsi, rax
0x180008849  mov     r8, rbx; dwBytes
0x18000884c  mov     edx, edi; dwFlags
0x18000884e  mov     rcx, rax; hHeap
0x180008851  call    cs:__imp_HeapAlloc
0x180008857  mov     rbx, rax
0x18000885a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008861  test    rax, rax
0x180008864  jnz     short loc_1800088AC
0x180008866  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000886c  jnz     short loc_1800088B7
0x18000886e  lea     rcx, ModuleName; "ntdll.dll"
0x180008875  call    cs:__imp_GetModuleHandleW
0x18000887b  test    rax, rax
0x18000887e  jz      short loc_180008899
0x180008880  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008887  mov     rcx, rax; hModule
0x18000888a  call    cs:__imp_GetProcAddress
0x180008890  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008897  jmp     short loc_1800088A0
0x180008899  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800088a0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800088a7  test    rax, rax
0x1800088aa  jz      short loc_1800088B7
0x1800088ac  mov     rdx, rbx
0x1800088af  mov     rcx, rsi
0x1800088b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088b7  mov     rax, rbx
0x1800088ba  mov     rbx, [rsp+28h+arg_0]
0x1800088bf  mov     rsi, [rsp+28h+arg_8]
0x1800088c4  add     rsp, 20h
0x1800088c8  pop     rdi
0x1800088c9  retn
```
