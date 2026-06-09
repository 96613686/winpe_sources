# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180012b30`
- end: `0x180012bce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800113dc`
- `0x180011a90`
- `0x180012e70`

## callees

- `0x180012b30`
- `0x180015010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180012b55`
- `KERNEL32!HeapAlloc` at `0x180012b55`
- `KERNEL32!GetProcessHeap` at `0x180012b44`
- `KERNEL32!GetProcessHeap` at `0x180012b44`
- `KERNEL32!GetModuleHandleW` at `0x180012b79`
- `KERNEL32!GetModuleHandleW` at `0x180012b79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b8e`

## string_xrefs

- `0x180012b72`: `ntdll.dll`

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
0x180012b30  mov     [rsp+arg_0], rbx
0x180012b35  mov     [rsp+arg_8], rsi
0x180012b3a  push    rdi
0x180012b3b  sub     rsp, 20h
0x180012b3f  mov     rbx, rdx
0x180012b42  mov     edi, ecx
0x180012b44  call    cs:__imp_GetProcessHeap
0x180012b4a  mov     r8, rbx; dwBytes
0x180012b4d  mov     edx, edi; dwFlags
0x180012b4f  mov     rcx, rax; hHeap
0x180012b52  mov     rsi, rax
0x180012b55  call    cs:__imp_HeapAlloc
0x180012b5b  mov     rbx, rax
0x180012b5e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012b65  test    rax, rax
0x180012b68  jnz     short loc_180012BB0
0x180012b6a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012b70  jnz     short loc_180012BBB
0x180012b72  lea     rcx, ModuleName; "ntdll.dll"
0x180012b79  call    cs:__imp_GetModuleHandleW
0x180012b7f  test    rax, rax
0x180012b82  jz      short loc_180012B9D
0x180012b84  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180012b8b  mov     rcx, rax; hModule
0x180012b8e  call    cs:__imp_GetProcAddress
0x180012b94  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180012b9b  jmp     short loc_180012BA4
0x180012b9d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012ba4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012bab  test    rax, rax
0x180012bae  jz      short loc_180012BBB
0x180012bb0  mov     rdx, rbx
0x180012bb3  mov     rcx, rsi
0x180012bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bbb  mov     rsi, [rsp+28h+arg_8]
0x180012bc0  mov     rax, rbx
0x180012bc3  mov     rbx, [rsp+28h+arg_0]
0x180012bc8  add     rsp, 20h
0x180012bcc  pop     rdi
0x180012bcd  retn
```
