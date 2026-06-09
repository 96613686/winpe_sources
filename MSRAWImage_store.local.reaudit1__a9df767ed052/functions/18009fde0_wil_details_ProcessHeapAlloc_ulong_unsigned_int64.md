# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18009fde0`
- end: `0x18009fea1`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `193`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18009fc2c`
- `0x1800a021c`
- `0x1800a05fc`

## callees

- `0x18009fde0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009fe5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009fe5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009fe3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009fe3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fdfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fdfe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fe15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fe15`

## string_xrefs

- `0x18009fe38`: `ntdll.dll`

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
0x18009fde0  push    rdi
0x18009fde2  sub     rsp, 30h
0x18009fde6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18009fdef  mov     [rsp+38h+arg_0], rbx
0x18009fdf4  mov     [rsp+38h+arg_8], rsi
0x18009fdf9  mov     rbx, rdx
0x18009fdfc  mov     edi, ecx
0x18009fdfe  call    cs:__imp_GetProcessHeap
0x18009fe05  nop     dword ptr [rax+rax+00h]
0x18009fe0a  mov     rsi, rax
0x18009fe0d  mov     r8, rbx; dwBytes
0x18009fe10  mov     edx, edi; dwFlags
0x18009fe12  mov     rcx, rax; hHeap
0x18009fe15  call    cs:__imp_HeapAlloc
0x18009fe1c  nop     dword ptr [rax+rax+00h]
0x18009fe21  mov     rbx, rax
0x18009fe24  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18009fe2b  test    rax, rax
0x18009fe2e  jnz     short loc_18009FE82
0x18009fe30  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18009fe36  jnz     short loc_18009FE8D
0x18009fe38  lea     rcx, ModuleName; "ntdll.dll"
0x18009fe3f  call    cs:__imp_GetModuleHandleW
0x18009fe46  nop     dword ptr [rax+rax+00h]
0x18009fe4b  test    rax, rax
0x18009fe4e  jz      short loc_18009FE6F
0x18009fe50  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18009fe57  mov     rcx, rax; hModule
0x18009fe5a  call    cs:__imp_GetProcAddress
0x18009fe61  nop     dword ptr [rax+rax+00h]
0x18009fe66  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18009fe6d  jmp     short loc_18009FE76
0x18009fe6f  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18009fe76  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18009fe7d  test    rax, rax
0x18009fe80  jz      short loc_18009FE8D
0x18009fe82  mov     rdx, rbx
0x18009fe85  mov     rcx, rsi
0x18009fe88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fe8d  mov     rax, rbx
0x18009fe90  mov     rbx, [rsp+38h+arg_0]
0x18009fe95  mov     rsi, [rsp+38h+arg_8]
0x18009fe9a  add     rsp, 30h
0x18009fe9e  pop     rdi
0x18009fe9f  retn
```
