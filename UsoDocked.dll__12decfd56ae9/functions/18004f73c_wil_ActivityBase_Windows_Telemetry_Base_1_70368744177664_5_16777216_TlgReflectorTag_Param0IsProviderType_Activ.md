# wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)

- ea: `0x18004f73c`
- end: `0x18004f9b1`
- name: `??0?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z`
- size: `629`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18004fc28`
- `0x18004fd80`
- `0x180053930`
- `0x180053a20`

## callees

- `0x180016180`
- `0x18004f73c`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f7ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f7ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f7c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f7c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f90a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f94c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f90a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f94c`

## string_xrefs

- `0x18004f968`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
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
  *(_QWORD *)a1 = &wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable';
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
0x18004f73c  push    rbx
0x18004f73e  push    rbp
0x18004f73f  push    rsi
0x18004f740  push    rdi
0x18004f741  push    r12
0x18004f743  push    r13
0x18004f745  push    r14
0x18004f747  push    r15
0x18004f749  sub     rsp, 28h
0x18004f74d  mov     r12b, r8b
0x18004f750  mov     rbp, rdx
0x18004f753  mov     rsi, rcx
0x18004f756  lea     rax, ??_7?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18004f75d  mov     [rcx], rax
0x18004f760  lea     rdi, [rcx+8]
0x18004f764  lea     r14, [rdx+8]
0x18004f768  xor     r13d, r13d
0x18004f76b  mov     [rdi], r13d
0x18004f76e  mov     [rdi+4], r13b
0x18004f772  mov     eax, [r14]
0x18004f775  mov     [rdi], eax
0x18004f777  mov     al, [r14+4]
0x18004f77b  mov     [rdi+4], al
0x18004f77e  movups  xmm0, xmmword ptr [r14+8]
0x18004f783  movdqu  xmmword ptr [rdi+8], xmm0
0x18004f788  movups  xmm1, xmmword ptr [r14+18h]
0x18004f78d  movdqu  xmmword ptr [rdi+18h], xmm1
0x18004f792  mov     [r14], r13d
0x18004f795  mov     [r14+4], r13b
0x18004f799  xorps   xmm0, xmm0
0x18004f79c  movups  xmmword ptr [rdi+28h], xmm0
0x18004f7a0  movups  xmmword ptr [rdi+38h], xmm0
0x18004f7a4  mov     eax, [r14+28h]
0x18004f7a8  mov     [rdi+28h], eax
0x18004f7ab  mov     rax, [r14+30h]
0x18004f7af  mov     [rdi+30h], rax
0x18004f7b3  lea     r15, [rdi+38h]
0x18004f7b7  cmp     [rdi+40h], r13b
0x18004f7bb  jz      short loc_18004F7D8
0x18004f7bd  mov     rbx, [r15]
0x18004f7c0  call    cs:__imp_GetProcessHeap
0x18004f7c6  mov     r8, rbx; lpMem
0x18004f7c9  xor     edx, edx; dwFlags
0x18004f7cb  mov     rcx, rax; hHeap
0x18004f7ce  call    cs:__imp_HeapFree
0x18004f7d4  mov     [rdi+40h], r13b
0x18004f7d8  mov     [r15], r13
0x18004f7db  mov     rax, [r14+38h]
0x18004f7df  mov     [r15], rax
0x18004f7e2  mov     [r14+38h], r13
0x18004f7e6  mov     al, [r14+40h]
0x18004f7ea  mov     [rdi+40h], al
0x18004f7ed  mov     [r14+40h], r13b
0x18004f7f1  mov     eax, [rbp+50h]
0x18004f7f4  mov     [rsi+50h], eax
0x18004f7f7  movups  xmm0, xmmword ptr [rbp+58h]
0x18004f7fb  movups  xmmword ptr [rsi+58h], xmm0
0x18004f7ff  movups  xmm1, xmmword ptr [rbp+68h]
0x18004f803  movups  xmmword ptr [rsi+68h], xmm1
0x18004f807  movups  xmm0, xmmword ptr [rbp+78h]
0x18004f80b  movups  xmmword ptr [rsi+78h], xmm0
0x18004f80f  movups  xmm1, xmmword ptr [rbp+88h]
0x18004f816  movups  xmmword ptr [rsi+88h], xmm1
0x18004f81d  movups  xmm0, xmmword ptr [rbp+98h]
0x18004f824  movups  xmmword ptr [rsi+98h], xmm0
0x18004f82b  movups  xmm1, xmmword ptr [rbp+0A8h]
0x18004f832  movups  xmmword ptr [rsi+0A8h], xmm1
0x18004f839  movups  xmm0, xmmword ptr [rbp+0B8h]
0x18004f840  movups  xmmword ptr [rsi+0B8h], xmm0
0x18004f847  movups  xmm1, xmmword ptr [rbp+0C8h]
0x18004f84e  movups  xmmword ptr [rsi+0C8h], xmm1
0x18004f855  movups  xmm0, xmmword ptr [rbp+0D8h]
0x18004f85c  movups  xmmword ptr [rsi+0D8h], xmm0
0x18004f863  mov     rax, [rbp+0E8h]
0x18004f86a  mov     [rsi+0E8h], rax
0x18004f871  mov     rax, [rbp+0F0h]
0x18004f878  mov     [rsi+0F0h], rax
0x18004f87f  mov     rax, [rbp+0F8h]
0x18004f886  mov     [rsi+0F8h], rax
0x18004f88d  mov     [rbp+0F0h], r13
0x18004f894  mov     [rbp+0F8h], r13
0x18004f89b  mov     eax, [rbp+100h]
0x18004f8a1  mov     [rsi+100h], eax
0x18004f8a7  xor     eax, eax
0x18004f8a9  mov     [rsi+108h], rax
0x18004f8b0  mov     rax, [rbp+118h]
0x18004f8b7  mov     [rsi+118h], rax
0x18004f8be  mov     [rbp+118h], r13
0x18004f8c5  lea     rbx, [rsi+120h]
0x18004f8cc  mov     [rbx], r13
0x18004f8cf  mov     [rbx+8], rsi
0x18004f8d3  mov     [rbx+10h], r13
0x18004f8d7  mov     [rbx+18h], r13d
0x18004f8db  mov     [rbx+20h], r13
0x18004f8df  mov     [rbx+28h], r13b
0x18004f8e3  test    r12b, r12b
0x18004f8e6  jz      short loc_18004F913
0x18004f8e8  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004f8ef  jz      short loc_18004F913
0x18004f8f1  mov     dl, 1
0x18004f8f3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18004f8f8  mov     [rbx], rax
0x18004f8fb  test    rax, rax
0x18004f8fe  jz      short loc_18004F913
0x18004f900  mov     rcx, [rax]
0x18004f903  mov     [rbx+10h], rcx
0x18004f907  mov     [rax], rbx
0x18004f90a  call    cs:__imp_GetCurrentThreadId
0x18004f910  mov     [rbx+18h], eax
0x18004f913  mov     rax, [rsi+118h]
0x18004f91a  test    rax, rax
0x18004f91d  jz      short loc_18004F923
0x18004f91f  lea     rdi, [rax+8]
0x18004f923  mov     [rsi+110h], rdi
0x18004f92a  lea     rax, [rdi+28h]
0x18004f92e  mov     [rsi+140h], rax
0x18004f935  mov     [rbp+110h], r14
0x18004f93c  cmp     [rbp+138h], r13d
0x18004f943  jz      short loc_18004F99D
0x18004f945  lea     rbx, [rbp+120h]
0x18004f94c  call    cs:__imp_GetCurrentThreadId
0x18004f952  cmp     [rbx+18h], eax
0x18004f955  jz      short loc_18004F974
0x18004f957  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18004f95e  test    rax, rax
0x18004f961  jz      short loc_18004F974
0x18004f963  mov     rdx, [rsp+68h]
0x18004f968  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18004f96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f974  mov     [rbx+18h], r13d
0x18004f978  mov     rcx, [rbx]
0x18004f97b  jmp     short loc_18004F989
0x18004f97d  cmp     rax, rbx
0x18004f980  jz      short loc_18004F993
0x18004f982  lea     rcx, [rax+10h]
0x18004f986  mov     [rbx], rcx
0x18004f989  mov     rax, [rcx]
0x18004f98c  test    rax, rax
0x18004f98f  jnz     short loc_18004F97D
0x18004f991  jmp     short loc_18004F99A
0x18004f993  mov     rax, [rbx+10h]
0x18004f997  mov     [rcx], rax
0x18004f99a  mov     [rbx], r13
0x18004f99d  mov     rax, rsi
0x18004f9a0  add     rsp, 28h
0x18004f9a4  pop     r15
0x18004f9a6  pop     r14
0x18004f9a8  pop     r13
0x18004f9aa  pop     r12
0x18004f9ac  pop     rdi
0x18004f9ad  pop     rsi
0x18004f9ae  pop     rbp
0x18004f9af  pop     rbx
0x18004f9b0  retn
```
