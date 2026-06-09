# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)

- ea: `0x18000df78`
- end: `0x18000e2a3`
- name: `??4?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `811`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x18000e9e8`
- `0x18000edbc`

## callees

- `0x180002f90`
- `0x180005330`
- `0x18000dd54`
- `0x18000df78`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dfeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dfeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dfdd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dfdd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e1c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e1d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e23e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e1c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e1d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e23e`

## string_xrefs

- `0x18000e1f2`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x18000e25a`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp
  __int64 v4; // r15
  __int64 v5; // rsi
  void **v6; // rdi
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  volatile signed __int32 **v9; // r12
  volatile signed __int32 **v10; // rdi
  volatile signed __int32 *v11; // rbx
  HANDLE v12; // rax
  volatile signed __int32 **v13; // r12
  volatile signed __int32 **v14; // rbx
  volatile signed __int32 *v15; // rdi
  _QWORD *v16; // rcx
  __int64 **v17; // rdi
  __int64 *Local; // rax
  int v19; // ebx
  __int64 *v20; // rcx
  __int64 v21; // rax
  __int64 **v22; // rbx
  __int64 *v23; // rcx
  __int64 v24; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]

  v2 = a2;
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
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(v2 + 80);
  *(_OWORD *)(a1 + 88) = *(_OWORD *)(v2 + 88);
  *(_OWORD *)(a1 + 104) = *(_OWORD *)(v2 + 104);
  *(_OWORD *)(a1 + 120) = *(_OWORD *)(v2 + 120);
  *(_OWORD *)(a1 + 136) = *(_OWORD *)(v2 + 136);
  *(_OWORD *)(a1 + 152) = *(_OWORD *)(v2 + 152);
  *(_OWORD *)(a1 + 168) = *(_OWORD *)(v2 + 168);
  *(_OWORD *)(a1 + 184) = *(_OWORD *)(v2 + 184);
  *(_OWORD *)(a1 + 200) = *(_OWORD *)(v2 + 200);
  *(_OWORD *)(a1 + 216) = *(_OWORD *)(v2 + 216);
  *(_QWORD *)(a1 + 232) = *(_QWORD *)(v2 + 232);
  v9 = (volatile signed __int32 **)(v2 + 240);
  v10 = (volatile signed __int32 **)(a1 + 240);
  if ( a1 + 240 != v2 + 240 )
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
    *(_QWORD *)(a1 + 248) = *(_QWORD *)(v2 + 248);
    *v9 = 0;
    *(_QWORD *)(v2 + 248) = 0;
  }
  *(_DWORD *)(a1 + 256) = *(_DWORD *)(v2 + 256);
  v13 = (volatile signed __int32 **)(v2 + 280);
  v14 = (volatile signed __int32 **)(a1 + 280);
  if ( a1 + 280 == v2 + 280 )
  {
    v16 = (_QWORD *)(a1 + 280);
  }
  else
  {
    if ( *v14 )
    {
      if ( _InterlockedExchangeAdd(*v14, 0xFFFFFFFF) == 1 && (v15 = *v14) != 0 )
      {
        wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>((__int64)(v15 + 2));
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
  v17 = (__int64 **)(a1 + 288);
  *(_QWORD *)(a1 + 320) = v5 + 40;
  if ( !*(_DWORD *)(v2 + 312) )
  {
    if ( !*(_DWORD *)(a1 + 312) )
      goto LABEL_37;
    v19 = *(_DWORD *)(a1 + 312);
    if ( v19 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(a1 + 312) = 0;
    v20 = *v17;
    while ( 1 )
    {
      v21 = *v20;
      if ( !*v20 )
        goto LABEL_36;
      if ( (__int64 **)v21 == v17 )
      {
        *v20 = *(_QWORD *)(a1 + 304);
        goto LABEL_36;
      }
      v20 = (__int64 *)(v21 + 16);
      *v17 = (__int64 *)(v21 + 16);
    }
  }
  if ( *(_DWORD *)(a1 + 312) )
    goto LABEL_37;
  if ( !wil::details::g_pThreadFailureCallbacks )
  {
LABEL_36:
    *v17 = 0;
    goto LABEL_37;
  }
  LOBYTE(a2) = 1;
  Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                       v16,
                       a2);
  *v17 = Local;
  if ( Local )
  {
    *(_QWORD *)(a1 + 304) = *Local;
    *Local = (__int64)v17;
    *(_DWORD *)(a1 + 312) = GetCurrentThreadId();
  }
LABEL_37:
  *(_QWORD *)(v2 + 272) = v4;
  if ( *(_DWORD *)(v2 + 312) )
  {
    v22 = (__int64 **)(v2 + 288);
    if ( *(_DWORD *)(v2 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(v2 + 312) = 0;
    v23 = *v22;
    while ( 1 )
    {
      v24 = *v23;
      if ( !*v23 )
        break;
      if ( (__int64 **)v24 == v22 )
      {
        *v23 = *(_QWORD *)(v2 + 304);
        break;
      }
      v23 = (__int64 *)(v24 + 16);
      *v22 = (__int64 *)(v24 + 16);
    }
    *v22 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000df78  push    rbx
0x18000df7a  push    rbp
0x18000df7b  push    rsi
0x18000df7c  push    rdi
0x18000df7d  push    r12
0x18000df7f  push    r13
0x18000df81  push    r14
0x18000df83  push    r15
0x18000df85  sub     rsp, 28h
0x18000df89  mov     rbp, rdx
0x18000df8c  mov     r14, rcx
0x18000df8f  lea     r15, [rdx+8]
0x18000df93  lea     rsi, [rcx+8]
0x18000df97  mov     eax, [r15]
0x18000df9a  mov     [rsi], eax
0x18000df9c  mov     al, [r15+4]
0x18000dfa0  mov     [rsi+4], al
0x18000dfa3  movups  xmm0, xmmword ptr [r15+8]
0x18000dfa8  movdqu  xmmword ptr [rsi+8], xmm0
0x18000dfad  movups  xmm1, xmmword ptr [r15+18h]
0x18000dfb2  movdqu  xmmword ptr [rsi+18h], xmm1
0x18000dfb7  xor     r13d, r13d
0x18000dfba  mov     [r15], r13d
0x18000dfbd  mov     [r15+4], r13b
0x18000dfc1  mov     eax, [r15+28h]
0x18000dfc5  mov     [rsi+28h], eax
0x18000dfc8  mov     rax, [r15+30h]
0x18000dfcc  mov     [rsi+30h], rax
0x18000dfd0  lea     rdi, [rsi+38h]
0x18000dfd4  cmp     [rsi+40h], r13b
0x18000dfd8  jz      short loc_18000DFF5
0x18000dfda  mov     rbx, [rdi]
0x18000dfdd  call    cs:__imp_GetProcessHeap
0x18000dfe3  mov     r8, rbx; lpMem
0x18000dfe6  xor     edx, edx; dwFlags
0x18000dfe8  mov     rcx, rax; hHeap
0x18000dfeb  call    cs:__imp_HeapFree
0x18000dff1  mov     [rsi+40h], r13b
0x18000dff5  mov     [rdi], r13
0x18000dff8  mov     rax, [r15+38h]
0x18000dffc  mov     [rdi], rax
0x18000dfff  mov     [r15+38h], r13
0x18000e003  mov     al, [r15+40h]
0x18000e007  mov     [rsi+40h], al
0x18000e00a  mov     [r15+40h], r13b
0x18000e00e  mov     eax, [rbp+50h]
0x18000e011  mov     [r14+50h], eax
0x18000e015  movups  xmm0, xmmword ptr [rbp+58h]
0x18000e019  movups  xmmword ptr [r14+58h], xmm0
0x18000e01e  movups  xmm1, xmmword ptr [rbp+68h]
0x18000e022  movups  xmmword ptr [r14+68h], xmm1
0x18000e027  movups  xmm0, xmmword ptr [rbp+78h]
0x18000e02b  movups  xmmword ptr [r14+78h], xmm0
0x18000e030  movups  xmm1, xmmword ptr [rbp+88h]
0x18000e037  movups  xmmword ptr [r14+88h], xmm1
0x18000e03f  movups  xmm0, xmmword ptr [rbp+98h]
0x18000e046  movups  xmmword ptr [r14+98h], xmm0
0x18000e04e  movups  xmm1, xmmword ptr [rbp+0A8h]
0x18000e055  movups  xmmword ptr [r14+0A8h], xmm1
0x18000e05d  movups  xmm0, xmmword ptr [rbp+0B8h]
0x18000e064  movups  xmmword ptr [r14+0B8h], xmm0
0x18000e06c  movups  xmm1, xmmword ptr [rbp+0C8h]
0x18000e073  movups  xmmword ptr [r14+0C8h], xmm1
0x18000e07b  movups  xmm0, xmmword ptr [rbp+0D8h]
0x18000e082  movups  xmmword ptr [r14+0D8h], xmm0
0x18000e08a  mov     rax, [rbp+0E8h]
0x18000e091  mov     [r14+0E8h], rax
0x18000e098  lea     r12, [rbp+0F0h]
0x18000e09f  lea     rdi, [r14+0F0h]
0x18000e0a6  cmp     rdi, r12
0x18000e0a9  jz      short loc_18000E0F6
0x18000e0ab  mov     rcx, [rdi]
0x18000e0ae  test    rcx, rcx
0x18000e0b1  jz      short loc_18000E0DD
0x18000e0b3  or      eax, 0FFFFFFFFh
0x18000e0b6  lock xadd [rcx], eax
0x18000e0ba  cmp     eax, 1
0x18000e0bd  jnz     short loc_18000E0D6
0x18000e0bf  mov     rbx, [rdi]
0x18000e0c2  call    cs:__imp_GetProcessHeap
0x18000e0c8  mov     r8, rbx; lpMem
0x18000e0cb  xor     edx, edx; dwFlags
0x18000e0cd  mov     rcx, rax; hHeap
0x18000e0d0  call    cs:__imp_HeapFree
0x18000e0d6  mov     [rdi], r13
0x18000e0d9  mov     [rdi+8], r13
0x18000e0dd  mov     rax, [r12]
0x18000e0e1  mov     [rdi], rax
0x18000e0e4  mov     rax, [r12+8]
0x18000e0e9  mov     [rdi+8], rax
0x18000e0ed  mov     [r12], r13
0x18000e0f1  mov     [r12+8], r13
0x18000e0f6  mov     eax, [rbp+100h]
0x18000e0fc  mov     [r14+100h], eax
0x18000e103  lea     r12, [rbp+118h]
0x18000e10a  lea     rbx, [r14+118h]
0x18000e111  cmp     rbx, r12
0x18000e114  jz      short loc_18000E169
0x18000e116  mov     rcx, [rbx]
0x18000e119  test    rcx, rcx
0x18000e11c  jz      short loc_18000E159
0x18000e11e  or      eax, 0FFFFFFFFh
0x18000e121  lock xadd [rcx], eax
0x18000e125  cmp     eax, 1
0x18000e128  jnz     short loc_18000E151
0x18000e12a  mov     rdi, [rbx]
0x18000e12d  test    rdi, rdi
0x18000e130  jz      short loc_18000E151
0x18000e132  lea     rcx, [rdi+8]
0x18000e136  call    ??1?$ActivityData@VServiceHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e13b  mov     edx, 110h; unsigned __int64
0x18000e140  mov     rcx, rdi; void *
0x18000e143  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e148  lea     rcx, [r14+118h]
0x18000e14f  jmp     short loc_18000E154
0x18000e151  mov     rcx, rbx
0x18000e154  mov     [rbx], r13
0x18000e157  jmp     short loc_18000E15C
0x18000e159  mov     rcx, rbx
0x18000e15c  mov     rax, [r12]
0x18000e160  mov     [rbx], rax
0x18000e163  mov     [r12], r13
0x18000e167  jmp     short loc_18000E16C
0x18000e169  mov     rcx, rbx
0x18000e16c  mov     rax, [rcx]
0x18000e16f  test    rax, rax
0x18000e172  jz      short loc_18000E178
0x18000e174  lea     rsi, [rax+8]
0x18000e178  mov     [r14+110h], rsi
0x18000e17f  lea     rdi, [r14+120h]
0x18000e186  lea     rax, [rsi+28h]
0x18000e18a  mov     [rdi+20h], rax
0x18000e18e  cmp     [rbp+138h], r13d
0x18000e195  jz      short loc_18000E1CE
0x18000e197  cmp     [rdi+18h], r13d
0x18000e19b  jnz     loc_18000E227
0x18000e1a1  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000e1a8  jz      short loc_18000E224
0x18000e1aa  mov     dl, 1
0x18000e1ac  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000e1b1  mov     [rdi], rax
0x18000e1b4  test    rax, rax
0x18000e1b7  jz      short loc_18000E227
0x18000e1b9  mov     rcx, [rax]
0x18000e1bc  mov     [rdi+10h], rcx
0x18000e1c0  mov     [rax], rdi
0x18000e1c3  call    cs:__imp_GetCurrentThreadId
0x18000e1c9  mov     [rdi+18h], eax
0x18000e1cc  jmp     short loc_18000E227
0x18000e1ce  cmp     [rdi+18h], r13d
0x18000e1d2  jz      short loc_18000E227
0x18000e1d4  mov     ebx, [rdi+18h]
0x18000e1d7  call    cs:__imp_GetCurrentThreadId
0x18000e1dd  cmp     ebx, eax
0x18000e1df  jz      short loc_18000E1FE
0x18000e1e1  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000e1e8  test    rax, rax
0x18000e1eb  jz      short loc_18000E1FE
0x18000e1ed  mov     rdx, [rsp+68h]
0x18000e1f2  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000e1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1fe  mov     [rdi+18h], r13d
0x18000e202  mov     rcx, [rdi]
0x18000e205  jmp     short loc_18000E213
0x18000e207  cmp     rax, rdi
0x18000e20a  jz      short loc_18000E21D
0x18000e20c  lea     rcx, [rax+10h]
0x18000e210  mov     [rdi], rcx
0x18000e213  mov     rax, [rcx]
0x18000e216  test    rax, rax
0x18000e219  jnz     short loc_18000E207
0x18000e21b  jmp     short loc_18000E224
0x18000e21d  mov     rax, [rdi+10h]
0x18000e221  mov     [rcx], rax
0x18000e224  mov     [rdi], r13
0x18000e227  mov     [rbp+110h], r15
0x18000e22e  cmp     [rbp+138h], r13d
0x18000e235  jz      short loc_18000E28F
0x18000e237  lea     rbx, [rbp+120h]
0x18000e23e  call    cs:__imp_GetCurrentThreadId
0x18000e244  cmp     [rbx+18h], eax
0x18000e247  jz      short loc_18000E266
0x18000e249  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000e250  test    rax, rax
0x18000e253  jz      short loc_18000E266
0x18000e255  mov     rdx, [rsp+68h]
0x18000e25a  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000e261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e266  mov     [rbx+18h], r13d
0x18000e26a  mov     rcx, [rbx]
0x18000e26d  jmp     short loc_18000E27B
0x18000e26f  cmp     rax, rbx
0x18000e272  jz      short loc_18000E285
0x18000e274  lea     rcx, [rax+10h]
0x18000e278  mov     [rbx], rcx
0x18000e27b  mov     rax, [rcx]
0x18000e27e  test    rax, rax
0x18000e281  jnz     short loc_18000E26F
0x18000e283  jmp     short loc_18000E28C
0x18000e285  mov     rax, [rbx+10h]
0x18000e289  mov     [rcx], rax
0x18000e28c  mov     [rbx], r13
0x18000e28f  mov     rax, r14
0x18000e292  add     rsp, 28h
0x18000e296  pop     r15
0x18000e298  pop     r14
0x18000e29a  pop     r13
0x18000e29c  pop     r12
0x18000e29e  pop     rdi
0x18000e29f  pop     rsi
0x18000e2a0  pop     rbp
0x18000e2a1  pop     rbx
0x18000e2a2  retn
```
