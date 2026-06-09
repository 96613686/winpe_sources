# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000bc90`
- end: `0x14000bd2e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140009088`
- `0x14000942c`
- `0x14000d89c`
- `0x14000f454`

## callees

- `0x14000bc90`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bcd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bcd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bcee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bcee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bcb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bcb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bca4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bca4`

## string_xrefs

- `0x14000bcd2`: `ntdll.dll`

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
0x14000bc90  mov     [rsp+arg_0], rbx
0x14000bc95  mov     [rsp+arg_8], rsi
0x14000bc9a  push    rdi
0x14000bc9b  sub     rsp, 20h
0x14000bc9f  mov     rbx, rdx
0x14000bca2  mov     edi, ecx
0x14000bca4  call    cs:__imp_GetProcessHeap
0x14000bcaa  mov     rsi, rax
0x14000bcad  mov     r8, rbx; dwBytes
0x14000bcb0  mov     edx, edi; dwFlags
0x14000bcb2  mov     rcx, rax; hHeap
0x14000bcb5  call    cs:__imp_HeapAlloc
0x14000bcbb  mov     rbx, rax
0x14000bcbe  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000bcc5  test    rax, rax
0x14000bcc8  jnz     short loc_14000BD10
0x14000bcca  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000bcd0  jnz     short loc_14000BD1B
0x14000bcd2  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000bcd9  call    cs:__imp_GetModuleHandleW
0x14000bcdf  test    rax, rax
0x14000bce2  jz      short loc_14000BCFD
0x14000bce4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000bceb  mov     rcx, rax; hModule
0x14000bcee  call    cs:__imp_GetProcAddress
0x14000bcf4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000bcfb  jmp     short loc_14000BD04
0x14000bcfd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000bd04  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000bd0b  test    rax, rax
0x14000bd0e  jz      short loc_14000BD1B
0x14000bd10  mov     rdx, rbx
0x14000bd13  mov     rcx, rsi
0x14000bd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd1b  mov     rax, rbx
0x14000bd1e  mov     rbx, [rsp+28h+arg_0]
0x14000bd23  mov     rsi, [rsp+28h+arg_8]
0x14000bd28  add     rsp, 20h
0x14000bd2c  pop     rdi
0x14000bd2d  retn
```
