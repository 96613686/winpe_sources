# wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)

- ea: `0x180016948`
- end: `0x180016c44`
- name: `??4?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `764`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180016c60`

## callees

- `0x1800025f8`
- `0x180005764`
- `0x180009fc8`
- `0x180016948`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800169ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016a88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800169ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016a88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800169bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016a96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800169bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016a96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016b78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016b78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bdf`

## string_xrefs

- `0x180016b93`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x180016bfb`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r15
  __int64 v5; // rdi
  void **v6; // r14
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  volatile signed __int32 **v9; // r12
  volatile signed __int32 **v10; // r14
  volatile signed __int32 *v11; // rbx
  HANDLE v12; // rax
  volatile signed __int32 **v13; // r12
  volatile signed __int32 **v14; // rbx
  volatile signed __int32 *v15; // r14
  _QWORD *v16; // rcx
  __int64 **v17; // rdi
  int v18; // ebx
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 **v21; // rbx
  __int64 *v22; // rcx
  __int64 v23; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]

  v4 = a2 + 8;
  v5 = a1 + 8;
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  *(_BYTE *)(a1 + 12) = *(_BYTE *)(a2 + 12);
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(a2 + 32);
  *(_DWORD *)(a2 + 8) = 0;
  *(_BYTE *)(a2 + 12) = 0;
  *(_DWORD *)(a1 + 48) = *(_DWORD *)(a2 + 48);
  *(_QWORD *)(a1 + 56) = *(_QWORD *)(a2 + 56);
  v6 = (void **)(a1 + 64);
  if ( *(_BYTE *)(a1 + 72) )
  {
    v7 = *v6;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
    *(_BYTE *)(v5 + 64) = 0;
  }
  *v6 = 0;
  *v6 = *(void **)(v4 + 56);
  *(_QWORD *)(v4 + 56) = 0;
  *(_BYTE *)(v5 + 64) = *(_BYTE *)(v4 + 64);
  *(_BYTE *)(v4 + 64) = 0;
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
  v9 = (volatile signed __int32 **)(a2 + 240);
  v10 = (volatile signed __int32 **)(a1 + 240);
  if ( a1 + 240 != a2 + 240 )
  {
    if ( *v10 )
    {
      if ( _InterlockedExchangeAdd(*v10, 0xFFFFFFFF) == 1 )
      {
        v11 = *v10;
        v12 = GetProcessHeap();
        HeapFree(v12, 0, (LPVOID)v11);
      }
      *v10 = 0;
      *(_QWORD *)(a1 + 248) = 0;
    }
    *v10 = *v9;
    *(_QWORD *)(a1 + 248) = *(_QWORD *)(a2 + 248);
    *v9 = 0;
    *(_QWORD *)(a2 + 248) = 0;
  }
  *(_DWORD *)(a1 + 256) = *(_DWORD *)(a2 + 256);
  v13 = (volatile signed __int32 **)(a2 + 280);
  v14 = (volatile signed __int32 **)(a1 + 280);
  if ( a1 + 280 == a2 + 280 )
  {
    v16 = (_QWORD *)(a1 + 280);
  }
  else
  {
    if ( *v14 )
    {
      if ( _InterlockedExchangeAdd(*v14, 0xFFFFFFFF) == 1 && (v15 = *v14) != 0 )
      {
        wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FirewallUxTraceLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<FirewallUxTraceLoggingProvider,_TlgReflectorTag_Param0IsProviderType>(v15 + 2);
        operator delete((void *)v15);
        v16 = (_QWORD *)(a1 + 280);
      }
      else
      {
        v16 = (_QWORD *)(a1 + 280);
      }
      *v14 = 0;
    }
    else
    {
      v16 = (_QWORD *)(a1 + 280);
    }
    *v14 = *v13;
    *v13 = 0;
  }
  if ( *v16 )
    v5 = *v16 + 8LL;
  *(_QWORD *)(a1 + 272) = v5;
  *(_QWORD *)(a1 + 320) = v5 + 40;
  v17 = (__int64 **)(a1 + 288);
  if ( *(_DWORD *)(a2 + 312) )
  {
    if ( !*(_DWORD *)(a1 + 312) )
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  }
  else if ( *(_DWORD *)(a1 + 312) )
  {
    v18 = *(_DWORD *)(a1 + 312);
    if ( v18 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(a1 + 312) = 0;
    v19 = *v17;
    while ( 1 )
    {
      v20 = *v19;
      if ( !*v19 )
        break;
      if ( (__int64 **)v20 == v17 )
      {
        *v19 = *(_QWORD *)(a1 + 304);
        break;
      }
      v19 = (__int64 *)(v20 + 16);
      *v17 = (__int64 *)(v20 + 16);
    }
    *v17 = 0;
  }
  *(_QWORD *)(a2 + 272) = v4;
  if ( *(_DWORD *)(a2 + 312) )
  {
    v21 = (__int64 **)(a2 + 288);
    if ( *(_DWORD *)(a2 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(a2 + 312) = 0;
    v22 = *v21;
    while ( 1 )
    {
      v23 = *v22;
      if ( !*v22 )
        break;
      if ( (__int64 **)v23 == v21 )
      {
        *v22 = *(_QWORD *)(a2 + 304);
        break;
      }
      v22 = (__int64 *)(v23 + 16);
      *v21 = (__int64 *)(v23 + 16);
    }
    *v21 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180016948  push    rbx
0x18001694a  push    rbp
0x18001694b  push    rsi
0x18001694c  push    rdi
0x18001694d  push    r12
0x18001694f  push    r13
0x180016951  push    r14
0x180016953  push    r15
0x180016955  sub     rsp, 28h
0x180016959  mov     rbp, rdx
0x18001695c  mov     rsi, rcx
0x18001695f  lea     r15, [rdx+8]
0x180016963  lea     rdi, [rcx+8]
0x180016967  mov     eax, [r15]
0x18001696a  mov     [rdi], eax
0x18001696c  mov     al, [r15+4]
0x180016970  mov     [rdi+4], al
0x180016973  movups  xmm0, xmmword ptr [r15+8]
0x180016978  movdqu  xmmword ptr [rdi+8], xmm0
0x18001697d  movups  xmm1, xmmword ptr [r15+18h]
0x180016982  movdqu  xmmword ptr [rdi+18h], xmm1
0x180016987  xor     r13d, r13d
0x18001698a  mov     [r15], r13d
0x18001698d  mov     [r15+4], r13b
0x180016991  mov     eax, [r15+28h]
0x180016995  mov     [rdi+28h], eax
0x180016998  mov     rax, [r15+30h]
0x18001699c  mov     [rdi+30h], rax
0x1800169a0  lea     r14, [rdi+38h]
0x1800169a4  cmp     [rdi+40h], r13b
0x1800169a8  jz      short loc_1800169C5
0x1800169aa  mov     rbx, [r14]
0x1800169ad  call    cs:__imp_GetProcessHeap
0x1800169b3  mov     r8, rbx; lpMem
0x1800169b6  xor     edx, edx; dwFlags
0x1800169b8  mov     rcx, rax; hHeap
0x1800169bb  call    cs:__imp_HeapFree
0x1800169c1  mov     [rdi+40h], r13b
0x1800169c5  mov     [r14], r13
0x1800169c8  mov     rax, [r15+38h]
0x1800169cc  mov     [r14], rax
0x1800169cf  mov     [r15+38h], r13
0x1800169d3  mov     al, [r15+40h]
0x1800169d7  mov     [rdi+40h], al
0x1800169da  mov     [r15+40h], r13b
0x1800169de  mov     eax, [rbp+50h]
0x1800169e1  mov     [rsi+50h], eax
0x1800169e4  movups  xmm0, xmmword ptr [rbp+58h]
0x1800169e8  movups  xmmword ptr [rsi+58h], xmm0
0x1800169ec  movups  xmm1, xmmword ptr [rbp+68h]
0x1800169f0  movups  xmmword ptr [rsi+68h], xmm1
0x1800169f4  movups  xmm0, xmmword ptr [rbp+78h]
0x1800169f8  movups  xmmword ptr [rsi+78h], xmm0
0x1800169fc  movups  xmm1, xmmword ptr [rbp+88h]
0x180016a03  movups  xmmword ptr [rsi+88h], xmm1
0x180016a0a  movups  xmm0, xmmword ptr [rbp+98h]
0x180016a11  movups  xmmword ptr [rsi+98h], xmm0
0x180016a18  movups  xmm1, xmmword ptr [rbp+0A8h]
0x180016a1f  movups  xmmword ptr [rsi+0A8h], xmm1
0x180016a26  movups  xmm0, xmmword ptr [rbp+0B8h]
0x180016a2d  movups  xmmword ptr [rsi+0B8h], xmm0
0x180016a34  movups  xmm1, xmmword ptr [rbp+0C8h]
0x180016a3b  movups  xmmword ptr [rsi+0C8h], xmm1
0x180016a42  movups  xmm0, xmmword ptr [rbp+0D8h]
0x180016a49  movups  xmmword ptr [rsi+0D8h], xmm0
0x180016a50  mov     rax, [rbp+0E8h]
0x180016a57  mov     [rsi+0E8h], rax
0x180016a5e  lea     r12, [rbp+0F0h]
0x180016a65  lea     r14, [rsi+0F0h]
0x180016a6c  cmp     r14, r12
0x180016a6f  jz      short loc_180016ABC
0x180016a71  mov     rcx, [r14]
0x180016a74  test    rcx, rcx
0x180016a77  jz      short loc_180016AA3
0x180016a79  or      eax, 0FFFFFFFFh
0x180016a7c  lock xadd [rcx], eax
0x180016a80  cmp     eax, 1
0x180016a83  jnz     short loc_180016A9C
0x180016a85  mov     rbx, [r14]
0x180016a88  call    cs:__imp_GetProcessHeap
0x180016a8e  mov     r8, rbx; lpMem
0x180016a91  xor     edx, edx; dwFlags
0x180016a93  mov     rcx, rax; hHeap
0x180016a96  call    cs:__imp_HeapFree
0x180016a9c  mov     [r14], r13
0x180016a9f  mov     [r14+8], r13
0x180016aa3  mov     rax, [r12]
0x180016aa7  mov     [r14], rax
0x180016aaa  mov     rax, [r12+8]
0x180016aaf  mov     [r14+8], rax
0x180016ab3  mov     [r12], r13
0x180016ab7  mov     [r12+8], r13
0x180016abc  mov     eax, [rbp+100h]
0x180016ac2  mov     [rsi+100h], eax
0x180016ac8  lea     r12, [rbp+118h]
0x180016acf  lea     rbx, [rsi+118h]
0x180016ad6  cmp     rbx, r12
0x180016ad9  jz      short loc_180016B2E
0x180016adb  mov     rcx, [rbx]
0x180016ade  test    rcx, rcx
0x180016ae1  jz      short loc_180016B1E
0x180016ae3  or      eax, 0FFFFFFFFh
0x180016ae6  lock xadd [rcx], eax
0x180016aea  cmp     eax, 1
0x180016aed  jnz     short loc_180016B16
0x180016aef  mov     r14, [rbx]
0x180016af2  test    r14, r14
0x180016af5  jz      short loc_180016B16
0x180016af7  lea     rcx, [r14+8]
0x180016afb  call    ??1?$ActivityData@VFirewallUxTraceLoggingProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FirewallUxTraceLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<FirewallUxTraceLoggingProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180016b00  mov     edx, 110h; unsigned __int64
0x180016b05  mov     rcx, r14; void *
0x180016b08  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016b0d  lea     rcx, [rsi+118h]
0x180016b14  jmp     short loc_180016B19
0x180016b16  mov     rcx, rbx
0x180016b19  mov     [rbx], r13
0x180016b1c  jmp     short loc_180016B21
0x180016b1e  mov     rcx, rbx
0x180016b21  mov     rax, [r12]
0x180016b25  mov     [rbx], rax
0x180016b28  mov     [r12], r13
0x180016b2c  jmp     short loc_180016B31
0x180016b2e  mov     rcx, rbx
0x180016b31  mov     rax, [rcx]
0x180016b34  test    rax, rax
0x180016b37  jz      short loc_180016B3D
0x180016b39  lea     rdi, [rax+8]
0x180016b3d  mov     [rsi+110h], rdi
0x180016b44  lea     rax, [rdi+28h]
0x180016b48  mov     [rsi+140h], rax
0x180016b4f  lea     rdi, [rsi+120h]
0x180016b56  cmp     [rbp+138h], r13d
0x180016b5d  jz      short loc_180016B6F
0x180016b5f  cmp     [rdi+18h], r13d
0x180016b63  jnz     short loc_180016BC8
0x180016b65  mov     rcx, rdi; this
0x180016b68  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180016b6d  jmp     short loc_180016BC8
0x180016b6f  cmp     [rdi+18h], r13d
0x180016b73  jz      short loc_180016BC8
0x180016b75  mov     ebx, [rdi+18h]
0x180016b78  call    cs:__imp_GetCurrentThreadId
0x180016b7e  cmp     ebx, eax
0x180016b80  jz      short loc_180016B9F
0x180016b82  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180016b89  test    rax, rax
0x180016b8c  jz      short loc_180016B9F
0x180016b8e  mov     rdx, [rsp+68h]
0x180016b93  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180016b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b9f  mov     [rdi+18h], r13d
0x180016ba3  mov     rcx, [rdi]
0x180016ba6  jmp     short loc_180016BB4
0x180016ba8  cmp     rax, rdi
0x180016bab  jz      short loc_180016BBE
0x180016bad  lea     rcx, [rax+10h]
0x180016bb1  mov     [rdi], rcx
0x180016bb4  mov     rax, [rcx]
0x180016bb7  test    rax, rax
0x180016bba  jnz     short loc_180016BA8
0x180016bbc  jmp     short loc_180016BC5
0x180016bbe  mov     rax, [rdi+10h]
0x180016bc2  mov     [rcx], rax
0x180016bc5  mov     [rdi], r13
0x180016bc8  mov     [rbp+110h], r15
0x180016bcf  cmp     [rbp+138h], r13d
0x180016bd6  jz      short loc_180016C30
0x180016bd8  lea     rbx, [rbp+120h]
0x180016bdf  call    cs:__imp_GetCurrentThreadId
0x180016be5  cmp     [rbx+18h], eax
0x180016be8  jz      short loc_180016C07
0x180016bea  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180016bf1  test    rax, rax
0x180016bf4  jz      short loc_180016C07
0x180016bf6  mov     rdx, [rsp+68h]
0x180016bfb  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180016c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c07  mov     [rbx+18h], r13d
0x180016c0b  mov     rcx, [rbx]
0x180016c0e  jmp     short loc_180016C1C
0x180016c10  cmp     rax, rbx
0x180016c13  jz      short loc_180016C26
0x180016c15  lea     rcx, [rax+10h]
0x180016c19  mov     [rbx], rcx
0x180016c1c  mov     rax, [rcx]
0x180016c1f  test    rax, rax
0x180016c22  jnz     short loc_180016C10
0x180016c24  jmp     short loc_180016C2D
0x180016c26  mov     rax, [rbx+10h]
0x180016c2a  mov     [rcx], rax
0x180016c2d  mov     [rbx], r13
0x180016c30  mov     rax, rsi
0x180016c33  add     rsp, 28h
0x180016c37  pop     r15
0x180016c39  pop     r14
0x180016c3b  pop     r13
0x180016c3d  pop     r12
0x180016c3f  pop     rdi
0x180016c40  pop     rsi
0x180016c41  pop     rbp
0x180016c42  pop     rbx
0x180016c43  retn
```
