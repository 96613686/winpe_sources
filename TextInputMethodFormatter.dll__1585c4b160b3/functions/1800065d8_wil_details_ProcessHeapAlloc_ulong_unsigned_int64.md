# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800065d8`
- end: `0x180006676`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800048d8`
- `0x180005280`
- `0x1800058fc`
- `0x180006b04`
- `0x180009dec`
- `0x18001268c`

## callees

- `0x1800065d8`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006636`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006636`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006621`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006621`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800065fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800065fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065ec`

## string_xrefs

- `0x18000661a`: `ntdll.dll`

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
0x1800065d8  mov     [rsp+arg_0], rbx
0x1800065dd  mov     [rsp+arg_8], rsi
0x1800065e2  push    rdi
0x1800065e3  sub     rsp, 20h
0x1800065e7  mov     rbx, rdx
0x1800065ea  mov     edi, ecx
0x1800065ec  call    cs:__imp_GetProcessHeap
0x1800065f2  mov     rsi, rax
0x1800065f5  mov     r8, rbx; dwBytes
0x1800065f8  mov     edx, edi; dwFlags
0x1800065fa  mov     rcx, rax; hHeap
0x1800065fd  call    cs:__imp_HeapAlloc
0x180006603  mov     rbx, rax
0x180006606  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000660d  test    rax, rax
0x180006610  jnz     short loc_180006658
0x180006612  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006618  jnz     short loc_180006663
0x18000661a  lea     rcx, ModuleName; "ntdll.dll"
0x180006621  call    cs:__imp_GetModuleHandleW
0x180006627  test    rax, rax
0x18000662a  jz      short loc_180006645
0x18000662c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006633  mov     rcx, rax; hModule
0x180006636  call    cs:__imp_GetProcAddress
0x18000663c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006643  jmp     short loc_18000664C
0x180006645  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000664c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006653  test    rax, rax
0x180006656  jz      short loc_180006663
0x180006658  mov     rdx, rbx
0x18000665b  mov     rcx, rsi
0x18000665e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006663  mov     rax, rbx
0x180006666  mov     rbx, [rsp+28h+arg_0]
0x18000666b  mov     rsi, [rsp+28h+arg_8]
0x180006670  add     rsp, 20h
0x180006674  pop     rdi
0x180006675  retn
```
