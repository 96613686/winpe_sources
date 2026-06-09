# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400107dc`
- end: `0x14001087a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000da1c`
- `0x14000f370`
- `0x14000f4d4`
- `0x140013eec`
- `0x140014380`
- `0x14001ac08`

## callees

- `0x1400107dc`
- `0x14001f010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140010801`
- `KERNEL32!HeapAlloc` at `0x140010801`
- `KERNEL32!GetProcAddress` at `0x14001083a`
- `KERNEL32!GetProcAddress` at `0x14001083a`
- `KERNEL32!GetProcessHeap` at `0x1400107f0`
- `KERNEL32!GetProcessHeap` at `0x1400107f0`
- `KERNEL32!GetModuleHandleW` at `0x140010825`
- `KERNEL32!GetModuleHandleW` at `0x140010825`

## string_xrefs

- `0x14001081e`: `ntdll.dll`

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
0x1400107dc  mov     [rsp+arg_0], rbx
0x1400107e1  mov     [rsp+arg_8], rsi
0x1400107e6  push    rdi
0x1400107e7  sub     rsp, 20h
0x1400107eb  mov     rbx, rdx
0x1400107ee  mov     edi, ecx
0x1400107f0  call    cs:__imp_GetProcessHeap
0x1400107f6  mov     r8, rbx; dwBytes
0x1400107f9  mov     edx, edi; dwFlags
0x1400107fb  mov     rcx, rax; hHeap
0x1400107fe  mov     rsi, rax
0x140010801  call    cs:__imp_HeapAlloc
0x140010807  mov     rbx, rax
0x14001080a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140010811  test    rax, rax
0x140010814  jnz     short loc_14001085C
0x140010816  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14001081c  jnz     short loc_140010867
0x14001081e  lea     rcx, ModuleName; "ntdll.dll"
0x140010825  call    cs:__imp_GetModuleHandleW
0x14001082b  test    rax, rax
0x14001082e  jz      short loc_140010849
0x140010830  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140010837  mov     rcx, rax; hModule
0x14001083a  call    cs:__imp_GetProcAddress
0x140010840  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140010847  jmp     short loc_140010850
0x140010849  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140010850  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140010857  test    rax, rax
0x14001085a  jz      short loc_140010867
0x14001085c  mov     rdx, rbx
0x14001085f  mov     rcx, rsi
0x140010862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010867  mov     rsi, [rsp+28h+arg_8]
0x14001086c  mov     rax, rbx
0x14001086f  mov     rbx, [rsp+28h+arg_0]
0x140010874  add     rsp, 20h
0x140010878  pop     rdi
0x140010879  retn
```
