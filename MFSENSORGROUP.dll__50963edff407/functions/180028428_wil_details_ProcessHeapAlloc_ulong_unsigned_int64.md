# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180028428`
- end: `0x1800284c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180028380`
- `0x180046ff8`
- `0x1800472c4`
- `0x18004743c`

## callees

- `0x180028428`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028486`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028486`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028471`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028471`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002844d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002844d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002843c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002843c`

## string_xrefs

- `0x18002846a`: `ntdll.dll`

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
0x180028428  mov     [rsp+arg_0], rbx
0x18002842d  mov     [rsp+arg_8], rsi
0x180028432  push    rdi
0x180028433  sub     rsp, 20h
0x180028437  mov     rbx, rdx
0x18002843a  mov     edi, ecx
0x18002843c  call    cs:__imp_GetProcessHeap
0x180028442  mov     r8, rbx; dwBytes
0x180028445  mov     edx, edi; dwFlags
0x180028447  mov     rcx, rax; hHeap
0x18002844a  mov     rsi, rax
0x18002844d  call    cs:__imp_HeapAlloc
0x180028453  mov     rbx, rax
0x180028456  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002845d  test    rax, rax
0x180028460  jnz     short loc_18002849F
0x180028462  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180028468  jnz     short loc_1800284AA
0x18002846a  lea     rcx, ModuleName; "ntdll.dll"
0x180028471  call    cs:__imp_GetModuleHandleW
0x180028477  test    rax, rax
0x18002847a  jz      short loc_1800284BD
0x18002847c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180028483  mov     rcx, rax; hModule
0x180028486  call    cs:__imp_GetProcAddress
0x18002848c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180028493  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002849a  test    rax, rax
0x18002849d  jz      short loc_1800284AA
0x18002849f  mov     rdx, rbx
0x1800284a2  mov     rcx, rsi
0x1800284a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284aa  mov     rsi, [rsp+28h+arg_8]
0x1800284af  mov     rax, rbx
0x1800284b2  mov     rbx, [rsp+28h+arg_0]
0x1800284b7  add     rsp, 20h
0x1800284bb  pop     rdi
0x1800284bc  retn
0x1800284bd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800284c4  jmp     short loc_180028493
```
