# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800263fc`
- end: `0x1800264bd`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `193`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025ee8`
- `0x180026038`
- `0x18002732c`
- `0x180027800`
- `0x18002b1a4`

## callees

- `0x1800263fc`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002645b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002645b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026476`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026476`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026431`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026431`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002641a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002641a`

## string_xrefs

- `0x180026454`: `ntdll.dll`

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
0x1800263fc  push    rdi
0x1800263fe  sub     rsp, 30h
0x180026402  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002640b  mov     [rsp+38h+arg_0], rbx
0x180026410  mov     [rsp+38h+arg_8], rsi
0x180026415  mov     rbx, rdx
0x180026418  mov     edi, ecx
0x18002641a  call    cs:__imp_GetProcessHeap
0x180026421  nop     dword ptr [rax+rax+00h]
0x180026426  mov     rsi, rax
0x180026429  mov     r8, rbx; dwBytes
0x18002642c  mov     edx, edi; dwFlags
0x18002642e  mov     rcx, rax; hHeap
0x180026431  call    cs:__imp_HeapAlloc
0x180026438  nop     dword ptr [rax+rax+00h]
0x18002643d  mov     rbx, rax
0x180026440  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180026447  test    rax, rax
0x18002644a  jnz     short loc_18002649E
0x18002644c  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180026452  jnz     short loc_1800264A9
0x180026454  lea     rcx, LibFileName; "ntdll.dll"
0x18002645b  call    cs:__imp_GetModuleHandleW
0x180026462  nop     dword ptr [rax+rax+00h]
0x180026467  test    rax, rax
0x18002646a  jz      short loc_18002648B
0x18002646c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180026473  mov     rcx, rax; hModule
0x180026476  call    cs:__imp_GetProcAddress
0x18002647d  nop     dword ptr [rax+rax+00h]
0x180026482  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180026489  jmp     short loc_180026492
0x18002648b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180026492  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180026499  test    rax, rax
0x18002649c  jz      short loc_1800264A9
0x18002649e  mov     rdx, rbx
0x1800264a1  mov     rcx, rsi
0x1800264a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264a9  mov     rax, rbx
0x1800264ac  mov     rbx, [rsp+38h+arg_0]
0x1800264b1  mov     rsi, [rsp+38h+arg_8]
0x1800264b6  add     rsp, 30h
0x1800264ba  pop     rdi
0x1800264bb  retn
```
