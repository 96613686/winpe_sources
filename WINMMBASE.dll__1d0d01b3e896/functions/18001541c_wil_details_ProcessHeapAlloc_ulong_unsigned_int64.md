# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001541c`
- end: `0x1800154ba`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015214`
- `0x180015afc`
- `0x180015e94`
- `0x1800166ec`

## callees

- `0x18001541c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015430`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015430`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015441`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015441`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015465`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015465`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001547a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001547a`

## string_xrefs

- `0x18001545e`: `ntdll.dll`

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
0x18001541c  mov     [rsp+arg_0], rbx
0x180015421  mov     [rsp+arg_8], rsi
0x180015426  push    rdi
0x180015427  sub     rsp, 20h
0x18001542b  mov     rbx, rdx
0x18001542e  mov     edi, ecx
0x180015430  call    cs:__imp_GetProcessHeap
0x180015436  mov     rsi, rax
0x180015439  mov     r8, rbx; dwBytes
0x18001543c  mov     edx, edi; dwFlags
0x18001543e  mov     rcx, rax; hHeap
0x180015441  call    cs:__imp_HeapAlloc
0x180015447  mov     rbx, rax
0x18001544a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180015451  test    rax, rax
0x180015454  jnz     short loc_18001549C
0x180015456  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001545c  jnz     short loc_1800154A7
0x18001545e  lea     rcx, ModuleName; "ntdll.dll"
0x180015465  call    cs:__imp_GetModuleHandleW
0x18001546b  test    rax, rax
0x18001546e  jz      short loc_180015489
0x180015470  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180015477  mov     rcx, rax; hModule
0x18001547a  call    cs:__imp_GetProcAddress
0x180015480  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180015487  jmp     short loc_180015490
0x180015489  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180015490  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180015497  test    rax, rax
0x18001549a  jz      short loc_1800154A7
0x18001549c  mov     rdx, rbx
0x18001549f  mov     rcx, rsi
0x1800154a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154a7  mov     rax, rbx
0x1800154aa  mov     rbx, [rsp+28h+arg_0]
0x1800154af  mov     rsi, [rsp+28h+arg_8]
0x1800154b4  add     rsp, 20h
0x1800154b8  pop     rdi
0x1800154b9  retn
```
