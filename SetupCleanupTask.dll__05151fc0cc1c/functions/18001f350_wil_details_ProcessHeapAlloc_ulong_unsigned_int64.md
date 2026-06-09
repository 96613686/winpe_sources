# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001f350`
- end: `0x18001f3ee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019770`
- `0x180019b14`
- `0x1800223ec`
- `0x18002487c`

## callees

- `0x18001f350`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f399`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f399`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f3ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f3ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f375`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f375`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f364`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f364`

## string_xrefs

- `0x18001f392`: `ntdll.dll`

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
0x18001f350  mov     [rsp+arg_0], rbx
0x18001f355  mov     [rsp+arg_8], rsi
0x18001f35a  push    rdi
0x18001f35b  sub     rsp, 20h
0x18001f35f  mov     rbx, rdx
0x18001f362  mov     edi, ecx
0x18001f364  call    cs:__imp_GetProcessHeap
0x18001f36a  mov     r8, rbx; dwBytes
0x18001f36d  mov     edx, edi; dwFlags
0x18001f36f  mov     rcx, rax; hHeap
0x18001f372  mov     rsi, rax
0x18001f375  call    cs:__imp_HeapAlloc
0x18001f37b  mov     rbx, rax
0x18001f37e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001f385  test    rax, rax
0x18001f388  jnz     short loc_18001F3D0
0x18001f38a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001f390  jnz     short loc_18001F3DB
0x18001f392  lea     rcx, LibFileName; "ntdll.dll"
0x18001f399  call    cs:__imp_GetModuleHandleW
0x18001f39f  test    rax, rax
0x18001f3a2  jz      short loc_18001F3BD
0x18001f3a4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001f3ab  mov     rcx, rax; hModule
0x18001f3ae  call    cs:__imp_GetProcAddress
0x18001f3b4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001f3bb  jmp     short loc_18001F3C4
0x18001f3bd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001f3c4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001f3cb  test    rax, rax
0x18001f3ce  jz      short loc_18001F3DB
0x18001f3d0  mov     rdx, rbx
0x18001f3d3  mov     rcx, rsi
0x18001f3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3db  mov     rsi, [rsp+28h+arg_8]
0x18001f3e0  mov     rax, rbx
0x18001f3e3  mov     rbx, [rsp+28h+arg_0]
0x18001f3e8  add     rsp, 20h
0x18001f3ec  pop     rdi
0x18001f3ed  retn
```
