# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000650c`
- end: `0x1800065aa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007f08`
- `0x180008370`
- `0x180008580`
- `0x1800091b8`
- `0x180009ee4`

## callees

- `0x18000650c`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006555`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006555`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000656a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000656a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006531`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006531`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006520`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006520`

## string_xrefs

- `0x18000654e`: `ntdll.dll`

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
0x18000650c  mov     [rsp+arg_0], rbx
0x180006511  mov     [rsp+arg_8], rsi
0x180006516  push    rdi
0x180006517  sub     rsp, 20h
0x18000651b  mov     rbx, rdx
0x18000651e  mov     edi, ecx
0x180006520  call    cs:__imp_GetProcessHeap
0x180006526  mov     rsi, rax
0x180006529  mov     r8, rbx; dwBytes
0x18000652c  mov     edx, edi; dwFlags
0x18000652e  mov     rcx, rax; hHeap
0x180006531  call    cs:__imp_HeapAlloc
0x180006537  mov     rbx, rax
0x18000653a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006541  test    rax, rax
0x180006544  jnz     short loc_18000658C
0x180006546  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000654c  jnz     short loc_180006597
0x18000654e  lea     rcx, ModuleName; "ntdll.dll"
0x180006555  call    cs:__imp_GetModuleHandleW
0x18000655b  test    rax, rax
0x18000655e  jz      short loc_180006579
0x180006560  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180006567  mov     rcx, rax; hModule
0x18000656a  call    cs:__imp_GetProcAddress
0x180006570  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006577  jmp     short loc_180006580
0x180006579  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006580  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006587  test    rax, rax
0x18000658a  jz      short loc_180006597
0x18000658c  mov     rdx, rbx
0x18000658f  mov     rcx, rsi
0x180006592  call    _guard_dispatch_icall
0x180006597  mov     rax, rbx
0x18000659a  mov     rbx, [rsp+28h+arg_0]
0x18000659f  mov     rsi, [rsp+28h+arg_8]
0x1800065a4  add     rsp, 20h
0x1800065a8  pop     rdi
0x1800065a9  retn
```
