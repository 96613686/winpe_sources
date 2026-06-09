# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005ef0`
- end: `0x180005f8e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003a78`
- `0x180003e1c`
- `0x180004bf0`
- `0x1800076b8`
- `0x18000a0e4`

## callees

- `0x180005ef0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005f15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005f15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f39`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f39`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f4e`

## string_xrefs

- `0x180005f32`: `ntdll.dll`

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
0x180005ef0  mov     [rsp+arg_0], rbx
0x180005ef5  mov     [rsp+arg_8], rsi
0x180005efa  push    rdi
0x180005efb  sub     rsp, 20h
0x180005eff  mov     rbx, rdx
0x180005f02  mov     edi, ecx
0x180005f04  call    cs:__imp_GetProcessHeap
0x180005f0a  mov     r8, rbx; dwBytes
0x180005f0d  mov     edx, edi; dwFlags
0x180005f0f  mov     rcx, rax; hHeap
0x180005f12  mov     rsi, rax
0x180005f15  call    cs:__imp_HeapAlloc
0x180005f1b  mov     rbx, rax
0x180005f1e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005f25  test    rax, rax
0x180005f28  jnz     short loc_180005F70
0x180005f2a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005f30  jnz     short loc_180005F7B
0x180005f32  lea     rcx, ModuleName; "ntdll.dll"
0x180005f39  call    cs:__imp_GetModuleHandleW
0x180005f3f  test    rax, rax
0x180005f42  jz      short loc_180005F5D
0x180005f44  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005f4b  mov     rcx, rax; hModule
0x180005f4e  call    cs:__imp_GetProcAddress
0x180005f54  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005f5b  jmp     short loc_180005F64
0x180005f5d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005f64  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005f6b  test    rax, rax
0x180005f6e  jz      short loc_180005F7B
0x180005f70  mov     rdx, rbx
0x180005f73  mov     rcx, rsi
0x180005f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f7b  mov     rsi, [rsp+28h+arg_8]
0x180005f80  mov     rax, rbx
0x180005f83  mov     rbx, [rsp+28h+arg_0]
0x180005f88  add     rsp, 20h
0x180005f8c  pop     rdi
0x180005f8d  retn
```
