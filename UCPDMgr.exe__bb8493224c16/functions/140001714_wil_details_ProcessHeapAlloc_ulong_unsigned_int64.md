# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140001714`
- end: `0x1400017b2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400034ac`
- `0x140003910`
- `0x140003b20`
- `0x140005ba4`

## callees

- `0x140001714`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140001739`
- `KERNEL32!HeapAlloc` at `0x140001739`
- `KERNEL32!GetProcAddress` at `0x140001772`
- `KERNEL32!GetProcAddress` at `0x140001772`
- `KERNEL32!GetProcessHeap` at `0x140001728`
- `KERNEL32!GetProcessHeap` at `0x140001728`
- `KERNEL32!GetModuleHandleW` at `0x14000175d`
- `KERNEL32!GetModuleHandleW` at `0x14000175d`

## string_xrefs

- `0x140001756`: `ntdll.dll`

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
0x140001714  mov     [rsp+arg_0], rbx
0x140001719  mov     [rsp+arg_8], rsi
0x14000171e  push    rdi
0x14000171f  sub     rsp, 20h
0x140001723  mov     rbx, rdx
0x140001726  mov     edi, ecx
0x140001728  call    cs:__imp_GetProcessHeap
0x14000172e  mov     rsi, rax
0x140001731  mov     r8, rbx; dwBytes
0x140001734  mov     edx, edi; dwFlags
0x140001736  mov     rcx, rax; hHeap
0x140001739  call    cs:__imp_HeapAlloc
0x14000173f  mov     rbx, rax
0x140001742  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140001749  test    rax, rax
0x14000174c  jnz     short loc_140001794
0x14000174e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140001754  jnz     short loc_14000179F
0x140001756  lea     rcx, ModuleName; "ntdll.dll"
0x14000175d  call    cs:__imp_GetModuleHandleW
0x140001763  test    rax, rax
0x140001766  jz      short loc_140001781
0x140001768  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x14000176f  mov     rcx, rax; hModule
0x140001772  call    cs:__imp_GetProcAddress
0x140001778  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000177f  jmp     short loc_140001788
0x140001781  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140001788  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000178f  test    rax, rax
0x140001792  jz      short loc_14000179F
0x140001794  mov     rdx, rbx
0x140001797  mov     rcx, rsi
0x14000179a  call    _guard_dispatch_icall
0x14000179f  mov     rax, rbx
0x1400017a2  mov     rbx, [rsp+28h+arg_0]
0x1400017a7  mov     rsi, [rsp+28h+arg_8]
0x1400017ac  add     rsp, 20h
0x1400017b0  pop     rdi
0x1400017b1  retn
```
