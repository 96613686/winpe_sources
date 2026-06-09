# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180025b78`
- end: `0x180025c16`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800238d4`
- `0x180023ca4`
- `0x1800248d0`
- `0x180026fd8`
- `0x180027e3c`

## callees

- `0x180025b78`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180025bc1`
- `KERNEL32!GetModuleHandleW` at `0x180025bc1`
- `KERNEL32!GetProcessHeap` at `0x180025b8c`
- `KERNEL32!GetProcessHeap` at `0x180025b8c`
- `KERNEL32!HeapAlloc` at `0x180025b9d`
- `KERNEL32!HeapAlloc` at `0x180025b9d`
- `KERNEL32!GetProcAddress` at `0x180025bd6`
- `KERNEL32!GetProcAddress` at `0x180025bd6`

## string_xrefs

- `0x180025bba`: `ntdll.dll`

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
0x180025b78  mov     [rsp+arg_0], rbx
0x180025b7d  mov     [rsp+arg_8], rsi
0x180025b82  push    rdi
0x180025b83  sub     rsp, 20h
0x180025b87  mov     rbx, rdx
0x180025b8a  mov     edi, ecx
0x180025b8c  call    cs:__imp_GetProcessHeap
0x180025b92  mov     r8, rbx; dwBytes
0x180025b95  mov     edx, edi; dwFlags
0x180025b97  mov     rcx, rax; hHeap
0x180025b9a  mov     rsi, rax
0x180025b9d  call    cs:__imp_HeapAlloc
0x180025ba3  mov     rbx, rax
0x180025ba6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180025bad  test    rax, rax
0x180025bb0  jnz     short loc_180025BF8
0x180025bb2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180025bb8  jnz     short loc_180025C03
0x180025bba  lea     rcx, aNtdllDll; "ntdll.dll"
0x180025bc1  call    cs:__imp_GetModuleHandleW
0x180025bc7  test    rax, rax
0x180025bca  jz      short loc_180025BE5
0x180025bcc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180025bd3  mov     rcx, rax; hModule
0x180025bd6  call    cs:__imp_GetProcAddress
0x180025bdc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180025be3  jmp     short loc_180025BEC
0x180025be5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180025bec  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180025bf3  test    rax, rax
0x180025bf6  jz      short loc_180025C03
0x180025bf8  mov     rdx, rbx
0x180025bfb  mov     rcx, rsi
0x180025bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c03  mov     rsi, [rsp+28h+arg_8]
0x180025c08  mov     rax, rbx
0x180025c0b  mov     rbx, [rsp+28h+arg_0]
0x180025c10  add     rsp, 20h
0x180025c14  pop     rdi
0x180025c15  retn
```
