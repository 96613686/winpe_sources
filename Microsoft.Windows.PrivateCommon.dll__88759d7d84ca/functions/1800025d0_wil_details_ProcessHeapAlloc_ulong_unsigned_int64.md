# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800025d0`
- end: `0x18000266f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800046d0`
- `0x180004c80`
- `0x180005aa0`

## callees

- `0x1800025d0`
- `0x18000b930`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800025f5`
- `KERNEL32!HeapAlloc` at `0x1800025f5`
- `KERNEL32!GetProcAddress` at `0x18000262e`
- `KERNEL32!GetProcAddress` at `0x18000262e`
- `KERNEL32!GetProcessHeap` at `0x1800025e4`
- `KERNEL32!GetProcessHeap` at `0x1800025e4`
- `KERNEL32!GetModuleHandleW` at `0x180002619`
- `KERNEL32!GetModuleHandleW` at `0x180002619`

## string_xrefs

- `0x180002612`: `ntdll.dll`

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
0x1800025d0  mov     [rsp+arg_0], rbx
0x1800025d5  mov     [rsp+arg_8], rsi
0x1800025da  push    rdi
0x1800025db  sub     rsp, 20h
0x1800025df  mov     rbx, rdx
0x1800025e2  mov     edi, ecx
0x1800025e4  call    cs:__imp_GetProcessHeap
0x1800025ea  mov     rsi, rax
0x1800025ed  mov     r8, rbx; dwBytes
0x1800025f0  mov     edx, edi; dwFlags
0x1800025f2  mov     rcx, rax; hHeap
0x1800025f5  call    cs:__imp_HeapAlloc
0x1800025fb  mov     rbx, rax
0x1800025fe  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180002605  test    rax, rax
0x180002608  jnz     short loc_180002650
0x18000260a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180002610  jnz     short loc_18000265C
0x180002612  lea     rcx, ModuleName; "ntdll.dll"
0x180002619  call    cs:__imp_GetModuleHandleW
0x18000261f  test    rax, rax
0x180002622  jz      short loc_18000263D
0x180002624  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000262b  mov     rcx, rax; hModule
0x18000262e  call    cs:__imp_GetProcAddress
0x180002634  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000263b  jmp     short loc_180002644
0x18000263d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180002644  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000264b  test    rax, rax
0x18000264e  jz      short loc_18000265C
0x180002650  mov     rdx, rbx
0x180002653  mov     rcx, rsi
0x180002656  call    cs:__guard_dispatch_icall_fptr
0x18000265c  mov     rax, rbx
0x18000265f  mov     rbx, [rsp+28h+arg_0]
0x180002664  mov     rsi, [rsp+28h+arg_8]
0x180002669  add     rsp, 20h
0x18000266d  pop     rdi
0x18000266e  retn
```
