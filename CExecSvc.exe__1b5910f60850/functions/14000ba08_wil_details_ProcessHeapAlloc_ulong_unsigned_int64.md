# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000ba08`
- end: `0x14000baa6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008a58`
- `0x140009570`
- `0x140009b98`
- `0x14000c4cc`
- `0x14000fe64`
- `0x140012c34`

## callees

- `0x14000ba08`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ba66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ba66`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ba51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ba51`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000ba2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000ba2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ba1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ba1c`

## string_xrefs

- `0x14000ba4a`: `ntdll.dll`

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
0x14000ba08  mov     [rsp+arg_0], rbx
0x14000ba0d  mov     [rsp+arg_8], rsi
0x14000ba12  push    rdi
0x14000ba13  sub     rsp, 20h
0x14000ba17  mov     rbx, rdx
0x14000ba1a  mov     edi, ecx
0x14000ba1c  call    cs:__imp_GetProcessHeap
0x14000ba22  mov     rsi, rax
0x14000ba25  mov     r8, rbx; dwBytes
0x14000ba28  mov     edx, edi; dwFlags
0x14000ba2a  mov     rcx, rax; hHeap
0x14000ba2d  call    cs:__imp_HeapAlloc
0x14000ba33  mov     rbx, rax
0x14000ba36  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000ba3d  test    rax, rax
0x14000ba40  jnz     short loc_14000BA88
0x14000ba42  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000ba48  jnz     short loc_14000BA93
0x14000ba4a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000ba51  call    cs:__imp_GetModuleHandleW
0x14000ba57  test    rax, rax
0x14000ba5a  jz      short loc_14000BA75
0x14000ba5c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000ba63  mov     rcx, rax; hModule
0x14000ba66  call    cs:__imp_GetProcAddress
0x14000ba6c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000ba73  jmp     short loc_14000BA7C
0x14000ba75  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000ba7c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000ba83  test    rax, rax
0x14000ba86  jz      short loc_14000BA93
0x14000ba88  mov     rdx, rbx
0x14000ba8b  mov     rcx, rsi
0x14000ba8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba93  mov     rax, rbx
0x14000ba96  mov     rbx, [rsp+28h+arg_0]
0x14000ba9b  mov     rsi, [rsp+28h+arg_8]
0x14000baa0  add     rsp, 20h
0x14000baa4  pop     rdi
0x14000baa5  retn
```
