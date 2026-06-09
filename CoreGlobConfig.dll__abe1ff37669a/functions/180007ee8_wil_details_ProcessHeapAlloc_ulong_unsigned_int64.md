# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007ee8`
- end: `0x180007f86`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800071ec`
- `0x180007290`
- `0x180007c68`
- `0x180008374`
- `0x18000870c`
- `0x180016360`
- `0x18001eacc`

## callees

- `0x180007ee8`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007f46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007f46`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007efc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007efc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007f0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007f0d`

## string_xrefs

- `0x180007f2a`: `ntdll.dll`

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
0x180007ee8  mov     [rsp+arg_0], rbx
0x180007eed  mov     [rsp+arg_8], rsi
0x180007ef2  push    rdi
0x180007ef3  sub     rsp, 20h
0x180007ef7  mov     rbx, rdx
0x180007efa  mov     edi, ecx
0x180007efc  call    cs:__imp_GetProcessHeap
0x180007f02  mov     rsi, rax
0x180007f05  mov     r8, rbx; dwBytes
0x180007f08  mov     edx, edi; dwFlags
0x180007f0a  mov     rcx, rax; hHeap
0x180007f0d  call    cs:__imp_HeapAlloc
0x180007f13  mov     rbx, rax
0x180007f16  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007f1d  test    rax, rax
0x180007f20  jnz     short loc_180007F68
0x180007f22  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007f28  jnz     short loc_180007F73
0x180007f2a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180007f31  call    cs:__imp_GetModuleHandleW
0x180007f37  test    rax, rax
0x180007f3a  jz      short loc_180007F55
0x180007f3c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007f43  mov     rcx, rax; hModule
0x180007f46  call    cs:__imp_GetProcAddress
0x180007f4c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007f53  jmp     short loc_180007F5C
0x180007f55  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007f5c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007f63  test    rax, rax
0x180007f66  jz      short loc_180007F73
0x180007f68  mov     rdx, rbx
0x180007f6b  mov     rcx, rsi
0x180007f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f73  mov     rax, rbx
0x180007f76  mov     rbx, [rsp+28h+arg_0]
0x180007f7b  mov     rsi, [rsp+28h+arg_8]
0x180007f80  add     rsp, 20h
0x180007f84  pop     rdi
0x180007f85  retn
```
