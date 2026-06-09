# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001bf38`
- end: `0x18001bfd6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001928c`
- `0x180019c70`
- `0x18001c550`

## callees

- `0x18001bf38`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001bf96`
- `KERNEL32!GetProcAddress` at `0x18001bf96`
- `KERNEL32!GetModuleHandleW` at `0x18001bf81`
- `KERNEL32!GetModuleHandleW` at `0x18001bf81`
- `KERNEL32!GetProcessHeap` at `0x18001bf4c`
- `KERNEL32!GetProcessHeap` at `0x18001bf4c`
- `KERNEL32!HeapAlloc` at `0x18001bf5d`
- `KERNEL32!HeapAlloc` at `0x18001bf5d`

## string_xrefs

- `0x18001bf7a`: `ntdll.dll`

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
0x18001bf38  mov     [rsp+arg_0], rbx
0x18001bf3d  mov     [rsp+arg_8], rsi
0x18001bf42  push    rdi
0x18001bf43  sub     rsp, 20h
0x18001bf47  mov     rbx, rdx
0x18001bf4a  mov     edi, ecx
0x18001bf4c  call    cs:__imp_GetProcessHeap
0x18001bf52  mov     rsi, rax
0x18001bf55  mov     r8, rbx; dwBytes
0x18001bf58  mov     edx, edi; dwFlags
0x18001bf5a  mov     rcx, rax; hHeap
0x18001bf5d  call    cs:__imp_HeapAlloc
0x18001bf63  mov     rbx, rax
0x18001bf66  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001bf6d  test    rax, rax
0x18001bf70  jnz     short loc_18001BFB8
0x18001bf72  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001bf78  jnz     short loc_18001BFC3
0x18001bf7a  lea     rcx, aNtdllDll; "ntdll.dll"
0x18001bf81  call    cs:__imp_GetModuleHandleW
0x18001bf87  test    rax, rax
0x18001bf8a  jz      short loc_18001BFA5
0x18001bf8c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001bf93  mov     rcx, rax; hModule
0x18001bf96  call    cs:__imp_GetProcAddress
0x18001bf9c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001bfa3  jmp     short loc_18001BFAC
0x18001bfa5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001bfac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001bfb3  test    rax, rax
0x18001bfb6  jz      short loc_18001BFC3
0x18001bfb8  mov     rdx, rbx
0x18001bfbb  mov     rcx, rsi
0x18001bfbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfc3  mov     rax, rbx
0x18001bfc6  mov     rbx, [rsp+28h+arg_0]
0x18001bfcb  mov     rsi, [rsp+28h+arg_8]
0x18001bfd0  add     rsp, 20h
0x18001bfd4  pop     rdi
0x18001bfd5  retn
```
