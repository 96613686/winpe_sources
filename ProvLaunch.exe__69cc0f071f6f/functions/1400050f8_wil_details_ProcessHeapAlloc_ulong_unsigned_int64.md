# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400050f8`
- end: `0x140005196`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003830`
- `0x140005a14`

## callees

- `0x1400050f8`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005141`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005141`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005156`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005156`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000511d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000511d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000510c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000510c`

## string_xrefs

- `0x14000513a`: `ntdll.dll`

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
0x1400050f8  mov     [rsp+arg_0], rbx
0x1400050fd  mov     [rsp+arg_8], rsi
0x140005102  push    rdi
0x140005103  sub     rsp, 20h
0x140005107  mov     rbx, rdx
0x14000510a  mov     edi, ecx
0x14000510c  call    cs:__imp_GetProcessHeap
0x140005112  mov     rsi, rax
0x140005115  mov     r8, rbx; dwBytes
0x140005118  mov     edx, edi; dwFlags
0x14000511a  mov     rcx, rax; hHeap
0x14000511d  call    cs:__imp_HeapAlloc
0x140005123  mov     rbx, rax
0x140005126  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000512d  test    rax, rax
0x140005130  jnz     short loc_140005178
0x140005132  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005138  jnz     short loc_140005183
0x14000513a  lea     rcx, ModuleName; "ntdll.dll"
0x140005141  call    cs:__imp_GetModuleHandleW
0x140005147  test    rax, rax
0x14000514a  jz      short loc_140005165
0x14000514c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140005153  mov     rcx, rax; hModule
0x140005156  call    cs:__imp_GetProcAddress
0x14000515c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005163  jmp     short loc_14000516C
0x140005165  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000516c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005173  test    rax, rax
0x140005176  jz      short loc_140005183
0x140005178  mov     rdx, rbx
0x14000517b  mov     rcx, rsi
0x14000517e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005183  mov     rax, rbx
0x140005186  mov     rbx, [rsp+28h+arg_0]
0x14000518b  mov     rsi, [rsp+28h+arg_8]
0x140005190  add     rsp, 20h
0x140005194  pop     rdi
0x140005195  retn
```
