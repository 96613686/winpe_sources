# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005894`
- end: `0x18000594b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005508`
- `0x1800060c8`

## callees

- `0x180005894`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005904`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005904`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800058bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800058bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058a8`

## string_xrefs

- `0x1800058e2`: `ntdll.dll`

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
0x180005894  mov     [rsp+arg_0], rbx
0x180005899  mov     [rsp+arg_8], rsi
0x18000589e  push    rdi
0x18000589f  sub     rsp, 20h
0x1800058a3  mov     rbx, rdx
0x1800058a6  mov     edi, ecx
0x1800058a8  call    cs:__imp_GetProcessHeap
0x1800058af  nop     dword ptr [rax+rax+00h]
0x1800058b4  mov     rsi, rax
0x1800058b7  mov     r8, rbx; dwBytes
0x1800058ba  mov     edx, edi; dwFlags
0x1800058bc  mov     rcx, rax; hHeap
0x1800058bf  call    cs:__imp_HeapAlloc
0x1800058c6  nop     dword ptr [rax+rax+00h]
0x1800058cb  mov     rbx, rax
0x1800058ce  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800058d5  test    rax, rax
0x1800058d8  jnz     short loc_18000592C
0x1800058da  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800058e0  jnz     short loc_180005937
0x1800058e2  lea     rcx, ModuleName; "ntdll.dll"
0x1800058e9  call    cs:__imp_GetModuleHandleW
0x1800058f0  nop     dword ptr [rax+rax+00h]
0x1800058f5  test    rax, rax
0x1800058f8  jz      short loc_180005919
0x1800058fa  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005901  mov     rcx, rax; hModule
0x180005904  call    cs:__imp_GetProcAddress
0x18000590b  nop     dword ptr [rax+rax+00h]
0x180005910  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005917  jmp     short loc_180005920
0x180005919  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005920  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005927  test    rax, rax
0x18000592a  jz      short loc_180005937
0x18000592c  mov     rdx, rbx
0x18000592f  mov     rcx, rsi
0x180005932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005937  mov     rax, rbx
0x18000593a  mov     rbx, [rsp+28h+arg_0]
0x18000593f  mov     rsi, [rsp+28h+arg_8]
0x180005944  add     rsp, 20h
0x180005948  pop     rdi
0x180005949  retn
```
