# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140006638`
- end: `0x1400066d6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000576c`
- `0x1400062dc`
- `0x140006b50`
- `0x140006ee8`

## callees

- `0x140006638`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006681`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006681`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006696`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006696`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000665d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000665d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000664c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000664c`

## string_xrefs

- `0x14000667a`: `ntdll.dll`

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
0x140006638  mov     [rsp+arg_0], rbx
0x14000663d  mov     [rsp+arg_8], rsi
0x140006642  push    rdi
0x140006643  sub     rsp, 20h
0x140006647  mov     rbx, rdx
0x14000664a  mov     edi, ecx
0x14000664c  call    cs:__imp_GetProcessHeap
0x140006652  mov     rsi, rax
0x140006655  mov     r8, rbx; dwBytes
0x140006658  mov     edx, edi; dwFlags
0x14000665a  mov     rcx, rax; hHeap
0x14000665d  call    cs:__imp_HeapAlloc
0x140006663  mov     rbx, rax
0x140006666  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000666d  test    rax, rax
0x140006670  jnz     short loc_1400066B8
0x140006672  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006678  jnz     short loc_1400066C3
0x14000667a  lea     rcx, ModuleName; "ntdll.dll"
0x140006681  call    cs:__imp_GetModuleHandleW
0x140006687  test    rax, rax
0x14000668a  jz      short loc_1400066A5
0x14000668c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140006693  mov     rcx, rax; hModule
0x140006696  call    cs:__imp_GetProcAddress
0x14000669c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400066a3  jmp     short loc_1400066AC
0x1400066a5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400066ac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400066b3  test    rax, rax
0x1400066b6  jz      short loc_1400066C3
0x1400066b8  mov     rdx, rbx
0x1400066bb  mov     rcx, rsi
0x1400066be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066c3  mov     rax, rbx
0x1400066c6  mov     rbx, [rsp+28h+arg_0]
0x1400066cb  mov     rsi, [rsp+28h+arg_8]
0x1400066d0  add     rsp, 20h
0x1400066d4  pop     rdi
0x1400066d5  retn
```
