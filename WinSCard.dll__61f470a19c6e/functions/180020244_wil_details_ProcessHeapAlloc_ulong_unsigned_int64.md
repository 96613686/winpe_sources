# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180020244`
- end: `0x1800202e2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001825c`
- `0x18001fb68`
- `0x18001fcfc`
- `0x180021340`
- `0x1800217c4`

## callees

- `0x180020244`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800202a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800202a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002028d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002028d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020258`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020258`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020269`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020269`

## string_xrefs

- `0x180020286`: `ntdll.dll`

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
0x180020244  mov     [rsp+arg_0], rbx
0x180020249  mov     [rsp+arg_8], rsi
0x18002024e  push    rdi
0x18002024f  sub     rsp, 20h
0x180020253  mov     rbx, rdx
0x180020256  mov     edi, ecx
0x180020258  call    cs:__imp_GetProcessHeap
0x18002025e  mov     rsi, rax
0x180020261  mov     r8, rbx; dwBytes
0x180020264  mov     edx, edi; dwFlags
0x180020266  mov     rcx, rax; hHeap
0x180020269  call    cs:__imp_HeapAlloc
0x18002026f  mov     rbx, rax
0x180020272  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180020279  test    rax, rax
0x18002027c  jnz     short loc_1800202C4
0x18002027e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180020284  jnz     short loc_1800202CF
0x180020286  lea     rcx, ModuleName; "ntdll.dll"
0x18002028d  call    cs:__imp_GetModuleHandleW
0x180020293  test    rax, rax
0x180020296  jz      short loc_1800202B1
0x180020298  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18002029f  mov     rcx, rax; hModule
0x1800202a2  call    cs:__imp_GetProcAddress
0x1800202a8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800202af  jmp     short loc_1800202B8
0x1800202b1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800202b8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800202bf  test    rax, rax
0x1800202c2  jz      short loc_1800202CF
0x1800202c4  mov     rdx, rbx
0x1800202c7  mov     rcx, rsi
0x1800202ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202cf  mov     rax, rbx
0x1800202d2  mov     rbx, [rsp+28h+arg_0]
0x1800202d7  mov     rsi, [rsp+28h+arg_8]
0x1800202dc  add     rsp, 20h
0x1800202e0  pop     rdi
0x1800202e1  retn
```
