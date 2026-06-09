# wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)

- ea: `0x18001584c`
- end: `0x180015a9c`
- name: `??0?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z`
- size: `592`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180016c60`
- `0x18001815c`
- `0x18001fd60`

## callees

- `0x180009fc8`
- `0x18001584c`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800158d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800158d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800158de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800158de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015a37`

## string_xrefs

- `0x180015a53`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2,
        char a3)
{
  __int64 v6; // rdi
  __int64 v7; // r14
  void **v8; // r15
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v11; // rax
  __int64 **v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)a1 = &wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
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
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(a2 + 80);
  *(_OWORD *)(a1 + 88) = *(_OWORD *)(a2 + 88);
  *(_OWORD *)(a1 + 104) = *(_OWORD *)(a2 + 104);
  *(_OWORD *)(a1 + 120) = *(_OWORD *)(a2 + 120);
  *(_OWORD *)(a1 + 136) = *(_OWORD *)(a2 + 136);
  *(_OWORD *)(a1 + 152) = *(_OWORD *)(a2 + 152);
  *(_OWORD *)(a1 + 168) = *(_OWORD *)(a2 + 168);
  *(_OWORD *)(a1 + 184) = *(_OWORD *)(a2 + 184);
  *(_OWORD *)(a1 + 200) = *(_OWORD *)(a2 + 200);
  *(_OWORD *)(a1 + 216) = *(_OWORD *)(a2 + 216);
  *(_QWORD *)(a1 + 232) = *(_QWORD *)(a2 + 232);
  *(_QWORD *)(a1 + 240) = *(_QWORD *)(a2 + 240);
  *(_QWORD *)(a1 + 248) = *(_QWORD *)(a2 + 248);
  *(_QWORD *)(a2 + 240) = 0;
  *(_QWORD *)(a2 + 248) = 0;
  *(_DWORD *)(a1 + 256) = *(_DWORD *)(a2 + 256);
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 280) = *(_QWORD *)(a2 + 280);
  *(_QWORD *)(a2 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = a1;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  *(_BYTE *)(a1 + 328) = 0;
  if ( a3 )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  v11 = *(_QWORD *)(a1 + 280);
  if ( v11 )
    v6 = v11 + 8;
  *(_QWORD *)(a1 + 272) = v6;
  *(_QWORD *)(a1 + 320) = v6 + 40;
  *(_QWORD *)(a2 + 272) = v7;
  if ( *(_DWORD *)(a2 + 312) )
  {
    v12 = (__int64 **)(a2 + 288);
    if ( *(_DWORD *)(a2 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(a2 + 312) = 0;
    v13 = *v12;
    while ( 1 )
    {
      v14 = *v13;
      if ( !*v13 )
        break;
      if ( (__int64 **)v14 == v12 )
      {
        *v13 = *(_QWORD *)(a2 + 304);
        break;
      }
      v13 = (__int64 *)(v14 + 16);
      *v12 = (__int64 *)(v14 + 16);
    }
    *v12 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001584c  push    rbx
0x18001584e  push    rbp
0x18001584f  push    rsi
0x180015850  push    rdi
0x180015851  push    r12
0x180015853  push    r13
0x180015855  push    r14
0x180015857  push    r15
0x180015859  sub     rsp, 28h
0x18001585d  mov     r12b, r8b
0x180015860  mov     rbp, rdx
0x180015863  mov     rsi, rcx
0x180015866  lea     rax, ??_7?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18001586d  mov     [rcx], rax
0x180015870  lea     rdi, [rcx+8]
0x180015874  lea     r14, [rdx+8]
0x180015878  xor     r13d, r13d
0x18001587b  mov     [rdi], r13d
0x18001587e  mov     [rdi+4], r13b
0x180015882  mov     eax, [r14]
0x180015885  mov     [rdi], eax
0x180015887  mov     al, [r14+4]
0x18001588b  mov     [rdi+4], al
0x18001588e  movups  xmm0, xmmword ptr [r14+8]
0x180015893  movdqu  xmmword ptr [rdi+8], xmm0
0x180015898  movups  xmm1, xmmword ptr [r14+18h]
0x18001589d  movdqu  xmmword ptr [rdi+18h], xmm1
0x1800158a2  mov     [r14], r13d
0x1800158a5  mov     [r14+4], r13b
0x1800158a9  xorps   xmm0, xmm0
0x1800158ac  movups  xmmword ptr [rdi+28h], xmm0
0x1800158b0  movups  xmmword ptr [rdi+38h], xmm0
0x1800158b4  mov     eax, [r14+28h]
0x1800158b8  mov     [rdi+28h], eax
0x1800158bb  mov     rax, [r14+30h]
0x1800158bf  mov     [rdi+30h], rax
0x1800158c3  lea     r15, [rdi+38h]
0x1800158c7  cmp     [rdi+40h], r13b
0x1800158cb  jz      short loc_1800158E8
0x1800158cd  mov     rbx, [r15]
0x1800158d0  call    cs:__imp_GetProcessHeap
0x1800158d6  mov     r8, rbx; lpMem
0x1800158d9  xor     edx, edx; dwFlags
0x1800158db  mov     rcx, rax; hHeap
0x1800158de  call    cs:__imp_HeapFree
0x1800158e4  mov     [rdi+40h], r13b
0x1800158e8  mov     [r15], r13
0x1800158eb  mov     rax, [r14+38h]
0x1800158ef  mov     [r15], rax
0x1800158f2  mov     [r14+38h], r13
0x1800158f6  mov     al, [r14+40h]
0x1800158fa  mov     [rdi+40h], al
0x1800158fd  mov     [r14+40h], r13b
0x180015901  mov     eax, [rbp+50h]
0x180015904  mov     [rsi+50h], eax
0x180015907  movups  xmm0, xmmword ptr [rbp+58h]
0x18001590b  movups  xmmword ptr [rsi+58h], xmm0
0x18001590f  movups  xmm1, xmmword ptr [rbp+68h]
0x180015913  movups  xmmword ptr [rsi+68h], xmm1
0x180015917  movups  xmm0, xmmword ptr [rbp+78h]
0x18001591b  movups  xmmword ptr [rsi+78h], xmm0
0x18001591f  movups  xmm1, xmmword ptr [rbp+88h]
0x180015926  movups  xmmword ptr [rsi+88h], xmm1
0x18001592d  movups  xmm0, xmmword ptr [rbp+98h]
0x180015934  movups  xmmword ptr [rsi+98h], xmm0
0x18001593b  movups  xmm1, xmmword ptr [rbp+0A8h]
0x180015942  movups  xmmword ptr [rsi+0A8h], xmm1
0x180015949  movups  xmm0, xmmword ptr [rbp+0B8h]
0x180015950  movups  xmmword ptr [rsi+0B8h], xmm0
0x180015957  movups  xmm1, xmmword ptr [rbp+0C8h]
0x18001595e  movups  xmmword ptr [rsi+0C8h], xmm1
0x180015965  movups  xmm0, xmmword ptr [rbp+0D8h]
0x18001596c  movups  xmmword ptr [rsi+0D8h], xmm0
0x180015973  mov     rax, [rbp+0E8h]
0x18001597a  mov     [rsi+0E8h], rax
0x180015981  mov     rax, [rbp+0F0h]
0x180015988  mov     [rsi+0F0h], rax
0x18001598f  mov     rax, [rbp+0F8h]
0x180015996  mov     [rsi+0F8h], rax
0x18001599d  mov     [rbp+0F0h], r13
0x1800159a4  mov     [rbp+0F8h], r13
0x1800159ab  mov     eax, [rbp+100h]
0x1800159b1  mov     [rsi+100h], eax
0x1800159b7  xor     eax, eax
0x1800159b9  mov     [rsi+108h], rax
0x1800159c0  mov     rax, [rbp+118h]
0x1800159c7  mov     [rsi+118h], rax
0x1800159ce  mov     [rbp+118h], r13
0x1800159d5  lea     rcx, [rsi+120h]; this
0x1800159dc  mov     [rcx], r13
0x1800159df  mov     [rcx+8], rsi
0x1800159e3  mov     [rcx+10h], r13
0x1800159e7  mov     [rcx+18h], r13d
0x1800159eb  mov     [rcx+20h], r13
0x1800159ef  mov     [rcx+28h], r13b
0x1800159f3  test    r12b, r12b
0x1800159f6  jz      short loc_1800159FE
0x1800159f8  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800159fd  nop
0x1800159fe  mov     rax, [rsi+118h]
0x180015a05  test    rax, rax
0x180015a08  jz      short loc_180015A0E
0x180015a0a  lea     rdi, [rax+8]
0x180015a0e  mov     [rsi+110h], rdi
0x180015a15  lea     rax, [rdi+28h]
0x180015a19  mov     [rsi+140h], rax
0x180015a20  mov     [rbp+110h], r14
0x180015a27  cmp     [rbp+138h], r13d
0x180015a2e  jz      short loc_180015A88
0x180015a30  lea     rbx, [rbp+120h]
0x180015a37  call    cs:__imp_GetCurrentThreadId
0x180015a3d  cmp     [rbx+18h], eax
0x180015a40  jz      short loc_180015A5F
0x180015a42  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180015a49  test    rax, rax
0x180015a4c  jz      short loc_180015A5F
0x180015a4e  mov     rdx, [rsp+68h]
0x180015a53  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180015a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a5f  mov     [rbx+18h], r13d
0x180015a63  mov     rcx, [rbx]
0x180015a66  jmp     short loc_180015A74
0x180015a68  cmp     rax, rbx
0x180015a6b  jz      short loc_180015A7E
0x180015a6d  lea     rcx, [rax+10h]
0x180015a71  mov     [rbx], rcx
0x180015a74  mov     rax, [rcx]
0x180015a77  test    rax, rax
0x180015a7a  jnz     short loc_180015A68
0x180015a7c  jmp     short loc_180015A85
0x180015a7e  mov     rax, [rbx+10h]
0x180015a82  mov     [rcx], rax
0x180015a85  mov     [rbx], r13
0x180015a88  mov     rax, rsi
0x180015a8b  add     rsp, 28h
0x180015a8f  pop     r15
0x180015a91  pop     r14
0x180015a93  pop     r13
0x180015a95  pop     r12
0x180015a97  pop     rdi
0x180015a98  pop     rsi
0x180015a99  pop     rbp
0x180015a9a  pop     rbx
0x180015a9b  retn
```
