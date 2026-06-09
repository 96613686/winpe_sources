# wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> &&)

- ea: `0x180005f24`
- end: `0x18000624a`
- name: `??4?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `806`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000b5dc`

## callees

- `0x180001be0`
- `0x1800042fc`
- `0x180005b50`
- `0x180005f24`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000606e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000606e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000607c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000607c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000616a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000617e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000616a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000617e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061e5`

## string_xrefs

- `0x180006199`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x180006201`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r15
  __int64 v3; // rsi
  void **v4; // rdi
  __int64 v5; // rbp
  int v7; // eax
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  volatile signed __int32 **v10; // r12
  volatile signed __int32 **v11; // rdi
  char v12; // al
  volatile signed __int32 *v13; // rbx
  HANDLE v14; // rax
  volatile signed __int32 **v15; // r12
  volatile signed __int32 **v16; // rbx
  volatile signed __int32 *v17; // rdi
  _QWORD *v18; // rcx
  __int64 **v19; // rdi
  __int64 *Local; // rax
  int v21; // ebx
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int64 **v24; // rbx
  __int64 *v25; // rcx
  __int64 v26; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]

  v2 = a2 + 8;
  v3 = a1 + 8;
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  v4 = (void **)(a1 + 64);
  v5 = a2;
  *(_BYTE *)(a1 + 12) = *(_BYTE *)(a2 + 12);
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(a2 + 32);
  v7 = *(_DWORD *)(a2 + 48);
  *(_DWORD *)(a2 + 8) = 0;
  *(_BYTE *)(a2 + 12) = 0;
  *(_DWORD *)(a1 + 48) = v7;
  *(_QWORD *)(a1 + 56) = *(_QWORD *)(a2 + 56);
  if ( *(_BYTE *)(a1 + 72) )
  {
    v8 = *v4;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    *(_BYTE *)(v3 + 64) = 0;
  }
  *v4 = 0;
  v10 = (volatile signed __int32 **)(v5 + 240);
  *v4 = *(void **)(v2 + 56);
  v11 = (volatile signed __int32 **)(a1 + 240);
  v12 = *(_BYTE *)(v2 + 64);
  *(_QWORD *)(v2 + 56) = 0;
  *(_BYTE *)(v3 + 64) = v12;
  *(_BYTE *)(v2 + 64) = 0;
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(v5 + 80);
  *(_OWORD *)(a1 + 88) = *(_OWORD *)(v5 + 88);
  *(_OWORD *)(a1 + 104) = *(_OWORD *)(v5 + 104);
  *(_OWORD *)(a1 + 120) = *(_OWORD *)(v5 + 120);
  *(_OWORD *)(a1 + 136) = *(_OWORD *)(v5 + 136);
  *(_OWORD *)(a1 + 152) = *(_OWORD *)(v5 + 152);
  *(_OWORD *)(a1 + 168) = *(_OWORD *)(v5 + 168);
  *(_OWORD *)(a1 + 184) = *(_OWORD *)(v5 + 184);
  *(_OWORD *)(a1 + 200) = *(_OWORD *)(v5 + 200);
  *(_OWORD *)(a1 + 216) = *(_OWORD *)(v5 + 216);
  *(_QWORD *)(a1 + 232) = *(_QWORD *)(v5 + 232);
  if ( a1 + 240 != v5 + 240 )
  {
    if ( *v11 )
    {
      if ( _InterlockedExchangeAdd(*v11, 0xFFFFFFFF) == 1 )
      {
        v13 = *v11;
        v14 = GetProcessHeap();
        HeapFree(v14, 0, (LPVOID)v13);
      }
      *v11 = 0;
      *(_QWORD *)(a1 + 248) = 0;
    }
    *v11 = *v10;
    *(_QWORD *)(a1 + 248) = *(_QWORD *)(v5 + 248);
    *v10 = 0;
    *(_QWORD *)(v5 + 248) = 0;
  }
  v15 = (volatile signed __int32 **)(v5 + 280);
  v16 = (volatile signed __int32 **)(a1 + 280);
  *(_DWORD *)(a1 + 256) = *(_DWORD *)(v5 + 256);
  if ( a1 + 280 == v5 + 280 )
  {
    v18 = (_QWORD *)(a1 + 280);
  }
  else
  {
    if ( *v16 )
    {
      if ( _InterlockedExchangeAdd(*v16, 0xFFFFFFFF) == 1 && (v17 = *v16) != 0 )
      {
        wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>((__int64)(v17 + 2));
        operator delete((void *)v17);
        v18 = (_QWORD *)(a1 + 280);
      }
      else
      {
        v18 = (_QWORD *)(a1 + 280);
      }
      *v16 = 0;
    }
    else
    {
      v18 = (_QWORD *)(a1 + 280);
    }
    *v16 = *v15;
    *v15 = 0;
  }
  if ( *v18 )
    v3 = *v18 + 8LL;
  v19 = (__int64 **)(a1 + 288);
  *(_QWORD *)(a1 + 272) = v3;
  *(_QWORD *)(a1 + 320) = v3 + 40;
  if ( !*(_DWORD *)(v5 + 312) )
  {
    if ( !*(_DWORD *)(a1 + 312) )
      goto LABEL_37;
    v21 = *(_DWORD *)(a1 + 312);
    if ( v21 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    v22 = *v19;
    *(_DWORD *)(a1 + 312) = 0;
    while ( 1 )
    {
      v23 = *v22;
      if ( !*v22 )
        goto LABEL_36;
      if ( (__int64 **)v23 == v19 )
      {
        *v22 = *(_QWORD *)(a1 + 304);
        goto LABEL_36;
      }
      v22 = (__int64 *)(v23 + 16);
      *v19 = (__int64 *)(v23 + 16);
    }
  }
  if ( *(_DWORD *)(a1 + 312) )
    goto LABEL_37;
  if ( !wil::details::g_pThreadFailureCallbacks )
  {
LABEL_36:
    *v19 = 0;
    goto LABEL_37;
  }
  LOBYTE(a2) = 1;
  Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                       v18,
                       a2);
  *v19 = Local;
  if ( Local )
  {
    *(_QWORD *)(a1 + 304) = *Local;
    *Local = (__int64)v19;
    *(_DWORD *)(a1 + 312) = GetCurrentThreadId();
  }
LABEL_37:
  *(_QWORD *)(v5 + 272) = v2;
  if ( *(_DWORD *)(v5 + 312) )
  {
    v24 = (__int64 **)(v5 + 288);
    if ( *(_DWORD *)(v5 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    v25 = *v24;
    *(_DWORD *)(v5 + 312) = 0;
    while ( 1 )
    {
      v26 = *v25;
      if ( !*v25 )
        break;
      if ( (__int64 **)v26 == v24 )
      {
        *v25 = *(_QWORD *)(v5 + 304);
        break;
      }
      v25 = (__int64 *)(v26 + 16);
      *v24 = (__int64 *)(v26 + 16);
    }
    *v24 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180005f24  push    rbx
0x180005f26  push    rbp
0x180005f27  push    rsi
0x180005f28  push    rdi
0x180005f29  push    r12
0x180005f2b  push    r13
0x180005f2d  push    r14
0x180005f2f  push    r15
0x180005f31  sub     rsp, 28h
0x180005f35  lea     r15, [rdx+8]
0x180005f39  xor     r13d, r13d
0x180005f3c  mov     eax, [r15]
0x180005f3f  lea     rsi, [rcx+8]
0x180005f43  mov     [rsi], eax
0x180005f45  lea     rdi, [rsi+38h]
0x180005f49  mov     al, [r15+4]
0x180005f4d  mov     rbp, rdx
0x180005f50  mov     [rsi+4], al
0x180005f53  mov     r14, rcx
0x180005f56  movups  xmm0, xmmword ptr [r15+8]
0x180005f5b  movdqu  xmmword ptr [rsi+8], xmm0
0x180005f60  movups  xmm1, xmmword ptr [r15+18h]
0x180005f65  movdqu  xmmword ptr [rsi+18h], xmm1
0x180005f6a  mov     eax, [r15+28h]
0x180005f6e  mov     [r15], r13d
0x180005f71  mov     [r15+4], r13b
0x180005f75  mov     [rsi+28h], eax
0x180005f78  mov     rax, [r15+30h]
0x180005f7c  mov     [rsi+30h], rax
0x180005f80  cmp     [rsi+40h], r13b
0x180005f84  jz      short loc_180005FA1
0x180005f86  mov     rbx, [rdi]
0x180005f89  call    cs:__imp_GetProcessHeap
0x180005f8f  mov     r8, rbx; lpMem
0x180005f92  xor     edx, edx; dwFlags
0x180005f94  mov     rcx, rax; hHeap
0x180005f97  call    cs:__imp_HeapFree
0x180005f9d  mov     [rsi+40h], r13b
0x180005fa1  mov     [rdi], r13
0x180005fa4  lea     r12, [rbp+0F0h]
0x180005fab  mov     rax, [r15+38h]
0x180005faf  mov     [rdi], rax
0x180005fb2  lea     rdi, [r14+0F0h]
0x180005fb9  mov     al, [r15+40h]
0x180005fbd  mov     [r15+38h], r13
0x180005fc1  mov     [rsi+40h], al
0x180005fc4  mov     [r15+40h], r13b
0x180005fc8  mov     eax, [rbp+50h]
0x180005fcb  mov     [r14+50h], eax
0x180005fcf  movups  xmm0, xmmword ptr [rbp+58h]
0x180005fd3  movups  xmmword ptr [r14+58h], xmm0
0x180005fd8  movups  xmm1, xmmword ptr [rbp+68h]
0x180005fdc  movups  xmmword ptr [r14+68h], xmm1
0x180005fe1  movups  xmm0, xmmword ptr [rbp+78h]
0x180005fe5  movups  xmmword ptr [r14+78h], xmm0
0x180005fea  movups  xmm1, xmmword ptr [rbp+88h]
0x180005ff1  movups  xmmword ptr [r14+88h], xmm1
0x180005ff9  movups  xmm0, xmmword ptr [rbp+98h]
0x180006000  movups  xmmword ptr [r14+98h], xmm0
0x180006008  movups  xmm1, xmmword ptr [rbp+0A8h]
0x18000600f  movups  xmmword ptr [r14+0A8h], xmm1
0x180006017  movups  xmm0, xmmword ptr [rbp+0B8h]
0x18000601e  movups  xmmword ptr [r14+0B8h], xmm0
0x180006026  movups  xmm1, xmmword ptr [rbp+0C8h]
0x18000602d  movups  xmmword ptr [r14+0C8h], xmm1
0x180006035  movups  xmm0, xmmword ptr [rbp+0D8h]
0x18000603c  movups  xmmword ptr [r14+0D8h], xmm0
0x180006044  mov     rax, [rbp+0E8h]
0x18000604b  mov     [r14+0E8h], rax
0x180006052  cmp     rdi, r12
0x180006055  jz      short loc_1800060A2
0x180006057  mov     rcx, [rdi]
0x18000605a  test    rcx, rcx
0x18000605d  jz      short loc_180006089
0x18000605f  or      eax, 0FFFFFFFFh
0x180006062  lock xadd [rcx], eax
0x180006066  cmp     eax, 1
0x180006069  jnz     short loc_180006082
0x18000606b  mov     rbx, [rdi]
0x18000606e  call    cs:__imp_GetProcessHeap
0x180006074  mov     r8, rbx; lpMem
0x180006077  xor     edx, edx; dwFlags
0x180006079  mov     rcx, rax; hHeap
0x18000607c  call    cs:__imp_HeapFree
0x180006082  mov     [rdi], r13
0x180006085  mov     [rdi+8], r13
0x180006089  mov     rax, [r12]
0x18000608d  mov     [rdi], rax
0x180006090  mov     rax, [r12+8]
0x180006095  mov     [rdi+8], rax
0x180006099  mov     [r12], r13
0x18000609d  mov     [r12+8], r13
0x1800060a2  mov     eax, [rbp+100h]
0x1800060a8  lea     r12, [rbp+118h]
0x1800060af  lea     rbx, [r14+118h]
0x1800060b6  mov     [r14+100h], eax
0x1800060bd  cmp     rbx, r12
0x1800060c0  jz      short loc_180006110
0x1800060c2  mov     rcx, [rbx]
0x1800060c5  test    rcx, rcx
0x1800060c8  jz      short loc_180006100
0x1800060ca  or      eax, 0FFFFFFFFh
0x1800060cd  lock xadd [rcx], eax
0x1800060d1  cmp     eax, 1
0x1800060d4  jnz     short loc_1800060F8
0x1800060d6  mov     rdi, [rbx]
0x1800060d9  test    rdi, rdi
0x1800060dc  jz      short loc_1800060F8
0x1800060de  lea     rcx, [rdi+8]
0x1800060e2  call    ??1?$ActivityData@VDeviceCenterContextHandlersLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800060e7  mov     rcx, rdi; Block
0x1800060ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800060ef  lea     rcx, [r14+118h]
0x1800060f6  jmp     short loc_1800060FB
0x1800060f8  mov     rcx, rbx
0x1800060fb  mov     [rbx], r13
0x1800060fe  jmp     short loc_180006103
0x180006100  mov     rcx, rbx
0x180006103  mov     rax, [r12]
0x180006107  mov     [rbx], rax
0x18000610a  mov     [r12], r13
0x18000610e  jmp     short loc_180006113
0x180006110  mov     rcx, rbx
0x180006113  mov     rax, [rcx]
0x180006116  test    rax, rax
0x180006119  jz      short loc_18000611F
0x18000611b  lea     rsi, [rax+8]
0x18000611f  lea     rdi, [r14+120h]
0x180006126  mov     [r14+110h], rsi
0x18000612d  lea     rax, [rsi+28h]
0x180006131  mov     [rdi+20h], rax
0x180006135  cmp     [rbp+138h], r13d
0x18000613c  jz      short loc_180006175
0x18000613e  cmp     [rdi+18h], r13d
0x180006142  jnz     loc_1800061CE
0x180006148  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000614f  jz      short loc_1800061CB
0x180006151  mov     dl, 1
0x180006153  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180006158  mov     [rdi], rax
0x18000615b  test    rax, rax
0x18000615e  jz      short loc_1800061CE
0x180006160  mov     rcx, [rax]
0x180006163  mov     [rdi+10h], rcx
0x180006167  mov     [rax], rdi
0x18000616a  call    cs:__imp_GetCurrentThreadId
0x180006170  mov     [rdi+18h], eax
0x180006173  jmp     short loc_1800061CE
0x180006175  cmp     [rdi+18h], r13d
0x180006179  jz      short loc_1800061CE
0x18000617b  mov     ebx, [rdi+18h]
0x18000617e  call    cs:__imp_GetCurrentThreadId
0x180006184  cmp     ebx, eax
0x180006186  jz      short loc_1800061A5
0x180006188  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000618f  test    rax, rax
0x180006192  jz      short loc_1800061A5
0x180006194  mov     rdx, [rsp+68h]
0x180006199  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800061a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a5  mov     rcx, [rdi]
0x1800061a8  mov     [rdi+18h], r13d
0x1800061ac  jmp     short loc_1800061BA
0x1800061ae  cmp     rax, rdi
0x1800061b1  jz      short loc_1800061C4
0x1800061b3  lea     rcx, [rax+10h]
0x1800061b7  mov     [rdi], rcx
0x1800061ba  mov     rax, [rcx]
0x1800061bd  test    rax, rax
0x1800061c0  jnz     short loc_1800061AE
0x1800061c2  jmp     short loc_1800061CB
0x1800061c4  mov     rax, [rdi+10h]
0x1800061c8  mov     [rcx], rax
0x1800061cb  mov     [rdi], r13
0x1800061ce  mov     [rbp+110h], r15
0x1800061d5  cmp     [rbp+138h], r13d
0x1800061dc  jz      short loc_180006236
0x1800061de  lea     rbx, [rbp+120h]
0x1800061e5  call    cs:__imp_GetCurrentThreadId
0x1800061eb  cmp     [rbx+18h], eax
0x1800061ee  jz      short loc_18000620D
0x1800061f0  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800061f7  test    rax, rax
0x1800061fa  jz      short loc_18000620D
0x1800061fc  mov     rdx, [rsp+68h]
0x180006201  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180006208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000620d  mov     rcx, [rbx]
0x180006210  mov     [rbx+18h], r13d
0x180006214  jmp     short loc_180006222
0x180006216  cmp     rax, rbx
0x180006219  jz      short loc_18000622C
0x18000621b  lea     rcx, [rax+10h]
0x18000621f  mov     [rbx], rcx
0x180006222  mov     rax, [rcx]
0x180006225  test    rax, rax
0x180006228  jnz     short loc_180006216
0x18000622a  jmp     short loc_180006233
0x18000622c  mov     rax, [rbx+10h]
0x180006230  mov     [rcx], rax
0x180006233  mov     [rbx], r13
0x180006236  mov     rax, r14
0x180006239  add     rsp, 28h
0x18000623d  pop     r15
0x18000623f  pop     r14
0x180006241  pop     r13
0x180006243  pop     r12
0x180006245  pop     rdi
0x180006246  pop     rsi
0x180006247  pop     rbp
0x180006248  pop     rbx
0x180006249  retn
```
