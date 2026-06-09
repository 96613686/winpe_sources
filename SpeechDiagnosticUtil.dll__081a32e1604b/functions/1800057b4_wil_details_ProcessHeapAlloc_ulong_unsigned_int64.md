# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800057b4`
- end: `0x18000586b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800049bc`
- `0x180005434`
- `0x180005bc0`

## callees

- `0x1800057b4`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180005809`
- `KERNEL32!GetModuleHandleW` at `0x180005809`
- `KERNEL32!GetProcessHeap` at `0x1800057c8`
- `KERNEL32!GetProcessHeap` at `0x1800057c8`
- `KERNEL32!GetProcAddress` at `0x180005824`
- `KERNEL32!GetProcAddress` at `0x180005824`
- `KERNEL32!HeapAlloc` at `0x1800057df`
- `KERNEL32!HeapAlloc` at `0x1800057df`

## string_xrefs

- `0x180005802`: `ntdll.dll`

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
0x1800057b4  mov     [rsp+arg_0], rbx
0x1800057b9  mov     [rsp+arg_8], rsi
0x1800057be  push    rdi
0x1800057bf  sub     rsp, 20h
0x1800057c3  mov     rbx, rdx
0x1800057c6  mov     edi, ecx
0x1800057c8  call    cs:__imp_GetProcessHeap
0x1800057cf  nop     dword ptr [rax+rax+00h]
0x1800057d4  mov     r8, rbx; dwBytes
0x1800057d7  mov     edx, edi; dwFlags
0x1800057d9  mov     rcx, rax; hHeap
0x1800057dc  mov     rsi, rax
0x1800057df  call    cs:__imp_HeapAlloc
0x1800057e6  nop     dword ptr [rax+rax+00h]
0x1800057eb  mov     rbx, rax
0x1800057ee  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800057f5  test    rax, rax
0x1800057f8  jnz     short loc_18000584C
0x1800057fa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005800  jnz     short loc_180005857
0x180005802  lea     rcx, ModuleName; "ntdll.dll"
0x180005809  call    cs:__imp_GetModuleHandleW
0x180005810  nop     dword ptr [rax+rax+00h]
0x180005815  test    rax, rax
0x180005818  jz      short loc_180005839
0x18000581a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005821  mov     rcx, rax; hModule
0x180005824  call    cs:__imp_GetProcAddress
0x18000582b  nop     dword ptr [rax+rax+00h]
0x180005830  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005837  jmp     short loc_180005840
0x180005839  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005840  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005847  test    rax, rax
0x18000584a  jz      short loc_180005857
0x18000584c  mov     rdx, rbx
0x18000584f  mov     rcx, rsi
0x180005852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005857  mov     rsi, [rsp+28h+arg_8]
0x18000585c  mov     rax, rbx
0x18000585f  mov     rbx, [rsp+28h+arg_0]
0x180005864  add     rsp, 20h
0x180005868  pop     rdi
0x180005869  retn
```
