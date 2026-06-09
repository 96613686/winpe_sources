# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800055ac`
- end: `0x18000564a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003ad0`
- `0x180006198`
- `0x180008f1c`
- `0x18000d014`

## callees

- `0x1800055ac`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000560a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000560a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800055d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800055d1`

## string_xrefs

- `0x1800055ee`: `ntdll.dll`

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
0x1800055ac  mov     [rsp+arg_0], rbx
0x1800055b1  mov     [rsp+arg_8], rsi
0x1800055b6  push    rdi
0x1800055b7  sub     rsp, 20h
0x1800055bb  mov     rbx, rdx
0x1800055be  mov     edi, ecx
0x1800055c0  call    cs:__imp_GetProcessHeap
0x1800055c6  mov     rsi, rax
0x1800055c9  mov     r8, rbx; dwBytes
0x1800055cc  mov     edx, edi; dwFlags
0x1800055ce  mov     rcx, rax; hHeap
0x1800055d1  call    cs:__imp_HeapAlloc
0x1800055d7  mov     rbx, rax
0x1800055da  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800055e1  test    rax, rax
0x1800055e4  jnz     short loc_18000562C
0x1800055e6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800055ec  jnz     short loc_180005637
0x1800055ee  lea     rcx, ModuleName; "ntdll.dll"
0x1800055f5  call    cs:__imp_GetModuleHandleW
0x1800055fb  test    rax, rax
0x1800055fe  jz      short loc_180005619
0x180005600  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005607  mov     rcx, rax; hModule
0x18000560a  call    cs:__imp_GetProcAddress
0x180005610  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005617  jmp     short loc_180005620
0x180005619  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005620  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005627  test    rax, rax
0x18000562a  jz      short loc_180005637
0x18000562c  mov     rdx, rbx
0x18000562f  mov     rcx, rsi
0x180005632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005637  mov     rax, rbx
0x18000563a  mov     rbx, [rsp+28h+arg_0]
0x18000563f  mov     rsi, [rsp+28h+arg_8]
0x180005644  add     rsp, 20h
0x180005648  pop     rdi
0x180005649  retn
```
