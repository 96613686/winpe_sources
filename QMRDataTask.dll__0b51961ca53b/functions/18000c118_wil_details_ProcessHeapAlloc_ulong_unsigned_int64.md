# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c118`
- end: `0x18000c1b6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006108`
- `0x1800064ac`
- `0x18000e810`
- `0x180011eec`

## callees

- `0x18000c118`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000c176`
- `KERNEL32!GetProcAddress` at `0x18000c176`
- `KERNEL32!GetModuleHandleW` at `0x18000c161`
- `KERNEL32!GetModuleHandleW` at `0x18000c161`
- `KERNEL32!GetProcessHeap` at `0x18000c12c`
- `KERNEL32!GetProcessHeap` at `0x18000c12c`
- `KERNEL32!HeapAlloc` at `0x18000c13d`
- `KERNEL32!HeapAlloc` at `0x18000c13d`

## string_xrefs

- `0x18000c15a`: `ntdll.dll`

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
0x18000c118  mov     [rsp+arg_0], rbx
0x18000c11d  mov     [rsp+arg_8], rsi
0x18000c122  push    rdi
0x18000c123  sub     rsp, 20h
0x18000c127  mov     rbx, rdx
0x18000c12a  mov     edi, ecx
0x18000c12c  call    cs:__imp_GetProcessHeap
0x18000c132  mov     rsi, rax
0x18000c135  mov     r8, rbx; dwBytes
0x18000c138  mov     edx, edi; dwFlags
0x18000c13a  mov     rcx, rax; hHeap
0x18000c13d  call    cs:__imp_HeapAlloc
0x18000c143  mov     rbx, rax
0x18000c146  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c14d  test    rax, rax
0x18000c150  jnz     short loc_18000C198
0x18000c152  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c158  jnz     short loc_18000C1A3
0x18000c15a  lea     rcx, ModuleName; "ntdll.dll"
0x18000c161  call    cs:__imp_GetModuleHandleW
0x18000c167  test    rax, rax
0x18000c16a  jz      short loc_18000C185
0x18000c16c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000c173  mov     rcx, rax; hModule
0x18000c176  call    cs:__imp_GetProcAddress
0x18000c17c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000c183  jmp     short loc_18000C18C
0x18000c185  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c18c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c193  test    rax, rax
0x18000c196  jz      short loc_18000C1A3
0x18000c198  mov     rdx, rbx
0x18000c19b  mov     rcx, rsi
0x18000c19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1a3  mov     rax, rbx
0x18000c1a6  mov     rbx, [rsp+28h+arg_0]
0x18000c1ab  mov     rsi, [rsp+28h+arg_8]
0x18000c1b0  add     rsp, 20h
0x18000c1b4  pop     rdi
0x18000c1b5  retn
```
