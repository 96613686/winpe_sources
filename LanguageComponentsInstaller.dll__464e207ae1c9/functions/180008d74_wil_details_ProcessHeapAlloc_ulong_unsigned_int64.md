# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008d74`
- end: `0x180008e12`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006a78`
- `0x180007b10`
- `0x1800080e0`
- `0x180009394`
- `0x180015244`
- `0x180021e9c`

## callees

- `0x180008d74`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008dd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008dd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dbd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d88`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d99`

## string_xrefs

- `0x180008db6`: `ntdll.dll`

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
0x180008d74  mov     [rsp+arg_0], rbx
0x180008d79  mov     [rsp+arg_8], rsi
0x180008d7e  push    rdi
0x180008d7f  sub     rsp, 20h
0x180008d83  mov     rbx, rdx
0x180008d86  mov     edi, ecx
0x180008d88  call    cs:__imp_GetProcessHeap
0x180008d8e  mov     rsi, rax
0x180008d91  mov     r8, rbx; dwBytes
0x180008d94  mov     edx, edi; dwFlags
0x180008d96  mov     rcx, rax; hHeap
0x180008d99  call    cs:__imp_HeapAlloc
0x180008d9f  mov     rbx, rax
0x180008da2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008da9  test    rax, rax
0x180008dac  jnz     short loc_180008DF4
0x180008dae  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008db4  jnz     short loc_180008DFF
0x180008db6  lea     rcx, ModuleName; "ntdll.dll"
0x180008dbd  call    cs:__imp_GetModuleHandleW
0x180008dc3  test    rax, rax
0x180008dc6  jz      short loc_180008DE1
0x180008dc8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008dcf  mov     rcx, rax; hModule
0x180008dd2  call    cs:__imp_GetProcAddress
0x180008dd8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008ddf  jmp     short loc_180008DE8
0x180008de1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008de8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008def  test    rax, rax
0x180008df2  jz      short loc_180008DFF
0x180008df4  mov     rdx, rbx
0x180008df7  mov     rcx, rsi
0x180008dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dff  mov     rax, rbx
0x180008e02  mov     rbx, [rsp+28h+arg_0]
0x180008e07  mov     rsi, [rsp+28h+arg_8]
0x180008e0c  add     rsp, 20h
0x180008e10  pop     rdi
0x180008e11  retn
```
