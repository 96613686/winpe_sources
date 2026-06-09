# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007d40`
- end: `0x180007dde`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009220`
- `0x180009680`
- `0x180009e48`

## callees

- `0x180007d40`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007d9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007d9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007d89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007d89`

## string_xrefs

- `0x180007d82`: `ntdll.dll`

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
0x180007d40  mov     [rsp+arg_0], rbx
0x180007d45  mov     [rsp+arg_8], rsi
0x180007d4a  push    rdi
0x180007d4b  sub     rsp, 20h
0x180007d4f  mov     rbx, rdx
0x180007d52  mov     edi, ecx
0x180007d54  call    cs:__imp_GetProcessHeap
0x180007d5a  mov     rsi, rax
0x180007d5d  mov     r8, rbx; dwBytes
0x180007d60  mov     edx, edi; dwFlags
0x180007d62  mov     rcx, rax; hHeap
0x180007d65  call    cs:__imp_HeapAlloc
0x180007d6b  mov     rbx, rax
0x180007d6e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007d75  test    rax, rax
0x180007d78  jnz     short loc_180007DC0
0x180007d7a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007d80  jnz     short loc_180007DCB
0x180007d82  lea     rcx, ModuleName; "ntdll.dll"
0x180007d89  call    cs:__imp_GetModuleHandleW
0x180007d8f  test    rax, rax
0x180007d92  jz      short loc_180007DAD
0x180007d94  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007d9b  mov     rcx, rax; hModule
0x180007d9e  call    cs:__imp_GetProcAddress
0x180007da4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007dab  jmp     short loc_180007DB4
0x180007dad  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007db4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007dbb  test    rax, rax
0x180007dbe  jz      short loc_180007DCB
0x180007dc0  mov     rdx, rbx
0x180007dc3  mov     rcx, rsi
0x180007dc6  call    _guard_dispatch_icall
0x180007dcb  mov     rax, rbx
0x180007dce  mov     rbx, [rsp+28h+arg_0]
0x180007dd3  mov     rsi, [rsp+28h+arg_8]
0x180007dd8  add     rsp, 20h
0x180007ddc  pop     rdi
0x180007ddd  retn
```
