# Windows::Telemetry::Continuation::Continuation(wil::ActivityThreadWatcher &&)

- ea: `0x18004fab8`
- end: `0x18004fc22`
- name: `??0Continuation@Telemetry@Windows@@QEAA@$$QEAVActivityThreadWatcher@wil@@@Z`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180050a80`
- `0x180053b10`

## callees

- `0x18000856c`
- `0x180016180`
- `0x180019bc0`
- `0x18004fab8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fb01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fb01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fb66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fbe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fb66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fbe0`

## string_xrefs

- `0x18004fb84`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Telemetry::Continuation::Continuation(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  void **v5; // rdi
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v8; // rdi
  __int64 v9; // r14
  int v10; // ebx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 v13; // rax
  _QWORD *Local; // rax
  const struct wil::FailureInfo *v16; // rdx
  _BYTE v17[216]; // [rsp+20h] [rbp-D8h] BYREF
  void *retaddr; // [rsp+F8h] [rbp+0h]

  *(_QWORD *)a1 = &Windows::Telemetry::Continuation::`vftable';
  v4 = a1 + 8;
  *(_OWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 8) = *(_DWORD *)a2;
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 8);
  v5 = (void **)(a1 + 24);
  if ( *(_BYTE *)(a1 + 32) )
  {
    v6 = *v5;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
    *(_BYTE *)(v4 + 24) = 0;
  }
  *v5 = 0;
  *v5 = *(void **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = 0;
  *(_BYTE *)(v4 + 24) = *(_BYTE *)(a2 + 24);
  *(_BYTE *)(a2 + 24) = 0;
  v8 = (_QWORD *)(v4 + 32);
  v9 = a2 + 32;
  *(_QWORD *)(v4 + 32) = 0;
  *(_QWORD *)(v4 + 40) = *(_QWORD *)(v9 + 8);
  *(_QWORD *)(v4 + 48) = 0;
  *(_DWORD *)(v4 + 56) = 0;
  *(_QWORD *)(v4 + 64) = *(_QWORD *)(v9 + 32);
  *(_BYTE *)(v4 + 72) = 0;
  if ( *(_DWORD *)(v9 + 24) )
  {
    v10 = *(_DWORD *)(v9 + 24);
    if ( v10 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(v9 + 24) = 0;
    v12 = *(__int64 **)v9;
    while ( 1 )
    {
      v13 = *v12;
      if ( !*v12 )
        break;
      if ( v13 == v9 )
      {
        *v12 = *(_QWORD *)(v9 + 16);
        break;
      }
      v12 = (__int64 *)(v13 + 16);
      *(_QWORD *)v9 = v13 + 16;
    }
    *(_QWORD *)v9 = 0;
    if ( *(_DWORD *)(v4 + 56) )
    {
      memset_0(v17, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v17, v16);
    }
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v11) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v12,
                          v11);
      *v8 = Local;
      if ( Local )
      {
        *(_QWORD *)(v4 + 48) = *Local;
        *Local = v8;
        *(_DWORD *)(v4 + 56) = GetCurrentThreadId();
      }
    }
    else
    {
      *v8 = 0;
    }
  }
  *(_QWORD *)(v4 + 64) = v4;
  return a1;
}

```

## disassembly

```asm
0x18004fab8  push    rbx
0x18004faba  push    rbp
0x18004fabb  push    rsi
0x18004fabc  push    rdi
0x18004fabd  push    r14
0x18004fabf  push    r15
0x18004fac1  sub     rsp, 0C8h
0x18004fac8  mov     r14, rdx
0x18004facb  mov     r15, rcx
0x18004face  lea     rax, ??_7Continuation@Telemetry@Windows@@6B@; const Windows::Telemetry::Continuation::`vftable'
0x18004fad5  mov     [rcx], rax
0x18004fad8  lea     rsi, [rcx+8]
0x18004fadc  xorps   xmm0, xmm0
0x18004fadf  movups  xmmword ptr [rsi], xmm0
0x18004fae2  movups  xmmword ptr [rsi+10h], xmm0
0x18004fae6  mov     eax, [rdx]
0x18004fae8  mov     [rsi], eax
0x18004faea  mov     rax, [rdx+8]
0x18004faee  mov     [rsi+8], rax
0x18004faf2  lea     rdi, [rsi+10h]
0x18004faf6  xor     ebp, ebp
0x18004faf8  cmp     [rsi+18h], bpl
0x18004fafc  jz      short loc_18004FB19
0x18004fafe  mov     rbx, [rdi]
0x18004fb01  call    cs:__imp_GetProcessHeap
0x18004fb07  mov     r8, rbx; lpMem
0x18004fb0a  xor     edx, edx; dwFlags
0x18004fb0c  mov     rcx, rax; hHeap
0x18004fb0f  call    cs:__imp_HeapFree
0x18004fb15  mov     [rsi+18h], bpl
0x18004fb19  mov     [rdi], rbp
0x18004fb1c  mov     rax, [r14+10h]
0x18004fb20  mov     [rdi], rax
0x18004fb23  mov     [r14+10h], rbp
0x18004fb27  mov     al, [r14+18h]
0x18004fb2b  mov     [rsi+18h], al
0x18004fb2e  mov     [r14+18h], bpl
0x18004fb32  lea     rdi, [rsi+20h]
0x18004fb36  add     r14, 20h ; ' '
0x18004fb3a  mov     [rdi], rbp
0x18004fb3d  mov     rax, [r14+8]
0x18004fb41  mov     [rdi+8], rax
0x18004fb45  mov     [rdi+10h], rbp
0x18004fb49  mov     [rdi+18h], ebp
0x18004fb4c  mov     rax, [r14+20h]
0x18004fb50  mov     [rdi+20h], rax
0x18004fb54  mov     [rdi+28h], bpl
0x18004fb58  cmp     [r14+18h], ebp
0x18004fb5c  jz      loc_18004FBEE
0x18004fb62  mov     ebx, [r14+18h]
0x18004fb66  call    cs:__imp_GetCurrentThreadId
0x18004fb6c  cmp     ebx, eax
0x18004fb6e  jz      short loc_18004FB90
0x18004fb70  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18004fb77  test    rax, rax
0x18004fb7a  jz      short loc_18004FB90
0x18004fb7c  mov     rdx, [rsp+0F8h]
0x18004fb84  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18004fb8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb90  mov     [r14+18h], ebp
0x18004fb94  mov     rcx, [r14]
0x18004fb97  jmp     short loc_18004FBA5
0x18004fb99  cmp     rax, r14
0x18004fb9c  jz      short loc_18004FBAF
0x18004fb9e  lea     rcx, [rax+10h]
0x18004fba2  mov     [r14], rcx
0x18004fba5  mov     rax, [rcx]
0x18004fba8  test    rax, rax
0x18004fbab  jnz     short loc_18004FB99
0x18004fbad  jmp     short loc_18004FBB6
0x18004fbaf  mov     rax, [r14+10h]
0x18004fbb3  mov     [rcx], rax
0x18004fbb6  mov     [r14], rbp
0x18004fbb9  cmp     [rdi+18h], ebp
0x18004fbbc  jnz     short loc_18004FC05
0x18004fbbe  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, rbp; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004fbc5  jz      short loc_18004FBEB
0x18004fbc7  mov     dl, 1
0x18004fbc9  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18004fbce  mov     [rdi], rax
0x18004fbd1  test    rax, rax
0x18004fbd4  jz      short loc_18004FBEE
0x18004fbd6  mov     rcx, [rax]
0x18004fbd9  mov     [rdi+10h], rcx
0x18004fbdd  mov     [rax], rdi
0x18004fbe0  call    cs:__imp_GetCurrentThreadId
0x18004fbe6  mov     [rdi+18h], eax
0x18004fbe9  jmp     short loc_18004FBEE
0x18004fbeb  mov     [rdi], rbp
0x18004fbee  mov     [rsi+40h], rsi
0x18004fbf2  mov     rax, r15
0x18004fbf5  add     rsp, 0C8h
0x18004fbfc  pop     r15
0x18004fbfe  pop     r14
0x18004fc00  pop     rdi
0x18004fc01  pop     rsi
0x18004fc02  pop     rbp
0x18004fc03  pop     rbx
0x18004fc04  retn
0x18004fc05  xor     edx, edx; Val
0x18004fc07  mov     r8d, 98h; Size
0x18004fc0d  lea     rcx, [rsp+0F8h+var_D8]; void *
0x18004fc12  call    memset_0
0x18004fc17  lea     rcx, [rsp+0F8h+var_D8]; this
0x18004fc1c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
