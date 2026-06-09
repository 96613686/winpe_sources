# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007dfc`
- end: `0x180007e9b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800044a8`
- `0x18000487c`
- `0x180006060`
- `0x180009748`
- `0x18000c40c`

## callees

- `0x180007dfc`
- `0x180011010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007e21`
- `KERNEL32!HeapAlloc` at `0x180007e21`
- `KERNEL32!GetProcessHeap` at `0x180007e10`
- `KERNEL32!GetProcessHeap` at `0x180007e10`
- `KERNEL32!GetModuleHandleW` at `0x180007e45`
- `KERNEL32!GetModuleHandleW` at `0x180007e45`
- `KERNEL32!GetProcAddress` at `0x180007e5a`
- `KERNEL32!GetProcAddress` at `0x180007e5a`

## string_xrefs

- `0x180007e3e`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180007dfc  mov     [rsp+arg_0], rbx
0x180007e01  mov     [rsp+arg_8], rsi
0x180007e06  push    rdi
0x180007e07  sub     rsp, 20h
0x180007e0b  mov     rbx, rdx
0x180007e0e  mov     edi, ecx
0x180007e10  call    cs:__imp_GetProcessHeap
0x180007e16  mov     rsi, rax
0x180007e19  mov     r8, rbx; dwBytes
0x180007e1c  mov     edx, edi; dwFlags
0x180007e1e  mov     rcx, rax; hHeap
0x180007e21  call    cs:__imp_HeapAlloc
0x180007e27  mov     rbx, rax
0x180007e2a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007e31  test    rax, rax
0x180007e34  jnz     short loc_180007E7D
0x180007e36  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007e3c  jnz     short loc_180007E88
0x180007e3e  lea     rcx, ModuleName; "ntdll.dll"
0x180007e45  call    cs:__imp_GetModuleHandleW
0x180007e4b  test    rax, rax
0x180007e4e  jz      short loc_180007E6A
0x180007e50  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007e57  mov     rcx, rax; hModule
0x180007e5a  call    cs:__imp_GetProcAddress
0x180007e60  nop
0x180007e61  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007e68  jmp     short loc_180007E71
0x180007e6a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007e71  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007e78  test    rax, rax
0x180007e7b  jz      short loc_180007E88
0x180007e7d  mov     rdx, rbx
0x180007e80  mov     rcx, rsi
0x180007e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e88  mov     rax, rbx
0x180007e8b  mov     rbx, [rsp+28h+arg_0]
0x180007e90  mov     rsi, [rsp+28h+arg_8]
0x180007e95  add     rsp, 20h
0x180007e99  pop     rdi
0x180007e9a  retn
```
