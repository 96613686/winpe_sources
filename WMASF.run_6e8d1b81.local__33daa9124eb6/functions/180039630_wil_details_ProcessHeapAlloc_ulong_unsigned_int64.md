# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180039630`
- end: `0x1800396ce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180039270`
- `0x18003a99c`
- `0x18003acb8`
- `0x18003c0e0`

## callees

- `0x180039630`
- `0x180040010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180039644`
- `KERNEL32!GetProcessHeap` at `0x180039644`
- `KERNEL32!HeapAlloc` at `0x180039655`
- `KERNEL32!HeapAlloc` at `0x180039655`
- `KERNEL32!GetProcAddress` at `0x18003968e`
- `KERNEL32!GetProcAddress` at `0x18003968e`
- `KERNEL32!GetModuleHandleW` at `0x180039679`
- `KERNEL32!GetModuleHandleW` at `0x180039679`

## string_xrefs

- `0x180039672`: `ntdll.dll`

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
0x180039630  mov     [rsp+arg_0], rbx
0x180039635  mov     [rsp+arg_8], rsi
0x18003963a  push    rdi
0x18003963b  sub     rsp, 20h
0x18003963f  mov     rbx, rdx
0x180039642  mov     edi, ecx
0x180039644  call    cs:__imp_GetProcessHeap
0x18003964a  mov     r8, rbx; dwBytes
0x18003964d  mov     edx, edi; dwFlags
0x18003964f  mov     rcx, rax; hHeap
0x180039652  mov     rsi, rax
0x180039655  call    cs:__imp_HeapAlloc
0x18003965b  mov     rbx, rax
0x18003965e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180039665  test    rax, rax
0x180039668  jnz     short loc_1800396B0
0x18003966a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180039670  jnz     short loc_1800396BB
0x180039672  lea     rcx, ModuleName; "ntdll.dll"
0x180039679  call    cs:__imp_GetModuleHandleW
0x18003967f  test    rax, rax
0x180039682  jz      short loc_18003969D
0x180039684  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18003968b  mov     rcx, rax; hModule
0x18003968e  call    cs:__imp_GetProcAddress
0x180039694  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18003969b  jmp     short loc_1800396A4
0x18003969d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800396a4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800396ab  test    rax, rax
0x1800396ae  jz      short loc_1800396BB
0x1800396b0  mov     rdx, rbx
0x1800396b3  mov     rcx, rsi
0x1800396b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396bb  mov     rsi, [rsp+28h+arg_8]
0x1800396c0  mov     rax, rbx
0x1800396c3  mov     rbx, [rsp+28h+arg_0]
0x1800396c8  add     rsp, 20h
0x1800396cc  pop     rdi
0x1800396cd  retn
```
