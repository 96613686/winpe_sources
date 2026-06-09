# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005bac`
- end: `0x180005c4a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800041d4`
- `0x1800049f0`
- `0x180004fc0`
- `0x180006304`

## callees

- `0x180005bac`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005bf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005bf5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bc0`

## string_xrefs

- `0x180005bee`: `ntdll.dll`

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
0x180005bac  mov     [rsp+arg_0], rbx
0x180005bb1  mov     [rsp+arg_8], rsi
0x180005bb6  push    rdi
0x180005bb7  sub     rsp, 20h
0x180005bbb  mov     rbx, rdx
0x180005bbe  mov     edi, ecx
0x180005bc0  call    cs:__imp_GetProcessHeap
0x180005bc6  mov     rsi, rax
0x180005bc9  mov     r8, rbx; dwBytes
0x180005bcc  mov     edx, edi; dwFlags
0x180005bce  mov     rcx, rax; hHeap
0x180005bd1  call    cs:__imp_HeapAlloc
0x180005bd7  mov     rbx, rax
0x180005bda  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005be1  test    rax, rax
0x180005be4  jnz     short loc_180005C2C
0x180005be6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005bec  jnz     short loc_180005C37
0x180005bee  lea     rcx, ModuleName; "ntdll.dll"
0x180005bf5  call    cs:__imp_GetModuleHandleW
0x180005bfb  test    rax, rax
0x180005bfe  jz      short loc_180005C19
0x180005c00  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005c07  mov     rcx, rax; hModule
0x180005c0a  call    cs:__imp_GetProcAddress
0x180005c10  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005c17  jmp     short loc_180005C20
0x180005c19  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005c20  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005c27  test    rax, rax
0x180005c2a  jz      short loc_180005C37
0x180005c2c  mov     rdx, rbx
0x180005c2f  mov     rcx, rsi
0x180005c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c37  mov     rax, rbx
0x180005c3a  mov     rbx, [rsp+28h+arg_0]
0x180005c3f  mov     rsi, [rsp+28h+arg_8]
0x180005c44  add     rsp, 20h
0x180005c48  pop     rdi
0x180005c49  retn
```
