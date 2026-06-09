# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007e0c`
- end: `0x180007eaa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800069ec`
- `0x1800077c8`
- `0x1800078f8`
- `0x1800097d0`
- `0x180009c60`
- `0x18000b290`

## callees

- `0x180007e0c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e55`

## string_xrefs

- `0x180007e4e`: `ntdll.dll`

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
0x180007e0c  mov     [rsp+arg_0], rbx
0x180007e11  mov     [rsp+arg_8], rsi
0x180007e16  push    rdi
0x180007e17  sub     rsp, 20h
0x180007e1b  mov     rbx, rdx
0x180007e1e  mov     edi, ecx
0x180007e20  call    cs:__imp_GetProcessHeap
0x180007e26  mov     rsi, rax
0x180007e29  mov     r8, rbx; dwBytes
0x180007e2c  mov     edx, edi; dwFlags
0x180007e2e  mov     rcx, rax; hHeap
0x180007e31  call    cs:__imp_HeapAlloc
0x180007e37  mov     rbx, rax
0x180007e3a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007e41  test    rax, rax
0x180007e44  jnz     short loc_180007E8C
0x180007e46  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007e4c  jnz     short loc_180007E97
0x180007e4e  lea     rcx, ModuleName; "ntdll.dll"
0x180007e55  call    cs:__imp_GetModuleHandleW
0x180007e5b  test    rax, rax
0x180007e5e  jz      short loc_180007E79
0x180007e60  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180007e67  mov     rcx, rax; hModule
0x180007e6a  call    cs:__imp_GetProcAddress
0x180007e70  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007e77  jmp     short loc_180007E80
0x180007e79  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007e80  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007e87  test    rax, rax
0x180007e8a  jz      short loc_180007E97
0x180007e8c  mov     rdx, rbx
0x180007e8f  mov     rcx, rsi
0x180007e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e97  mov     rax, rbx
0x180007e9a  mov     rbx, [rsp+28h+arg_0]
0x180007e9f  mov     rsi, [rsp+28h+arg_8]
0x180007ea4  add     rsp, 20h
0x180007ea8  pop     rdi
0x180007ea9  retn
```
