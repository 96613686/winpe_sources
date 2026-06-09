# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800541ec`
- end: `0x180054294`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004e134`
- `0x180053d80`
- `0x180053ea4`
- `0x180054edc`
- `0x1800554d0`

## callees

- `0x1800541ec`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18005423f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18005423f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180054254`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180054254`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005420a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005420a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005421b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005421b`

## string_xrefs

- `0x180054238`: `ntdll.dll`

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
0x1800541ec  push    rdi
0x1800541ee  sub     rsp, 30h
0x1800541f2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800541fb  mov     [rsp+38h+arg_0], rbx
0x180054200  mov     [rsp+38h+arg_8], rsi
0x180054205  mov     rbx, rdx
0x180054208  mov     edi, ecx
0x18005420a  call    cs:__imp_GetProcessHeap
0x180054210  mov     rsi, rax
0x180054213  mov     r8, rbx; dwBytes
0x180054216  mov     edx, edi; dwFlags
0x180054218  mov     rcx, rax; hHeap
0x18005421b  call    cs:__imp_HeapAlloc
0x180054221  mov     rbx, rax
0x180054224  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18005422b  test    rax, rax
0x18005422e  jnz     short loc_180054276
0x180054230  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180054236  jnz     short loc_180054281
0x180054238  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18005423f  call    cs:__imp_GetModuleHandleW
0x180054245  test    rax, rax
0x180054248  jz      short loc_180054263
0x18005424a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180054251  mov     rcx, rax; hModule
0x180054254  call    cs:__imp_GetProcAddress
0x18005425a  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180054261  jmp     short loc_18005426A
0x180054263  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18005426a  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180054271  test    rax, rax
0x180054274  jz      short loc_180054281
0x180054276  mov     rdx, rbx
0x180054279  mov     rcx, rsi
0x18005427c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054281  mov     rax, rbx
0x180054284  mov     rbx, [rsp+38h+arg_0]
0x180054289  mov     rsi, [rsp+38h+arg_8]
0x18005428e  add     rsp, 30h
0x180054292  pop     rdi
0x180054293  retn
```
