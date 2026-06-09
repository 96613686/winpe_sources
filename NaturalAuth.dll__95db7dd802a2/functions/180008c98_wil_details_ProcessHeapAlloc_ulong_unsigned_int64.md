# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008c98`
- end: `0x180008d36`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800087bc`
- `0x180009588`
- `0x180009920`
- `0x18002ff64`
- `0x180031740`

## callees

- `0x180008c98`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008cf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008cf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ce1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ce1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008cbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008cbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008cac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008cac`

## string_xrefs

- `0x180008cda`: `ntdll.dll`

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
0x180008c98  mov     [rsp+arg_0], rbx
0x180008c9d  mov     [rsp+arg_8], rsi
0x180008ca2  push    rdi
0x180008ca3  sub     rsp, 20h
0x180008ca7  mov     rbx, rdx
0x180008caa  mov     edi, ecx
0x180008cac  call    cs:__imp_GetProcessHeap
0x180008cb2  mov     rsi, rax
0x180008cb5  mov     r8, rbx; dwBytes
0x180008cb8  mov     edx, edi; dwFlags
0x180008cba  mov     rcx, rax; hHeap
0x180008cbd  call    cs:__imp_HeapAlloc
0x180008cc3  mov     rbx, rax
0x180008cc6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008ccd  test    rax, rax
0x180008cd0  jnz     short loc_180008D18
0x180008cd2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008cd8  jnz     short loc_180008D23
0x180008cda  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008ce1  call    cs:__imp_GetModuleHandleW
0x180008ce7  test    rax, rax
0x180008cea  jz      short loc_180008D05
0x180008cec  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008cf3  mov     rcx, rax; hModule
0x180008cf6  call    cs:__imp_GetProcAddress
0x180008cfc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008d03  jmp     short loc_180008D0C
0x180008d05  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008d0c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008d13  test    rax, rax
0x180008d16  jz      short loc_180008D23
0x180008d18  mov     rdx, rbx
0x180008d1b  mov     rcx, rsi
0x180008d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d23  mov     rax, rbx
0x180008d26  mov     rbx, [rsp+28h+arg_0]
0x180008d2b  mov     rsi, [rsp+28h+arg_8]
0x180008d30  add     rsp, 20h
0x180008d34  pop     rdi
0x180008d35  retn
```
