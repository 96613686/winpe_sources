# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001315c`
- end: `0x1800131fb`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010f58`
- `0x180011324`
- `0x180014c60`
- `0x180015cac`

## callees

- `0x18001315c`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180013181`
- `KERNEL32!HeapAlloc` at `0x180013181`
- `KERNEL32!GetProcessHeap` at `0x180013170`
- `KERNEL32!GetProcessHeap` at `0x180013170`
- `KERNEL32!GetModuleHandleW` at `0x1800131a5`
- `KERNEL32!GetModuleHandleW` at `0x1800131a5`
- `KERNEL32!GetProcAddress` at `0x1800131ba`
- `KERNEL32!GetProcAddress` at `0x1800131ba`

## string_xrefs

- `0x18001319e`: `ntdll.dll`

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
0x18001315c  mov     [rsp+arg_0], rbx
0x180013161  mov     [rsp+arg_8], rsi
0x180013166  push    rdi
0x180013167  sub     rsp, 20h
0x18001316b  mov     rbx, rdx
0x18001316e  mov     edi, ecx
0x180013170  call    cs:__imp_GetProcessHeap
0x180013176  mov     rsi, rax
0x180013179  mov     r8, rbx; dwBytes
0x18001317c  mov     edx, edi; dwFlags
0x18001317e  mov     rcx, rax; hHeap
0x180013181  call    cs:__imp_HeapAlloc
0x180013187  mov     rbx, rax
0x18001318a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180013191  test    rax, rax
0x180013194  jnz     short loc_1800131DD
0x180013196  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001319c  jnz     short loc_1800131E8
0x18001319e  lea     rcx, ModuleName; "ntdll.dll"
0x1800131a5  call    cs:__imp_GetModuleHandleW
0x1800131ab  test    rax, rax
0x1800131ae  jz      short loc_1800131CA
0x1800131b0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800131b7  mov     rcx, rax; hModule
0x1800131ba  call    cs:__imp_GetProcAddress
0x1800131c0  nop
0x1800131c1  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800131c8  jmp     short loc_1800131D1
0x1800131ca  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800131d1  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800131d8  test    rax, rax
0x1800131db  jz      short loc_1800131E8
0x1800131dd  mov     rdx, rbx
0x1800131e0  mov     rcx, rsi
0x1800131e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131e8  mov     rax, rbx
0x1800131eb  mov     rbx, [rsp+28h+arg_0]
0x1800131f0  mov     rsi, [rsp+28h+arg_8]
0x1800131f5  add     rsp, 20h
0x1800131f9  pop     rdi
0x1800131fa  retn
```
