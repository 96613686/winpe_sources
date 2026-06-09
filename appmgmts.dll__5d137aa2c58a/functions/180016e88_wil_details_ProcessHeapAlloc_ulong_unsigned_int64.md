# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180016e88`
- end: `0x180016f26`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014d7c`
- `0x180015120`
- `0x180015d20`
- `0x1800182a4`
- `0x18001980c`

## callees

- `0x180016e88`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016ee6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016ee6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016ed1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016ed1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ead`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ead`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016e9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016e9c`

## string_xrefs

- `0x180016eca`: `ntdll.dll`

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
0x180016e88  mov     [rsp+arg_0], rbx
0x180016e8d  mov     [rsp+arg_8], rsi
0x180016e92  push    rdi
0x180016e93  sub     rsp, 20h
0x180016e97  mov     rbx, rdx
0x180016e9a  mov     edi, ecx
0x180016e9c  call    cs:__imp_GetProcessHeap
0x180016ea2  mov     rsi, rax
0x180016ea5  mov     r8, rbx; dwBytes
0x180016ea8  mov     edx, edi; dwFlags
0x180016eaa  mov     rcx, rax; hHeap
0x180016ead  call    cs:__imp_HeapAlloc
0x180016eb3  mov     rbx, rax
0x180016eb6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180016ebd  test    rax, rax
0x180016ec0  jnz     short loc_180016F08
0x180016ec2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180016ec8  jnz     short loc_180016F13
0x180016eca  lea     rcx, ModuleName; "ntdll.dll"
0x180016ed1  call    cs:__imp_GetModuleHandleW
0x180016ed7  test    rax, rax
0x180016eda  jz      short loc_180016EF5
0x180016edc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180016ee3  mov     rcx, rax; hModule
0x180016ee6  call    cs:__imp_GetProcAddress
0x180016eec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180016ef3  jmp     short loc_180016EFC
0x180016ef5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180016efc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180016f03  test    rax, rax
0x180016f06  jz      short loc_180016F13
0x180016f08  mov     rdx, rbx
0x180016f0b  mov     rcx, rsi
0x180016f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f13  mov     rax, rbx
0x180016f16  mov     rbx, [rsp+28h+arg_0]
0x180016f1b  mov     rsi, [rsp+28h+arg_8]
0x180016f20  add     rsp, 20h
0x180016f24  pop     rdi
0x180016f25  retn
```
