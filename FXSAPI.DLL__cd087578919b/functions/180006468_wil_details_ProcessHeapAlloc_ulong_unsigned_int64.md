# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006468`
- end: `0x18000651f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003648`
- `0x1800039f4`
- `0x1800080d4`
- `0x18000971c`

## callees

- `0x180006468`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000647c`
- `KERNEL32!GetProcessHeap` at `0x18000647c`
- `KERNEL32!GetProcAddress` at `0x1800064d8`
- `KERNEL32!GetProcAddress` at `0x1800064d8`
- `KERNEL32!GetModuleHandleW` at `0x1800064bd`
- `KERNEL32!GetModuleHandleW` at `0x1800064bd`
- `KERNEL32!HeapAlloc` at `0x180006493`
- `KERNEL32!HeapAlloc` at `0x180006493`

## string_xrefs

- `0x1800064b6`: `ntdll.dll`

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
0x180006468  mov     [rsp+arg_0], rbx
0x18000646d  mov     [rsp+arg_8], rsi
0x180006472  push    rdi
0x180006473  sub     rsp, 20h
0x180006477  mov     rbx, rdx
0x18000647a  mov     edi, ecx
0x18000647c  call    cs:__imp_GetProcessHeap
0x180006483  nop     dword ptr [rax+rax+00h]
0x180006488  mov     rsi, rax
0x18000648b  mov     r8, rbx; dwBytes
0x18000648e  mov     edx, edi; dwFlags
0x180006490  mov     rcx, rax; hHeap
0x180006493  call    cs:__imp_HeapAlloc
0x18000649a  nop     dword ptr [rax+rax+00h]
0x18000649f  mov     rbx, rax
0x1800064a2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800064a9  test    rax, rax
0x1800064ac  jnz     short loc_180006500
0x1800064ae  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800064b4  jnz     short loc_18000650B
0x1800064b6  lea     rcx, ModuleName; "ntdll.dll"
0x1800064bd  call    cs:__imp_GetModuleHandleW
0x1800064c4  nop     dword ptr [rax+rax+00h]
0x1800064c9  test    rax, rax
0x1800064cc  jz      short loc_1800064ED
0x1800064ce  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800064d5  mov     rcx, rax; hModule
0x1800064d8  call    cs:__imp_GetProcAddress
0x1800064df  nop     dword ptr [rax+rax+00h]
0x1800064e4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800064eb  jmp     short loc_1800064F4
0x1800064ed  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800064f4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800064fb  test    rax, rax
0x1800064fe  jz      short loc_18000650B
0x180006500  mov     rdx, rbx
0x180006503  mov     rcx, rsi
0x180006506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650b  mov     rax, rbx
0x18000650e  mov     rbx, [rsp+28h+arg_0]
0x180006513  mov     rsi, [rsp+28h+arg_8]
0x180006518  add     rsp, 20h
0x18000651c  pop     rdi
0x18000651d  retn
```
