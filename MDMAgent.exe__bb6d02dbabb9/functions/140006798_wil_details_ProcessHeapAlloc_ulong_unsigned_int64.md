# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140006798`
- end: `0x14000684f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400058a4`
- `0x140006510`
- `0x140006cd4`
- `0x140007088`
- `0x14000c1a0`
- `0x140011cd0`

## callees

- `0x140006798`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400067ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400067ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006808`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400067ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400067ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400067c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400067c3`

## string_xrefs

- `0x1400067e6`: `ntdll.dll`

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
0x140006798  mov     [rsp+arg_0], rbx
0x14000679d  mov     [rsp+arg_8], rsi
0x1400067a2  push    rdi
0x1400067a3  sub     rsp, 20h
0x1400067a7  mov     rbx, rdx
0x1400067aa  mov     edi, ecx
0x1400067ac  call    cs:__imp_GetProcessHeap
0x1400067b3  nop     dword ptr [rax+rax+00h]
0x1400067b8  mov     rsi, rax
0x1400067bb  mov     r8, rbx; dwBytes
0x1400067be  mov     edx, edi; dwFlags
0x1400067c0  mov     rcx, rax; hHeap
0x1400067c3  call    cs:__imp_HeapAlloc
0x1400067ca  nop     dword ptr [rax+rax+00h]
0x1400067cf  mov     rbx, rax
0x1400067d2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400067d9  test    rax, rax
0x1400067dc  jnz     short loc_140006830
0x1400067de  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400067e4  jnz     short loc_14000683B
0x1400067e6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1400067ed  call    cs:__imp_GetModuleHandleW
0x1400067f4  nop     dword ptr [rax+rax+00h]
0x1400067f9  test    rax, rax
0x1400067fc  jz      short loc_14000681D
0x1400067fe  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140006805  mov     rcx, rax; hModule
0x140006808  call    cs:__imp_GetProcAddress
0x14000680f  nop     dword ptr [rax+rax+00h]
0x140006814  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000681b  jmp     short loc_140006824
0x14000681d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006824  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000682b  test    rax, rax
0x14000682e  jz      short loc_14000683B
0x140006830  mov     rdx, rbx
0x140006833  mov     rcx, rsi
0x140006836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000683b  mov     rax, rbx
0x14000683e  mov     rbx, [rsp+28h+arg_0]
0x140006843  mov     rsi, [rsp+28h+arg_8]
0x140006848  add     rsp, 20h
0x14000684c  pop     rdi
0x14000684d  retn
```
