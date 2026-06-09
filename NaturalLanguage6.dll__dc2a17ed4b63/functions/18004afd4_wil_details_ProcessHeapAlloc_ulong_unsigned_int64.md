# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004afd4`
- end: `0x18004b07c`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004a83c`
- `0x18004c10c`
- `0x18004c2d8`
- `0x1800671bc`
- `0x18006930c`

## callees

- `0x18004afd4`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b03c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b03c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004b027`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004b027`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aff2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aff2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b003`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b003`

## string_xrefs

- `0x18004b020`: `ntdll.dll`

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
0x18004afd4  push    rdi
0x18004afd6  sub     rsp, 30h
0x18004afda  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18004afe3  mov     [rsp+38h+arg_0], rbx
0x18004afe8  mov     [rsp+38h+arg_8], rsi
0x18004afed  mov     rbx, rdx
0x18004aff0  mov     edi, ecx
0x18004aff2  call    cs:__imp_GetProcessHeap
0x18004aff8  mov     rsi, rax
0x18004affb  mov     r8, rbx; dwBytes
0x18004affe  mov     edx, edi; dwFlags
0x18004b000  mov     rcx, rax; hHeap
0x18004b003  call    cs:__imp_HeapAlloc
0x18004b009  mov     rbx, rax
0x18004b00c  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004b013  test    rax, rax
0x18004b016  jnz     short loc_18004B05E
0x18004b018  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004b01e  jnz     short loc_18004B069
0x18004b020  lea     rcx, aNtdllDll; "ntdll.dll"
0x18004b027  call    cs:__imp_GetModuleHandleW
0x18004b02d  test    rax, rax
0x18004b030  jz      short loc_18004B04B
0x18004b032  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18004b039  mov     rcx, rax; hModule
0x18004b03c  call    cs:__imp_GetProcAddress
0x18004b042  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18004b049  jmp     short loc_18004B052
0x18004b04b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004b052  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004b059  test    rax, rax
0x18004b05c  jz      short loc_18004B069
0x18004b05e  mov     rdx, rbx
0x18004b061  mov     rcx, rsi
0x18004b064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b069  mov     rax, rbx
0x18004b06c  mov     rbx, [rsp+38h+arg_0]
0x18004b071  mov     rsi, [rsp+38h+arg_8]
0x18004b076  add     rsp, 30h
0x18004b07a  pop     rdi
0x18004b07b  retn
```
