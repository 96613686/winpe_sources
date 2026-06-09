# wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)

- ea: `0x180005860`
- end: `0x180005ad5`
- name: `??0?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b5dc`

## callees

- `0x1800042fc`
- `0x180005860`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a70`

## string_xrefs

- `0x180005a8c`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2,
        char a3)
{
  __int64 v3; // rdi
  __int64 v4; // r14
  void **v5; // r15
  __int64 v7; // rbp
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v11; // rbx
  char v12; // al
  _QWORD *Local; // rax
  __int64 v14; // rax
  __int64 **v15; // rbx
  __int64 *v16; // rcx
  __int64 v17; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]

  v3 = a1 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  v4 = a2 + 8;
  *(_BYTE *)(a1 + 12) = 0;
  *(_QWORD *)a1 = &wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v5 = (void **)(a1 + 64);
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  v7 = a2;
  *(_BYTE *)(a1 + 12) = *(_BYTE *)(a2 + 12);
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(a2 + 32);
  *(_DWORD *)(a2 + 8) = 0;
  *(_BYTE *)(a2 + 12) = 0;
  *(_OWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 48) = *(_DWORD *)(a2 + 48);
  *(_QWORD *)(a1 + 56) = *(_QWORD *)(a2 + 56);
  if ( *(_BYTE *)(a1 + 72) )
  {
    v9 = *v5;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
    *(_BYTE *)(v3 + 64) = 0;
  }
  *v5 = 0;
  v11 = (_QWORD *)(a1 + 288);
  *v5 = *(void **)(v4 + 56);
  v12 = *(_BYTE *)(v4 + 64);
  *(_QWORD *)(v4 + 56) = 0;
  *(_BYTE *)(v3 + 64) = v12;
  *(_BYTE *)(v4 + 64) = 0;
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(v7 + 80);
  *(_OWORD *)(a1 + 88) = *(_OWORD *)(v7 + 88);
  *(_OWORD *)(a1 + 104) = *(_OWORD *)(v7 + 104);
  *(_OWORD *)(a1 + 120) = *(_OWORD *)(v7 + 120);
  *(_OWORD *)(a1 + 136) = *(_OWORD *)(v7 + 136);
  *(_OWORD *)(a1 + 152) = *(_OWORD *)(v7 + 152);
  *(_OWORD *)(a1 + 168) = *(_OWORD *)(v7 + 168);
  *(_OWORD *)(a1 + 184) = *(_OWORD *)(v7 + 184);
  *(_OWORD *)(a1 + 200) = *(_OWORD *)(v7 + 200);
  *(_OWORD *)(a1 + 216) = *(_OWORD *)(v7 + 216);
  *(_QWORD *)(a1 + 232) = *(_QWORD *)(v7 + 232);
  *(_QWORD *)(a1 + 240) = *(_QWORD *)(v7 + 240);
  *(_QWORD *)(a1 + 248) = *(_QWORD *)(v7 + 248);
  *(_QWORD *)(v7 + 240) = 0;
  *(_QWORD *)(v7 + 248) = 0;
  *(_DWORD *)(a1 + 256) = *(_DWORD *)(v7 + 256);
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 280) = *(_QWORD *)(v7 + 280);
  *(_QWORD *)(v7 + 280) = 0;
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
  v14 = *(_QWORD *)(a1 + 280);
  if ( v14 )
    v3 = v14 + 8;
  *(_QWORD *)(a1 + 272) = v3;
  *(_QWORD *)(a1 + 320) = v3 + 40;
  *(_QWORD *)(v7 + 272) = v4;
  if ( *(_DWORD *)(v7 + 312) )
  {
    v15 = (__int64 **)(v7 + 288);
    if ( *(_DWORD *)(v7 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    v16 = *v15;
    *(_DWORD *)(v7 + 312) = 0;
    while ( 1 )
    {
      v17 = *v16;
      if ( !*v16 )
        break;
      if ( (__int64 **)v17 == v15 )
      {
        *v16 = *(_QWORD *)(v7 + 304);
        break;
      }
      v16 = (__int64 *)(v17 + 16);
      *v15 = (__int64 *)(v17 + 16);
    }
    *v15 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180005860  push    rbx
0x180005862  push    rbp
0x180005863  push    rsi
0x180005864  push    rdi
0x180005865  push    r12
0x180005867  push    r13
0x180005869  push    r14
0x18000586b  push    r15
0x18000586d  sub     rsp, 28h
0x180005871  lea     rdi, [rcx+8]
0x180005875  xor     r13d, r13d
0x180005878  mov     [rdi], r13d
0x18000587b  lea     r14, [rdx+8]
0x18000587f  mov     [rdi+4], r13b
0x180005883  lea     rax, ??_7?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18000588a  mov     [rcx], rax
0x18000588d  lea     r15, [rdi+38h]
0x180005891  mov     eax, [r14]
0x180005894  mov     r12b, r8b
0x180005897  mov     [rdi], eax
0x180005899  mov     rbp, rdx
0x18000589c  mov     al, [r14+4]
0x1800058a0  mov     rsi, rcx
0x1800058a3  mov     [rdi+4], al
0x1800058a6  movups  xmm0, xmmword ptr [r14+8]
0x1800058ab  movdqu  xmmword ptr [rdi+8], xmm0
0x1800058b0  movups  xmm1, xmmword ptr [r14+18h]
0x1800058b5  xorps   xmm0, xmm0
0x1800058b8  movdqu  xmmword ptr [rdi+18h], xmm1
0x1800058bd  mov     [r14], r13d
0x1800058c0  mov     [r14+4], r13b
0x1800058c4  movups  xmmword ptr [rdi+28h], xmm0
0x1800058c8  movups  xmmword ptr [rdi+38h], xmm0
0x1800058cc  mov     eax, [r14+28h]
0x1800058d0  mov     [rdi+28h], eax
0x1800058d3  mov     rax, [r14+30h]
0x1800058d7  mov     [rdi+30h], rax
0x1800058db  cmp     [rdi+40h], r13b
0x1800058df  jz      short loc_1800058FC
0x1800058e1  mov     rbx, [r15]
0x1800058e4  call    cs:__imp_GetProcessHeap
0x1800058ea  mov     r8, rbx; lpMem
0x1800058ed  xor     edx, edx; dwFlags
0x1800058ef  mov     rcx, rax; hHeap
0x1800058f2  call    cs:__imp_HeapFree
0x1800058f8  mov     [rdi+40h], r13b
0x1800058fc  mov     [r15], r13
0x1800058ff  lea     rbx, [rsi+120h]
0x180005906  mov     rax, [r14+38h]
0x18000590a  mov     [r15], rax
0x18000590d  mov     al, [r14+40h]
0x180005911  mov     [r14+38h], r13
0x180005915  mov     [rdi+40h], al
0x180005918  mov     [r14+40h], r13b
0x18000591c  mov     eax, [rbp+50h]
0x18000591f  mov     [rsi+50h], eax
0x180005922  movups  xmm0, xmmword ptr [rbp+58h]
0x180005926  movups  xmmword ptr [rsi+58h], xmm0
0x18000592a  movups  xmm1, xmmword ptr [rbp+68h]
0x18000592e  movups  xmmword ptr [rsi+68h], xmm1
0x180005932  movups  xmm0, xmmword ptr [rbp+78h]
0x180005936  movups  xmmword ptr [rsi+78h], xmm0
0x18000593a  movups  xmm1, xmmword ptr [rbp+88h]
0x180005941  movups  xmmword ptr [rsi+88h], xmm1
0x180005948  movups  xmm0, xmmword ptr [rbp+98h]
0x18000594f  movups  xmmword ptr [rsi+98h], xmm0
0x180005956  movups  xmm1, xmmword ptr [rbp+0A8h]
0x18000595d  movups  xmmword ptr [rsi+0A8h], xmm1
0x180005964  movups  xmm0, xmmword ptr [rbp+0B8h]
0x18000596b  movups  xmmword ptr [rsi+0B8h], xmm0
0x180005972  movups  xmm1, xmmword ptr [rbp+0C8h]
0x180005979  movups  xmmword ptr [rsi+0C8h], xmm1
0x180005980  movups  xmm0, xmmword ptr [rbp+0D8h]
0x180005987  movups  xmmword ptr [rsi+0D8h], xmm0
0x18000598e  mov     rax, [rbp+0E8h]
0x180005995  mov     [rsi+0E8h], rax
0x18000599c  mov     rax, [rbp+0F0h]
0x1800059a3  mov     [rsi+0F0h], rax
0x1800059aa  mov     rax, [rbp+0F8h]
0x1800059b1  mov     [rsi+0F8h], rax
0x1800059b8  mov     [rbp+0F0h], r13
0x1800059bf  mov     [rbp+0F8h], r13
0x1800059c6  mov     eax, [rbp+100h]
0x1800059cc  mov     [rsi+100h], eax
0x1800059d2  xor     eax, eax
0x1800059d4  mov     [rsi+108h], rax
0x1800059db  mov     rax, [rbp+118h]
0x1800059e2  mov     [rsi+118h], rax
0x1800059e9  mov     [rbp+118h], r13
0x1800059f0  mov     [rbx], r13
0x1800059f3  mov     [rbx+8], rsi
0x1800059f7  mov     [rbx+10h], r13
0x1800059fb  mov     [rbx+18h], r13d
0x1800059ff  mov     [rbx+20h], r13
0x180005a03  mov     [rbx+28h], r13b
0x180005a07  test    r12b, r12b
0x180005a0a  jz      short loc_180005A37
0x180005a0c  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005a13  jz      short loc_180005A37
0x180005a15  mov     dl, 1
0x180005a17  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180005a1c  mov     [rbx], rax
0x180005a1f  test    rax, rax
0x180005a22  jz      short loc_180005A37
0x180005a24  mov     rcx, [rax]
0x180005a27  mov     [rbx+10h], rcx
0x180005a2b  mov     [rax], rbx
0x180005a2e  call    cs:__imp_GetCurrentThreadId
0x180005a34  mov     [rbx+18h], eax
0x180005a37  mov     rax, [rsi+118h]
0x180005a3e  test    rax, rax
0x180005a41  jz      short loc_180005A47
0x180005a43  lea     rdi, [rax+8]
0x180005a47  mov     [rsi+110h], rdi
0x180005a4e  lea     rax, [rdi+28h]
0x180005a52  mov     [rsi+140h], rax
0x180005a59  mov     [rbp+110h], r14
0x180005a60  cmp     [rbp+138h], r13d
0x180005a67  jz      short loc_180005AC1
0x180005a69  lea     rbx, [rbp+120h]
0x180005a70  call    cs:__imp_GetCurrentThreadId
0x180005a76  cmp     [rbx+18h], eax
0x180005a79  jz      short loc_180005A98
0x180005a7b  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180005a82  test    rax, rax
0x180005a85  jz      short loc_180005A98
0x180005a87  mov     rdx, [rsp+68h]
0x180005a8c  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180005a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a98  mov     rcx, [rbx]
0x180005a9b  mov     [rbx+18h], r13d
0x180005a9f  jmp     short loc_180005AAD
0x180005aa1  cmp     rax, rbx
0x180005aa4  jz      short loc_180005AB7
0x180005aa6  lea     rcx, [rax+10h]
0x180005aaa  mov     [rbx], rcx
0x180005aad  mov     rax, [rcx]
0x180005ab0  test    rax, rax
0x180005ab3  jnz     short loc_180005AA1
0x180005ab5  jmp     short loc_180005ABE
0x180005ab7  mov     rax, [rbx+10h]
0x180005abb  mov     [rcx], rax
0x180005abe  mov     [rbx], r13
0x180005ac1  mov     rax, rsi
0x180005ac4  add     rsp, 28h
0x180005ac8  pop     r15
0x180005aca  pop     r14
0x180005acc  pop     r13
0x180005ace  pop     r12
0x180005ad0  pop     rdi
0x180005ad1  pop     rsi
0x180005ad2  pop     rbp
0x180005ad3  pop     rbx
0x180005ad4  retn
```
