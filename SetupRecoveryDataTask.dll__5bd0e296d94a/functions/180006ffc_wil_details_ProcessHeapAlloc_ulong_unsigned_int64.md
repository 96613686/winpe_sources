# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006ffc`
- end: `0x18000709a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003940`
- `0x180003ce4`
- `0x18000902c`
- `0x18000af9c`

## callees

- `0x180006ffc`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000705a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000705a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007045`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007045`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007010`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007010`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007021`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007021`

## string_xrefs

- `0x18000703e`: `ntdll.dll`

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
0x180006ffc  mov     [rsp+arg_0], rbx
0x180007001  mov     [rsp+arg_8], rsi
0x180007006  push    rdi
0x180007007  sub     rsp, 20h
0x18000700b  mov     rbx, rdx
0x18000700e  mov     edi, ecx
0x180007010  call    cs:__imp_GetProcessHeap
0x180007016  mov     rsi, rax
0x180007019  mov     r8, rbx; dwBytes
0x18000701c  mov     edx, edi; dwFlags
0x18000701e  mov     rcx, rax; hHeap
0x180007021  call    cs:__imp_HeapAlloc
0x180007027  mov     rbx, rax
0x18000702a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007031  test    rax, rax
0x180007034  jnz     short loc_18000707C
0x180007036  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000703c  jnz     short loc_180007087
0x18000703e  lea     rcx, ModuleName; "ntdll.dll"
0x180007045  call    cs:__imp_GetModuleHandleW
0x18000704b  test    rax, rax
0x18000704e  jz      short loc_180007069
0x180007050  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007057  mov     rcx, rax; hModule
0x18000705a  call    cs:__imp_GetProcAddress
0x180007060  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007067  jmp     short loc_180007070
0x180007069  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007070  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007077  test    rax, rax
0x18000707a  jz      short loc_180007087
0x18000707c  mov     rdx, rbx
0x18000707f  mov     rcx, rsi
0x180007082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007087  mov     rax, rbx
0x18000708a  mov     rbx, [rsp+28h+arg_0]
0x18000708f  mov     rsi, [rsp+28h+arg_8]
0x180007094  add     rsp, 20h
0x180007098  pop     rdi
0x180007099  retn
```
