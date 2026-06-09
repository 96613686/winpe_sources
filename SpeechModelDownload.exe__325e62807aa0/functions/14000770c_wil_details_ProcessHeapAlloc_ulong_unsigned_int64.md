# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000770c`
- end: `0x1400077aa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005150`
- `0x140006210`
- `0x1400068f0`
- `0x140007eb4`
- `0x14000b964`
- `0x140013290`

## callees

- `0x14000770c`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007755`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007755`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000776a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000776a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007731`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007731`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007720`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007720`

## string_xrefs

- `0x14000774e`: `ntdll.dll`

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
0x14000770c  mov     [rsp+arg_0], rbx
0x140007711  mov     [rsp+arg_8], rsi
0x140007716  push    rdi
0x140007717  sub     rsp, 20h
0x14000771b  mov     rbx, rdx
0x14000771e  mov     edi, ecx
0x140007720  call    cs:__imp_GetProcessHeap
0x140007726  mov     rsi, rax
0x140007729  mov     r8, rbx; dwBytes
0x14000772c  mov     edx, edi; dwFlags
0x14000772e  mov     rcx, rax; hHeap
0x140007731  call    cs:__imp_HeapAlloc
0x140007737  mov     rbx, rax
0x14000773a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140007741  test    rax, rax
0x140007744  jnz     short loc_14000778C
0x140007746  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000774c  jnz     short loc_140007797
0x14000774e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140007755  call    cs:__imp_GetModuleHandleW
0x14000775b  test    rax, rax
0x14000775e  jz      short loc_140007779
0x140007760  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140007767  mov     rcx, rax; hModule
0x14000776a  call    cs:__imp_GetProcAddress
0x140007770  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140007777  jmp     short loc_140007780
0x140007779  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140007780  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140007787  test    rax, rax
0x14000778a  jz      short loc_140007797
0x14000778c  mov     rdx, rbx
0x14000778f  mov     rcx, rsi
0x140007792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007797  mov     rax, rbx
0x14000779a  mov     rbx, [rsp+28h+arg_0]
0x14000779f  mov     rsi, [rsp+28h+arg_8]
0x1400077a4  add     rsp, 20h
0x1400077a8  pop     rdi
0x1400077a9  retn
```
