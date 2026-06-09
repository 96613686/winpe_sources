# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005088`
- end: `0x140005126`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003960`
- `0x140005968`
- `0x140008710`
- `0x14000d7d4`

## callees

- `0x140005088`
- `0x14000f010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400050ad`
- `KERNEL32!HeapAlloc` at `0x1400050ad`
- `KERNEL32!GetProcAddress` at `0x1400050e6`
- `KERNEL32!GetProcAddress` at `0x1400050e6`
- `KERNEL32!GetProcessHeap` at `0x14000509c`
- `KERNEL32!GetProcessHeap` at `0x14000509c`
- `KERNEL32!GetModuleHandleW` at `0x1400050d1`
- `KERNEL32!GetModuleHandleW` at `0x1400050d1`

## string_xrefs

- `0x1400050ca`: `ntdll.dll`

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
0x140005088  mov     [rsp+arg_0], rbx
0x14000508d  mov     [rsp+arg_8], rsi
0x140005092  push    rdi
0x140005093  sub     rsp, 20h
0x140005097  mov     rbx, rdx
0x14000509a  mov     edi, ecx
0x14000509c  call    cs:__imp_GetProcessHeap
0x1400050a2  mov     rsi, rax
0x1400050a5  mov     r8, rbx; dwBytes
0x1400050a8  mov     edx, edi; dwFlags
0x1400050aa  mov     rcx, rax; hHeap
0x1400050ad  call    cs:__imp_HeapAlloc
0x1400050b3  mov     rbx, rax
0x1400050b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400050bd  test    rax, rax
0x1400050c0  jnz     short loc_140005108
0x1400050c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400050c8  jnz     short loc_140005113
0x1400050ca  lea     rcx, ModuleName; "ntdll.dll"
0x1400050d1  call    cs:__imp_GetModuleHandleW
0x1400050d7  test    rax, rax
0x1400050da  jz      short loc_1400050F5
0x1400050dc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400050e3  mov     rcx, rax; hModule
0x1400050e6  call    cs:__imp_GetProcAddress
0x1400050ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400050f3  jmp     short loc_1400050FC
0x1400050f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400050fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005103  test    rax, rax
0x140005106  jz      short loc_140005113
0x140005108  mov     rdx, rbx
0x14000510b  mov     rcx, rsi
0x14000510e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005113  mov     rax, rbx
0x140005116  mov     rbx, [rsp+28h+arg_0]
0x14000511b  mov     rsi, [rsp+28h+arg_8]
0x140005120  add     rsp, 20h
0x140005124  pop     rdi
0x140005125  retn
```
