# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800070ec`
- end: `0x18000718a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003eb0`
- `0x180004254`
- `0x18000927c`
- `0x18000bf6c`

## callees

- `0x1800070ec`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000714a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000714a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007135`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007135`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007100`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007111`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007111`

## string_xrefs

- `0x18000712e`: `ntdll.dll`

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
0x1800070ec  mov     [rsp+arg_0], rbx
0x1800070f1  mov     [rsp+arg_8], rsi
0x1800070f6  push    rdi
0x1800070f7  sub     rsp, 20h
0x1800070fb  mov     rbx, rdx
0x1800070fe  mov     edi, ecx
0x180007100  call    cs:__imp_GetProcessHeap
0x180007106  mov     rsi, rax
0x180007109  mov     r8, rbx; dwBytes
0x18000710c  mov     edx, edi; dwFlags
0x18000710e  mov     rcx, rax; hHeap
0x180007111  call    cs:__imp_HeapAlloc
0x180007117  mov     rbx, rax
0x18000711a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007121  test    rax, rax
0x180007124  jnz     short loc_18000716C
0x180007126  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000712c  jnz     short loc_180007177
0x18000712e  lea     rcx, ModuleName; "ntdll.dll"
0x180007135  call    cs:__imp_GetModuleHandleW
0x18000713b  test    rax, rax
0x18000713e  jz      short loc_180007159
0x180007140  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007147  mov     rcx, rax; hModule
0x18000714a  call    cs:__imp_GetProcAddress
0x180007150  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007157  jmp     short loc_180007160
0x180007159  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007160  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007167  test    rax, rax
0x18000716a  jz      short loc_180007177
0x18000716c  mov     rdx, rbx
0x18000716f  mov     rcx, rsi
0x180007172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007177  mov     rax, rbx
0x18000717a  mov     rbx, [rsp+28h+arg_0]
0x18000717f  mov     rsi, [rsp+28h+arg_8]
0x180007184  add     rsp, 20h
0x180007188  pop     rdi
0x180007189  retn
```
