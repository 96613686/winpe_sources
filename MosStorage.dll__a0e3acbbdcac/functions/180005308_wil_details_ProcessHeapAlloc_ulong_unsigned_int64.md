# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005308`
- end: `0x1800053a6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003c14`
- `0x1800042c0`
- `0x180005800`

## callees

- `0x180005308`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005351`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005351`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005366`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005366`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000532d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000532d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000531c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000531c`

## string_xrefs

- `0x18000534a`: `ntdll.dll`

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
0x180005308  mov     [rsp+arg_0], rbx
0x18000530d  mov     [rsp+arg_8], rsi
0x180005312  push    rdi
0x180005313  sub     rsp, 20h
0x180005317  mov     rbx, rdx
0x18000531a  mov     edi, ecx
0x18000531c  call    cs:__imp_GetProcessHeap
0x180005322  mov     rsi, rax
0x180005325  mov     r8, rbx; dwBytes
0x180005328  mov     edx, edi; dwFlags
0x18000532a  mov     rcx, rax; hHeap
0x18000532d  call    cs:__imp_HeapAlloc
0x180005333  mov     rbx, rax
0x180005336  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000533d  test    rax, rax
0x180005340  jnz     short loc_180005388
0x180005342  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005348  jnz     short loc_180005393
0x18000534a  lea     rcx, ModuleName; "ntdll.dll"
0x180005351  call    cs:__imp_GetModuleHandleW
0x180005357  test    rax, rax
0x18000535a  jz      short loc_180005375
0x18000535c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005363  mov     rcx, rax; hModule
0x180005366  call    cs:__imp_GetProcAddress
0x18000536c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005373  jmp     short loc_18000537C
0x180005375  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000537c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005383  test    rax, rax
0x180005386  jz      short loc_180005393
0x180005388  mov     rdx, rbx
0x18000538b  mov     rcx, rsi
0x18000538e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005393  mov     rax, rbx
0x180005396  mov     rbx, [rsp+28h+arg_0]
0x18000539b  mov     rsi, [rsp+28h+arg_8]
0x1800053a0  add     rsp, 20h
0x1800053a4  pop     rdi
0x1800053a5  retn
```
