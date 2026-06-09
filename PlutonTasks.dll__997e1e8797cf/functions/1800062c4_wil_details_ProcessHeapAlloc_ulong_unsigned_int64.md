# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800062c4`
- end: `0x180006362`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800050cc`
- `0x180005d50`
- `0x180005e74`
- `0x180007570`
- `0x1800079f4`
- `0x180008cec`

## callees

- `0x1800062c4`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000630d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000630d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006322`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006322`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062d8`

## string_xrefs

- `0x180006306`: `ntdll.dll`

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
0x1800062c4  mov     [rsp+arg_0], rbx
0x1800062c9  mov     [rsp+arg_8], rsi
0x1800062ce  push    rdi
0x1800062cf  sub     rsp, 20h
0x1800062d3  mov     rbx, rdx
0x1800062d6  mov     edi, ecx
0x1800062d8  call    cs:__imp_GetProcessHeap
0x1800062de  mov     rsi, rax
0x1800062e1  mov     r8, rbx; dwBytes
0x1800062e4  mov     edx, edi; dwFlags
0x1800062e6  mov     rcx, rax; hHeap
0x1800062e9  call    cs:__imp_HeapAlloc
0x1800062ef  mov     rbx, rax
0x1800062f2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800062f9  test    rax, rax
0x1800062fc  jnz     short loc_180006344
0x1800062fe  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006304  jnz     short loc_18000634F
0x180006306  lea     rcx, ModuleName; "ntdll.dll"
0x18000630d  call    cs:__imp_GetModuleHandleW
0x180006313  test    rax, rax
0x180006316  jz      short loc_180006331
0x180006318  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000631f  mov     rcx, rax; hModule
0x180006322  call    cs:__imp_GetProcAddress
0x180006328  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000632f  jmp     short loc_180006338
0x180006331  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006338  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000633f  test    rax, rax
0x180006342  jz      short loc_18000634F
0x180006344  mov     rdx, rbx
0x180006347  mov     rcx, rsi
0x18000634a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634f  mov     rax, rbx
0x180006352  mov     rbx, [rsp+28h+arg_0]
0x180006357  mov     rsi, [rsp+28h+arg_8]
0x18000635c  add     rsp, 20h
0x180006360  pop     rdi
0x180006361  retn
```
