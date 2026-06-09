# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180027370`
- end: `0x18002749a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027260`

## callees

- `0x180027370`
- `0x18009d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180027484`
- `KERNEL32!GetProcAddress` at `0x180027484`
- `KERNEL32!GetModuleHandleW` at `0x18002745a`
- `KERNEL32!GetModuleHandleW` at `0x18002745a`
- `KERNEL32!HeapAlloc` at `0x1800273f6`
- `KERNEL32!HeapAlloc` at `0x1800273f6`
- `KERNEL32!GetProcessHeap` at `0x1800273e2`
- `KERNEL32!GetProcessHeap` at `0x1800273e2`
- `KERNEL32!GetCurrentThreadId` at `0x180027385`
- `KERNEL32!GetCurrentThreadId` at `0x180027385`

## string_xrefs

- `0x180027453`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v3; // rbp
  unsigned __int64 CurrentThreadId; // rbx
  unsigned __int64 v5; // r14
  __int64 i; // rax
  HANDLE ProcessHeap; // rsi
  _DWORD *v9; // rdi
  FARPROC ProcAddress; // rax
  signed __int64 v11; // rax
  HMODULE ModuleHandleW; // rax

  v3 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v5 = 8 * ((CurrentThreadId >> 2) % 0xA);
  for ( i = *(_QWORD *)(v5 + v3); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      return (char *)(i + 16);
  }
  if ( !a2 )
    return 0;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 0x18u);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) != 0
      ? (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress)
      : (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, _DWORD *))ProcAddress)(ProcessHeap, v9);
  }
  if ( !v9 )
    return 0;
  *v9 = CurrentThreadId;
  v9[1] = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  do
  {
    v11 = *(_QWORD *)(v5 + v3);
    *((_QWORD *)v9 + 1) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v3), (signed __int64)v9, v11) );
  return (char *)(v9 + 4);
}

```

## disassembly

```asm
0x180027370  push    rbx
0x180027372  push    rbp
0x180027373  push    rsi
0x180027374  push    rdi
0x180027375  push    r14
0x180027377  sub     rsp, 20h
0x18002737b  movzx   edi, dl
0x18002737e  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180027385  call    cs:__imp_GetCurrentThreadId
0x18002738b  mov     ebx, eax
0x18002738d  mov     r8d, eax
0x180027390  shr     r8, 2
0x180027394  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002739e  mul     r8
0x1800273a1  shr     rdx, 3
0x1800273a5  lea     rcx, [rdx+rdx*4]
0x1800273a9  add     rcx, rcx
0x1800273ac  sub     r8, rcx
0x1800273af  lea     r14, ds:0[r8*8]
0x1800273b7  mov     rax, [r14+rbp]
0x1800273bb  test    rax, rax
0x1800273be  jz      short loc_1800273D9
0x1800273c0  cmp     [rax], ebx
0x1800273c2  jnz     short loc_1800273D3
0x1800273c4  add     rax, 10h
0x1800273c8  add     rsp, 20h
0x1800273cc  pop     r14
0x1800273ce  pop     rdi
0x1800273cf  pop     rsi
0x1800273d0  pop     rbp
0x1800273d1  pop     rbx
0x1800273d2  retn
0x1800273d3  mov     rax, [rax+8]
0x1800273d7  jmp     short loc_1800273BB
0x1800273d9  test    dil, dil
0x1800273dc  jz      loc_180027493
0x1800273e2  call    cs:__imp_GetProcessHeap
0x1800273e8  mov     rsi, rax
0x1800273eb  xor     edx, edx; dwFlags
0x1800273ed  mov     r8d, 18h; dwBytes
0x1800273f3  mov     rcx, rax; hHeap
0x1800273f6  call    cs:__imp_HeapAlloc
0x1800273fc  mov     rdi, rax
0x1800273ff  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180027406  test    rax, rax
0x180027409  jz      short loc_18002744A
0x18002740b  mov     rdx, rdi
0x18002740e  mov     rcx, rsi
0x180027411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027416  nop
0x180027417  test    rdi, rdi
0x18002741a  jz      short loc_180027493
0x18002741c  mov     [rdi], ebx
0x18002741e  xor     eax, eax
0x180027420  mov     [rdi+4], eax
0x180027423  mov     [rdi+8], rax
0x180027427  mov     [rdi+10h], rax
0x18002742b  mov     rax, [r14+rbp]
0x18002742f  mov     [rdi+8], rax
0x180027433  lock cmpxchg [r14+rbp], rdi
0x180027439  jnz     short loc_18002742B
0x18002743b  lea     rax, [rdi+10h]
0x18002743f  add     rsp, 20h
0x180027443  pop     r14
0x180027445  pop     rdi
0x180027446  pop     rsi
0x180027447  pop     rbp
0x180027448  pop     rbx
0x180027449  retn
0x18002744a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180027451  jnz     short loc_180027417
0x180027453  lea     rcx, ModuleName; "ntdll.dll"
0x18002745a  call    cs:__imp_GetModuleHandleW
0x180027460  test    rax, rax
0x180027463  jnz     short loc_18002747A
0x180027465  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002746c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180027473  test    rax, rax
0x180027476  jnz     short loc_18002740B
0x180027478  jmp     short loc_180027417
0x18002747a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180027481  mov     rcx, rax; hModule
0x180027484  call    cs:__imp_GetProcAddress
0x18002748a  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180027491  jmp     short loc_18002746C
0x180027493  xor     eax, eax
0x180027495  jmp     loc_1800273C8
```
