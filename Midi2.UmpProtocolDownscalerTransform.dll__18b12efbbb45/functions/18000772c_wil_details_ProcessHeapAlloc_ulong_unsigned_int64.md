# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000772c`
- end: `0x1800077ca`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004b58`
- `0x180006220`
- `0x1800089b0`

## callees

- `0x18000772c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007775`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007775`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000778a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000778a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007740`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007740`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007751`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007751`

## string_xrefs

- `0x18000776e`: `ntdll.dll`

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
0x18000772c  mov     [rsp+arg_0], rbx
0x180007731  mov     [rsp+arg_8], rsi
0x180007736  push    rdi
0x180007737  sub     rsp, 20h
0x18000773b  mov     rbx, rdx
0x18000773e  mov     edi, ecx
0x180007740  call    cs:__imp_GetProcessHeap
0x180007746  mov     rsi, rax
0x180007749  mov     r8, rbx; dwBytes
0x18000774c  mov     edx, edi; dwFlags
0x18000774e  mov     rcx, rax; hHeap
0x180007751  call    cs:__imp_HeapAlloc
0x180007757  mov     rbx, rax
0x18000775a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007761  test    rax, rax
0x180007764  jnz     short loc_1800077AC
0x180007766  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000776c  jnz     short loc_1800077B7
0x18000776e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180007775  call    cs:__imp_GetModuleHandleW
0x18000777b  test    rax, rax
0x18000777e  jz      short loc_180007799
0x180007780  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007787  mov     rcx, rax; hModule
0x18000778a  call    cs:__imp_GetProcAddress
0x180007790  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007797  jmp     short loc_1800077A0
0x180007799  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800077a0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800077a7  test    rax, rax
0x1800077aa  jz      short loc_1800077B7
0x1800077ac  mov     rdx, rbx
0x1800077af  mov     rcx, rsi
0x1800077b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b7  mov     rax, rbx
0x1800077ba  mov     rbx, [rsp+28h+arg_0]
0x1800077bf  mov     rsi, [rsp+28h+arg_8]
0x1800077c4  add     rsp, 20h
0x1800077c8  pop     rdi
0x1800077c9  retn
```
