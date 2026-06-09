# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180024860`
- end: `0x1800248fe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012fc0`
- `0x180017de0`
- `0x1800236fc`
- `0x18002382c`
- `0x180026648`
- `0x180026ad8`

## callees

- `0x180024860`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800248a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800248a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800248be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800248be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024874`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024874`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024885`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024885`

## string_xrefs

- `0x1800248a2`: `ntdll.dll`

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
0x180024860  mov     [rsp+arg_0], rbx
0x180024865  mov     [rsp+arg_8], rsi
0x18002486a  push    rdi
0x18002486b  sub     rsp, 20h
0x18002486f  mov     rbx, rdx
0x180024872  mov     edi, ecx
0x180024874  call    cs:__imp_GetProcessHeap
0x18002487a  mov     rsi, rax
0x18002487d  mov     r8, rbx; dwBytes
0x180024880  mov     edx, edi; dwFlags
0x180024882  mov     rcx, rax; hHeap
0x180024885  call    cs:__imp_HeapAlloc
0x18002488b  mov     rbx, rax
0x18002488e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180024895  test    rax, rax
0x180024898  jnz     short loc_1800248E0
0x18002489a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800248a0  jnz     short loc_1800248EB
0x1800248a2  lea     rcx, ModuleName; "ntdll.dll"
0x1800248a9  call    cs:__imp_GetModuleHandleW
0x1800248af  test    rax, rax
0x1800248b2  jz      short loc_1800248CD
0x1800248b4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800248bb  mov     rcx, rax; hModule
0x1800248be  call    cs:__imp_GetProcAddress
0x1800248c4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800248cb  jmp     short loc_1800248D4
0x1800248cd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800248d4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800248db  test    rax, rax
0x1800248de  jz      short loc_1800248EB
0x1800248e0  mov     rdx, rbx
0x1800248e3  mov     rcx, rsi
0x1800248e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248eb  mov     rax, rbx
0x1800248ee  mov     rbx, [rsp+28h+arg_0]
0x1800248f3  mov     rsi, [rsp+28h+arg_8]
0x1800248f8  add     rsp, 20h
0x1800248fc  pop     rdi
0x1800248fd  retn
```
