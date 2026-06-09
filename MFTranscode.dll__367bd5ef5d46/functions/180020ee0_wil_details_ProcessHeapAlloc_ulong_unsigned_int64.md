# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180020ee0`
- end: `0x180020f7e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800159c8`
- `0x1800212fc`
- `0x180021594`

## callees

- `0x180020ee0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020f29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020f29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020f3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020f3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ef4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ef4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020f05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020f05`

## string_xrefs

- `0x180020f22`: `ntdll.dll`

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
0x180020ee0  mov     [rsp+arg_0], rbx
0x180020ee5  mov     [rsp+arg_8], rsi
0x180020eea  push    rdi
0x180020eeb  sub     rsp, 20h
0x180020eef  mov     rbx, rdx
0x180020ef2  mov     edi, ecx
0x180020ef4  call    cs:__imp_GetProcessHeap
0x180020efa  mov     r8, rbx; dwBytes
0x180020efd  mov     edx, edi; dwFlags
0x180020eff  mov     rcx, rax; hHeap
0x180020f02  mov     rsi, rax
0x180020f05  call    cs:__imp_HeapAlloc
0x180020f0b  mov     rbx, rax
0x180020f0e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180020f15  test    rax, rax
0x180020f18  jnz     short loc_180020F60
0x180020f1a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180020f20  jnz     short loc_180020F6B
0x180020f22  lea     rcx, ModuleName; "ntdll.dll"
0x180020f29  call    cs:__imp_GetModuleHandleW
0x180020f2f  test    rax, rax
0x180020f32  jz      short loc_180020F4D
0x180020f34  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180020f3b  mov     rcx, rax; hModule
0x180020f3e  call    cs:__imp_GetProcAddress
0x180020f44  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180020f4b  jmp     short loc_180020F54
0x180020f4d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180020f54  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180020f5b  test    rax, rax
0x180020f5e  jz      short loc_180020F6B
0x180020f60  mov     rdx, rbx
0x180020f63  mov     rcx, rsi
0x180020f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f6b  mov     rsi, [rsp+28h+arg_8]
0x180020f70  mov     rax, rbx
0x180020f73  mov     rbx, [rsp+28h+arg_0]
0x180020f78  add     rsp, 20h
0x180020f7c  pop     rdi
0x180020f7d  retn
```
