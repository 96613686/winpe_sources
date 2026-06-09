# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)

- ea: `0x18000d9a0`
- end: `0x18000dc15`
- name: `??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e9e8`
- `0x18000edbc`

## callees

- `0x180005330`
- `0x18000d9a0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000da32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000da32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dbb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dbb0`

## string_xrefs

- `0x18000dbcc`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
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
  *(_QWORD *)a1 = &wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable';
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
0x18000d9a0  push    rbx
0x18000d9a2  push    rbp
0x18000d9a3  push    rsi
0x18000d9a4  push    rdi
0x18000d9a5  push    r12
0x18000d9a7  push    r13
0x18000d9a9  push    r14
0x18000d9ab  push    r15
0x18000d9ad  sub     rsp, 28h
0x18000d9b1  mov     r12b, r8b
0x18000d9b4  mov     rbp, rdx
0x18000d9b7  mov     rsi, rcx
0x18000d9ba  lea     rax, ??_7?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18000d9c1  mov     [rcx], rax
0x18000d9c4  lea     rdi, [rcx+8]
0x18000d9c8  lea     r14, [rdx+8]
0x18000d9cc  xor     r13d, r13d
0x18000d9cf  mov     [rdi], r13d
0x18000d9d2  mov     [rdi+4], r13b
0x18000d9d6  mov     eax, [r14]
0x18000d9d9  mov     [rdi], eax
0x18000d9db  mov     al, [r14+4]
0x18000d9df  mov     [rdi+4], al
0x18000d9e2  movups  xmm0, xmmword ptr [r14+8]
0x18000d9e7  movdqu  xmmword ptr [rdi+8], xmm0
0x18000d9ec  movups  xmm1, xmmword ptr [r14+18h]
0x18000d9f1  movdqu  xmmword ptr [rdi+18h], xmm1
0x18000d9f6  mov     [r14], r13d
0x18000d9f9  mov     [r14+4], r13b
0x18000d9fd  xorps   xmm0, xmm0
0x18000da00  movups  xmmword ptr [rdi+28h], xmm0
0x18000da04  movups  xmmword ptr [rdi+38h], xmm0
0x18000da08  mov     eax, [r14+28h]
0x18000da0c  mov     [rdi+28h], eax
0x18000da0f  mov     rax, [r14+30h]
0x18000da13  mov     [rdi+30h], rax
0x18000da17  lea     r15, [rdi+38h]
0x18000da1b  cmp     [rdi+40h], r13b
0x18000da1f  jz      short loc_18000DA3C
0x18000da21  mov     rbx, [r15]
0x18000da24  call    cs:__imp_GetProcessHeap
0x18000da2a  mov     r8, rbx; lpMem
0x18000da2d  xor     edx, edx; dwFlags
0x18000da2f  mov     rcx, rax; hHeap
0x18000da32  call    cs:__imp_HeapFree
0x18000da38  mov     [rdi+40h], r13b
0x18000da3c  mov     [r15], r13
0x18000da3f  mov     rax, [r14+38h]
0x18000da43  mov     [r15], rax
0x18000da46  mov     [r14+38h], r13
0x18000da4a  mov     al, [r14+40h]
0x18000da4e  mov     [rdi+40h], al
0x18000da51  mov     [r14+40h], r13b
0x18000da55  mov     eax, [rbp+50h]
0x18000da58  mov     [rsi+50h], eax
0x18000da5b  movups  xmm0, xmmword ptr [rbp+58h]
0x18000da5f  movups  xmmword ptr [rsi+58h], xmm0
0x18000da63  movups  xmm1, xmmword ptr [rbp+68h]
0x18000da67  movups  xmmword ptr [rsi+68h], xmm1
0x18000da6b  movups  xmm0, xmmword ptr [rbp+78h]
0x18000da6f  movups  xmmword ptr [rsi+78h], xmm0
0x18000da73  movups  xmm1, xmmword ptr [rbp+88h]
0x18000da7a  movups  xmmword ptr [rsi+88h], xmm1
0x18000da81  movups  xmm0, xmmword ptr [rbp+98h]
0x18000da88  movups  xmmword ptr [rsi+98h], xmm0
0x18000da8f  movups  xmm1, xmmword ptr [rbp+0A8h]
0x18000da96  movups  xmmword ptr [rsi+0A8h], xmm1
0x18000da9d  movups  xmm0, xmmword ptr [rbp+0B8h]
0x18000daa4  movups  xmmword ptr [rsi+0B8h], xmm0
0x18000daab  movups  xmm1, xmmword ptr [rbp+0C8h]
0x18000dab2  movups  xmmword ptr [rsi+0C8h], xmm1
0x18000dab9  movups  xmm0, xmmword ptr [rbp+0D8h]
0x18000dac0  movups  xmmword ptr [rsi+0D8h], xmm0
0x18000dac7  mov     rax, [rbp+0E8h]
0x18000dace  mov     [rsi+0E8h], rax
0x18000dad5  mov     rax, [rbp+0F0h]
0x18000dadc  mov     [rsi+0F0h], rax
0x18000dae3  mov     rax, [rbp+0F8h]
0x18000daea  mov     [rsi+0F8h], rax
0x18000daf1  mov     [rbp+0F0h], r13
0x18000daf8  mov     [rbp+0F8h], r13
0x18000daff  mov     eax, [rbp+100h]
0x18000db05  mov     [rsi+100h], eax
0x18000db0b  xor     eax, eax
0x18000db0d  mov     [rsi+108h], rax
0x18000db14  mov     rax, [rbp+118h]
0x18000db1b  mov     [rsi+118h], rax
0x18000db22  mov     [rbp+118h], r13
0x18000db29  lea     rbx, [rsi+120h]
0x18000db30  mov     [rbx], r13
0x18000db33  mov     [rbx+8], rsi
0x18000db37  mov     [rbx+10h], r13
0x18000db3b  mov     [rbx+18h], r13d
0x18000db3f  mov     [rbx+20h], r13
0x18000db43  mov     [rbx+28h], r13b
0x18000db47  test    r12b, r12b
0x18000db4a  jz      short loc_18000DB77
0x18000db4c  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000db53  jz      short loc_18000DB77
0x18000db55  mov     dl, 1
0x18000db57  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000db5c  mov     [rbx], rax
0x18000db5f  test    rax, rax
0x18000db62  jz      short loc_18000DB77
0x18000db64  mov     rcx, [rax]
0x18000db67  mov     [rbx+10h], rcx
0x18000db6b  mov     [rax], rbx
0x18000db6e  call    cs:__imp_GetCurrentThreadId
0x18000db74  mov     [rbx+18h], eax
0x18000db77  mov     rax, [rsi+118h]
0x18000db7e  test    rax, rax
0x18000db81  jz      short loc_18000DB87
0x18000db83  lea     rdi, [rax+8]
0x18000db87  mov     [rsi+110h], rdi
0x18000db8e  lea     rax, [rdi+28h]
0x18000db92  mov     [rsi+140h], rax
0x18000db99  mov     [rbp+110h], r14
0x18000dba0  cmp     [rbp+138h], r13d
0x18000dba7  jz      short loc_18000DC01
0x18000dba9  lea     rbx, [rbp+120h]
0x18000dbb0  call    cs:__imp_GetCurrentThreadId
0x18000dbb6  cmp     [rbx+18h], eax
0x18000dbb9  jz      short loc_18000DBD8
0x18000dbbb  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000dbc2  test    rax, rax
0x18000dbc5  jz      short loc_18000DBD8
0x18000dbc7  mov     rdx, [rsp+68h]
0x18000dbcc  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000dbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbd8  mov     [rbx+18h], r13d
0x18000dbdc  mov     rcx, [rbx]
0x18000dbdf  jmp     short loc_18000DBED
0x18000dbe1  cmp     rax, rbx
0x18000dbe4  jz      short loc_18000DBF7
0x18000dbe6  lea     rcx, [rax+10h]
0x18000dbea  mov     [rbx], rcx
0x18000dbed  mov     rax, [rcx]
0x18000dbf0  test    rax, rax
0x18000dbf3  jnz     short loc_18000DBE1
0x18000dbf5  jmp     short loc_18000DBFE
0x18000dbf7  mov     rax, [rbx+10h]
0x18000dbfb  mov     [rcx], rax
0x18000dbfe  mov     [rbx], r13
0x18000dc01  mov     rax, rsi
0x18000dc04  add     rsp, 28h
0x18000dc08  pop     r15
0x18000dc0a  pop     r14
0x18000dc0c  pop     r13
0x18000dc0e  pop     r12
0x18000dc10  pop     rdi
0x18000dc11  pop     rsi
0x18000dc12  pop     rbp
0x18000dc13  pop     rbx
0x18000dc14  retn
```
