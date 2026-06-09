# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005bb8`
- end: `0x140005c6f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005934`
- `0x14000667c`
- `0x140006a30`

## callees

- `0x140005bb8`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005c28`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005c28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005c0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005c0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005be3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005be3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005bcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005bcc`

## string_xrefs

- `0x140005c06`: `ntdll.dll`

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
0x140005bb8  mov     [rsp+arg_0], rbx
0x140005bbd  mov     [rsp+arg_8], rsi
0x140005bc2  push    rdi
0x140005bc3  sub     rsp, 20h
0x140005bc7  mov     rbx, rdx
0x140005bca  mov     edi, ecx
0x140005bcc  call    cs:__imp_GetProcessHeap
0x140005bd3  nop     dword ptr [rax+rax+00h]
0x140005bd8  mov     rsi, rax
0x140005bdb  mov     r8, rbx; dwBytes
0x140005bde  mov     edx, edi; dwFlags
0x140005be0  mov     rcx, rax; hHeap
0x140005be3  call    cs:__imp_HeapAlloc
0x140005bea  nop     dword ptr [rax+rax+00h]
0x140005bef  mov     rbx, rax
0x140005bf2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005bf9  test    rax, rax
0x140005bfc  jnz     short loc_140005C50
0x140005bfe  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005c04  jnz     short loc_140005C5B
0x140005c06  lea     rcx, ModuleName; "ntdll.dll"
0x140005c0d  call    cs:__imp_GetModuleHandleW
0x140005c14  nop     dword ptr [rax+rax+00h]
0x140005c19  test    rax, rax
0x140005c1c  jz      short loc_140005C3D
0x140005c1e  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140005c25  mov     rcx, rax; hModule
0x140005c28  call    cs:__imp_GetProcAddress
0x140005c2f  nop     dword ptr [rax+rax+00h]
0x140005c34  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005c3b  jmp     short loc_140005C44
0x140005c3d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005c44  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005c4b  test    rax, rax
0x140005c4e  jz      short loc_140005C5B
0x140005c50  mov     rdx, rbx
0x140005c53  mov     rcx, rsi
0x140005c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c5b  mov     rax, rbx
0x140005c5e  mov     rbx, [rsp+28h+arg_0]
0x140005c63  mov     rsi, [rsp+28h+arg_8]
0x140005c68  add     rsp, 20h
0x140005c6c  pop     rdi
0x140005c6d  retn
```
