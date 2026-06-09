# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002bdbc`
- end: `0x18002be5a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180028a60`
- `0x180028e30`
- `0x18002ab00`
- `0x18002e2cc`
- `0x1800302f4`

## callees

- `0x18002bdbc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002be1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002be1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002be05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002be05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bdd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bdd0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bde1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bde1`

## string_xrefs

- `0x18002bdfe`: `ntdll.dll`

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
0x18002bdbc  mov     [rsp+arg_0], rbx
0x18002bdc1  mov     [rsp+arg_8], rsi
0x18002bdc6  push    rdi
0x18002bdc7  sub     rsp, 20h
0x18002bdcb  mov     rbx, rdx
0x18002bdce  mov     edi, ecx
0x18002bdd0  call    cs:__imp_GetProcessHeap
0x18002bdd6  mov     rsi, rax
0x18002bdd9  mov     r8, rbx; dwBytes
0x18002bddc  mov     edx, edi; dwFlags
0x18002bdde  mov     rcx, rax; hHeap
0x18002bde1  call    cs:__imp_HeapAlloc
0x18002bde7  mov     rbx, rax
0x18002bdea  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002bdf1  test    rax, rax
0x18002bdf4  jnz     short loc_18002BE3C
0x18002bdf6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002bdfc  jnz     short loc_18002BE47
0x18002bdfe  lea     rcx, ModuleName; "ntdll.dll"
0x18002be05  call    cs:__imp_GetModuleHandleW
0x18002be0b  test    rax, rax
0x18002be0e  jz      short loc_18002BE29
0x18002be10  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18002be17  mov     rcx, rax; hModule
0x18002be1a  call    cs:__imp_GetProcAddress
0x18002be20  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002be27  jmp     short loc_18002BE30
0x18002be29  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002be30  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002be37  test    rax, rax
0x18002be3a  jz      short loc_18002BE47
0x18002be3c  mov     rdx, rbx
0x18002be3f  mov     rcx, rsi
0x18002be42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be47  mov     rax, rbx
0x18002be4a  mov     rbx, [rsp+28h+arg_0]
0x18002be4f  mov     rsi, [rsp+28h+arg_8]
0x18002be54  add     rsp, 20h
0x18002be58  pop     rdi
0x18002be59  retn
```
