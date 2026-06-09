# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004448`
- end: `0x1400044e6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002d58`
- `0x1400033f0`
- `0x1400047b0`

## callees

- `0x140004448`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400044a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400044a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004491`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004491`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000446d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000446d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000445c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000445c`

## string_xrefs

- `0x14000448a`: `ntdll.dll`

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
0x140004448  mov     [rsp+arg_0], rbx
0x14000444d  mov     [rsp+arg_8], rsi
0x140004452  push    rdi
0x140004453  sub     rsp, 20h
0x140004457  mov     rbx, rdx
0x14000445a  mov     edi, ecx
0x14000445c  call    cs:__imp_GetProcessHeap
0x140004462  mov     rsi, rax
0x140004465  mov     r8, rbx; dwBytes
0x140004468  mov     edx, edi; dwFlags
0x14000446a  mov     rcx, rax; hHeap
0x14000446d  call    cs:__imp_HeapAlloc
0x140004473  mov     rbx, rax
0x140004476  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000447d  test    rax, rax
0x140004480  jnz     short loc_1400044C8
0x140004482  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004488  jnz     short loc_1400044D3
0x14000448a  lea     rcx, ModuleName; "ntdll.dll"
0x140004491  call    cs:__imp_GetModuleHandleW
0x140004497  test    rax, rax
0x14000449a  jz      short loc_1400044B5
0x14000449c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400044a3  mov     rcx, rax; hModule
0x1400044a6  call    cs:__imp_GetProcAddress
0x1400044ac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400044b3  jmp     short loc_1400044BC
0x1400044b5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400044bc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400044c3  test    rax, rax
0x1400044c6  jz      short loc_1400044D3
0x1400044c8  mov     rdx, rbx
0x1400044cb  mov     rcx, rsi
0x1400044ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044d3  mov     rax, rbx
0x1400044d6  mov     rbx, [rsp+28h+arg_0]
0x1400044db  mov     rsi, [rsp+28h+arg_8]
0x1400044e0  add     rsp, 20h
0x1400044e4  pop     rdi
0x1400044e5  retn
```
