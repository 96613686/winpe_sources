# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800070f4`
- end: `0x18000719c`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004df8`
- `0x18000519c`
- `0x180005e50`
- `0x1800087e0`
- `0x18000a05c`

## callees

- `0x1800070f4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180007147`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180007147`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000715c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000715c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007112`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007112`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007123`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007123`

## string_xrefs

- `0x180007140`: `ntdll.dll`

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
0x1800070f4  push    rdi
0x1800070f6  sub     rsp, 30h
0x1800070fa  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180007103  mov     [rsp+38h+arg_0], rbx
0x180007108  mov     [rsp+38h+arg_8], rsi
0x18000710d  mov     rbx, rdx
0x180007110  mov     edi, ecx
0x180007112  call    cs:__imp_GetProcessHeap
0x180007118  mov     rsi, rax
0x18000711b  mov     r8, rbx; dwBytes
0x18000711e  mov     edx, edi; dwFlags
0x180007120  mov     rcx, rax; hHeap
0x180007123  call    cs:__imp_HeapAlloc
0x180007129  mov     rbx, rax
0x18000712c  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007133  test    rax, rax
0x180007136  jnz     short loc_18000717E
0x180007138  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000713e  jnz     short loc_180007189
0x180007140  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180007147  call    cs:__imp_GetModuleHandleW
0x18000714d  test    rax, rax
0x180007150  jz      short loc_18000716B
0x180007152  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007159  mov     rcx, rax; hModule
0x18000715c  call    cs:__imp_GetProcAddress
0x180007162  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007169  jmp     short loc_180007172
0x18000716b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007172  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007179  test    rax, rax
0x18000717c  jz      short loc_180007189
0x18000717e  mov     rdx, rbx
0x180007181  mov     rcx, rsi
0x180007184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007189  mov     rax, rbx
0x18000718c  mov     rbx, [rsp+38h+arg_0]
0x180007191  mov     rsi, [rsp+38h+arg_8]
0x180007196  add     rsp, 30h
0x18000719a  pop     rdi
0x18000719b  retn
```
