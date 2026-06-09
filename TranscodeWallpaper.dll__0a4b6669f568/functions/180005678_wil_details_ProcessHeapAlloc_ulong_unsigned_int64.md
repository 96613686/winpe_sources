# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005678`
- end: `0x180005716`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003e88`
- `0x180004620`
- `0x180005bc4`
- `0x180007c8c`
- `0x18000aa84`

## callees

- `0x180005678`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800056d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800056d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800056c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800056c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000568c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000568c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000569d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000569d`

## string_xrefs

- `0x1800056ba`: `ntdll.dll`

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
0x180005678  mov     [rsp+arg_0], rbx
0x18000567d  mov     [rsp+arg_8], rsi
0x180005682  push    rdi
0x180005683  sub     rsp, 20h
0x180005687  mov     rbx, rdx
0x18000568a  mov     edi, ecx
0x18000568c  call    cs:__imp_GetProcessHeap
0x180005692  mov     rsi, rax
0x180005695  mov     r8, rbx; dwBytes
0x180005698  mov     edx, edi; dwFlags
0x18000569a  mov     rcx, rax; hHeap
0x18000569d  call    cs:__imp_HeapAlloc
0x1800056a3  mov     rbx, rax
0x1800056a6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800056ad  test    rax, rax
0x1800056b0  jnz     short loc_1800056F8
0x1800056b2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800056b8  jnz     short loc_180005703
0x1800056ba  lea     rcx, ModuleName; "ntdll.dll"
0x1800056c1  call    cs:__imp_GetModuleHandleW
0x1800056c7  test    rax, rax
0x1800056ca  jz      short loc_1800056E5
0x1800056cc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800056d3  mov     rcx, rax; hModule
0x1800056d6  call    cs:__imp_GetProcAddress
0x1800056dc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800056e3  jmp     short loc_1800056EC
0x1800056e5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800056ec  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800056f3  test    rax, rax
0x1800056f6  jz      short loc_180005703
0x1800056f8  mov     rdx, rbx
0x1800056fb  mov     rcx, rsi
0x1800056fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005703  mov     rax, rbx
0x180005706  mov     rbx, [rsp+28h+arg_0]
0x18000570b  mov     rsi, [rsp+28h+arg_8]
0x180005710  add     rsp, 20h
0x180005714  pop     rdi
0x180005715  retn
```
