# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005bcc`
- end: `0x180005c6a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800059dc`
- `0x18000607c`
- `0x180006414`
- `0x18001d308`

## callees

- `0x180005bcc`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005be0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005be0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bf1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bf1`

## string_xrefs

- `0x180005c0e`: `ntdll.dll`

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
0x180005bcc  mov     [rsp+arg_0], rbx
0x180005bd1  mov     [rsp+arg_8], rsi
0x180005bd6  push    rdi
0x180005bd7  sub     rsp, 20h
0x180005bdb  mov     rbx, rdx
0x180005bde  mov     edi, ecx
0x180005be0  call    cs:__imp_GetProcessHeap
0x180005be6  mov     rsi, rax
0x180005be9  mov     r8, rbx; dwBytes
0x180005bec  mov     edx, edi; dwFlags
0x180005bee  mov     rcx, rax; hHeap
0x180005bf1  call    cs:__imp_HeapAlloc
0x180005bf7  mov     rbx, rax
0x180005bfa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005c01  test    rax, rax
0x180005c04  jnz     short loc_180005C4C
0x180005c06  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005c0c  jnz     short loc_180005C57
0x180005c0e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180005c15  call    cs:__imp_GetModuleHandleW
0x180005c1b  test    rax, rax
0x180005c1e  jz      short loc_180005C39
0x180005c20  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005c27  mov     rcx, rax; hModule
0x180005c2a  call    cs:__imp_GetProcAddress
0x180005c30  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005c37  jmp     short loc_180005C40
0x180005c39  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005c40  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005c47  test    rax, rax
0x180005c4a  jz      short loc_180005C57
0x180005c4c  mov     rdx, rbx
0x180005c4f  mov     rcx, rsi
0x180005c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c57  mov     rax, rbx
0x180005c5a  mov     rbx, [rsp+28h+arg_0]
0x180005c5f  mov     rsi, [rsp+28h+arg_8]
0x180005c64  add     rsp, 20h
0x180005c68  pop     rdi
0x180005c69  retn
```
