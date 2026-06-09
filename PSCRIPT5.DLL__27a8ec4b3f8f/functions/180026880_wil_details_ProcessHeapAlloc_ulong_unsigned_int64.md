# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180026880`
- end: `0x180026937`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180024584`
- `0x180024960`
- `0x1800254e0`
- `0x180027de8`
- `0x180028e2c`

## callees

- `0x180026880`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800268d5`
- `KERNEL32!GetModuleHandleW` at `0x1800268d5`
- `KERNEL32!GetProcessHeap` at `0x180026894`
- `KERNEL32!GetProcessHeap` at `0x180026894`
- `KERNEL32!HeapAlloc` at `0x1800268ab`
- `KERNEL32!HeapAlloc` at `0x1800268ab`
- `KERNEL32!GetProcAddress` at `0x1800268f0`
- `KERNEL32!GetProcAddress` at `0x1800268f0`

## string_xrefs

- `0x1800268ce`: `ntdll.dll`

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
0x180026880  mov     [rsp+arg_0], rbx
0x180026885  mov     [rsp+arg_8], rsi
0x18002688a  push    rdi
0x18002688b  sub     rsp, 20h
0x18002688f  mov     rbx, rdx
0x180026892  mov     edi, ecx
0x180026894  call    cs:__imp_GetProcessHeap
0x18002689b  nop     dword ptr [rax+rax+00h]
0x1800268a0  mov     r8, rbx; dwBytes
0x1800268a3  mov     edx, edi; dwFlags
0x1800268a5  mov     rcx, rax; hHeap
0x1800268a8  mov     rsi, rax
0x1800268ab  call    cs:__imp_HeapAlloc
0x1800268b2  nop     dword ptr [rax+rax+00h]
0x1800268b7  mov     rbx, rax
0x1800268ba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800268c1  test    rax, rax
0x1800268c4  jnz     short loc_180026918
0x1800268c6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800268cc  jnz     short loc_180026923
0x1800268ce  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800268d5  call    cs:__imp_GetModuleHandleW
0x1800268dc  nop     dword ptr [rax+rax+00h]
0x1800268e1  test    rax, rax
0x1800268e4  jz      short loc_180026905
0x1800268e6  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800268ed  mov     rcx, rax; hModule
0x1800268f0  call    cs:__imp_GetProcAddress
0x1800268f7  nop     dword ptr [rax+rax+00h]
0x1800268fc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180026903  jmp     short loc_18002690C
0x180026905  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002690c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180026913  test    rax, rax
0x180026916  jz      short loc_180026923
0x180026918  mov     rdx, rbx
0x18002691b  mov     rcx, rsi
0x18002691e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026923  mov     rsi, [rsp+28h+arg_8]
0x180026928  mov     rax, rbx
0x18002692b  mov     rbx, [rsp+28h+arg_0]
0x180026930  add     rsp, 20h
0x180026934  pop     rdi
0x180026935  retn
```
