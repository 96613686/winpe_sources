# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005bc90`
- end: `0x18005bd49`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `185`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004bad4`
- `0x180059a80`
- `0x18005a120`
- `0x18005a590`
- `0x18005ba74`
- `0x18005c430`
- `0x18005c57c`

## callees

- `0x18005bc90`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005bce5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005bce5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005bd00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005bd00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bcbb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bcbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bca4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bca4`

## string_xrefs

- `0x18005bcde`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18005bc90  mov     [rsp+arg_0], rbx
0x18005bc95  mov     [rsp+arg_8], rsi
0x18005bc9a  push    rdi
0x18005bc9b  sub     rsp, 20h
0x18005bc9f  mov     rbx, rdx
0x18005bca2  mov     edi, ecx
0x18005bca4  call    cs:__imp_GetProcessHeap
0x18005bcab  nop     dword ptr [rax+rax+00h]
0x18005bcb0  mov     rsi, rax
0x18005bcb3  mov     r8, rbx; dwBytes
0x18005bcb6  mov     edx, edi; dwFlags
0x18005bcb8  mov     rcx, rax; hHeap
0x18005bcbb  call    cs:__imp_HeapAlloc
0x18005bcc2  nop     dword ptr [rax+rax+00h]
0x18005bcc7  mov     rbx, rax
0x18005bcca  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18005bcd1  test    rax, rax
0x18005bcd4  jnz     short loc_18005BD29
0x18005bcd6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18005bcdc  jnz     short loc_18005BD35
0x18005bcde  lea     rcx, ModuleName; "ntdll.dll"
0x18005bce5  call    cs:__imp_GetModuleHandleW
0x18005bcec  nop     dword ptr [rax+rax+00h]
0x18005bcf1  test    rax, rax
0x18005bcf4  jz      short loc_18005BD16
0x18005bcf6  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18005bcfd  mov     rcx, rax; hModule
0x18005bd00  call    cs:__imp_GetProcAddress
0x18005bd07  nop     dword ptr [rax+rax+00h]
0x18005bd0c  nop
0x18005bd0d  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18005bd14  jmp     short loc_18005BD1D
0x18005bd16  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18005bd1d  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18005bd24  test    rax, rax
0x18005bd27  jz      short loc_18005BD35
0x18005bd29  mov     rdx, rbx
0x18005bd2c  mov     rcx, rsi
0x18005bd2f  call    cs:__guard_dispatch_icall_fptr
0x18005bd35  mov     rax, rbx
0x18005bd38  mov     rbx, [rsp+28h+arg_0]
0x18005bd3d  mov     rsi, [rsp+28h+arg_8]
0x18005bd42  add     rsp, 20h
0x18005bd46  pop     rdi
0x18005bd47  retn
```
