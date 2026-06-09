# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800067a4`
- end: `0x18000685b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800063e0`
- `0x1800076ec`

## callees

- `0x1800067a4`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180006814`
- `KERNEL32!GetProcAddress` at `0x180006814`
- `KERNEL32!GetModuleHandleW` at `0x1800067f9`
- `KERNEL32!GetModuleHandleW` at `0x1800067f9`
- `KERNEL32!GetProcessHeap` at `0x1800067b8`
- `KERNEL32!GetProcessHeap` at `0x1800067b8`
- `KERNEL32!HeapAlloc` at `0x1800067cf`
- `KERNEL32!HeapAlloc` at `0x1800067cf`

## string_xrefs

- `0x1800067f2`: `ntdll.dll`

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
0x1800067a4  mov     [rsp+arg_0], rbx
0x1800067a9  mov     [rsp+arg_8], rsi
0x1800067ae  push    rdi
0x1800067af  sub     rsp, 20h
0x1800067b3  mov     rbx, rdx
0x1800067b6  mov     edi, ecx
0x1800067b8  call    cs:__imp_GetProcessHeap
0x1800067bf  nop     dword ptr [rax+rax+00h]
0x1800067c4  mov     rsi, rax
0x1800067c7  mov     r8, rbx; dwBytes
0x1800067ca  mov     edx, edi; dwFlags
0x1800067cc  mov     rcx, rax; hHeap
0x1800067cf  call    cs:__imp_HeapAlloc
0x1800067d6  nop     dword ptr [rax+rax+00h]
0x1800067db  mov     rbx, rax
0x1800067de  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800067e5  test    rax, rax
0x1800067e8  jnz     short loc_18000683C
0x1800067ea  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800067f0  jnz     short loc_180006847
0x1800067f2  lea     rcx, ModuleName; "ntdll.dll"
0x1800067f9  call    cs:__imp_GetModuleHandleW
0x180006800  nop     dword ptr [rax+rax+00h]
0x180006805  test    rax, rax
0x180006808  jz      short loc_180006829
0x18000680a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006811  mov     rcx, rax; hModule
0x180006814  call    cs:__imp_GetProcAddress
0x18000681b  nop     dword ptr [rax+rax+00h]
0x180006820  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006827  jmp     short loc_180006830
0x180006829  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006830  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006837  test    rax, rax
0x18000683a  jz      short loc_180006847
0x18000683c  mov     rdx, rbx
0x18000683f  mov     rcx, rsi
0x180006842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006847  mov     rax, rbx
0x18000684a  mov     rbx, [rsp+28h+arg_0]
0x18000684f  mov     rsi, [rsp+28h+arg_8]
0x180006854  add     rsp, 20h
0x180006858  pop     rdi
0x180006859  retn
```
