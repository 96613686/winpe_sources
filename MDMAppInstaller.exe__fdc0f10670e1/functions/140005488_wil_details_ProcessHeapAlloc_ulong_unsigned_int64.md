# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005488`
- end: `0x140005526`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005270`
- `0x140005750`
- `0x140005ae8`
- `0x14000ded8`
- `0x140012b5c`

## callees

- `0x140005488`
- `0x14001c010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400054e6`
- `KERNEL32!GetProcAddress` at `0x1400054e6`
- `KERNEL32!GetModuleHandleW` at `0x1400054d1`
- `KERNEL32!GetModuleHandleW` at `0x1400054d1`
- `KERNEL32!GetProcessHeap` at `0x14000549c`
- `KERNEL32!GetProcessHeap` at `0x14000549c`
- `KERNEL32!HeapAlloc` at `0x1400054ad`
- `KERNEL32!HeapAlloc` at `0x1400054ad`

## string_xrefs

- `0x1400054ca`: `ntdll.dll`

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
0x140005488  mov     [rsp+arg_0], rbx
0x14000548d  mov     [rsp+arg_8], rsi
0x140005492  push    rdi
0x140005493  sub     rsp, 20h
0x140005497  mov     rbx, rdx
0x14000549a  mov     edi, ecx
0x14000549c  call    cs:__imp_GetProcessHeap
0x1400054a2  mov     rsi, rax
0x1400054a5  mov     r8, rbx; dwBytes
0x1400054a8  mov     edx, edi; dwFlags
0x1400054aa  mov     rcx, rax; hHeap
0x1400054ad  call    cs:__imp_HeapAlloc
0x1400054b3  mov     rbx, rax
0x1400054b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400054bd  test    rax, rax
0x1400054c0  jnz     short loc_140005508
0x1400054c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400054c8  jnz     short loc_140005513
0x1400054ca  lea     rcx, ModuleName; "ntdll.dll"
0x1400054d1  call    cs:__imp_GetModuleHandleW
0x1400054d7  test    rax, rax
0x1400054da  jz      short loc_1400054F5
0x1400054dc  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1400054e3  mov     rcx, rax; hModule
0x1400054e6  call    cs:__imp_GetProcAddress
0x1400054ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400054f3  jmp     short loc_1400054FC
0x1400054f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400054fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005503  test    rax, rax
0x140005506  jz      short loc_140005513
0x140005508  mov     rdx, rbx
0x14000550b  mov     rcx, rsi
0x14000550e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005513  mov     rax, rbx
0x140005516  mov     rbx, [rsp+28h+arg_0]
0x14000551b  mov     rsi, [rsp+28h+arg_8]
0x140005520  add     rsp, 20h
0x140005524  pop     rdi
0x140005525  retn
```
