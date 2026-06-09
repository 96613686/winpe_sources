# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008e2c`
- end: `0x180008eca`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006238`
- `0x180007920`
- `0x18000a0b0`
- `0x180021838`

## callees

- `0x180008e2c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008e75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008e75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008e8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008e8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e51`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e40`

## string_xrefs

- `0x180008e6e`: `ntdll.dll`

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
0x180008e2c  mov     [rsp+arg_0], rbx
0x180008e31  mov     [rsp+arg_8], rsi
0x180008e36  push    rdi
0x180008e37  sub     rsp, 20h
0x180008e3b  mov     rbx, rdx
0x180008e3e  mov     edi, ecx
0x180008e40  call    cs:__imp_GetProcessHeap
0x180008e46  mov     rsi, rax
0x180008e49  mov     r8, rbx; dwBytes
0x180008e4c  mov     edx, edi; dwFlags
0x180008e4e  mov     rcx, rax; hHeap
0x180008e51  call    cs:__imp_HeapAlloc
0x180008e57  mov     rbx, rax
0x180008e5a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008e61  test    rax, rax
0x180008e64  jnz     short loc_180008EAC
0x180008e66  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008e6c  jnz     short loc_180008EB7
0x180008e6e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180008e75  call    cs:__imp_GetModuleHandleW
0x180008e7b  test    rax, rax
0x180008e7e  jz      short loc_180008E99
0x180008e80  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008e87  mov     rcx, rax; hModule
0x180008e8a  call    cs:__imp_GetProcAddress
0x180008e90  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008e97  jmp     short loc_180008EA0
0x180008e99  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008ea0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008ea7  test    rax, rax
0x180008eaa  jz      short loc_180008EB7
0x180008eac  mov     rdx, rbx
0x180008eaf  mov     rcx, rsi
0x180008eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eb7  mov     rax, rbx
0x180008eba  mov     rbx, [rsp+28h+arg_0]
0x180008ebf  mov     rsi, [rsp+28h+arg_8]
0x180008ec4  add     rsp, 20h
0x180008ec8  pop     rdi
0x180008ec9  retn
```
