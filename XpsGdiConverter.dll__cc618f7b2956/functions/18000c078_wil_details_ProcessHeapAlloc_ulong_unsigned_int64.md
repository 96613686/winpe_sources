# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c078`
- end: `0x18000c116`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000be74`
- `0x18000c310`
- `0x18000c6a8`
- `0x18001f1b8`
- `0x180022f8c`

## callees

- `0x18000c078`
- `0x18004a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000c0c1`
- `KERNEL32!GetModuleHandleW` at `0x18000c0c1`
- `KERNEL32!GetProcessHeap` at `0x18000c08c`
- `KERNEL32!GetProcessHeap` at `0x18000c08c`
- `KERNEL32!GetProcAddress` at `0x18000c0d6`
- `KERNEL32!GetProcAddress` at `0x18000c0d6`
- `KERNEL32!HeapAlloc` at `0x18000c09d`
- `KERNEL32!HeapAlloc` at `0x18000c09d`

## string_xrefs

- `0x18000c0ba`: `ntdll.dll`

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
0x18000c078  mov     [rsp+arg_0], rbx
0x18000c07d  mov     [rsp+arg_8], rsi
0x18000c082  push    rdi
0x18000c083  sub     rsp, 20h
0x18000c087  mov     rbx, rdx
0x18000c08a  mov     edi, ecx
0x18000c08c  call    cs:__imp_GetProcessHeap
0x18000c092  mov     rsi, rax
0x18000c095  mov     r8, rbx; dwBytes
0x18000c098  mov     edx, edi; dwFlags
0x18000c09a  mov     rcx, rax; hHeap
0x18000c09d  call    cs:__imp_HeapAlloc
0x18000c0a3  mov     rbx, rax
0x18000c0a6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c0ad  test    rax, rax
0x18000c0b0  jnz     short loc_18000C0F8
0x18000c0b2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c0b8  jnz     short loc_18000C103
0x18000c0ba  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000c0c1  call    cs:__imp_GetModuleHandleW
0x18000c0c7  test    rax, rax
0x18000c0ca  jz      short loc_18000C0E5
0x18000c0cc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000c0d3  mov     rcx, rax; hModule
0x18000c0d6  call    cs:__imp_GetProcAddress
0x18000c0dc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000c0e3  jmp     short loc_18000C0EC
0x18000c0e5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c0ec  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c0f3  test    rax, rax
0x18000c0f6  jz      short loc_18000C103
0x18000c0f8  mov     rdx, rbx
0x18000c0fb  mov     rcx, rsi
0x18000c0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c103  mov     rax, rbx
0x18000c106  mov     rbx, [rsp+28h+arg_0]
0x18000c10b  mov     rsi, [rsp+28h+arg_8]
0x18000c110  add     rsp, 20h
0x18000c114  pop     rdi
0x18000c115  retn
```
