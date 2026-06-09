# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14006ea30`
- end: `0x14006eae7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14006c548`
- `0x14006c8f4`
- `0x14007059c`
- `0x1400716b8`

## callees

- `0x14006ea30`
- `0x14008b010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14006ea5b`
- `KERNEL32!HeapAlloc` at `0x14006ea5b`
- `KERNEL32!GetProcessHeap` at `0x14006ea44`
- `KERNEL32!GetProcessHeap` at `0x14006ea44`
- `KERNEL32!GetProcAddress` at `0x14006eaa0`
- `KERNEL32!GetProcAddress` at `0x14006eaa0`
- `KERNEL32!GetModuleHandleW` at `0x14006ea85`
- `KERNEL32!GetModuleHandleW` at `0x14006ea85`

## string_xrefs

- `0x14006ea7e`: `ntdll.dll`

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
0x14006ea30  mov     [rsp+arg_0], rbx
0x14006ea35  mov     [rsp+arg_8], rsi
0x14006ea3a  push    rdi
0x14006ea3b  sub     rsp, 20h
0x14006ea3f  mov     rbx, rdx
0x14006ea42  mov     edi, ecx
0x14006ea44  call    cs:__imp_GetProcessHeap
0x14006ea4b  nop     dword ptr [rax+rax+00h]
0x14006ea50  mov     rsi, rax
0x14006ea53  mov     r8, rbx; dwBytes
0x14006ea56  mov     edx, edi; dwFlags
0x14006ea58  mov     rcx, rax; hHeap
0x14006ea5b  call    cs:__imp_HeapAlloc
0x14006ea62  nop     dword ptr [rax+rax+00h]
0x14006ea67  mov     rbx, rax
0x14006ea6a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14006ea71  test    rax, rax
0x14006ea74  jnz     short loc_14006EAC8
0x14006ea76  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14006ea7c  jnz     short loc_14006EAD3
0x14006ea7e  lea     rcx, ModuleName; "ntdll.dll"
0x14006ea85  call    cs:__imp_GetModuleHandleW
0x14006ea8c  nop     dword ptr [rax+rax+00h]
0x14006ea91  test    rax, rax
0x14006ea94  jz      short loc_14006EAB5
0x14006ea96  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14006ea9d  mov     rcx, rax; hModule
0x14006eaa0  call    cs:__imp_GetProcAddress
0x14006eaa7  nop     dword ptr [rax+rax+00h]
0x14006eaac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14006eab3  jmp     short loc_14006EABC
0x14006eab5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14006eabc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14006eac3  test    rax, rax
0x14006eac6  jz      short loc_14006EAD3
0x14006eac8  mov     rdx, rbx
0x14006eacb  mov     rcx, rsi
0x14006eace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ead3  mov     rax, rbx
0x14006ead6  mov     rbx, [rsp+28h+arg_0]
0x14006eadb  mov     rsi, [rsp+28h+arg_8]
0x14006eae0  add     rsp, 20h
0x14006eae4  pop     rdi
0x14006eae5  retn
```
