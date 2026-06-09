# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800083fc`
- end: `0x18000849a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005828`
- `0x180006ef0`
- `0x180009810`
- `0x180011f8c`

## callees

- `0x1800083fc`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000845a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000845a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008445`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008445`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008421`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008421`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008410`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008410`

## string_xrefs

- `0x18000843e`: `ntdll.dll`

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
0x1800083fc  mov     [rsp+arg_0], rbx
0x180008401  mov     [rsp+arg_8], rsi
0x180008406  push    rdi
0x180008407  sub     rsp, 20h
0x18000840b  mov     rbx, rdx
0x18000840e  mov     edi, ecx
0x180008410  call    cs:__imp_GetProcessHeap
0x180008416  mov     rsi, rax
0x180008419  mov     r8, rbx; dwBytes
0x18000841c  mov     edx, edi; dwFlags
0x18000841e  mov     rcx, rax; hHeap
0x180008421  call    cs:__imp_HeapAlloc
0x180008427  mov     rbx, rax
0x18000842a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008431  test    rax, rax
0x180008434  jnz     short loc_18000847C
0x180008436  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000843c  jnz     short loc_180008487
0x18000843e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180008445  call    cs:__imp_GetModuleHandleW
0x18000844b  test    rax, rax
0x18000844e  jz      short loc_180008469
0x180008450  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008457  mov     rcx, rax; hModule
0x18000845a  call    cs:__imp_GetProcAddress
0x180008460  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008467  jmp     short loc_180008470
0x180008469  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008470  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008477  test    rax, rax
0x18000847a  jz      short loc_180008487
0x18000847c  mov     rdx, rbx
0x18000847f  mov     rcx, rsi
0x180008482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008487  mov     rax, rbx
0x18000848a  mov     rbx, [rsp+28h+arg_0]
0x18000848f  mov     rsi, [rsp+28h+arg_8]
0x180008494  add     rsp, 20h
0x180008498  pop     rdi
0x180008499  retn
```
