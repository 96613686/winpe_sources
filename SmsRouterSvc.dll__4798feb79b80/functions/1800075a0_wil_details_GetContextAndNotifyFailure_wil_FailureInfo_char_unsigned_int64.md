# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800075a0`
- end: `0x1800077a7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800075a0`
- `0x180007c9c`
- `0x180007d80`
- `0x1800085f8`
- `0x180008ad4`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000768c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000768c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v16; // r8
  struct wil::details_abi::ThreadLocalData *v17; // rbx
  int v18; // esi
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 v24; // dx

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v5);
  }
  v12 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v12 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v12;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14, v13);
      v17 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v18 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v18 )
          {
            v19 = wil::details::ProcessHeapAlloc(8u, 0x190u, v16);
            *((_QWORD *)v17 + 3) = v19;
            if ( v19 )
            {
              *((_DWORD *)v17 + 8) = 5;
              v20 = v19 + 200;
              while ( v19 != v20 )
              {
                *v19 = 80;
                v19 += 40;
              }
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_36:
            v24 = ((unsigned int)*((unsigned __int16 *)v17 + 17) + 1) % *((unsigned __int16 *)v17 + 16);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v17 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v5 + 2) )
            {
              v22 += 80;
              if ( v22 == v23 )
                goto LABEL_36;
            }
          }
        }
      }
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x1800075a0  push    rbx
0x1800075a2  push    rbp
0x1800075a3  push    rsi
0x1800075a4  push    rdi
0x1800075a5  push    r14
0x1800075a7  sub     rsp, 20h
0x1800075ab  mov     r14, r8
0x1800075ae  mov     rsi, rdx
0x1800075b1  mov     rdi, rcx
0x1800075b4  mov     byte ptr [rdx], 0
0x1800075b7  xor     bpl, bpl
0x1800075ba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800075c1  test    rbx, rbx
0x1800075c4  jz      loc_180007660
0x1800075ca  call    cs:__imp_GetCurrentThreadId
0x1800075d0  mov     r9d, eax
0x1800075d3  mov     r8d, eax
0x1800075d6  shr     r8, 2
0x1800075da  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800075e4  mul     r8
0x1800075e7  shr     rdx, 3
0x1800075eb  lea     rcx, [rdx+rdx*4]
0x1800075ef  add     rcx, rcx
0x1800075f2  sub     r8, rcx
0x1800075f5  mov     rbx, [rbx+r8*8]
0x1800075f9  jmp     short loc_180007604
0x1800075fb  cmp     [rbx], r9d
0x1800075fe  jz      short loc_18000767B
0x180007600  mov     rbx, [rbx+8]
0x180007604  test    rbx, rbx
0x180007607  jnz     short loc_1800075FB
0x180007609  test    rbx, rbx
0x18000760c  jz      short loc_180007660
0x18000760e  cmp     qword ptr [rbx], 0
0x180007612  jz      short loc_180007660
0x180007614  mov     [rsi], bpl
0x180007617  mov     r9, r14; unsigned __int64
0x18000761a  mov     r8, rsi; char *
0x18000761d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007620  mov     rcx, rdi; struct wil::FailureInfo *
0x180007623  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007628  test    al, al
0x18000762a  jz      short loc_180007630
0x18000762c  mov     [rdi+48h], rsi
0x180007630  mov     rbx, [rbx]
0x180007633  mov     al, [rbx+28h]
0x180007636  mov     byte ptr [rbx+28h], 1
0x18000763a  test    al, al
0x18000763c  jnz     short loc_180007657
0x18000763e  mov     rcx, [rbx+8]
0x180007642  mov     rax, [rcx]
0x180007645  mov     rdx, rdi
0x180007648  mov     rax, [rax]
0x18000764b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007650  or      bpl, al
0x180007653  mov     byte ptr [rbx+28h], 0
0x180007657  mov     rbx, [rbx+10h]
0x18000765b  test    rbx, rbx
0x18000765e  jnz     short loc_180007633
0x180007660  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007667  test    rax, rax
0x18000766a  jz      short loc_18000768C
0x18000766c  test    bpl, bpl
0x18000766f  jnz     short loc_180007681
0x180007671  test    byte ptr [rdi+4], 2
0x180007675  jnz     short loc_180007681
0x180007677  xor     ecx, ecx
0x180007679  jmp     short loc_180007683
0x18000767b  add     rbx, 10h
0x18000767f  jmp     short loc_180007609
0x180007681  mov     cl, 1
0x180007683  mov     rdx, rdi
0x180007686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000768b  nop
0x18000768c  call    cs:__imp_GetCurrentThreadId
0x180007692  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007698  cmp     ecx, eax
0x18000769a  jz      loc_18000779C
0x1800076a0  mov     ecx, 1
0x1800076a5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800076ad  inc     ecx; this
0x1800076af  cmp     ecx, 4
0x1800076b2  jge     loc_180007795
0x1800076b8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800076be  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800076c3  mov     rbx, rax
0x1800076c6  test    rax, rax
0x1800076c9  jz      loc_18000778B
0x1800076cf  mov     esi, [rax+10h]
0x1800076d2  mov     ebp, 50h ; 'P'
0x1800076d7  cmp     qword ptr [rax+18h], 0
0x1800076dc  jnz     short loc_180007713
0x1800076de  test    esi, esi
0x1800076e0  jz      short loc_180007713
0x1800076e2  mov     edx, 190h; dwBytes
0x1800076e7  lea     ecx, [rbp-48h]; dwFlags
0x1800076ea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800076ef  mov     [rbx+18h], rax
0x1800076f3  test    rax, rax
0x1800076f6  jz      short loc_180007713
0x1800076f8  mov     dword ptr [rbx+20h], 5
0x1800076ff  lea     rcx, [rax+190h]
0x180007706  jmp     short loc_18000770E
0x180007708  mov     [rax], bp
0x18000770b  add     rax, rbp
0x18000770e  cmp     rax, rcx
0x180007711  jnz     short loc_180007708
0x180007713  mov     r9, [rbx+18h]
0x180007717  test    r9, r9
0x18000771a  jz      short loc_18000778B
0x18000771c  test    esi, esi
0x18000771e  jz      short loc_180007751
0x180007720  mov     rcx, r9
0x180007723  movzx   eax, word ptr [rbx+20h]
0x180007727  lea     rdx, [rax+rax*4]
0x18000772b  shl     rdx, 4
0x18000772f  add     rdx, r9
0x180007732  cmp     r9, rdx
0x180007735  jz      short loc_180007751
0x180007737  mov     r8d, [rbx+10h]
0x18000773b  cmp     [rcx+4], r8d
0x18000773f  jbe     short loc_180007749
0x180007741  mov     eax, [rdi+8]
0x180007744  cmp     [rcx+8], eax
0x180007747  jz      short loc_18000778B
0x180007749  add     rcx, rbp
0x18000774c  cmp     rcx, rdx
0x18000774f  jnz     short loc_18000773B
0x180007751  movzx   eax, word ptr [rbx+22h]
0x180007755  inc     eax
0x180007757  movzx   ecx, word ptr [rbx+20h]
0x18000775b  xor     edx, edx
0x18000775d  div     ecx
0x18000775f  mov     [rbx+22h], dx
0x180007763  mov     rax, [rbx+8]
0x180007767  mov     r8d, 1
0x18000776d  lock xadd [rax], r8d
0x180007772  inc     r8d; unsigned int
0x180007775  movzx   eax, dx
0x180007778  lea     rcx, [rax+rax*4]
0x18000777c  shl     rcx, 4
0x180007780  add     rcx, r9; this
0x180007783  mov     rdx, rdi; struct wil::FailureInfo *
0x180007786  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000778b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007795  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000779c  add     rsp, 20h
0x1800077a0  pop     r14
0x1800077a2  pop     rdi
0x1800077a3  pop     rsi
0x1800077a4  pop     rbp
0x1800077a5  pop     rbx
0x1800077a6  retn
```
