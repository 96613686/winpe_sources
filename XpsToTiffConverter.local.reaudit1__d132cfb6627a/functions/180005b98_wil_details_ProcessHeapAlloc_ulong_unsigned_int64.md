# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005b98`
- end: `0x180005c36`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003ab8`
- `0x180003e5c`
- `0x180004a30`
- `0x1800071b4`
- `0x18000885c`

## callees

- `0x180005b98`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005bf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005bf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005be1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005be1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bac`

## string_xrefs

- `0x180005bda`: `ntdll.dll`

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
0x180005b98  mov     [rsp+arg_0], rbx
0x180005b9d  mov     [rsp+arg_8], rsi
0x180005ba2  push    rdi
0x180005ba3  sub     rsp, 20h
0x180005ba7  mov     rbx, rdx
0x180005baa  mov     edi, ecx
0x180005bac  call    cs:__imp_GetProcessHeap
0x180005bb2  mov     rsi, rax
0x180005bb5  mov     r8, rbx; dwBytes
0x180005bb8  mov     edx, edi; dwFlags
0x180005bba  mov     rcx, rax; hHeap
0x180005bbd  call    cs:__imp_HeapAlloc
0x180005bc3  mov     rbx, rax
0x180005bc6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005bcd  test    rax, rax
0x180005bd0  jnz     short loc_180005C18
0x180005bd2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005bd8  jnz     short loc_180005C23
0x180005bda  lea     rcx, ModuleName; "ntdll.dll"
0x180005be1  call    cs:__imp_GetModuleHandleW
0x180005be7  test    rax, rax
0x180005bea  jz      short loc_180005C05
0x180005bec  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005bf3  mov     rcx, rax; hModule
0x180005bf6  call    cs:__imp_GetProcAddress
0x180005bfc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005c03  jmp     short loc_180005C0C
0x180005c05  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005c0c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005c13  test    rax, rax
0x180005c16  jz      short loc_180005C23
0x180005c18  mov     rdx, rbx
0x180005c1b  mov     rcx, rsi
0x180005c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c23  mov     rax, rbx
0x180005c26  mov     rbx, [rsp+28h+arg_0]
0x180005c2b  mov     rsi, [rsp+28h+arg_8]
0x180005c30  add     rsp, 20h
0x180005c34  pop     rdi
0x180005c35  retn
```
