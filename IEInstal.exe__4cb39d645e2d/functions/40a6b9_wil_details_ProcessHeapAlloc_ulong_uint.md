# wil::details::ProcessHeapAlloc(ulong,uint)

- ea: `0x40a6b9`
- end: `0x40a730`
- name: `?ProcessHeapAlloc@details@wil@@YGPAXKI@Z`
- size: `119`
- prototype: `LPVOID __fastcall(DWORD, SIZE_T)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x40b164`
- `0x40b2ec`
- `0x40c61e`

## callees

- `0x40a6b9`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x40a6fd`
- `KERNEL32!GetProcAddress` at `0x40a6fd`
- `KERNEL32!GetModuleHandleW` at `0x40a6ed`
- `KERNEL32!GetModuleHandleW` at `0x40a6ed`
- `KERNEL32!GetProcessHeap` at `0x40a6c2`
- `KERNEL32!GetProcessHeap` at `0x40a6c2`
- `KERNEL32!HeapAlloc` at `0x40a6cd`
- `KERNEL32!HeapAlloc` at `0x40a6cd`

## string_xrefs

- `0x40a6e8`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD a1, SIZE_T a2)
{
  HANDLE ProcessHeap; // ebx
  LPVOID v5; // eax
  FARPROC RtlDisownModuleHeapAllocation; // esi
  LPVOID v7; // edi
  HMODULE ModuleHandleW; // eax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, a1, a2);
  RtlDisownModuleHeapAllocation = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  v7 = v5;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (RtlDisownModuleHeapAllocation = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(RtlDisownModuleHeapAllocation = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (int)RtlDisownModuleHeapAllocation),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        RtlDisownModuleHeapAllocation) )
  {
    ((void (__thiscall *)(FARPROC, HANDLE, LPVOID))RtlDisownModuleHeapAllocation)(
      RtlDisownModuleHeapAllocation,
      ProcessHeap,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x40a6b9  mov     edi, edi
0x40a6bb  push    ebx
0x40a6bc  push    esi
0x40a6bd  push    edi
0x40a6be  mov     esi, edx
0x40a6c0  mov     edi, ecx
0x40a6c2  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x40a6c8  push    esi; dwBytes
0x40a6c9  mov     ebx, eax
0x40a6cb  push    edi; dwFlags
0x40a6cc  push    ebx; hHeap
0x40a6cd  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x40a6d3  mov     esi, ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA
0x40a6d9  mov     edi, eax
0x40a6db  test    esi, esi
0x40a6dd  jnz     short loc_40A71E
0x40a6df  cmp     ?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,uint)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x40a6e6  jnz     short loc_40A72A
0x40a6e8  push    offset aNtdllDll; "ntdll.dll"
0x40a6ed  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x40a6f3  test    eax, eax
0x40a6f5  jz      short loc_40A70D
0x40a6f7  push    offset aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x40a6fc  push    eax; hModule
0x40a6fd  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x40a703  mov     esi, eax
0x40a705  mov     ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA, esi
0x40a70b  jmp     short loc_40A713
0x40a70d  mov     esi, ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA
0x40a713  mov     ?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,uint)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x40a71a  test    esi, esi
0x40a71c  jz      short loc_40A72A
0x40a71e  push    edi
0x40a71f  push    ebx
0x40a720  mov     ecx, esi
0x40a722  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40a728  call    esi ; ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA
0x40a72a  mov     eax, edi
0x40a72c  pop     edi
0x40a72d  pop     esi
0x40a72e  pop     ebx
0x40a72f  retn
```
