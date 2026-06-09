# wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)

- ea: `0x140014c1c`
- end: `0x140014e91`
- name: `??0?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140018fb0`
- `0x140019970`

## callees

- `0x1400068f0`
- `0x140014c1c`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014ca0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014ca0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014cae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014cae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140014dea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140014e2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140014dea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140014e2c`

## string_xrefs

- `0x140014e48`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2,
        char a3)
{
  __int64 v4; // rbp
  __int64 v6; // rdi
  __int64 v7; // r14
  void **v8; // r15
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v11; // rbx
  _QWORD *Local; // rax
  __int64 v13; // rax
  __int64 **v14; // rbx
  __int64 *v15; // rcx
  __int64 v16; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]

  v4 = a2;
  *(_QWORD *)a1 = &wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v6 = a1 + 8;
  v7 = a2 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  *(_BYTE *)(a1 + 12) = *(_BYTE *)(a2 + 12);
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(a2 + 32);
  *(_DWORD *)(a2 + 8) = 0;
  *(_BYTE *)(a2 + 12) = 0;
  *(_OWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 48) = *(_DWORD *)(a2 + 48);
  *(_QWORD *)(a1 + 56) = *(_QWORD *)(a2 + 56);
  v8 = (void **)(a1 + 64);
  if ( *(_BYTE *)(a1 + 72) )
  {
    v9 = *v8;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
    *(_BYTE *)(v6 + 64) = 0;
  }
  *v8 = 0;
  *v8 = *(void **)(v7 + 56);
  *(_QWORD *)(v7 + 56) = 0;
  *(_BYTE *)(v6 + 64) = *(_BYTE *)(v7 + 64);
  *(_BYTE *)(v7 + 64) = 0;
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(v4 + 80);
  *(_OWORD *)(a1 + 88) = *(_OWORD *)(v4 + 88);
  *(_OWORD *)(a1 + 104) = *(_OWORD *)(v4 + 104);
  *(_OWORD *)(a1 + 120) = *(_OWORD *)(v4 + 120);
  *(_OWORD *)(a1 + 136) = *(_OWORD *)(v4 + 136);
  *(_OWORD *)(a1 + 152) = *(_OWORD *)(v4 + 152);
  *(_OWORD *)(a1 + 168) = *(_OWORD *)(v4 + 168);
  *(_OWORD *)(a1 + 184) = *(_OWORD *)(v4 + 184);
  *(_OWORD *)(a1 + 200) = *(_OWORD *)(v4 + 200);
  *(_OWORD *)(a1 + 216) = *(_OWORD *)(v4 + 216);
  *(_QWORD *)(a1 + 232) = *(_QWORD *)(v4 + 232);
  *(_QWORD *)(a1 + 240) = *(_QWORD *)(v4 + 240);
  *(_QWORD *)(a1 + 248) = *(_QWORD *)(v4 + 248);
  *(_QWORD *)(v4 + 240) = 0;
  *(_QWORD *)(v4 + 248) = 0;
  *(_DWORD *)(a1 + 256) = *(_DWORD *)(v4 + 256);
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 280) = *(_QWORD *)(v4 + 280);
  *(_QWORD *)(v4 + 280) = 0;
  v11 = (_QWORD *)(a1 + 288);
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = a1;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  *(_BYTE *)(a1 + 328) = 0;
  if ( a3 )
  {
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(a2) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          a1,
                          a2);
      *v11 = Local;
      if ( Local )
      {
        *(_QWORD *)(a1 + 304) = *Local;
        *Local = v11;
        *(_DWORD *)(a1 + 312) = GetCurrentThreadId();
      }
    }
  }
  v13 = *(_QWORD *)(a1 + 280);
  if ( v13 )
    v6 = v13 + 8;
  *(_QWORD *)(a1 + 272) = v6;
  *(_QWORD *)(a1 + 320) = v6 + 40;
  *(_QWORD *)(v4 + 272) = v7;
  if ( *(_DWORD *)(v4 + 312) )
  {
    v14 = (__int64 **)(v4 + 288);
    if ( *(_DWORD *)(v4 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(v4 + 312) = 0;
    v15 = *v14;
    while ( 1 )
    {
      v16 = *v15;
      if ( !*v15 )
        break;
      if ( (__int64 **)v16 == v14 )
      {
        *v15 = *(_QWORD *)(v4 + 304);
        break;
      }
      v15 = (__int64 *)(v16 + 16);
      *v14 = (__int64 *)(v16 + 16);
    }
    *v14 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x140014c1c  push    rbx
0x140014c1e  push    rbp
0x140014c1f  push    rsi
0x140014c20  push    rdi
0x140014c21  push    r12
0x140014c23  push    r13
0x140014c25  push    r14
0x140014c27  push    r15
0x140014c29  sub     rsp, 28h
0x140014c2d  mov     r12b, r8b
0x140014c30  mov     rbp, rdx
0x140014c33  mov     rsi, rcx
0x140014c36  lea     rax, ??_7?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x140014c3d  mov     [rcx], rax
0x140014c40  lea     rdi, [rcx+8]
0x140014c44  lea     r14, [rdx+8]
0x140014c48  xor     r13d, r13d
0x140014c4b  mov     [rdi], r13d
0x140014c4e  mov     [rdi+4], r13b
0x140014c52  mov     eax, [r14]
0x140014c55  mov     [rdi], eax
0x140014c57  mov     al, [r14+4]
0x140014c5b  mov     [rdi+4], al
0x140014c5e  movups  xmm0, xmmword ptr [r14+8]
0x140014c63  movdqu  xmmword ptr [rdi+8], xmm0
0x140014c68  movups  xmm1, xmmword ptr [r14+18h]
0x140014c6d  movdqu  xmmword ptr [rdi+18h], xmm1
0x140014c72  mov     [r14], r13d
0x140014c75  mov     [r14+4], r13b
0x140014c79  xorps   xmm0, xmm0
0x140014c7c  movups  xmmword ptr [rdi+28h], xmm0
0x140014c80  movups  xmmword ptr [rdi+38h], xmm0
0x140014c84  mov     eax, [r14+28h]
0x140014c88  mov     [rdi+28h], eax
0x140014c8b  mov     rax, [r14+30h]
0x140014c8f  mov     [rdi+30h], rax
0x140014c93  lea     r15, [rdi+38h]
0x140014c97  cmp     [rdi+40h], r13b
0x140014c9b  jz      short loc_140014CB8
0x140014c9d  mov     rbx, [r15]
0x140014ca0  call    cs:__imp_GetProcessHeap
0x140014ca6  mov     r8, rbx; lpMem
0x140014ca9  xor     edx, edx; dwFlags
0x140014cab  mov     rcx, rax; hHeap
0x140014cae  call    cs:__imp_HeapFree
0x140014cb4  mov     [rdi+40h], r13b
0x140014cb8  mov     [r15], r13
0x140014cbb  mov     rax, [r14+38h]
0x140014cbf  mov     [r15], rax
0x140014cc2  mov     [r14+38h], r13
0x140014cc6  mov     al, [r14+40h]
0x140014cca  mov     [rdi+40h], al
0x140014ccd  mov     [r14+40h], r13b
0x140014cd1  mov     eax, [rbp+50h]
0x140014cd4  mov     [rsi+50h], eax
0x140014cd7  movups  xmm0, xmmword ptr [rbp+58h]
0x140014cdb  movups  xmmword ptr [rsi+58h], xmm0
0x140014cdf  movups  xmm1, xmmword ptr [rbp+68h]
0x140014ce3  movups  xmmword ptr [rsi+68h], xmm1
0x140014ce7  movups  xmm0, xmmword ptr [rbp+78h]
0x140014ceb  movups  xmmword ptr [rsi+78h], xmm0
0x140014cef  movups  xmm1, xmmword ptr [rbp+88h]
0x140014cf6  movups  xmmword ptr [rsi+88h], xmm1
0x140014cfd  movups  xmm0, xmmword ptr [rbp+98h]
0x140014d04  movups  xmmword ptr [rsi+98h], xmm0
0x140014d0b  movups  xmm1, xmmword ptr [rbp+0A8h]
0x140014d12  movups  xmmword ptr [rsi+0A8h], xmm1
0x140014d19  movups  xmm0, xmmword ptr [rbp+0B8h]
0x140014d20  movups  xmmword ptr [rsi+0B8h], xmm0
0x140014d27  movups  xmm1, xmmword ptr [rbp+0C8h]
0x140014d2e  movups  xmmword ptr [rsi+0C8h], xmm1
0x140014d35  movups  xmm0, xmmword ptr [rbp+0D8h]
0x140014d3c  movups  xmmword ptr [rsi+0D8h], xmm0
0x140014d43  mov     rax, [rbp+0E8h]
0x140014d4a  mov     [rsi+0E8h], rax
0x140014d51  mov     rax, [rbp+0F0h]
0x140014d58  mov     [rsi+0F0h], rax
0x140014d5f  mov     rax, [rbp+0F8h]
0x140014d66  mov     [rsi+0F8h], rax
0x140014d6d  mov     [rbp+0F0h], r13
0x140014d74  mov     [rbp+0F8h], r13
0x140014d7b  mov     eax, [rbp+100h]
0x140014d81  mov     [rsi+100h], eax
0x140014d87  xor     eax, eax
0x140014d89  mov     [rsi+108h], rax
0x140014d90  mov     rax, [rbp+118h]
0x140014d97  mov     [rsi+118h], rax
0x140014d9e  mov     [rbp+118h], r13
0x140014da5  lea     rbx, [rsi+120h]
0x140014dac  mov     [rbx], r13
0x140014daf  mov     [rbx+8], rsi
0x140014db3  mov     [rbx+10h], r13
0x140014db7  mov     [rbx+18h], r13d
0x140014dbb  mov     [rbx+20h], r13
0x140014dbf  mov     [rbx+28h], r13b
0x140014dc3  test    r12b, r12b
0x140014dc6  jz      short loc_140014DF3
0x140014dc8  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140014dcf  jz      short loc_140014DF3
0x140014dd1  mov     dl, 1
0x140014dd3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140014dd8  mov     [rbx], rax
0x140014ddb  test    rax, rax
0x140014dde  jz      short loc_140014DF3
0x140014de0  mov     rcx, [rax]
0x140014de3  mov     [rbx+10h], rcx
0x140014de7  mov     [rax], rbx
0x140014dea  call    cs:__imp_GetCurrentThreadId
0x140014df0  mov     [rbx+18h], eax
0x140014df3  mov     rax, [rsi+118h]
0x140014dfa  test    rax, rax
0x140014dfd  jz      short loc_140014E03
0x140014dff  lea     rdi, [rax+8]
0x140014e03  mov     [rsi+110h], rdi
0x140014e0a  lea     rax, [rdi+28h]
0x140014e0e  mov     [rsi+140h], rax
0x140014e15  mov     [rbp+110h], r14
0x140014e1c  cmp     [rbp+138h], r13d
0x140014e23  jz      short loc_140014E7D
0x140014e25  lea     rbx, [rbp+120h]
0x140014e2c  call    cs:__imp_GetCurrentThreadId
0x140014e32  cmp     [rbx+18h], eax
0x140014e35  jz      short loc_140014E54
0x140014e37  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140014e3e  test    rax, rax
0x140014e41  jz      short loc_140014E54
0x140014e43  mov     rdx, [rsp+68h]
0x140014e48  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140014e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e54  mov     [rbx+18h], r13d
0x140014e58  mov     rcx, [rbx]
0x140014e5b  jmp     short loc_140014E69
0x140014e5d  cmp     rax, rbx
0x140014e60  jz      short loc_140014E73
0x140014e62  lea     rcx, [rax+10h]
0x140014e66  mov     [rbx], rcx
0x140014e69  mov     rax, [rcx]
0x140014e6c  test    rax, rax
0x140014e6f  jnz     short loc_140014E5D
0x140014e71  jmp     short loc_140014E7A
0x140014e73  mov     rax, [rbx+10h]
0x140014e77  mov     [rcx], rax
0x140014e7a  mov     [rbx], r13
0x140014e7d  mov     rax, rsi
0x140014e80  add     rsp, 28h
0x140014e84  pop     r15
0x140014e86  pop     r14
0x140014e88  pop     r13
0x140014e8a  pop     r12
0x140014e8c  pop     rdi
0x140014e8d  pop     rsi
0x140014e8e  pop     rbp
0x140014e8f  pop     rbx
0x140014e90  retn
```
