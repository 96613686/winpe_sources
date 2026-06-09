# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400058c8`
- end: `0x140005966`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005648`
- `0x1400062cc`
- `0x140006664`

## callees

- `0x1400058c8`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005926`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005926`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005911`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005911`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400058ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400058ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400058dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400058dc`

## string_xrefs

- `0x14000590a`: `ntdll.dll`

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
0x1400058c8  mov     [rsp+arg_0], rbx
0x1400058cd  mov     [rsp+arg_8], rsi
0x1400058d2  push    rdi
0x1400058d3  sub     rsp, 20h
0x1400058d7  mov     rbx, rdx
0x1400058da  mov     edi, ecx
0x1400058dc  call    cs:__imp_GetProcessHeap
0x1400058e2  mov     rsi, rax
0x1400058e5  mov     r8, rbx; dwBytes
0x1400058e8  mov     edx, edi; dwFlags
0x1400058ea  mov     rcx, rax; hHeap
0x1400058ed  call    cs:__imp_HeapAlloc
0x1400058f3  mov     rbx, rax
0x1400058f6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400058fd  test    rax, rax
0x140005900  jnz     short loc_140005948
0x140005902  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005908  jnz     short loc_140005953
0x14000590a  lea     rcx, ModuleName; "ntdll.dll"
0x140005911  call    cs:__imp_GetModuleHandleW
0x140005917  test    rax, rax
0x14000591a  jz      short loc_140005935
0x14000591c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140005923  mov     rcx, rax; hModule
0x140005926  call    cs:__imp_GetProcAddress
0x14000592c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005933  jmp     short loc_14000593C
0x140005935  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000593c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005943  test    rax, rax
0x140005946  jz      short loc_140005953
0x140005948  mov     rdx, rbx
0x14000594b  mov     rcx, rsi
0x14000594e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005953  mov     rax, rbx
0x140005956  mov     rbx, [rsp+28h+arg_0]
0x14000595b  mov     rsi, [rsp+28h+arg_8]
0x140005960  add     rsp, 20h
0x140005964  pop     rdi
0x140005965  retn
```
