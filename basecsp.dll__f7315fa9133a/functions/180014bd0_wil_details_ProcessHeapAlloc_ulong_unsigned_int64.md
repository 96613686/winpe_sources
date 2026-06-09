# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180014bd0`
- end: `0x180014c6e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014608`
- `0x180014738`
- `0x180016770`
- `0x180016c00`
- `0x180018e68`

## callees

- `0x180014bd0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c19`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014c2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014c2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014be4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014be4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014bf5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014bf5`

## string_xrefs

- `0x180014c12`: `ntdll.dll`

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
0x180014bd0  mov     [rsp+arg_0], rbx
0x180014bd5  mov     [rsp+arg_8], rsi
0x180014bda  push    rdi
0x180014bdb  sub     rsp, 20h
0x180014bdf  mov     rbx, rdx
0x180014be2  mov     edi, ecx
0x180014be4  call    cs:__imp_GetProcessHeap
0x180014bea  mov     rsi, rax
0x180014bed  mov     r8, rbx; dwBytes
0x180014bf0  mov     edx, edi; dwFlags
0x180014bf2  mov     rcx, rax; hHeap
0x180014bf5  call    cs:__imp_HeapAlloc
0x180014bfb  mov     rbx, rax
0x180014bfe  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014c05  test    rax, rax
0x180014c08  jnz     short loc_180014C50
0x180014c0a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180014c10  jnz     short loc_180014C5B
0x180014c12  lea     rcx, ModuleName; "ntdll.dll"
0x180014c19  call    cs:__imp_GetModuleHandleW
0x180014c1f  test    rax, rax
0x180014c22  jz      short loc_180014C3D
0x180014c24  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180014c2b  mov     rcx, rax; hModule
0x180014c2e  call    cs:__imp_GetProcAddress
0x180014c34  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180014c3b  jmp     short loc_180014C44
0x180014c3d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014c44  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180014c4b  test    rax, rax
0x180014c4e  jz      short loc_180014C5B
0x180014c50  mov     rdx, rbx
0x180014c53  mov     rcx, rsi
0x180014c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c5b  mov     rax, rbx
0x180014c5e  mov     rbx, [rsp+28h+arg_0]
0x180014c63  mov     rsi, [rsp+28h+arg_8]
0x180014c68  add     rsp, 20h
0x180014c6c  pop     rdi
0x180014c6d  retn
```
