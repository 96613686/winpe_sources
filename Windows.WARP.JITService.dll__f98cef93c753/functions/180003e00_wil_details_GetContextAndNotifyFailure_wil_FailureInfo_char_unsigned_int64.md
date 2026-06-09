# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003e00`
- end: `0x18000421b`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `1051`
- prototype: `void __fastcall(wil::details *this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001224`
- `0x1800017fc`
- `0x180003924`
- `0x180003d14`
- `0x180003e00`
- `0x18000941c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f00`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // r14
  char v6; // si
  __int64 v7; // rbp
  __int64 v8; // rbx
  unsigned __int64 CurrentThreadId; // r9
  struct wil::details::ThreadFailureCallbackHolder **v10; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al
  __int64 v13; // r15
  DWORD v14; // eax
  bool v15; // dl
  wil::details_abi *v16; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v18; // r8
  struct wil::details_abi::ThreadLocalData *v19; // rbx
  int v20; // esi
  _WORD *v21; // rax
  _WORD *v22; // rcx
  __int64 v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rdx
  unsigned int v26; // edx
  __int64 v27; // rsi
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rbp
  __int64 v33; // rcx
  __int64 v34; // rax
  SIZE_T v35; // rbp
  void *v36; // r15
  void *v37; // rbx
  HANDLE ProcessHeap; // rax
  char *v39; // rbx
  rsize_t v40; // rdx
  char *v41; // rbp
  _BYTE *v42; // r8
  __int64 v43; // rax
  __int64 v44; // r15
  _BYTE *v45; // r8
  __int64 v46; // rax
  __int64 v47; // r15
  _WORD *v48; // r8
  __int64 v49; // rax
  unsigned __int64 v50; // r14

  v5 = this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = 1;
  v8 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    for ( this = *(wil::details **)(v8 + 8 * ((CurrentThreadId >> 2) % 0xA)); ; this = (wil::details *)*((_QWORD *)this + 1) )
    {
      if ( !this )
      {
        v10 = 0;
        goto LABEL_7;
      }
      if ( *(_DWORD *)this == (_DWORD)CurrentThreadId )
        break;
    }
    v10 = (struct wil::details::ThreadFailureCallbackHolder **)((char *)this + 16);
LABEL_7:
    if ( v10 && *v10 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v10, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v11 = *v10;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  v13 = 2;
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (LOBYTE(this) = 0, (*((_BYTE *)v5 + 4) & 2) != 0) )
      LOBYTE(this) = 1;
    wil::details::g_pfnTelemetryCallback(this, v5);
  }
  v14 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v14 )
  {
    v16 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v16 >= 4 )
    {
LABEL_83:
      _InterlockedAdd(&`wil::SetLastError'::`5'::depth, 0xFFFFFFFF);
      return;
    }
    `wil::SetLastError'::`2'::lastThread = v14;
    ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v16, v15);
    v19 = ThreadLocalDataCache;
    if ( !ThreadLocalDataCache )
      goto LABEL_82;
    v20 = *((_DWORD *)ThreadLocalDataCache + 4);
    if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
    {
      if ( v20 )
      {
        v21 = wil::details::ProcessHeapAlloc(8u, 0x190u, v18);
        *((_QWORD *)v19 + 3) = v21;
        if ( v21 )
        {
          *((_DWORD *)v19 + 8) = 5;
          v22 = v21 + 200;
          while ( v21 != v22 )
          {
            *v21 = 80;
            v21 += 40;
          }
        }
      }
    }
    v23 = *((_QWORD *)v19 + 3);
    if ( !v23 )
      goto LABEL_82;
    if ( v20 )
    {
      v24 = *((_QWORD *)v19 + 3);
      v25 = v23 + 80LL * *((unsigned __int16 *)v19 + 16);
      if ( v23 != v25 )
      {
        v18 = *((unsigned int *)v19 + 4);
        while ( *(_DWORD *)(v24 + 4) <= (unsigned int)v18 || *(_DWORD *)(v24 + 8) != *((_DWORD *)v5 + 2) )
        {
          v24 += 80;
          if ( v24 == v25 )
            goto LABEL_37;
        }
        goto LABEL_82;
      }
    }
LABEL_37:
    v26 = ((unsigned int)*((unsigned __int16 *)v19 + 17) + 1) % *((unsigned __int16 *)v19 + 16);
    *((_WORD *)v19 + 17) = v26;
    v27 = 10LL * (unsigned __int16)v26;
    *(_DWORD *)(v23 + 8 * v27 + 4) = _InterlockedIncrement(*((volatile signed __int32 **)v19 + 1));
    *(_DWORD *)(v23 + 8 * v27 + 8) = *((_DWORD *)v5 + 2);
    *(_QWORD *)(v23 + 8 * v27 + 16) = 0;
    *(_WORD *)(v23 + 8 * v27 + 24) = *((_WORD *)v5 + 32);
    *(_BYTE *)(v23 + 8 * v27 + 26) = *(_BYTE *)v5;
    *(_QWORD *)(v23 + 8 * v27 + 32) = 0;
    *(_QWORD *)(v23 + 8 * v27 + 40) = *((_QWORD *)v5 + 17);
    *(_QWORD *)(v23 + 8 * v27 + 48) = *((_QWORD *)v5 + 18);
    *(_QWORD *)(v23 + 8 * v27 + 56) = 0;
    v28 = *((_QWORD *)v5 + 7);
    if ( v28 )
    {
      v30 = -1;
      do
        ++v30;
      while ( *(_BYTE *)(v28 + v30) );
      v29 = v30 + 1;
    }
    else
    {
      v29 = 1;
    }
    v31 = *((_QWORD *)v5 + 16);
    if ( v31 )
    {
      v32 = -1;
      do
        ++v32;
      while ( *(_BYTE *)(v31 + v32) );
      v7 = v32 + 1;
    }
    v33 = *((_QWORD *)v5 + 3);
    if ( v33 )
    {
      v34 = -1;
      do
        ++v34;
      while ( *(_WORD *)(v33 + 2 * v34) );
      v13 = 2 * v34 + 2;
    }
    v35 = v29 + v13 + v7;
    if ( !*(_QWORD *)(v23 + 8 * v27 + 64) || *(_QWORD *)(v23 + 8 * v27 + 72) < v35 )
    {
      v36 = wil::details::ProcessHeapAlloc(8u, v35, v18);
      if ( v36 )
      {
        v37 = *(void **)(v23 + 8 * v27 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v37);
        *(_QWORD *)(v23 + 8 * v27 + 64) = v36;
        *(_QWORD *)(v23 + 8 * v27 + 72) = v35;
      }
    }
    v39 = *(char **)(v23 + 8 * v27 + 64);
    if ( !v39 )
    {
LABEL_82:
      `wil::SetLastError'::`2'::lastThread = 0;
      goto LABEL_83;
    }
    v40 = *(_QWORD *)(v23 + 8 * v27 + 72);
    v41 = &v39[v40];
    if ( v39 != &v39[v40] && (v42 = (_BYTE *)*((_QWORD *)v5 + 7)) != 0 && *v42 )
    {
      v43 = -1;
      do
        ++v43;
      while ( v42[v43] );
      v44 = v43 + 1;
      if ( v40 < v43 + 1 )
      {
        *(_QWORD *)(v23 + 8 * v27 + 16) = 0;
LABEL_65:
        v45 = (_BYTE *)*((_QWORD *)v5 + 16);
        if ( v45 && *v45 )
        {
          v46 = -1;
          do
            ++v46;
          while ( v45[v46] );
          v47 = v46 + 1;
          if ( v41 - v39 < (unsigned __int64)(v46 + 1) )
          {
            *(_QWORD *)(v23 + 8 * v27 + 32) = 0;
LABEL_74:
            v48 = (_WORD *)*((_QWORD *)v5 + 3);
            if ( v48 )
            {
              if ( *v48 )
              {
                v49 = -1;
                do
                  ++v49;
                while ( v48[v49] );
                v50 = 2 * v49 + 2;
                if ( v41 - v39 >= v50 )
                {
                  memcpy_s(v39, v41 - v39, v48, 2 * v49 + 2);
                  *(_QWORD *)(v23 + 8 * v27 + 56) = v39;
                  v39 += v50;
LABEL_81:
                  memset_0(v39, 0, v41 - v39);
                  goto LABEL_82;
                }
              }
            }
LABEL_80:
            *(_QWORD *)(v23 + 8 * v27 + 56) = 0;
            goto LABEL_81;
          }
          memcpy_s(v39, v41 - v39, v45, v46 + 1);
          *(_QWORD *)(v23 + 8 * v27 + 32) = v39;
          v39 += v47;
LABEL_73:
          if ( v39 == v41 )
            goto LABEL_80;
          goto LABEL_74;
        }
LABEL_72:
        *(_QWORD *)(v23 + 8 * v27 + 32) = 0;
        goto LABEL_73;
      }
      memcpy_s(*(void *const *)(v23 + 8 * v27 + 64), v40, v42, v43 + 1);
      *(_QWORD *)(v23 + 8 * v27 + 16) = v39;
      v39 += v44;
    }
    else
    {
      *(_QWORD *)(v23 + 8 * v27 + 16) = 0;
    }
    if ( v39 == v41 )
      goto LABEL_72;
    goto LABEL_65;
  }
}

```

## disassembly

```asm
0x180003e00  push    rbx
0x180003e02  push    rbp
0x180003e03  push    rsi
0x180003e04  push    rdi
0x180003e05  push    r12
0x180003e07  push    r13
0x180003e09  push    r14
0x180003e0b  push    r15
0x180003e0d  sub     rsp, 28h
0x180003e11  mov     r15, r8
0x180003e14  mov     rdi, rdx
0x180003e17  mov     r14, rcx
0x180003e1a  xor     r12d, r12d
0x180003e1d  mov     [rdx], r12b
0x180003e20  mov     sil, r12b
0x180003e23  lea     ebp, [r12+1]
0x180003e28  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003e2f  test    rbx, rbx
0x180003e32  jz      loc_180003ED4
0x180003e38  call    cs:__imp_GetCurrentThreadId
0x180003e3e  mov     r9d, eax
0x180003e41  mov     r8d, eax
0x180003e44  shr     r8, 2
0x180003e48  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003e52  mul     r8
0x180003e55  shr     rdx, 3
0x180003e59  lea     rcx, [rdx+rdx*4]
0x180003e5d  add     rcx, rcx
0x180003e60  sub     r8, rcx
0x180003e63  mov     rcx, [rbx+r8*8]
0x180003e67  jmp     short loc_180003E76
0x180003e69  cmp     [rcx], r9d
0x180003e6c  jz      loc_180003F8C
0x180003e72  mov     rcx, [rcx+8]
0x180003e76  test    rcx, rcx
0x180003e79  jnz     short loc_180003E69
0x180003e7b  mov     rbx, r12
0x180003e7e  test    rbx, rbx
0x180003e81  jz      short loc_180003ED4
0x180003e83  cmp     [rbx], r12
0x180003e86  jz      short loc_180003ED4
0x180003e88  mov     [rdi], r12b
0x180003e8b  mov     r9, r15; unsigned __int64
0x180003e8e  mov     r8, rdi; char *
0x180003e91  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003e94  mov     rcx, r14; struct wil::FailureInfo *
0x180003e97  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003e9c  test    al, al
0x180003e9e  jz      short loc_180003EA4
0x180003ea0  mov     [r14+48h], rdi
0x180003ea4  mov     rbx, [rbx]
0x180003ea7  mov     al, [rbx+28h]
0x180003eaa  mov     [rbx+28h], bpl
0x180003eae  test    al, al
0x180003eb0  jnz     short loc_180003ECB
0x180003eb2  mov     rcx, [rbx+8]
0x180003eb6  mov     rax, [rcx]
0x180003eb9  mov     rdx, r14
0x180003ebc  mov     rax, [rax]
0x180003ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec4  or      sil, al
0x180003ec7  mov     [rbx+28h], r12b
0x180003ecb  mov     rbx, [rbx+10h]
0x180003ecf  test    rbx, rbx
0x180003ed2  jnz     short loc_180003EA7
0x180003ed4  mov     r15d, 2
0x180003eda  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003ee1  test    rax, rax
0x180003ee4  jz      short loc_180003F00
0x180003ee6  test    sil, sil
0x180003ee9  jnz     short loc_180003EF4
0x180003eeb  test    [r14+4], r15b
0x180003eef  mov     cl, r12b
0x180003ef2  jz      short loc_180003EF7
0x180003ef4  mov     cl, bpl
0x180003ef7  mov     rdx, r14
0x180003efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eff  nop
0x180003f00  call    cs:__imp_GetCurrentThreadId
0x180003f06  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003f0c  cmp     ecx, eax
0x180003f0e  jz      loc_18000420A
0x180003f14  mov     ecx, ebp
0x180003f16  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003f1e  add     ecx, ebp; this
0x180003f20  or      r13, 0FFFFFFFFFFFFFFFFh
0x180003f24  cmp     ecx, 4
0x180003f27  jge     loc_180004202
0x180003f2d  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003f33  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003f38  mov     rbx, rax
0x180003f3b  test    rax, rax
0x180003f3e  jz      loc_1800041FB
0x180003f44  mov     esi, [rax+10h]
0x180003f47  lea     r9d, [r13+51h]
0x180003f4b  cmp     [rax+18h], r12
0x180003f4f  jnz     short loc_180003F95
0x180003f51  test    esi, esi
0x180003f53  jz      short loc_180003F95
0x180003f55  mov     edx, 190h; dwBytes
0x180003f5a  lea     ecx, [r13+9]; dwFlags
0x180003f5e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003f63  mov     [rbx+18h], rax
0x180003f67  lea     r9d, [r13+51h]
0x180003f6b  test    rax, rax
0x180003f6e  jz      short loc_180003F95
0x180003f70  mov     dword ptr [rbx+20h], 5
0x180003f77  lea     rcx, [rax+190h]
0x180003f7e  cmp     rax, rcx
0x180003f81  jz      short loc_180003F95
0x180003f83  mov     [rax], r9w
0x180003f87  add     rax, r9
0x180003f8a  jmp     short loc_180003F7E
0x180003f8c  lea     rbx, [rcx+10h]
0x180003f90  jmp     loc_180003E7E
0x180003f95  mov     rdi, [rbx+18h]
0x180003f99  test    rdi, rdi
0x180003f9c  jz      loc_1800041FB
0x180003fa2  test    esi, esi
0x180003fa4  jz      short loc_180003FDC
0x180003fa6  mov     rcx, rdi
0x180003fa9  movzx   eax, word ptr [rbx+20h]
0x180003fad  lea     rdx, [rax+rax*4]
0x180003fb1  shl     rdx, 4
0x180003fb5  add     rdx, rdi
0x180003fb8  cmp     rdi, rdx
0x180003fbb  jz      short loc_180003FDC
0x180003fbd  mov     r8d, [rbx+10h]; unsigned __int64
0x180003fc1  cmp     [rcx+4], r8d
0x180003fc5  jbe     short loc_180003FD4
0x180003fc7  mov     eax, [r14+8]
0x180003fcb  cmp     [rcx+8], eax
0x180003fce  jz      loc_1800041FB
0x180003fd4  add     rcx, r9
0x180003fd7  cmp     rcx, rdx
0x180003fda  jnz     short loc_180003FC1
0x180003fdc  movzx   eax, word ptr [rbx+22h]
0x180003fe0  add     eax, ebp
0x180003fe2  movzx   ecx, word ptr [rbx+20h]
0x180003fe6  xor     edx, edx
0x180003fe8  div     ecx
0x180003fea  mov     [rbx+22h], dx
0x180003fee  movzx   eax, dx
0x180003ff1  lea     rsi, [rax+rax*4]
0x180003ff5  add     rsi, rsi
0x180003ff8  mov     rax, [rbx+8]
0x180003ffc  mov     ecx, ebp
0x180003ffe  lock xadd [rax], ecx
0x180004002  add     ecx, ebp
0x180004004  mov     [rdi+rsi*8+4], ecx
0x180004008  mov     eax, [r14+8]
0x18000400c  mov     [rdi+rsi*8+8], eax
0x180004010  mov     [rdi+rsi*8+10h], r12
0x180004015  movzx   eax, word ptr [r14+40h]
0x18000401a  mov     [rdi+rsi*8+18h], ax
0x18000401f  mov     al, [r14]
0x180004022  mov     [rdi+rsi*8+1Ah], al
0x180004026  mov     [rdi+rsi*8+20h], r12
0x18000402b  mov     rax, [r14+88h]
0x180004032  mov     [rdi+rsi*8+28h], rax
0x180004037  mov     rax, [r14+90h]
0x18000403e  mov     [rdi+rsi*8+30h], rax
0x180004043  mov     [rdi+rsi*8+38h], r12
0x180004048  mov     rcx, [r14+38h]
0x18000404c  test    rcx, rcx
0x18000404f  jnz     short loc_180004056
0x180004051  mov     rdx, rbp
0x180004054  jmp     short loc_180004066
0x180004056  mov     rax, r13
0x180004059  inc     rax
0x18000405c  cmp     [rcx+rax], r12b
0x180004060  jnz     short loc_180004059
0x180004062  lea     rdx, [rax+1]
0x180004066  mov     rax, [r14+80h]
0x18000406d  test    rax, rax
0x180004070  jz      short loc_180004081
0x180004072  mov     rbp, r13
0x180004075  inc     rbp
0x180004078  cmp     [rax+rbp], r12b
0x18000407c  jnz     short loc_180004075
0x18000407e  inc     rbp
0x180004081  mov     rcx, [r14+18h]
0x180004085  test    rcx, rcx
0x180004088  jz      short loc_18000409F
0x18000408a  mov     rax, r13
0x18000408d  inc     rax
0x180004090  cmp     [rcx+rax*2], r12w
0x180004095  jnz     short loc_18000408D
0x180004097  lea     r15, ds:2[rax*2]
0x18000409f  add     rbp, r15
0x1800040a2  add     rbp, rdx
0x1800040a5  cmp     [rdi+rsi*8+40h], r12
0x1800040aa  jz      short loc_1800040B3
0x1800040ac  cmp     [rdi+rsi*8+48h], rbp
0x1800040b1  jnb     short loc_1800040EB
0x1800040b3  mov     rdx, rbp; dwBytes
0x1800040b6  mov     ecx, 8; dwFlags
0x1800040bb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800040c0  mov     r15, rax
0x1800040c3  test    rax, rax
0x1800040c6  jz      short loc_1800040EB
0x1800040c8  mov     rbx, [rdi+rsi*8+40h]
0x1800040cd  call    cs:__imp_GetProcessHeap
0x1800040d3  mov     r8, rbx; lpMem
0x1800040d6  xor     edx, edx; dwFlags
0x1800040d8  mov     rcx, rax; hHeap
0x1800040db  call    cs:__imp_HeapFree
0x1800040e1  mov     [rdi+rsi*8+40h], r15
0x1800040e6  mov     [rdi+rsi*8+48h], rbp
0x1800040eb  mov     rbx, [rdi+rsi*8+40h]
0x1800040f0  test    rbx, rbx
0x1800040f3  jz      loc_1800041FB
0x1800040f9  mov     rdx, [rdi+rsi*8+48h]; DestinationSize
0x1800040fe  lea     rbp, [rdx+rbx]
0x180004102  cmp     rbx, rbp
0x180004105  jz      short loc_180004146
0x180004107  mov     r8, [r14+38h]; Source
0x18000410b  test    r8, r8
0x18000410e  jz      short loc_180004146
0x180004110  cmp     [r8], r12b
0x180004113  jz      short loc_180004146
0x180004115  mov     rax, r13
0x180004118  inc     rax
0x18000411b  cmp     [r8+rax], r12b
0x18000411f  jnz     short loc_180004118
0x180004121  lea     r15, [rax+1]
0x180004125  cmp     rdx, r15
0x180004128  jnb     short loc_180004131
0x18000412a  mov     [rdi+rsi*8+10h], r12
0x18000412f  jmp     short loc_180004150
0x180004131  mov     r9, r15; SourceSize
0x180004134  mov     rcx, rbx; Destination
0x180004137  call    memcpy_s
0x18000413c  mov     [rdi+rsi*8+10h], rbx
0x180004141  add     rbx, r15
0x180004144  jmp     short loc_18000414B
0x180004146  mov     [rdi+rsi*8+10h], r12
0x18000414b  cmp     rbx, rbp
0x18000414e  jz      short loc_180004198
0x180004150  mov     r8, [r14+80h]; Source
0x180004157  test    r8, r8
0x18000415a  jz      short loc_180004198
0x18000415c  cmp     [r8], r12b
0x18000415f  jz      short loc_180004198
0x180004161  mov     rax, r13
0x180004164  inc     rax
0x180004167  cmp     [r8+rax], r12b
0x18000416b  jnz     short loc_180004164
0x18000416d  lea     r15, [rax+1]
0x180004171  mov     rdx, rbp
0x180004174  sub     rdx, rbx; DestinationSize
0x180004177  cmp     rdx, r15
0x18000417a  jnb     short loc_180004183
0x18000417c  mov     [rdi+rsi*8+20h], r12
0x180004181  jmp     short loc_1800041A2
0x180004183  mov     r9, r15; SourceSize
0x180004186  mov     rcx, rbx; Destination
0x180004189  call    memcpy_s
0x18000418e  mov     [rdi+rsi*8+20h], rbx
0x180004193  add     rbx, r15
0x180004196  jmp     short loc_18000419D
0x180004198  mov     [rdi+rsi*8+20h], r12
0x18000419d  cmp     rbx, rbp
0x1800041a0  jz      short loc_1800041E6
0x1800041a2  mov     r8, [r14+18h]; Source
0x1800041a6  test    r8, r8
0x1800041a9  jz      short loc_1800041E6
0x1800041ab  cmp     [r8], r12w
0x1800041af  jz      short loc_1800041E6
0x1800041b1  mov     rax, r13
0x1800041b4  inc     rax
0x1800041b7  cmp     [r8+rax*2], r12w
0x1800041bc  jnz     short loc_1800041B4
0x1800041be  lea     r14, ds:2[rax*2]
0x1800041c6  mov     rdx, rbp
0x1800041c9  sub     rdx, rbx; DestinationSize
0x1800041cc  cmp     rdx, r14
0x1800041cf  jb      short loc_1800041E6
0x1800041d1  mov     r9, r14; SourceSize
0x1800041d4  mov     rcx, rbx; Destination
0x1800041d7  call    memcpy_s
0x1800041dc  mov     [rdi+rsi*8+38h], rbx
0x1800041e1  add     rbx, r14
0x1800041e4  jmp     short loc_1800041EB
0x1800041e6  mov     [rdi+rsi*8+38h], r12
0x1800041eb  sub     rbp, rbx
0x1800041ee  mov     r8, rbp; Size
0x1800041f1  xor     edx, edx; Val
0x1800041f3  mov     rcx, rbx; void *
0x1800041f6  call    memset_0
0x1800041fb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r12d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004202  lock add cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, r13d; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000420a  add     rsp, 28h
0x18000420e  pop     r15
0x180004210  pop     r14
0x180004212  pop     r13
0x180004214  pop     r12
0x180004216  pop     rdi
0x180004217  pop     rsi
0x180004218  pop     rbp
  ... truncated ...
```
