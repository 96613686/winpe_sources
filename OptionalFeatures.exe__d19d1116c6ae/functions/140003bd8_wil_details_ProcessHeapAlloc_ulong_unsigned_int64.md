# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140003bd8`
- end: `0x140003c76`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400024f4`
- `0x140002b90`
- `0x140003f20`

## callees

- `0x140003bd8`
- `0x140005010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140003bfd`
- `KERNEL32!HeapAlloc` at `0x140003bfd`
- `KERNEL32!GetProcAddress` at `0x140003c36`
- `KERNEL32!GetProcAddress` at `0x140003c36`
- `KERNEL32!GetProcessHeap` at `0x140003bec`
- `KERNEL32!GetProcessHeap` at `0x140003bec`
- `KERNEL32!GetModuleHandleW` at `0x140003c21`
- `KERNEL32!GetModuleHandleW` at `0x140003c21`

## string_xrefs

- `0x140003c1a`: `ntdll.dll`

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
0x140003bd8  mov     [rsp+arg_0], rbx
0x140003bdd  mov     [rsp+arg_8], rsi
0x140003be2  push    rdi
0x140003be3  sub     rsp, 20h
0x140003be7  mov     rbx, rdx
0x140003bea  mov     edi, ecx
0x140003bec  call    cs:__imp_GetProcessHeap
0x140003bf2  mov     r8, rbx; dwBytes
0x140003bf5  mov     edx, edi; dwFlags
0x140003bf7  mov     rcx, rax; hHeap
0x140003bfa  mov     rsi, rax
0x140003bfd  call    cs:__imp_HeapAlloc
0x140003c03  mov     rbx, rax
0x140003c06  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140003c0d  test    rax, rax
0x140003c10  jnz     short loc_140003C58
0x140003c12  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140003c18  jnz     short loc_140003C63
0x140003c1a  lea     rcx, ModuleName; "ntdll.dll"
0x140003c21  call    cs:__imp_GetModuleHandleW
0x140003c27  test    rax, rax
0x140003c2a  jz      short loc_140003C45
0x140003c2c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140003c33  mov     rcx, rax; hModule
0x140003c36  call    cs:__imp_GetProcAddress
0x140003c3c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140003c43  jmp     short loc_140003C4C
0x140003c45  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140003c4c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140003c53  test    rax, rax
0x140003c56  jz      short loc_140003C63
0x140003c58  mov     rdx, rbx
0x140003c5b  mov     rcx, rsi
0x140003c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c63  mov     rsi, [rsp+28h+arg_8]
0x140003c68  mov     rax, rbx
0x140003c6b  mov     rbx, [rsp+28h+arg_0]
0x140003c70  add     rsp, 20h
0x140003c74  pop     rdi
0x140003c75  retn
```
