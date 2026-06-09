# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004abc`
- end: `0x140004b5a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000323c`
- `0x140003920`
- `0x140005190`

## callees

- `0x140004abc`
- `0x140008010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140004ae1`
- `KERNEL32!HeapAlloc` at `0x140004ae1`
- `KERNEL32!GetProcAddress` at `0x140004b1a`
- `KERNEL32!GetProcAddress` at `0x140004b1a`
- `KERNEL32!GetProcessHeap` at `0x140004ad0`
- `KERNEL32!GetProcessHeap` at `0x140004ad0`
- `KERNEL32!GetModuleHandleW` at `0x140004b05`
- `KERNEL32!GetModuleHandleW` at `0x140004b05`

## string_xrefs

- `0x140004afe`: `ntdll.dll`

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
0x140004abc  mov     [rsp+arg_0], rbx
0x140004ac1  mov     [rsp+arg_8], rsi
0x140004ac6  push    rdi
0x140004ac7  sub     rsp, 20h
0x140004acb  mov     rbx, rdx
0x140004ace  mov     edi, ecx
0x140004ad0  call    cs:__imp_GetProcessHeap
0x140004ad6  mov     r8, rbx; dwBytes
0x140004ad9  mov     edx, edi; dwFlags
0x140004adb  mov     rcx, rax; hHeap
0x140004ade  mov     rsi, rax
0x140004ae1  call    cs:__imp_HeapAlloc
0x140004ae7  mov     rbx, rax
0x140004aea  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140004af1  test    rax, rax
0x140004af4  jnz     short loc_140004B3C
0x140004af6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004afc  jnz     short loc_140004B47
0x140004afe  lea     rcx, ModuleName; "ntdll.dll"
0x140004b05  call    cs:__imp_GetModuleHandleW
0x140004b0b  test    rax, rax
0x140004b0e  jz      short loc_140004B29
0x140004b10  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140004b17  mov     rcx, rax; hModule
0x140004b1a  call    cs:__imp_GetProcAddress
0x140004b20  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140004b27  jmp     short loc_140004B30
0x140004b29  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140004b30  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004b37  test    rax, rax
0x140004b3a  jz      short loc_140004B47
0x140004b3c  mov     rdx, rbx
0x140004b3f  mov     rcx, rsi
0x140004b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b47  mov     rsi, [rsp+28h+arg_8]
0x140004b4c  mov     rax, rbx
0x140004b4f  mov     rbx, [rsp+28h+arg_0]
0x140004b54  add     rsp, 20h
0x140004b58  pop     rdi
0x140004b59  retn
```
