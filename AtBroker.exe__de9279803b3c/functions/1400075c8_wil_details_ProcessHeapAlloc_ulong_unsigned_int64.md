# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400075c8`
- end: `0x140007666`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400040c8`
- `0x140004498`
- `0x1400059f0`
- `0x140009478`
- `0x14000a87c`

## callees

- `0x1400075c8`
- `0x140017010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400075ed`
- `KERNEL32!HeapAlloc` at `0x1400075ed`
- `KERNEL32!GetProcAddress` at `0x140007626`
- `KERNEL32!GetProcAddress` at `0x140007626`
- `KERNEL32!GetProcessHeap` at `0x1400075dc`
- `KERNEL32!GetProcessHeap` at `0x1400075dc`
- `KERNEL32!GetModuleHandleW` at `0x140007611`
- `KERNEL32!GetModuleHandleW` at `0x140007611`

## string_xrefs

- `0x14000760a`: `ntdll.dll`

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
0x1400075c8  mov     [rsp+arg_0], rbx
0x1400075cd  mov     [rsp+arg_8], rsi
0x1400075d2  push    rdi
0x1400075d3  sub     rsp, 20h
0x1400075d7  mov     rbx, rdx
0x1400075da  mov     edi, ecx
0x1400075dc  call    cs:__imp_GetProcessHeap
0x1400075e2  mov     r8, rbx; dwBytes
0x1400075e5  mov     edx, edi; dwFlags
0x1400075e7  mov     rcx, rax; hHeap
0x1400075ea  mov     rsi, rax
0x1400075ed  call    cs:__imp_HeapAlloc
0x1400075f3  mov     rbx, rax
0x1400075f6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400075fd  test    rax, rax
0x140007600  jnz     short loc_140007648
0x140007602  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140007608  jnz     short loc_140007653
0x14000760a  lea     rcx, ModuleName; "ntdll.dll"
0x140007611  call    cs:__imp_GetModuleHandleW
0x140007617  test    rax, rax
0x14000761a  jz      short loc_140007635
0x14000761c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140007623  mov     rcx, rax; hModule
0x140007626  call    cs:__imp_GetProcAddress
0x14000762c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140007633  jmp     short loc_14000763C
0x140007635  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000763c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140007643  test    rax, rax
0x140007646  jz      short loc_140007653
0x140007648  mov     rdx, rbx
0x14000764b  mov     rcx, rsi
0x14000764e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007653  mov     rsi, [rsp+28h+arg_8]
0x140007658  mov     rax, rbx
0x14000765b  mov     rbx, [rsp+28h+arg_0]
0x140007660  add     rsp, 20h
0x140007664  pop     rdi
0x140007665  retn
```
