# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005f30`
- end: `0x140005fce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003c20`
- `0x140004450`
- `0x140006514`

## callees

- `0x140005f30`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140005f79`
- `KERNEL32!GetModuleHandleW` at `0x140005f79`
- `KERNEL32!GetProcessHeap` at `0x140005f44`
- `KERNEL32!GetProcessHeap` at `0x140005f44`
- `KERNEL32!GetProcAddress` at `0x140005f8e`
- `KERNEL32!GetProcAddress` at `0x140005f8e`
- `KERNEL32!HeapAlloc` at `0x140005f55`
- `KERNEL32!HeapAlloc` at `0x140005f55`

## string_xrefs

- `0x140005f72`: `ntdll.dll`

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
0x140005f30  mov     [rsp+arg_0], rbx
0x140005f35  mov     [rsp+arg_8], rsi
0x140005f3a  push    rdi
0x140005f3b  sub     rsp, 20h
0x140005f3f  mov     rbx, rdx
0x140005f42  mov     edi, ecx
0x140005f44  call    cs:__imp_GetProcessHeap
0x140005f4a  mov     rsi, rax
0x140005f4d  mov     r8, rbx; dwBytes
0x140005f50  mov     edx, edi; dwFlags
0x140005f52  mov     rcx, rax; hHeap
0x140005f55  call    cs:__imp_HeapAlloc
0x140005f5b  mov     rbx, rax
0x140005f5e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005f65  test    rax, rax
0x140005f68  jnz     short loc_140005FB0
0x140005f6a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005f70  jnz     short loc_140005FBB
0x140005f72  lea     rcx, ModuleName; "ntdll.dll"
0x140005f79  call    cs:__imp_GetModuleHandleW
0x140005f7f  test    rax, rax
0x140005f82  jz      short loc_140005F9D
0x140005f84  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140005f8b  mov     rcx, rax; hModule
0x140005f8e  call    cs:__imp_GetProcAddress
0x140005f94  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005f9b  jmp     short loc_140005FA4
0x140005f9d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005fa4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005fab  test    rax, rax
0x140005fae  jz      short loc_140005FBB
0x140005fb0  mov     rdx, rbx
0x140005fb3  mov     rcx, rsi
0x140005fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fbb  mov     rax, rbx
0x140005fbe  mov     rbx, [rsp+28h+arg_0]
0x140005fc3  mov     rsi, [rsp+28h+arg_8]
0x140005fc8  add     rsp, 20h
0x140005fcc  pop     rdi
0x140005fcd  retn
```
