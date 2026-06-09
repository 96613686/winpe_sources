# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000b3b4`
- end: `0x14000b452`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000af14`
- `0x14000b058`
- `0x14000c038`
- `0x14000c4ac`
- `0x14000db64`

## callees

- `0x14000b3b4`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b412`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b412`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b3fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b3fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b3d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b3d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3c8`

## string_xrefs

- `0x14000b3f6`: `ntdll.dll`

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
0x14000b3b4  mov     [rsp+arg_0], rbx
0x14000b3b9  mov     [rsp+arg_8], rsi
0x14000b3be  push    rdi
0x14000b3bf  sub     rsp, 20h
0x14000b3c3  mov     rbx, rdx
0x14000b3c6  mov     edi, ecx
0x14000b3c8  call    cs:__imp_GetProcessHeap
0x14000b3ce  mov     rsi, rax
0x14000b3d1  mov     r8, rbx; dwBytes
0x14000b3d4  mov     edx, edi; dwFlags
0x14000b3d6  mov     rcx, rax; hHeap
0x14000b3d9  call    cs:__imp_HeapAlloc
0x14000b3df  mov     rbx, rax
0x14000b3e2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000b3e9  test    rax, rax
0x14000b3ec  jnz     short loc_14000B434
0x14000b3ee  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000b3f4  jnz     short loc_14000B43F
0x14000b3f6  lea     rcx, ModuleName; "ntdll.dll"
0x14000b3fd  call    cs:__imp_GetModuleHandleW
0x14000b403  test    rax, rax
0x14000b406  jz      short loc_14000B421
0x14000b408  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000b40f  mov     rcx, rax; hModule
0x14000b412  call    cs:__imp_GetProcAddress
0x14000b418  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000b41f  jmp     short loc_14000B428
0x14000b421  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000b428  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000b42f  test    rax, rax
0x14000b432  jz      short loc_14000B43F
0x14000b434  mov     rdx, rbx
0x14000b437  mov     rcx, rsi
0x14000b43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b43f  mov     rax, rbx
0x14000b442  mov     rbx, [rsp+28h+arg_0]
0x14000b447  mov     rsi, [rsp+28h+arg_8]
0x14000b44c  add     rsp, 20h
0x14000b450  pop     rdi
0x14000b451  retn
```
