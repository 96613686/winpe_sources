# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180012e70`
- end: `0x180012f0f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800043f0`
- `0x18000eab0`
- `0x180014bf0`
- `0x1800151a0`
- `0x180015db0`

## callees

- `0x180012e70`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180012ece`
- `KERNEL32!GetProcAddress` at `0x180012ece`
- `KERNEL32!GetProcessHeap` at `0x180012e84`
- `KERNEL32!GetProcessHeap` at `0x180012e84`
- `KERNEL32!HeapAlloc` at `0x180012e95`
- `KERNEL32!HeapAlloc` at `0x180012e95`
- `KERNEL32!GetModuleHandleW` at `0x180012eb9`
- `KERNEL32!GetModuleHandleW` at `0x180012eb9`

## string_xrefs

- `0x180012eb2`: `ntdll.dll`

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
0x180012e70  mov     [rsp+arg_0], rbx
0x180012e75  mov     [rsp+arg_8], rsi
0x180012e7a  push    rdi
0x180012e7b  sub     rsp, 20h
0x180012e7f  mov     rbx, rdx
0x180012e82  mov     edi, ecx
0x180012e84  call    cs:__imp_GetProcessHeap
0x180012e8a  mov     rsi, rax
0x180012e8d  mov     r8, rbx; dwBytes
0x180012e90  mov     edx, edi; dwFlags
0x180012e92  mov     rcx, rax; hHeap
0x180012e95  call    cs:__imp_HeapAlloc
0x180012e9b  mov     rbx, rax
0x180012e9e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012ea5  test    rax, rax
0x180012ea8  jnz     short loc_180012EF0
0x180012eaa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012eb0  jnz     short loc_180012EFC
0x180012eb2  lea     rcx, aNtdllDll; "ntdll.dll"
0x180012eb9  call    cs:__imp_GetModuleHandleW
0x180012ebf  test    rax, rax
0x180012ec2  jz      short loc_180012EDD
0x180012ec4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180012ecb  mov     rcx, rax; hModule
0x180012ece  call    cs:__imp_GetProcAddress
0x180012ed4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180012edb  jmp     short loc_180012EE4
0x180012edd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012ee4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012eeb  test    rax, rax
0x180012eee  jz      short loc_180012EFC
0x180012ef0  mov     rdx, rbx
0x180012ef3  mov     rcx, rsi
0x180012ef6  call    cs:__guard_dispatch_icall_fptr
0x180012efc  mov     rax, rbx
0x180012eff  mov     rbx, [rsp+28h+arg_0]
0x180012f04  mov     rsi, [rsp+28h+arg_8]
0x180012f09  add     rsp, 20h
0x180012f0d  pop     rdi
0x180012f0e  retn
```
