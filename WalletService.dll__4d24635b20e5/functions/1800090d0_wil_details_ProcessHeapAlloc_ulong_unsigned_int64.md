# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800090d0`
- end: `0x18000916e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007c78`
- `0x180008958`
- `0x180008aa8`
- `0x18000a7f8`
- `0x18000aa30`
- `0x18000bc2c`

## callees

- `0x1800090d0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000912e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000912e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009119`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009119`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800090f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800090f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090e4`

## string_xrefs

- `0x180009112`: `ntdll.dll`

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
0x1800090d0  mov     [rsp+arg_0], rbx
0x1800090d5  mov     [rsp+arg_8], rsi
0x1800090da  push    rdi
0x1800090db  sub     rsp, 20h
0x1800090df  mov     rbx, rdx
0x1800090e2  mov     edi, ecx
0x1800090e4  call    cs:__imp_GetProcessHeap
0x1800090ea  mov     r8, rbx; dwBytes
0x1800090ed  mov     edx, edi; dwFlags
0x1800090ef  mov     rcx, rax; hHeap
0x1800090f2  mov     rsi, rax
0x1800090f5  call    cs:__imp_HeapAlloc
0x1800090fb  mov     rbx, rax
0x1800090fe  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009105  test    rax, rax
0x180009108  jnz     short loc_180009150
0x18000910a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009110  jnz     short loc_18000915B
0x180009112  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009119  call    cs:__imp_GetModuleHandleW
0x18000911f  test    rax, rax
0x180009122  jz      short loc_18000913D
0x180009124  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000912b  mov     rcx, rax; hModule
0x18000912e  call    cs:__imp_GetProcAddress
0x180009134  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000913b  jmp     short loc_180009144
0x18000913d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009144  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000914b  test    rax, rax
0x18000914e  jz      short loc_18000915B
0x180009150  mov     rdx, rbx
0x180009153  mov     rcx, rsi
0x180009156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000915b  mov     rsi, [rsp+28h+arg_8]
0x180009160  mov     rax, rbx
0x180009163  mov     rbx, [rsp+28h+arg_0]
0x180009168  add     rsp, 20h
0x18000916c  pop     rdi
0x18000916d  retn
```
