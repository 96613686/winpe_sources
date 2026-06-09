# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800059dc`
- end: `0x180005a7a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003df0`
- `0x1800066f4`

## callees

- `0x1800059dc`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a01`

## string_xrefs

- `0x180005a1e`: `ntdll.dll`

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
0x1800059dc  mov     [rsp+arg_0], rbx
0x1800059e1  mov     [rsp+arg_8], rsi
0x1800059e6  push    rdi
0x1800059e7  sub     rsp, 20h
0x1800059eb  mov     rbx, rdx
0x1800059ee  mov     edi, ecx
0x1800059f0  call    cs:__imp_GetProcessHeap
0x1800059f6  mov     rsi, rax
0x1800059f9  mov     r8, rbx; dwBytes
0x1800059fc  mov     edx, edi; dwFlags
0x1800059fe  mov     rcx, rax; hHeap
0x180005a01  call    cs:__imp_HeapAlloc
0x180005a07  mov     rbx, rax
0x180005a0a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005a11  test    rax, rax
0x180005a14  jnz     short loc_180005A5C
0x180005a16  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005a1c  jnz     short loc_180005A67
0x180005a1e  lea     rcx, ModuleName; "ntdll.dll"
0x180005a25  call    cs:__imp_GetModuleHandleW
0x180005a2b  test    rax, rax
0x180005a2e  jz      short loc_180005A49
0x180005a30  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005a37  mov     rcx, rax; hModule
0x180005a3a  call    cs:__imp_GetProcAddress
0x180005a40  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005a47  jmp     short loc_180005A50
0x180005a49  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005a50  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005a57  test    rax, rax
0x180005a5a  jz      short loc_180005A67
0x180005a5c  mov     rdx, rbx
0x180005a5f  mov     rcx, rsi
0x180005a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a67  mov     rax, rbx
0x180005a6a  mov     rbx, [rsp+28h+arg_0]
0x180005a6f  mov     rsi, [rsp+28h+arg_8]
0x180005a74  add     rsp, 20h
0x180005a78  pop     rdi
0x180005a79  retn
```
