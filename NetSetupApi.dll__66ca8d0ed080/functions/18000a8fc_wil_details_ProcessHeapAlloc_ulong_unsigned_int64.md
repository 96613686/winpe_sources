# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a8fc`
- end: `0x18000a9a4`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a680`
- `0x18000abd4`
- `0x18000ad10`

## callees

- `0x18000a8fc`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a964`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a964`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a94f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a94f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a91a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a91a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a92b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a92b`

## string_xrefs

- `0x18000a948`: `ntdll.dll`

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
0x18000a8fc  push    rdi
0x18000a8fe  sub     rsp, 30h
0x18000a902  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a90b  mov     [rsp+38h+arg_0], rbx
0x18000a910  mov     [rsp+38h+arg_8], rsi
0x18000a915  mov     rbx, rdx
0x18000a918  mov     edi, ecx
0x18000a91a  call    cs:__imp_GetProcessHeap
0x18000a920  mov     rsi, rax
0x18000a923  mov     r8, rbx; dwBytes
0x18000a926  mov     edx, edi; dwFlags
0x18000a928  mov     rcx, rax; hHeap
0x18000a92b  call    cs:__imp_HeapAlloc
0x18000a931  mov     rbx, rax
0x18000a934  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a93b  test    rax, rax
0x18000a93e  jnz     short loc_18000A986
0x18000a940  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a946  jnz     short loc_18000A991
0x18000a948  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a94f  call    cs:__imp_GetModuleHandleW
0x18000a955  test    rax, rax
0x18000a958  jz      short loc_18000A973
0x18000a95a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000a961  mov     rcx, rax; hModule
0x18000a964  call    cs:__imp_GetProcAddress
0x18000a96a  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a971  jmp     short loc_18000A97A
0x18000a973  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a97a  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a981  test    rax, rax
0x18000a984  jz      short loc_18000A991
0x18000a986  mov     rdx, rbx
0x18000a989  mov     rcx, rsi
0x18000a98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a991  mov     rax, rbx
0x18000a994  mov     rbx, [rsp+38h+arg_0]
0x18000a999  mov     rsi, [rsp+38h+arg_8]
0x18000a99e  add     rsp, 30h
0x18000a9a2  pop     rdi
0x18000a9a3  retn
```
