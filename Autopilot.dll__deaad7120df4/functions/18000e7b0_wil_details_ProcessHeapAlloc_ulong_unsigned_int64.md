# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000e7b0`
- end: `0x18000e867`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b8cc`
- `0x18000bcd4`
- `0x18000d620`
- `0x180010d9c`
- `0x1800124c0`

## callees

- `0x18000e7b0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e805`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e805`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e820`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e820`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7db`

## string_xrefs

- `0x18000e7fe`: `ntdll.dll`

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
0x18000e7b0  mov     [rsp+arg_0], rbx
0x18000e7b5  mov     [rsp+arg_8], rsi
0x18000e7ba  push    rdi
0x18000e7bb  sub     rsp, 20h
0x18000e7bf  mov     rbx, rdx
0x18000e7c2  mov     edi, ecx
0x18000e7c4  call    cs:__imp_GetProcessHeap
0x18000e7cb  nop     dword ptr [rax+rax+00h]
0x18000e7d0  mov     rsi, rax
0x18000e7d3  mov     r8, rbx; dwBytes
0x18000e7d6  mov     edx, edi; dwFlags
0x18000e7d8  mov     rcx, rax; hHeap
0x18000e7db  call    cs:__imp_HeapAlloc
0x18000e7e2  nop     dword ptr [rax+rax+00h]
0x18000e7e7  mov     rbx, rax
0x18000e7ea  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e7f1  test    rax, rax
0x18000e7f4  jnz     short loc_18000E848
0x18000e7f6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e7fc  jnz     short loc_18000E853
0x18000e7fe  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e805  call    cs:__imp_GetModuleHandleW
0x18000e80c  nop     dword ptr [rax+rax+00h]
0x18000e811  test    rax, rax
0x18000e814  jz      short loc_18000E835
0x18000e816  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000e81d  mov     rcx, rax; hModule
0x18000e820  call    cs:__imp_GetProcAddress
0x18000e827  nop     dword ptr [rax+rax+00h]
0x18000e82c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000e833  jmp     short loc_18000E83C
0x18000e835  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e83c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e843  test    rax, rax
0x18000e846  jz      short loc_18000E853
0x18000e848  mov     rdx, rbx
0x18000e84b  mov     rcx, rsi
0x18000e84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e853  mov     rax, rbx
0x18000e856  mov     rbx, [rsp+28h+arg_0]
0x18000e85b  mov     rsi, [rsp+28h+arg_8]
0x18000e860  add     rsp, 20h
0x18000e864  pop     rdi
0x18000e865  retn
```
