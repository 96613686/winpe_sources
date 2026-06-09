# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001393c`
- end: `0x1800139f4`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `184`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011648`
- `0x180011a14`
- `0x1800155a4`
- `0x18001685c`

## callees

- `0x18001393c`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180013967`
- `KERNEL32!HeapAlloc` at `0x180013967`
- `KERNEL32!GetProcessHeap` at `0x180013950`
- `KERNEL32!GetProcessHeap` at `0x180013950`
- `KERNEL32!GetModuleHandleW` at `0x180013991`
- `KERNEL32!GetModuleHandleW` at `0x180013991`
- `KERNEL32!GetProcAddress` at `0x1800139ac`
- `KERNEL32!GetProcAddress` at `0x1800139ac`

## string_xrefs

- `0x18001398a`: `ntdll.dll`

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
0x18001393c  mov     [rsp+arg_0], rbx
0x180013941  mov     [rsp+arg_8], rsi
0x180013946  push    rdi
0x180013947  sub     rsp, 20h
0x18001394b  mov     rbx, rdx
0x18001394e  mov     edi, ecx
0x180013950  call    cs:__imp_GetProcessHeap
0x180013957  nop     dword ptr [rax+rax+00h]
0x18001395c  mov     rsi, rax
0x18001395f  mov     r8, rbx; dwBytes
0x180013962  mov     edx, edi; dwFlags
0x180013964  mov     rcx, rax; hHeap
0x180013967  call    cs:__imp_HeapAlloc
0x18001396e  nop     dword ptr [rax+rax+00h]
0x180013973  mov     rbx, rax
0x180013976  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001397d  test    rax, rax
0x180013980  jnz     short loc_1800139D5
0x180013982  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180013988  jnz     short loc_1800139E0
0x18001398a  lea     rcx, ModuleName; "ntdll.dll"
0x180013991  call    cs:__imp_GetModuleHandleW
0x180013998  nop     dword ptr [rax+rax+00h]
0x18001399d  test    rax, rax
0x1800139a0  jz      short loc_1800139C2
0x1800139a2  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800139a9  mov     rcx, rax; hModule
0x1800139ac  call    cs:__imp_GetProcAddress
0x1800139b3  nop     dword ptr [rax+rax+00h]
0x1800139b8  nop
0x1800139b9  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800139c0  jmp     short loc_1800139C9
0x1800139c2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800139c9  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800139d0  test    rax, rax
0x1800139d3  jz      short loc_1800139E0
0x1800139d5  mov     rdx, rbx
0x1800139d8  mov     rcx, rsi
0x1800139db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139e0  mov     rax, rbx
0x1800139e3  mov     rbx, [rsp+28h+arg_0]
0x1800139e8  mov     rsi, [rsp+28h+arg_8]
0x1800139ed  add     rsp, 20h
0x1800139f1  pop     rdi
0x1800139f2  retn
```
