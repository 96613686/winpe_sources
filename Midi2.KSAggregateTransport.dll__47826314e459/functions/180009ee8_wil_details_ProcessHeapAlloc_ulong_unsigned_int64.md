# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009ee8`
- end: `0x180009f86`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007238`
- `0x1800089c0`
- `0x18000b420`
- `0x18000c76c`

## callees

- `0x180009ee8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f31`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009efc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009efc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f0d`

## string_xrefs

- `0x180009f2a`: `ntdll.dll`

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
0x180009ee8  mov     [rsp+arg_0], rbx
0x180009eed  mov     [rsp+arg_8], rsi
0x180009ef2  push    rdi
0x180009ef3  sub     rsp, 20h
0x180009ef7  mov     rbx, rdx
0x180009efa  mov     edi, ecx
0x180009efc  call    cs:__imp_GetProcessHeap
0x180009f02  mov     rsi, rax
0x180009f05  mov     r8, rbx; dwBytes
0x180009f08  mov     edx, edi; dwFlags
0x180009f0a  mov     rcx, rax; hHeap
0x180009f0d  call    cs:__imp_HeapAlloc
0x180009f13  mov     rbx, rax
0x180009f16  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009f1d  test    rax, rax
0x180009f20  jnz     short loc_180009F68
0x180009f22  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009f28  jnz     short loc_180009F73
0x180009f2a  lea     rcx, aNtdllDll; "ntdll.dll"
0x180009f31  call    cs:__imp_GetModuleHandleW
0x180009f37  test    rax, rax
0x180009f3a  jz      short loc_180009F55
0x180009f3c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180009f43  mov     rcx, rax; hModule
0x180009f46  call    cs:__imp_GetProcAddress
0x180009f4c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180009f53  jmp     short loc_180009F5C
0x180009f55  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009f5c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009f63  test    rax, rax
0x180009f66  jz      short loc_180009F73
0x180009f68  mov     rdx, rbx
0x180009f6b  mov     rcx, rsi
0x180009f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f73  mov     rax, rbx
0x180009f76  mov     rbx, [rsp+28h+arg_0]
0x180009f7b  mov     rsi, [rsp+28h+arg_8]
0x180009f80  add     rsp, 20h
0x180009f84  pop     rdi
0x180009f85  retn
```
