# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400061e4`
- end: `0x14000628c`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400048f8`
- `0x1400050a0`
- `0x1400056a0`
- `0x140006560`
- `0x14000c164`
- `0x14000ea94`

## callees

- `0x1400061e4`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000624c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000624c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006237`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006237`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006202`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006202`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006213`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006213`

## string_xrefs

- `0x140006230`: `ntdll.dll`

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
0x1400061e4  push    rdi
0x1400061e6  sub     rsp, 30h
0x1400061ea  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400061f3  mov     [rsp+38h+arg_0], rbx
0x1400061f8  mov     [rsp+38h+arg_8], rsi
0x1400061fd  mov     rbx, rdx
0x140006200  mov     edi, ecx
0x140006202  call    cs:__imp_GetProcessHeap
0x140006208  mov     rsi, rax
0x14000620b  mov     r8, rbx; dwBytes
0x14000620e  mov     edx, edi; dwFlags
0x140006210  mov     rcx, rax; hHeap
0x140006213  call    cs:__imp_HeapAlloc
0x140006219  mov     rbx, rax
0x14000621c  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006223  test    rax, rax
0x140006226  jnz     short loc_14000626E
0x140006228  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000622e  jnz     short loc_140006279
0x140006230  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140006237  call    cs:__imp_GetModuleHandleW
0x14000623d  test    rax, rax
0x140006240  jz      short loc_14000625B
0x140006242  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140006249  mov     rcx, rax; hModule
0x14000624c  call    cs:__imp_GetProcAddress
0x140006252  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140006259  jmp     short loc_140006262
0x14000625b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006262  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006269  test    rax, rax
0x14000626c  jz      short loc_140006279
0x14000626e  mov     rdx, rbx
0x140006271  mov     rcx, rsi
0x140006274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006279  mov     rax, rbx
0x14000627c  mov     rbx, [rsp+38h+arg_0]
0x140006281  mov     rsi, [rsp+38h+arg_8]
0x140006286  add     rsp, 30h
0x14000628a  pop     rdi
0x14000628b  retn
```
