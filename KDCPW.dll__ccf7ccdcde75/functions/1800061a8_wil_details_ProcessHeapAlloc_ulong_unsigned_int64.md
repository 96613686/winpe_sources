# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800061a8`
- end: `0x180006246`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800039e4`
- `0x180003d88`
- `0x180004ce0`
- `0x180007cc8`
- `0x180008f3c`

## callees

- `0x1800061a8`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006206`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006206`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800061cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800061cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061bc`

## string_xrefs

- `0x1800061ea`: `ntdll.dll`

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
0x1800061a8  mov     [rsp+arg_0], rbx
0x1800061ad  mov     [rsp+arg_8], rsi
0x1800061b2  push    rdi
0x1800061b3  sub     rsp, 20h
0x1800061b7  mov     rbx, rdx
0x1800061ba  mov     edi, ecx
0x1800061bc  call    cs:__imp_GetProcessHeap
0x1800061c2  mov     r8, rbx; dwBytes
0x1800061c5  mov     edx, edi; dwFlags
0x1800061c7  mov     rcx, rax; hHeap
0x1800061ca  mov     rsi, rax
0x1800061cd  call    cs:__imp_HeapAlloc
0x1800061d3  mov     rbx, rax
0x1800061d6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800061dd  test    rax, rax
0x1800061e0  jnz     short loc_180006228
0x1800061e2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800061e8  jnz     short loc_180006233
0x1800061ea  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800061f1  call    cs:__imp_GetModuleHandleW
0x1800061f7  test    rax, rax
0x1800061fa  jz      short loc_180006215
0x1800061fc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006203  mov     rcx, rax; hModule
0x180006206  call    cs:__imp_GetProcAddress
0x18000620c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006213  jmp     short loc_18000621C
0x180006215  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000621c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006223  test    rax, rax
0x180006226  jz      short loc_180006233
0x180006228  mov     rdx, rbx
0x18000622b  mov     rcx, rsi
0x18000622e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006233  mov     rsi, [rsp+28h+arg_8]
0x180006238  mov     rax, rbx
0x18000623b  mov     rbx, [rsp+28h+arg_0]
0x180006240  add     rsp, 20h
0x180006244  pop     rdi
0x180006245  retn
```
