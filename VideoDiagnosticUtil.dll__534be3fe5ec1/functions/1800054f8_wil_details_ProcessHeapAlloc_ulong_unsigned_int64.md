# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800054f8`
- end: `0x1800055af`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003354`
- `0x180003700`
- `0x1800041a0`
- `0x180006894`
- `0x180008360`

## callees

- `0x1800054f8`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180005568`
- `KERNEL32!GetProcAddress` at `0x180005568`
- `KERNEL32!GetModuleHandleW` at `0x18000554d`
- `KERNEL32!GetModuleHandleW` at `0x18000554d`
- `KERNEL32!HeapAlloc` at `0x180005523`
- `KERNEL32!HeapAlloc` at `0x180005523`
- `KERNEL32!GetProcessHeap` at `0x18000550c`
- `KERNEL32!GetProcessHeap` at `0x18000550c`

## string_xrefs

- `0x180005546`: `ntdll.dll`

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
0x1800054f8  mov     [rsp+arg_0], rbx
0x1800054fd  mov     [rsp+arg_8], rsi
0x180005502  push    rdi
0x180005503  sub     rsp, 20h
0x180005507  mov     rbx, rdx
0x18000550a  mov     edi, ecx
0x18000550c  call    cs:__imp_GetProcessHeap
0x180005513  nop     dword ptr [rax+rax+00h]
0x180005518  mov     r8, rbx; dwBytes
0x18000551b  mov     edx, edi; dwFlags
0x18000551d  mov     rcx, rax; hHeap
0x180005520  mov     rsi, rax
0x180005523  call    cs:__imp_HeapAlloc
0x18000552a  nop     dword ptr [rax+rax+00h]
0x18000552f  mov     rbx, rax
0x180005532  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005539  test    rax, rax
0x18000553c  jnz     short loc_180005590
0x18000553e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005544  jnz     short loc_18000559B
0x180005546  lea     rcx, ModuleName; "ntdll.dll"
0x18000554d  call    cs:__imp_GetModuleHandleW
0x180005554  nop     dword ptr [rax+rax+00h]
0x180005559  test    rax, rax
0x18000555c  jz      short loc_18000557D
0x18000555e  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005565  mov     rcx, rax; hModule
0x180005568  call    cs:__imp_GetProcAddress
0x18000556f  nop     dword ptr [rax+rax+00h]
0x180005574  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000557b  jmp     short loc_180005584
0x18000557d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005584  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000558b  test    rax, rax
0x18000558e  jz      short loc_18000559B
0x180005590  mov     rdx, rbx
0x180005593  mov     rcx, rsi
0x180005596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000559b  mov     rsi, [rsp+28h+arg_8]
0x1800055a0  mov     rax, rbx
0x1800055a3  mov     rbx, [rsp+28h+arg_0]
0x1800055a8  add     rsp, 20h
0x1800055ac  pop     rdi
0x1800055ad  retn
```
