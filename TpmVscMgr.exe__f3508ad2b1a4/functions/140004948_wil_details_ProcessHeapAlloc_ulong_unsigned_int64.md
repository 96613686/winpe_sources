# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004948`
- end: `0x1400049e6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003258`
- `0x140003900`
- `0x140004e40`

## callees

- `0x140004948`
- `0x140013010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000496d`
- `KERNEL32!HeapAlloc` at `0x14000496d`
- `KERNEL32!GetProcAddress` at `0x1400049a6`
- `KERNEL32!GetProcAddress` at `0x1400049a6`
- `KERNEL32!GetProcessHeap` at `0x14000495c`
- `KERNEL32!GetProcessHeap` at `0x14000495c`
- `KERNEL32!GetModuleHandleW` at `0x140004991`
- `KERNEL32!GetModuleHandleW` at `0x140004991`

## string_xrefs

- `0x14000498a`: `ntdll.dll`

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
0x140004948  mov     [rsp+arg_0], rbx
0x14000494d  mov     [rsp+arg_8], rsi
0x140004952  push    rdi
0x140004953  sub     rsp, 20h
0x140004957  mov     rbx, rdx
0x14000495a  mov     edi, ecx
0x14000495c  call    cs:__imp_GetProcessHeap
0x140004962  mov     rsi, rax
0x140004965  mov     r8, rbx; dwBytes
0x140004968  mov     edx, edi; dwFlags
0x14000496a  mov     rcx, rax; hHeap
0x14000496d  call    cs:__imp_HeapAlloc
0x140004973  mov     rbx, rax
0x140004976  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000497d  test    rax, rax
0x140004980  jnz     short loc_1400049C8
0x140004982  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004988  jnz     short loc_1400049D3
0x14000498a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140004991  call    cs:__imp_GetModuleHandleW
0x140004997  test    rax, rax
0x14000499a  jz      short loc_1400049B5
0x14000499c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400049a3  mov     rcx, rax; hModule
0x1400049a6  call    cs:__imp_GetProcAddress
0x1400049ac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400049b3  jmp     short loc_1400049BC
0x1400049b5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400049bc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400049c3  test    rax, rax
0x1400049c6  jz      short loc_1400049D3
0x1400049c8  mov     rdx, rbx
0x1400049cb  mov     rcx, rsi
0x1400049ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049d3  mov     rax, rbx
0x1400049d6  mov     rbx, [rsp+28h+arg_0]
0x1400049db  mov     rsi, [rsp+28h+arg_8]
0x1400049e0  add     rsp, 20h
0x1400049e4  pop     rdi
0x1400049e5  retn
```
