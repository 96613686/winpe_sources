# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800187f8`
- end: `0x180018896`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018750`
- `0x180023afc`
- `0x180023c2c`
- `0x1800247f0`
- `0x180024a18`

## callees

- `0x1800187f8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018841`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018841`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018887`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018887`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001881d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001881d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001880c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001880c`

## string_xrefs

- `0x18001883a`: `ntdll.dll`

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
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) != 0
      ? (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress)
      : (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation),
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
0x1800187f8  mov     [rsp+arg_0], rbx
0x1800187fd  mov     [rsp+arg_8], rsi
0x180018802  push    rdi
0x180018803  sub     rsp, 20h
0x180018807  mov     rbx, rdx
0x18001880a  mov     edi, ecx
0x18001880c  call    cs:__imp_GetProcessHeap
0x180018812  mov     rsi, rax
0x180018815  mov     r8, rbx; dwBytes
0x180018818  mov     edx, edi; dwFlags
0x18001881a  mov     rcx, rax; hHeap
0x18001881d  call    cs:__imp_HeapAlloc
0x180018823  mov     rbx, rax
0x180018826  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001882d  test    rax, rax
0x180018830  jnz     short loc_18001885F
0x180018832  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180018838  jnz     short loc_18001886A
0x18001883a  lea     rcx, ModuleName; "ntdll.dll"
0x180018841  call    cs:__imp_GetModuleHandleW
0x180018847  test    rax, rax
0x18001884a  jnz     short loc_18001887D
0x18001884c  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180018853  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001885a  test    rax, rax
0x18001885d  jz      short loc_18001886A
0x18001885f  mov     rdx, rbx
0x180018862  mov     rcx, rsi
0x180018865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001886a  mov     rax, rbx
0x18001886d  mov     rbx, [rsp+28h+arg_0]
0x180018872  mov     rsi, [rsp+28h+arg_8]
0x180018877  add     rsp, 20h
0x18001887b  pop     rdi
0x18001887c  retn
0x18001887d  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180018884  mov     rcx, rax; hModule
0x180018887  call    cs:__imp_GetProcAddress
0x18001888d  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180018894  jmp     short loc_180018853
```
