# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140003e78`
- end: `0x140003f16`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003c80`
- `0x1400042b8`
- `0x140004430`

## callees

- `0x140003e78`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003e9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003e9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003e8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003ed6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003ed6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003ec1`

## string_xrefs

- `0x140003eba`: `ntdll.dll`

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
0x140003e78  mov     [rsp+arg_0], rbx
0x140003e7d  mov     [rsp+arg_8], rsi
0x140003e82  push    rdi
0x140003e83  sub     rsp, 20h
0x140003e87  mov     rbx, rdx
0x140003e8a  mov     edi, ecx
0x140003e8c  call    cs:__imp_GetProcessHeap
0x140003e92  mov     r8, rbx; dwBytes
0x140003e95  mov     edx, edi; dwFlags
0x140003e97  mov     rcx, rax; hHeap
0x140003e9a  mov     rsi, rax
0x140003e9d  call    cs:__imp_HeapAlloc
0x140003ea3  mov     rbx, rax
0x140003ea6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140003ead  test    rax, rax
0x140003eb0  jnz     short loc_140003EF8
0x140003eb2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140003eb8  jnz     short loc_140003F03
0x140003eba  lea     rcx, ModuleName; "ntdll.dll"
0x140003ec1  call    cs:__imp_GetModuleHandleW
0x140003ec7  test    rax, rax
0x140003eca  jz      short loc_140003EE5
0x140003ecc  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140003ed3  mov     rcx, rax; hModule
0x140003ed6  call    cs:__imp_GetProcAddress
0x140003edc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140003ee3  jmp     short loc_140003EEC
0x140003ee5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140003eec  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140003ef3  test    rax, rax
0x140003ef6  jz      short loc_140003F03
0x140003ef8  mov     rdx, rbx
0x140003efb  mov     rcx, rsi
0x140003efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f03  mov     rsi, [rsp+28h+arg_8]
0x140003f08  mov     rax, rbx
0x140003f0b  mov     rbx, [rsp+28h+arg_0]
0x140003f10  add     rsp, 20h
0x140003f14  pop     rdi
0x140003f15  retn
```
