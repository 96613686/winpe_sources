# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140009228`
- end: `0x1400092c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400078ec`
- `0x140007cbc`
- `0x1400088b0`
- `0x14000a5c4`
- `0x14000bb9c`

## callees

- `0x140009228`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140009271`
- `KERNEL32!GetModuleHandleW` at `0x140009271`
- `KERNEL32!GetProcAddress` at `0x140009286`
- `KERNEL32!GetProcAddress` at `0x140009286`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000924d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000924d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000923c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000923c`

## string_xrefs

- `0x14000926a`: `ntdll.dll`

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
0x140009228  mov     [rsp+arg_0], rbx
0x14000922d  mov     [rsp+arg_8], rsi
0x140009232  push    rdi
0x140009233  sub     rsp, 20h
0x140009237  mov     rbx, rdx
0x14000923a  mov     edi, ecx
0x14000923c  call    cs:__imp_GetProcessHeap
0x140009242  mov     rsi, rax
0x140009245  mov     r8, rbx; dwBytes
0x140009248  mov     edx, edi; dwFlags
0x14000924a  mov     rcx, rax; hHeap
0x14000924d  call    cs:__imp_HeapAlloc
0x140009253  mov     rbx, rax
0x140009256  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000925d  test    rax, rax
0x140009260  jnz     short loc_1400092A8
0x140009262  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140009268  jnz     short loc_1400092B3
0x14000926a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140009271  call    cs:__imp_GetModuleHandleW
0x140009277  test    rax, rax
0x14000927a  jz      short loc_140009295
0x14000927c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140009283  mov     rcx, rax; hModule
0x140009286  call    cs:__imp_GetProcAddress
0x14000928c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140009293  jmp     short loc_14000929C
0x140009295  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000929c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400092a3  test    rax, rax
0x1400092a6  jz      short loc_1400092B3
0x1400092a8  mov     rdx, rbx
0x1400092ab  mov     rcx, rsi
0x1400092ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092b3  mov     rax, rbx
0x1400092b6  mov     rbx, [rsp+28h+arg_0]
0x1400092bb  mov     rsi, [rsp+28h+arg_8]
0x1400092c0  add     rsp, 20h
0x1400092c4  pop     rdi
0x1400092c5  retn
```
