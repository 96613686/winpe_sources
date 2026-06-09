# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400058d4`
- end: `0x140005972`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001988`
- `0x140005484`
- `0x1400055a8`
- `0x140006254`
- `0x1400064b8`

## callees

- `0x1400058d4`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005932`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005932`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000591d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000591d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400058f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400058f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400058e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400058e8`

## string_xrefs

- `0x140005916`: `ntdll.dll`

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
0x1400058d4  mov     [rsp+arg_0], rbx
0x1400058d9  mov     [rsp+arg_8], rsi
0x1400058de  push    rdi
0x1400058df  sub     rsp, 20h
0x1400058e3  mov     rbx, rdx
0x1400058e6  mov     edi, ecx
0x1400058e8  call    cs:__imp_GetProcessHeap
0x1400058ee  mov     r8, rbx; dwBytes
0x1400058f1  mov     edx, edi; dwFlags
0x1400058f3  mov     rcx, rax; hHeap
0x1400058f6  mov     rsi, rax
0x1400058f9  call    cs:__imp_HeapAlloc
0x1400058ff  mov     rbx, rax
0x140005902  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005909  test    rax, rax
0x14000590c  jnz     short loc_140005954
0x14000590e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005914  jnz     short loc_14000595F
0x140005916  lea     rcx, ModuleName; "ntdll.dll"
0x14000591d  call    cs:__imp_GetModuleHandleW
0x140005923  test    rax, rax
0x140005926  jz      short loc_140005941
0x140005928  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x14000592f  mov     rcx, rax; hModule
0x140005932  call    cs:__imp_GetProcAddress
0x140005938  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000593f  jmp     short loc_140005948
0x140005941  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005948  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000594f  test    rax, rax
0x140005952  jz      short loc_14000595F
0x140005954  mov     rdx, rbx
0x140005957  mov     rcx, rsi
0x14000595a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000595f  mov     rsi, [rsp+28h+arg_8]
0x140005964  mov     rax, rbx
0x140005967  mov     rbx, [rsp+28h+arg_0]
0x14000596c  add     rsp, 20h
0x140005970  pop     rdi
0x140005971  retn
```
