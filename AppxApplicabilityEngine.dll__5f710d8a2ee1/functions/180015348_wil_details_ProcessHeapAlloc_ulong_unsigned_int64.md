# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180015348`
- end: `0x1800153f0`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800150cc`
- `0x18001584c`
- `0x180015be4`
- `0x18001ca9c`
- `0x18001e0b4`

## callees

- `0x180015348`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800153b0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800153b0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001539b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001539b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015366`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015366`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015377`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015377`

## string_xrefs

- `0x180015394`: `ntdll.dll`

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
0x180015348  push    rdi
0x18001534a  sub     rsp, 30h
0x18001534e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180015357  mov     [rsp+38h+arg_0], rbx
0x18001535c  mov     [rsp+38h+arg_8], rsi
0x180015361  mov     rbx, rdx
0x180015364  mov     edi, ecx
0x180015366  call    cs:__imp_GetProcessHeap
0x18001536c  mov     rsi, rax
0x18001536f  mov     r8, rbx; dwBytes
0x180015372  mov     edx, edi; dwFlags
0x180015374  mov     rcx, rax; hHeap
0x180015377  call    cs:__imp_HeapAlloc
0x18001537d  mov     rbx, rax
0x180015380  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180015387  test    rax, rax
0x18001538a  jnz     short loc_1800153D2
0x18001538c  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180015392  jnz     short loc_1800153DD
0x180015394  lea     rcx, ModuleName; "ntdll.dll"
0x18001539b  call    cs:__imp_GetModuleHandleW
0x1800153a1  test    rax, rax
0x1800153a4  jz      short loc_1800153BF
0x1800153a6  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800153ad  mov     rcx, rax; hModule
0x1800153b0  call    cs:__imp_GetProcAddress
0x1800153b6  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800153bd  jmp     short loc_1800153C6
0x1800153bf  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800153c6  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800153cd  test    rax, rax
0x1800153d0  jz      short loc_1800153DD
0x1800153d2  mov     rdx, rbx
0x1800153d5  mov     rcx, rsi
0x1800153d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153dd  mov     rax, rbx
0x1800153e0  mov     rbx, [rsp+38h+arg_0]
0x1800153e5  mov     rsi, [rsp+38h+arg_8]
0x1800153ea  add     rsp, 30h
0x1800153ee  pop     rdi
0x1800153ef  retn
```
