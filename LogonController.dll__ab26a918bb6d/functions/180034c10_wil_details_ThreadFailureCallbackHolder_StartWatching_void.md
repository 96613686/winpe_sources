# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180034c10`
- end: `0x180034d8a`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `378`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d850`
- `0x18001f98c`
- `0x180034be4`
- `0x1800868f4`

## callees

- `0x180034c10`
- `0x180061f20`
- `0x18006cad0`
- `0x18009d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180034d56`
- `KERNEL32!GetProcAddress` at `0x180034d56`
- `KERNEL32!GetModuleHandleW` at `0x180034d2c`
- `KERNEL32!GetModuleHandleW` at `0x180034d2c`
- `KERNEL32!HeapAlloc` at `0x180034cc8`
- `KERNEL32!HeapAlloc` at `0x180034cc8`
- `KERNEL32!GetProcessHeap` at `0x180034cb4`
- `KERNEL32!GetProcessHeap` at `0x180034cb4`
- `KERNEL32!GetCurrentThreadId` at `0x180034c39`
- `KERNEL32!GetCurrentThreadId` at `0x180034c8e`
- `KERNEL32!GetCurrentThreadId` at `0x180034c39`
- `KERNEL32!GetCurrentThreadId` at `0x180034c8e`

## string_xrefs

- `0x180034d25`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rsi
  unsigned __int64 CurrentThreadId; // rdi
  unsigned __int64 v4; // r15
  __int64 i; // rax
  _QWORD *v6; // rcx
  HANDLE ProcessHeap; // rbp
  char *v8; // r14
  FARPROC ProcAddress; // rax
  signed __int64 v10; // rax
  HMODULE ModuleHandleW; // rax
  const struct wil::FailureInfo *v12; // rdx
  _BYTE v13[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v12);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = 8 * ((CurrentThreadId >> 2) % 0xA);
    for ( i = *(_QWORD *)(v4 + v2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        v6 = (_QWORD *)(i + 16);
        goto LABEL_7;
      }
    }
    ProcessHeap = GetProcessHeap();
    v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
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
      ((void (__fastcall *)(HANDLE, char *))ProcAddress)(ProcessHeap, v8);
    }
    if ( v8 )
    {
      *(_DWORD *)v8 = CurrentThreadId;
      *((_DWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 1) = 0;
      v6 = v8 + 16;
      *((_QWORD *)v8 + 2) = 0;
      do
      {
        v10 = *(_QWORD *)(v4 + v2);
        *((_QWORD *)v8 + 1) = v10;
      }
      while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + v2), (signed __int64)v8, v10) );
    }
    else
    {
      v6 = 0;
    }
LABEL_7:
    *(_QWORD *)this = v6;
    if ( v6 )
    {
      *((_QWORD *)this + 2) = *v6;
      *v6 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180034c10  push    rbx
0x180034c12  push    rbp
0x180034c13  push    rsi
0x180034c14  push    rdi
0x180034c15  push    r14
0x180034c17  push    r15
0x180034c19  sub     rsp, 0C8h
0x180034c20  mov     rbx, rcx
0x180034c23  cmp     dword ptr [rcx+18h], 0
0x180034c27  jnz     loc_180034D65
0x180034c2d  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180034c34  test    rsi, rsi
0x180034c37  jz      short loc_180034CAD
0x180034c39  call    cs:__imp_GetCurrentThreadId
0x180034c3f  mov     edi, eax
0x180034c41  mov     r8d, eax
0x180034c44  shr     r8, 2
0x180034c48  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180034c52  mul     r8
0x180034c55  shr     rdx, 3
0x180034c59  lea     rcx, [rdx+rdx*4]
0x180034c5d  add     rcx, rcx
0x180034c60  sub     r8, rcx
0x180034c63  lea     r15, ds:0[r8*8]
0x180034c6b  mov     rax, [r15+rsi]
0x180034c6f  test    rax, rax
0x180034c72  jz      short loc_180034CB4
0x180034c74  cmp     [rax], edi
0x180034c76  jnz     short loc_180034CA7
0x180034c78  lea     rcx, [rax+10h]
0x180034c7c  mov     [rbx], rcx
0x180034c7f  test    rcx, rcx
0x180034c82  jz      short loc_180034C97
0x180034c84  mov     rax, [rcx]
0x180034c87  mov     [rbx+10h], rax
0x180034c8b  mov     [rcx], rbx
0x180034c8e  call    cs:__imp_GetCurrentThreadId
0x180034c94  mov     [rbx+18h], eax
0x180034c97  add     rsp, 0C8h
0x180034c9e  pop     r15
0x180034ca0  pop     r14
0x180034ca2  pop     rdi
0x180034ca3  pop     rsi
0x180034ca4  pop     rbp
0x180034ca5  pop     rbx
0x180034ca6  retn
0x180034ca7  mov     rax, [rax+8]
0x180034cab  jmp     short loc_180034C6F
0x180034cad  xor     eax, eax
0x180034caf  mov     [rcx], rax
0x180034cb2  jmp     short loc_180034C97
0x180034cb4  call    cs:__imp_GetProcessHeap
0x180034cba  mov     rbp, rax
0x180034cbd  xor     edx, edx; dwFlags
0x180034cbf  mov     r8d, 18h; dwBytes
0x180034cc5  mov     rcx, rax; hHeap
0x180034cc8  call    cs:__imp_HeapAlloc
0x180034cce  mov     r14, rax
0x180034cd1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180034cd8  test    rax, rax
0x180034cdb  jz      short loc_180034D1C
0x180034cdd  mov     rdx, r14
0x180034ce0  mov     rcx, rbp
0x180034ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ce8  nop
0x180034ce9  xor     eax, eax
0x180034ceb  test    r14, r14
0x180034cee  jz      loc_180034D82
0x180034cf4  mov     [r14], edi
0x180034cf7  mov     [r14+4], eax
0x180034cfb  mov     [r14+8], rax
0x180034cff  lea     rcx, [r14+10h]
0x180034d03  mov     [rcx], rax
0x180034d06  mov     rax, [r15+rsi]
0x180034d0a  mov     [r14+8], rax
0x180034d0e  lock cmpxchg [r15+rsi], r14
0x180034d14  jz      loc_180034C7C
0x180034d1a  jmp     short loc_180034D06
0x180034d1c  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180034d23  jnz     short loc_180034CE9
0x180034d25  lea     rcx, ModuleName; "ntdll.dll"
0x180034d2c  call    cs:__imp_GetModuleHandleW
0x180034d32  test    rax, rax
0x180034d35  jnz     short loc_180034D4C
0x180034d37  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180034d3e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180034d45  test    rax, rax
0x180034d48  jnz     short loc_180034CDD
0x180034d4a  jmp     short loc_180034CE9
0x180034d4c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180034d53  mov     rcx, rax; hModule
0x180034d56  call    cs:__imp_GetProcAddress
0x180034d5c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180034d63  jmp     short loc_180034D3E
0x180034d65  xor     edx, edx; Val
0x180034d67  mov     r8d, 98h; Size
0x180034d6d  lea     rcx, [rsp+0F8h+var_D8]; void *
0x180034d72  call    memset_0
0x180034d77  lea     rcx, [rsp+0F8h+var_D8]; this
0x180034d7c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180034d82  mov     rcx, rax
0x180034d85  jmp     loc_180034C7C
```
