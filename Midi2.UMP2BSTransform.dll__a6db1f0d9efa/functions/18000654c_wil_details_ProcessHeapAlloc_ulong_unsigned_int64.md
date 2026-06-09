# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000654c`
- end: `0x1800065ea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003978`
- `0x180005040`
- `0x1800077d0`
- `0x18000e2f0`

## callees

- `0x18000654c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006595`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006595`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800065aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800065aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006571`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006571`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006560`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006560`

## string_xrefs

- `0x18000658e`: `ntdll.dll`

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
0x18000654c  mov     [rsp+arg_0], rbx
0x180006551  mov     [rsp+arg_8], rsi
0x180006556  push    rdi
0x180006557  sub     rsp, 20h
0x18000655b  mov     rbx, rdx
0x18000655e  mov     edi, ecx
0x180006560  call    cs:__imp_GetProcessHeap
0x180006566  mov     rsi, rax
0x180006569  mov     r8, rbx; dwBytes
0x18000656c  mov     edx, edi; dwFlags
0x18000656e  mov     rcx, rax; hHeap
0x180006571  call    cs:__imp_HeapAlloc
0x180006577  mov     rbx, rax
0x18000657a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006581  test    rax, rax
0x180006584  jnz     short loc_1800065CC
0x180006586  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000658c  jnz     short loc_1800065D7
0x18000658e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180006595  call    cs:__imp_GetModuleHandleW
0x18000659b  test    rax, rax
0x18000659e  jz      short loc_1800065B9
0x1800065a0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800065a7  mov     rcx, rax; hModule
0x1800065aa  call    cs:__imp_GetProcAddress
0x1800065b0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800065b7  jmp     short loc_1800065C0
0x1800065b9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800065c0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800065c7  test    rax, rax
0x1800065ca  jz      short loc_1800065D7
0x1800065cc  mov     rdx, rbx
0x1800065cf  mov     rcx, rsi
0x1800065d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d7  mov     rax, rbx
0x1800065da  mov     rbx, [rsp+28h+arg_0]
0x1800065df  mov     rsi, [rsp+28h+arg_8]
0x1800065e4  add     rsp, 20h
0x1800065e8  pop     rdi
0x1800065e9  retn
```
