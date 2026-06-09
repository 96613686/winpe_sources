# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000753c`
- end: `0x1800075f3`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005eb4`
- `0x18000685c`
- `0x1800080cc`
- `0x180015c7c`
- `0x180021904`

## callees

- `0x18000753c`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007591`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007591`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800075ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800075ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007567`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007567`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007550`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007550`

## string_xrefs

- `0x18000758a`: `ntdll.dll`

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
0x18000753c  mov     [rsp+arg_0], rbx
0x180007541  mov     [rsp+arg_8], rsi
0x180007546  push    rdi
0x180007547  sub     rsp, 20h
0x18000754b  mov     rbx, rdx
0x18000754e  mov     edi, ecx
0x180007550  call    cs:__imp_GetProcessHeap
0x180007557  nop     dword ptr [rax+rax+00h]
0x18000755c  mov     rsi, rax
0x18000755f  mov     r8, rbx; dwBytes
0x180007562  mov     edx, edi; dwFlags
0x180007564  mov     rcx, rax; hHeap
0x180007567  call    cs:__imp_HeapAlloc
0x18000756e  nop     dword ptr [rax+rax+00h]
0x180007573  mov     rbx, rax
0x180007576  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000757d  test    rax, rax
0x180007580  jnz     short loc_1800075D4
0x180007582  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007588  jnz     short loc_1800075DF
0x18000758a  lea     rcx, ModuleName; "ntdll.dll"
0x180007591  call    cs:__imp_GetModuleHandleW
0x180007598  nop     dword ptr [rax+rax+00h]
0x18000759d  test    rax, rax
0x1800075a0  jz      short loc_1800075C1
0x1800075a2  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800075a9  mov     rcx, rax; hModule
0x1800075ac  call    cs:__imp_GetProcAddress
0x1800075b3  nop     dword ptr [rax+rax+00h]
0x1800075b8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800075bf  jmp     short loc_1800075C8
0x1800075c1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800075c8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800075cf  test    rax, rax
0x1800075d2  jz      short loc_1800075DF
0x1800075d4  mov     rdx, rbx
0x1800075d7  mov     rcx, rsi
0x1800075da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075df  mov     rax, rbx
0x1800075e2  mov     rbx, [rsp+28h+arg_0]
0x1800075e7  mov     rsi, [rsp+28h+arg_8]
0x1800075ec  add     rsp, 20h
0x1800075f0  pop     rdi
0x1800075f1  retn
```
