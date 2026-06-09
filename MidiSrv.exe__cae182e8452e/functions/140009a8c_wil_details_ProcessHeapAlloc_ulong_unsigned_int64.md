# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140009a8c`
- end: `0x140009b2a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008448`
- `0x140008bc0`
- `0x1400091a4`
- `0x14000a740`
- `0x14000c89c`

## callees

- `0x140009a8c`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009aea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009aea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009ad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009ad5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009ab1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009ab1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009aa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009aa0`

## string_xrefs

- `0x140009ace`: `ntdll.dll`

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
0x140009a8c  mov     [rsp+arg_0], rbx
0x140009a91  mov     [rsp+arg_8], rsi
0x140009a96  push    rdi
0x140009a97  sub     rsp, 20h
0x140009a9b  mov     rbx, rdx
0x140009a9e  mov     edi, ecx
0x140009aa0  call    cs:__imp_GetProcessHeap
0x140009aa6  mov     rsi, rax
0x140009aa9  mov     r8, rbx; dwBytes
0x140009aac  mov     edx, edi; dwFlags
0x140009aae  mov     rcx, rax; hHeap
0x140009ab1  call    cs:__imp_HeapAlloc
0x140009ab7  mov     rbx, rax
0x140009aba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140009ac1  test    rax, rax
0x140009ac4  jnz     short loc_140009B0C
0x140009ac6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140009acc  jnz     short loc_140009B17
0x140009ace  lea     rcx, ModuleName; "ntdll.dll"
0x140009ad5  call    cs:__imp_GetModuleHandleW
0x140009adb  test    rax, rax
0x140009ade  jz      short loc_140009AF9
0x140009ae0  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140009ae7  mov     rcx, rax; hModule
0x140009aea  call    cs:__imp_GetProcAddress
0x140009af0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140009af7  jmp     short loc_140009B00
0x140009af9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140009b00  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140009b07  test    rax, rax
0x140009b0a  jz      short loc_140009B17
0x140009b0c  mov     rdx, rbx
0x140009b0f  mov     rcx, rsi
0x140009b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b17  mov     rax, rbx
0x140009b1a  mov     rbx, [rsp+28h+arg_0]
0x140009b1f  mov     rsi, [rsp+28h+arg_8]
0x140009b24  add     rsp, 20h
0x140009b28  pop     rdi
0x140009b29  retn
```
