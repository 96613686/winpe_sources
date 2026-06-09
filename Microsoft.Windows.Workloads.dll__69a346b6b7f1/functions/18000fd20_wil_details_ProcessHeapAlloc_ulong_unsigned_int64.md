# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000fd20`
- end: `0x18000fdbf`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fdc0`
- `0x18002ee80`
- `0x18002f430`
- `0x180030560`

## callees

- `0x18000fd20`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000fd34`
- `KERNEL32!GetProcessHeap` at `0x18000fd34`
- `KERNEL32!GetModuleHandleW` at `0x18000fd69`
- `KERNEL32!GetModuleHandleW` at `0x18000fd69`
- `KERNEL32!HeapAlloc` at `0x18000fd45`
- `KERNEL32!HeapAlloc` at `0x18000fd45`
- `KERNEL32!GetProcAddress` at `0x18000fd7e`
- `KERNEL32!GetProcAddress` at `0x18000fd7e`

## string_xrefs

- `0x18000fd62`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x18000fd20  mov     [rsp+arg_0], rbx
0x18000fd25  mov     [rsp+arg_8], rsi
0x18000fd2a  push    rdi
0x18000fd2b  sub     rsp, 20h
0x18000fd2f  mov     rbx, rdx
0x18000fd32  mov     edi, ecx
0x18000fd34  call    cs:__imp_GetProcessHeap
0x18000fd3a  mov     rsi, rax
0x18000fd3d  mov     r8, rbx; dwBytes
0x18000fd40  mov     edx, edi; dwFlags
0x18000fd42  mov     rcx, rax; hHeap
0x18000fd45  call    cs:__imp_HeapAlloc
0x18000fd4b  mov     rbx, rax
0x18000fd4e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000fd55  test    rax, rax
0x18000fd58  jnz     short loc_18000FDA0
0x18000fd5a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000fd60  jnz     short loc_18000FDAC
0x18000fd62  lea     rcx, ModuleName; "ntdll.dll"
0x18000fd69  call    cs:__imp_GetModuleHandleW
0x18000fd6f  test    rax, rax
0x18000fd72  jz      short loc_18000FD8D
0x18000fd74  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000fd7b  mov     rcx, rax; hModule
0x18000fd7e  call    cs:__imp_GetProcAddress
0x18000fd84  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000fd8b  jmp     short loc_18000FD94
0x18000fd8d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000fd94  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000fd9b  test    rax, rax
0x18000fd9e  jz      short loc_18000FDAC
0x18000fda0  mov     rdx, rbx
0x18000fda3  mov     rcx, rsi
0x18000fda6  call    cs:__guard_dispatch_icall_fptr
0x18000fdac  mov     rax, rbx
0x18000fdaf  mov     rbx, [rsp+28h+arg_0]
0x18000fdb4  mov     rsi, [rsp+28h+arg_8]
0x18000fdb9  add     rsp, 20h
0x18000fdbd  pop     rdi
0x18000fdbe  retn
```
