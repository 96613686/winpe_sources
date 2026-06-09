# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800350d8`
- end: `0x180035176`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002c6b0`
- `0x180034cb0`
- `0x180034de0`
- `0x180035b90`
- `0x180036b6c`

## callees

- `0x1800350d8`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035121`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035121`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035136`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035136`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800350fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800350fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350ec`

## string_xrefs

- `0x18003511a`: `ntdll.dll`

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
0x1800350d8  mov     [rsp+arg_0], rbx
0x1800350dd  mov     [rsp+arg_8], rsi
0x1800350e2  push    rdi
0x1800350e3  sub     rsp, 20h
0x1800350e7  mov     rbx, rdx
0x1800350ea  mov     edi, ecx
0x1800350ec  call    cs:__imp_GetProcessHeap
0x1800350f2  mov     rsi, rax
0x1800350f5  mov     r8, rbx; dwBytes
0x1800350f8  mov     edx, edi; dwFlags
0x1800350fa  mov     rcx, rax; hHeap
0x1800350fd  call    cs:__imp_HeapAlloc
0x180035103  mov     rbx, rax
0x180035106  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003510d  test    rax, rax
0x180035110  jnz     short loc_180035158
0x180035112  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180035118  jnz     short loc_180035163
0x18003511a  lea     rcx, LibFileName; "ntdll.dll"
0x180035121  call    cs:__imp_GetModuleHandleW
0x180035127  test    rax, rax
0x18003512a  jz      short loc_180035145
0x18003512c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180035133  mov     rcx, rax; hModule
0x180035136  call    cs:__imp_GetProcAddress
0x18003513c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180035143  jmp     short loc_18003514C
0x180035145  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003514c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180035153  test    rax, rax
0x180035156  jz      short loc_180035163
0x180035158  mov     rdx, rbx
0x18003515b  mov     rcx, rsi
0x18003515e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035163  mov     rax, rbx
0x180035166  mov     rbx, [rsp+28h+arg_0]
0x18003516b  mov     rsi, [rsp+28h+arg_8]
0x180035170  add     rsp, 20h
0x180035174  pop     rdi
0x180035175  retn
```
