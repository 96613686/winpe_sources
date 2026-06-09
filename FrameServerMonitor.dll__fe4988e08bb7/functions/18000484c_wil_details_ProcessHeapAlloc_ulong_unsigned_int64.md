# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000484c`
- end: `0x1800048ea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004644`
- `0x180004c3c`
- `0x180004d78`
- `0x1800055ac`

## callees

- `0x18000484c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004895`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004895`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004871`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004871`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004860`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004860`

## string_xrefs

- `0x18000488e`: `ntdll.dll`

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
0x18000484c  mov     [rsp+arg_0], rbx
0x180004851  mov     [rsp+arg_8], rsi
0x180004856  push    rdi
0x180004857  sub     rsp, 20h
0x18000485b  mov     rbx, rdx
0x18000485e  mov     edi, ecx
0x180004860  call    cs:__imp_GetProcessHeap
0x180004866  mov     r8, rbx; dwBytes
0x180004869  mov     edx, edi; dwFlags
0x18000486b  mov     rcx, rax; hHeap
0x18000486e  mov     rsi, rax
0x180004871  call    cs:__imp_HeapAlloc
0x180004877  mov     rbx, rax
0x18000487a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004881  test    rax, rax
0x180004884  jnz     short loc_1800048CC
0x180004886  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000488c  jnz     short loc_1800048D7
0x18000488e  lea     rcx, ModuleName; "ntdll.dll"
0x180004895  call    cs:__imp_GetModuleHandleW
0x18000489b  test    rax, rax
0x18000489e  jz      short loc_1800048B9
0x1800048a0  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800048a7  mov     rcx, rax; hModule
0x1800048aa  call    cs:__imp_GetProcAddress
0x1800048b0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800048b7  jmp     short loc_1800048C0
0x1800048b9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800048c0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800048c7  test    rax, rax
0x1800048ca  jz      short loc_1800048D7
0x1800048cc  mov     rdx, rbx
0x1800048cf  mov     rcx, rsi
0x1800048d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048d7  mov     rsi, [rsp+28h+arg_8]
0x1800048dc  mov     rax, rbx
0x1800048df  mov     rbx, [rsp+28h+arg_0]
0x1800048e4  add     rsp, 20h
0x1800048e8  pop     rdi
0x1800048e9  retn
```
