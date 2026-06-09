# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004a94`
- end: `0x140004b32`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400030b0`
- `0x1400038d0`
- `0x140004dd8`
- `0x1400063bc`
- `0x140011fcc`

## callees

- `0x140004a94`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004af2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004af2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004add`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004add`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004aa8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004aa8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004ab9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004ab9`

## string_xrefs

- `0x140004ad6`: `ntdll.dll`

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
0x140004a94  mov     [rsp+arg_0], rbx
0x140004a99  mov     [rsp+arg_8], rsi
0x140004a9e  push    rdi
0x140004a9f  sub     rsp, 20h
0x140004aa3  mov     rbx, rdx
0x140004aa6  mov     edi, ecx
0x140004aa8  call    cs:__imp_GetProcessHeap
0x140004aae  mov     r8, rbx; dwBytes
0x140004ab1  mov     edx, edi; dwFlags
0x140004ab3  mov     rcx, rax; hHeap
0x140004ab6  mov     rsi, rax
0x140004ab9  call    cs:__imp_HeapAlloc
0x140004abf  mov     rbx, rax
0x140004ac2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140004ac9  test    rax, rax
0x140004acc  jnz     short loc_140004B14
0x140004ace  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004ad4  jnz     short loc_140004B1F
0x140004ad6  lea     rcx, ModuleName; "ntdll.dll"
0x140004add  call    cs:__imp_GetModuleHandleW
0x140004ae3  test    rax, rax
0x140004ae6  jz      short loc_140004B01
0x140004ae8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140004aef  mov     rcx, rax; hModule
0x140004af2  call    cs:__imp_GetProcAddress
0x140004af8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140004aff  jmp     short loc_140004B08
0x140004b01  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140004b08  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004b0f  test    rax, rax
0x140004b12  jz      short loc_140004B1F
0x140004b14  mov     rdx, rbx
0x140004b17  mov     rcx, rsi
0x140004b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b1f  mov     rsi, [rsp+28h+arg_8]
0x140004b24  mov     rax, rbx
0x140004b27  mov     rbx, [rsp+28h+arg_0]
0x140004b2c  add     rsp, 20h
0x140004b30  pop     rdi
0x140004b31  retn
```
