# wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> &&)

- ea: `0x14001582c`
- end: `0x140015b57`
- name: `??4?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `811`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140018fb0`

## callees

- `0x1400028d8`
- `0x1400068f0`
- `0x140015350`
- `0x14001582c`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015891`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015976`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015891`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015976`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001589f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015984`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001589f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015984`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015a8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015af2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015a8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015af2`

## string_xrefs

- `0x140015aa6`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x140015b0e`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(
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
        wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FlightDataRecorderActivityClass,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<FlightDataRecorderActivityClass,_TlgReflectorTag_Param0IsProviderType>(v15 + 2);
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
0x14001582c  push    rbx
0x14001582e  push    rbp
0x14001582f  push    rsi
0x140015830  push    rdi
0x140015831  push    r12
0x140015833  push    r13
0x140015835  push    r14
0x140015837  push    r15
0x140015839  sub     rsp, 28h
0x14001583d  mov     rbp, rdx
0x140015840  mov     r14, rcx
0x140015843  lea     r15, [rdx+8]
0x140015847  lea     rsi, [rcx+8]
0x14001584b  mov     eax, [r15]
0x14001584e  mov     [rsi], eax
0x140015850  mov     al, [r15+4]
0x140015854  mov     [rsi+4], al
0x140015857  movups  xmm0, xmmword ptr [r15+8]
0x14001585c  movdqu  xmmword ptr [rsi+8], xmm0
0x140015861  movups  xmm1, xmmword ptr [r15+18h]
0x140015866  movdqu  xmmword ptr [rsi+18h], xmm1
0x14001586b  xor     r13d, r13d
0x14001586e  mov     [r15], r13d
0x140015871  mov     [r15+4], r13b
0x140015875  mov     eax, [r15+28h]
0x140015879  mov     [rsi+28h], eax
0x14001587c  mov     rax, [r15+30h]
0x140015880  mov     [rsi+30h], rax
0x140015884  lea     rdi, [rsi+38h]
0x140015888  cmp     [rsi+40h], r13b
0x14001588c  jz      short loc_1400158A9
0x14001588e  mov     rbx, [rdi]
0x140015891  call    cs:__imp_GetProcessHeap
0x140015897  mov     r8, rbx; lpMem
0x14001589a  xor     edx, edx; dwFlags
0x14001589c  mov     rcx, rax; hHeap
0x14001589f  call    cs:__imp_HeapFree
0x1400158a5  mov     [rsi+40h], r13b
0x1400158a9  mov     [rdi], r13
0x1400158ac  mov     rax, [r15+38h]
0x1400158b0  mov     [rdi], rax
0x1400158b3  mov     [r15+38h], r13
0x1400158b7  mov     al, [r15+40h]
0x1400158bb  mov     [rsi+40h], al
0x1400158be  mov     [r15+40h], r13b
0x1400158c2  mov     eax, [rbp+50h]
0x1400158c5  mov     [r14+50h], eax
0x1400158c9  movups  xmm0, xmmword ptr [rbp+58h]
0x1400158cd  movups  xmmword ptr [r14+58h], xmm0
0x1400158d2  movups  xmm1, xmmword ptr [rbp+68h]
0x1400158d6  movups  xmmword ptr [r14+68h], xmm1
0x1400158db  movups  xmm0, xmmword ptr [rbp+78h]
0x1400158df  movups  xmmword ptr [r14+78h], xmm0
0x1400158e4  movups  xmm1, xmmword ptr [rbp+88h]
0x1400158eb  movups  xmmword ptr [r14+88h], xmm1
0x1400158f3  movups  xmm0, xmmword ptr [rbp+98h]
0x1400158fa  movups  xmmword ptr [r14+98h], xmm0
0x140015902  movups  xmm1, xmmword ptr [rbp+0A8h]
0x140015909  movups  xmmword ptr [r14+0A8h], xmm1
0x140015911  movups  xmm0, xmmword ptr [rbp+0B8h]
0x140015918  movups  xmmword ptr [r14+0B8h], xmm0
0x140015920  movups  xmm1, xmmword ptr [rbp+0C8h]
0x140015927  movups  xmmword ptr [r14+0C8h], xmm1
0x14001592f  movups  xmm0, xmmword ptr [rbp+0D8h]
0x140015936  movups  xmmword ptr [r14+0D8h], xmm0
0x14001593e  mov     rax, [rbp+0E8h]
0x140015945  mov     [r14+0E8h], rax
0x14001594c  lea     r12, [rbp+0F0h]
0x140015953  lea     rdi, [r14+0F0h]
0x14001595a  cmp     rdi, r12
0x14001595d  jz      short loc_1400159AA
0x14001595f  mov     rcx, [rdi]
0x140015962  test    rcx, rcx
0x140015965  jz      short loc_140015991
0x140015967  or      eax, 0FFFFFFFFh
0x14001596a  lock xadd [rcx], eax
0x14001596e  cmp     eax, 1
0x140015971  jnz     short loc_14001598A
0x140015973  mov     rbx, [rdi]
0x140015976  call    cs:__imp_GetProcessHeap
0x14001597c  mov     r8, rbx; lpMem
0x14001597f  xor     edx, edx; dwFlags
0x140015981  mov     rcx, rax; hHeap
0x140015984  call    cs:__imp_HeapFree
0x14001598a  mov     [rdi], r13
0x14001598d  mov     [rdi+8], r13
0x140015991  mov     rax, [r12]
0x140015995  mov     [rdi], rax
0x140015998  mov     rax, [r12+8]
0x14001599d  mov     [rdi+8], rax
0x1400159a1  mov     [r12], r13
0x1400159a5  mov     [r12+8], r13
0x1400159aa  mov     eax, [rbp+100h]
0x1400159b0  mov     [r14+100h], eax
0x1400159b7  lea     r12, [rbp+118h]
0x1400159be  lea     rbx, [r14+118h]
0x1400159c5  cmp     rbx, r12
0x1400159c8  jz      short loc_140015A1D
0x1400159ca  mov     rcx, [rbx]
0x1400159cd  test    rcx, rcx
0x1400159d0  jz      short loc_140015A0D
0x1400159d2  or      eax, 0FFFFFFFFh
0x1400159d5  lock xadd [rcx], eax
0x1400159d9  cmp     eax, 1
0x1400159dc  jnz     short loc_140015A05
0x1400159de  mov     rdi, [rbx]
0x1400159e1  test    rdi, rdi
0x1400159e4  jz      short loc_140015A05
0x1400159e6  lea     rcx, [rdi+8]
0x1400159ea  call    ??1?$ActivityData@VFlightDataRecorderActivityClass@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FlightDataRecorderActivityClass,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<FlightDataRecorderActivityClass,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400159ef  mov     edx, 110h
0x1400159f4  mov     rcx, rdi; Block
0x1400159f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400159fc  lea     rcx, [r14+118h]
0x140015a03  jmp     short loc_140015A08
0x140015a05  mov     rcx, rbx
0x140015a08  mov     [rbx], r13
0x140015a0b  jmp     short loc_140015A10
0x140015a0d  mov     rcx, rbx
0x140015a10  mov     rax, [r12]
0x140015a14  mov     [rbx], rax
0x140015a17  mov     [r12], r13
0x140015a1b  jmp     short loc_140015A20
0x140015a1d  mov     rcx, rbx
0x140015a20  mov     rax, [rcx]
0x140015a23  test    rax, rax
0x140015a26  jz      short loc_140015A2C
0x140015a28  lea     rsi, [rax+8]
0x140015a2c  mov     [r14+110h], rsi
0x140015a33  lea     rdi, [r14+120h]
0x140015a3a  lea     rax, [rsi+28h]
0x140015a3e  mov     [rdi+20h], rax
0x140015a42  cmp     [rbp+138h], r13d
0x140015a49  jz      short loc_140015A82
0x140015a4b  cmp     [rdi+18h], r13d
0x140015a4f  jnz     loc_140015ADB
0x140015a55  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140015a5c  jz      short loc_140015AD8
0x140015a5e  mov     dl, 1
0x140015a60  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140015a65  mov     [rdi], rax
0x140015a68  test    rax, rax
0x140015a6b  jz      short loc_140015ADB
0x140015a6d  mov     rcx, [rax]
0x140015a70  mov     [rdi+10h], rcx
0x140015a74  mov     [rax], rdi
0x140015a77  call    cs:__imp_GetCurrentThreadId
0x140015a7d  mov     [rdi+18h], eax
0x140015a80  jmp     short loc_140015ADB
0x140015a82  cmp     [rdi+18h], r13d
0x140015a86  jz      short loc_140015ADB
0x140015a88  mov     ebx, [rdi+18h]
0x140015a8b  call    cs:__imp_GetCurrentThreadId
0x140015a91  cmp     ebx, eax
0x140015a93  jz      short loc_140015AB2
0x140015a95  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140015a9c  test    rax, rax
0x140015a9f  jz      short loc_140015AB2
0x140015aa1  mov     rdx, [rsp+68h]
0x140015aa6  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140015aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ab2  mov     [rdi+18h], r13d
0x140015ab6  mov     rcx, [rdi]
0x140015ab9  jmp     short loc_140015AC7
0x140015abb  cmp     rax, rdi
0x140015abe  jz      short loc_140015AD1
0x140015ac0  lea     rcx, [rax+10h]
0x140015ac4  mov     [rdi], rcx
0x140015ac7  mov     rax, [rcx]
0x140015aca  test    rax, rax
0x140015acd  jnz     short loc_140015ABB
0x140015acf  jmp     short loc_140015AD8
0x140015ad1  mov     rax, [rdi+10h]
0x140015ad5  mov     [rcx], rax
0x140015ad8  mov     [rdi], r13
0x140015adb  mov     [rbp+110h], r15
0x140015ae2  cmp     [rbp+138h], r13d
0x140015ae9  jz      short loc_140015B43
0x140015aeb  lea     rbx, [rbp+120h]
0x140015af2  call    cs:__imp_GetCurrentThreadId
0x140015af8  cmp     [rbx+18h], eax
0x140015afb  jz      short loc_140015B1A
0x140015afd  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140015b04  test    rax, rax
0x140015b07  jz      short loc_140015B1A
0x140015b09  mov     rdx, [rsp+68h]
0x140015b0e  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140015b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015b1a  mov     [rbx+18h], r13d
0x140015b1e  mov     rcx, [rbx]
0x140015b21  jmp     short loc_140015B2F
0x140015b23  cmp     rax, rbx
0x140015b26  jz      short loc_140015B39
0x140015b28  lea     rcx, [rax+10h]
0x140015b2c  mov     [rbx], rcx
0x140015b2f  mov     rax, [rcx]
0x140015b32  test    rax, rax
0x140015b35  jnz     short loc_140015B23
0x140015b37  jmp     short loc_140015B40
0x140015b39  mov     rax, [rbx+10h]
0x140015b3d  mov     [rcx], rax
0x140015b40  mov     [rbx], r13
0x140015b43  mov     rax, r14
0x140015b46  add     rsp, 28h
0x140015b4a  pop     r15
0x140015b4c  pop     r14
0x140015b4e  pop     r13
0x140015b50  pop     r12
0x140015b52  pop     rdi
0x140015b53  pop     rsi
0x140015b54  pop     rbp
0x140015b55  pop     rbx
0x140015b56  retn
```
