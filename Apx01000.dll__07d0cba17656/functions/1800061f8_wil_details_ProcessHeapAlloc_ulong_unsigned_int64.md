# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800061f8`
- end: `0x180006296`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003f58`
- `0x1800042fc`
- `0x180004fa0`
- `0x1800078b4`
- `0x18000911c`

## callees

- `0x1800061f8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006241`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006241`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006256`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006256`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000621d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000621d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000620c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000620c`

## string_xrefs

- `0x18000623a`: `ntdll.dll`

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
0x1800061f8  mov     [rsp+arg_0], rbx
0x1800061fd  mov     [rsp+arg_8], rsi
0x180006202  push    rdi
0x180006203  sub     rsp, 20h
0x180006207  mov     rbx, rdx
0x18000620a  mov     edi, ecx
0x18000620c  call    cs:__imp_GetProcessHeap
0x180006212  mov     rsi, rax
0x180006215  mov     r8, rbx; dwBytes
0x180006218  mov     edx, edi; dwFlags
0x18000621a  mov     rcx, rax; hHeap
0x18000621d  call    cs:__imp_HeapAlloc
0x180006223  mov     rbx, rax
0x180006226  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000622d  test    rax, rax
0x180006230  jnz     short loc_180006278
0x180006232  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006238  jnz     short loc_180006283
0x18000623a  lea     rcx, ModuleName; "ntdll.dll"
0x180006241  call    cs:__imp_GetModuleHandleW
0x180006247  test    rax, rax
0x18000624a  jz      short loc_180006265
0x18000624c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006253  mov     rcx, rax; hModule
0x180006256  call    cs:__imp_GetProcAddress
0x18000625c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006263  jmp     short loc_18000626C
0x180006265  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000626c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006273  test    rax, rax
0x180006276  jz      short loc_180006283
0x180006278  mov     rdx, rbx
0x18000627b  mov     rcx, rsi
0x18000627e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006283  mov     rax, rbx
0x180006286  mov     rbx, [rsp+28h+arg_0]
0x18000628b  mov     rsi, [rsp+28h+arg_8]
0x180006290  add     rsp, 20h
0x180006294  pop     rdi
0x180006295  retn
```
