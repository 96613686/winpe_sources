# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004608`
- end: `0x1800046a6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002eb8`
- `0x1800035b0`
- `0x180004970`

## callees

- `0x180004608`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004666`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004666`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004651`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004651`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000462d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000462d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000461c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000461c`

## string_xrefs

- `0x18000464a`: `ntdll.dll`

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
0x180004608  mov     [rsp+arg_0], rbx
0x18000460d  mov     [rsp+arg_8], rsi
0x180004612  push    rdi
0x180004613  sub     rsp, 20h
0x180004617  mov     rbx, rdx
0x18000461a  mov     edi, ecx
0x18000461c  call    cs:__imp_GetProcessHeap
0x180004622  mov     rsi, rax
0x180004625  mov     r8, rbx; dwBytes
0x180004628  mov     edx, edi; dwFlags
0x18000462a  mov     rcx, rax; hHeap
0x18000462d  call    cs:__imp_HeapAlloc
0x180004633  mov     rbx, rax
0x180004636  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000463d  test    rax, rax
0x180004640  jnz     short loc_180004688
0x180004642  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004648  jnz     short loc_180004693
0x18000464a  lea     rcx, ModuleName; "ntdll.dll"
0x180004651  call    cs:__imp_GetModuleHandleW
0x180004657  test    rax, rax
0x18000465a  jz      short loc_180004675
0x18000465c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004663  mov     rcx, rax; hModule
0x180004666  call    cs:__imp_GetProcAddress
0x18000466c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004673  jmp     short loc_18000467C
0x180004675  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000467c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004683  test    rax, rax
0x180004686  jz      short loc_180004693
0x180004688  mov     rdx, rbx
0x18000468b  mov     rcx, rsi
0x18000468e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004693  mov     rax, rbx
0x180004696  mov     rbx, [rsp+28h+arg_0]
0x18000469b  mov     rsi, [rsp+28h+arg_8]
0x1800046a0  add     rsp, 20h
0x1800046a4  pop     rdi
0x1800046a5  retn
```
