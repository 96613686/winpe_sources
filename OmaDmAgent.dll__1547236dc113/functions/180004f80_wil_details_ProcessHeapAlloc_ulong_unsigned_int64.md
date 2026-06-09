# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004f80`
- end: `0x180005037`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800045f8`
- `0x18000549c`
- `0x180005850`

## callees

- `0x180004f80`
- `0x180021010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180004fab`
- `KERNEL32!HeapAlloc` at `0x180004fab`
- `KERNEL32!GetProcAddress` at `0x180004ff0`
- `KERNEL32!GetProcAddress` at `0x180004ff0`
- `KERNEL32!GetProcessHeap` at `0x180004f94`
- `KERNEL32!GetProcessHeap` at `0x180004f94`
- `KERNEL32!GetModuleHandleW` at `0x180004fd5`
- `KERNEL32!GetModuleHandleW` at `0x180004fd5`

## string_xrefs

- `0x180004fce`: `ntdll.dll`

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
0x180004f80  mov     [rsp+arg_0], rbx
0x180004f85  mov     [rsp+arg_8], rsi
0x180004f8a  push    rdi
0x180004f8b  sub     rsp, 20h
0x180004f8f  mov     rbx, rdx
0x180004f92  mov     edi, ecx
0x180004f94  call    cs:__imp_GetProcessHeap
0x180004f9b  nop     dword ptr [rax+rax+00h]
0x180004fa0  mov     rsi, rax
0x180004fa3  mov     r8, rbx; dwBytes
0x180004fa6  mov     edx, edi; dwFlags
0x180004fa8  mov     rcx, rax; hHeap
0x180004fab  call    cs:__imp_HeapAlloc
0x180004fb2  nop     dword ptr [rax+rax+00h]
0x180004fb7  mov     rbx, rax
0x180004fba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004fc1  test    rax, rax
0x180004fc4  jnz     short loc_180005018
0x180004fc6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004fcc  jnz     short loc_180005023
0x180004fce  lea     rcx, ModuleName; "ntdll.dll"
0x180004fd5  call    cs:__imp_GetModuleHandleW
0x180004fdc  nop     dword ptr [rax+rax+00h]
0x180004fe1  test    rax, rax
0x180004fe4  jz      short loc_180005005
0x180004fe6  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180004fed  mov     rcx, rax; hModule
0x180004ff0  call    cs:__imp_GetProcAddress
0x180004ff7  nop     dword ptr [rax+rax+00h]
0x180004ffc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005003  jmp     short loc_18000500C
0x180005005  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000500c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005013  test    rax, rax
0x180005016  jz      short loc_180005023
0x180005018  mov     rdx, rbx
0x18000501b  mov     rcx, rsi
0x18000501e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005023  mov     rax, rbx
0x180005026  mov     rbx, [rsp+28h+arg_0]
0x18000502b  mov     rsi, [rsp+28h+arg_8]
0x180005030  add     rsp, 20h
0x180005034  pop     rdi
0x180005035  retn
```
