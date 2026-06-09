# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000627c`
- end: `0x18000631a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800046d8`
- `0x1800050a0`
- `0x180006968`

## callees

- `0x18000627c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006290`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006290`

## string_xrefs

- `0x1800062be`: `ntdll.dll`

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
0x18000627c  mov     [rsp+arg_0], rbx
0x180006281  mov     [rsp+arg_8], rsi
0x180006286  push    rdi
0x180006287  sub     rsp, 20h
0x18000628b  mov     rbx, rdx
0x18000628e  mov     edi, ecx
0x180006290  call    cs:__imp_GetProcessHeap
0x180006296  mov     rsi, rax
0x180006299  mov     r8, rbx; dwBytes
0x18000629c  mov     edx, edi; dwFlags
0x18000629e  mov     rcx, rax; hHeap
0x1800062a1  call    cs:__imp_HeapAlloc
0x1800062a7  mov     rbx, rax
0x1800062aa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800062b1  test    rax, rax
0x1800062b4  jnz     short loc_1800062FC
0x1800062b6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800062bc  jnz     short loc_180006307
0x1800062be  lea     rcx, ModuleName; "ntdll.dll"
0x1800062c5  call    cs:__imp_GetModuleHandleW
0x1800062cb  test    rax, rax
0x1800062ce  jz      short loc_1800062E9
0x1800062d0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800062d7  mov     rcx, rax; hModule
0x1800062da  call    cs:__imp_GetProcAddress
0x1800062e0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800062e7  jmp     short loc_1800062F0
0x1800062e9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800062f0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800062f7  test    rax, rax
0x1800062fa  jz      short loc_180006307
0x1800062fc  mov     rdx, rbx
0x1800062ff  mov     rcx, rsi
0x180006302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006307  mov     rax, rbx
0x18000630a  mov     rbx, [rsp+28h+arg_0]
0x18000630f  mov     rsi, [rsp+28h+arg_8]
0x180006314  add     rsp, 20h
0x180006318  pop     rdi
0x180006319  retn
```
