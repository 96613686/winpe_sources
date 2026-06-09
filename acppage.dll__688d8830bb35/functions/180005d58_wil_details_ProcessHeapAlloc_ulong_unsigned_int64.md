# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005d58`
- end: `0x180005df6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800038a8`
- `0x180003c4c`
- `0x180004a30`
- `0x180007368`
- `0x18000835c`

## callees

- `0x180005d58`
- `0x180017010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180005d7d`
- `KERNEL32!HeapAlloc` at `0x180005d7d`
- `KERNEL32!GetProcessHeap` at `0x180005d6c`
- `KERNEL32!GetProcessHeap` at `0x180005d6c`
- `KERNEL32!GetModuleHandleW` at `0x180005da1`
- `KERNEL32!GetModuleHandleW` at `0x180005da1`
- `KERNEL32!GetProcAddress` at `0x180005db6`
- `KERNEL32!GetProcAddress` at `0x180005db6`

## string_xrefs

- `0x180005d9a`: `ntdll.dll`

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
0x180005d58  mov     [rsp+arg_0], rbx
0x180005d5d  mov     [rsp+arg_8], rsi
0x180005d62  push    rdi
0x180005d63  sub     rsp, 20h
0x180005d67  mov     rbx, rdx
0x180005d6a  mov     edi, ecx
0x180005d6c  call    cs:__imp_GetProcessHeap
0x180005d72  mov     r8, rbx; dwBytes
0x180005d75  mov     edx, edi; dwFlags
0x180005d77  mov     rcx, rax; hHeap
0x180005d7a  mov     rsi, rax
0x180005d7d  call    cs:__imp_HeapAlloc
0x180005d83  mov     rbx, rax
0x180005d86  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005d8d  test    rax, rax
0x180005d90  jnz     short loc_180005DD8
0x180005d92  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005d98  jnz     short loc_180005DE3
0x180005d9a  lea     rcx, ModuleName; "ntdll.dll"
0x180005da1  call    cs:__imp_GetModuleHandleW
0x180005da7  test    rax, rax
0x180005daa  jz      short loc_180005DC5
0x180005dac  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005db3  mov     rcx, rax; hModule
0x180005db6  call    cs:__imp_GetProcAddress
0x180005dbc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005dc3  jmp     short loc_180005DCC
0x180005dc5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005dcc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005dd3  test    rax, rax
0x180005dd6  jz      short loc_180005DE3
0x180005dd8  mov     rdx, rbx
0x180005ddb  mov     rcx, rsi
0x180005dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de3  mov     rsi, [rsp+28h+arg_8]
0x180005de8  mov     rax, rbx
0x180005deb  mov     rbx, [rsp+28h+arg_0]
0x180005df0  add     rsp, 20h
0x180005df4  pop     rdi
0x180005df5  retn
```
