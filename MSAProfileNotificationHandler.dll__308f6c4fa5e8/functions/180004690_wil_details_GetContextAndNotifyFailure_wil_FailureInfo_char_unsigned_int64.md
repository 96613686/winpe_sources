# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004690`
- end: `0x180004897`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004690`
- `0x180004d8c`
- `0x180004e70`
- `0x18000577c`
- `0x180005e50`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000477c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000477c`

## pseudocode

```c
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
0x180004690  push    rbx
0x180004692  push    rbp
0x180004693  push    rsi
0x180004694  push    rdi
0x180004695  push    r14
0x180004697  sub     rsp, 20h
0x18000469b  mov     r14, r8
0x18000469e  mov     rsi, rdx
0x1800046a1  mov     rdi, rcx
0x1800046a4  mov     byte ptr [rdx], 0
0x1800046a7  xor     bpl, bpl
0x1800046aa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800046b1  test    rbx, rbx
0x1800046b4  jz      loc_180004750
0x1800046ba  call    cs:__imp_GetCurrentThreadId
0x1800046c0  mov     r9d, eax
0x1800046c3  mov     r8d, eax
0x1800046c6  shr     r8, 2
0x1800046ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800046d4  mul     r8
0x1800046d7  shr     rdx, 3
0x1800046db  lea     rcx, [rdx+rdx*4]
0x1800046df  add     rcx, rcx
0x1800046e2  sub     r8, rcx
0x1800046e5  mov     rbx, [rbx+r8*8]
0x1800046e9  jmp     short loc_1800046F4
0x1800046eb  cmp     [rbx], r9d
0x1800046ee  jz      short loc_18000476B
0x1800046f0  mov     rbx, [rbx+8]
0x1800046f4  test    rbx, rbx
0x1800046f7  jnz     short loc_1800046EB
0x1800046f9  test    rbx, rbx
0x1800046fc  jz      short loc_180004750
0x1800046fe  cmp     qword ptr [rbx], 0
0x180004702  jz      short loc_180004750
0x180004704  mov     [rsi], bpl
0x180004707  mov     r9, r14; unsigned __int64
0x18000470a  mov     r8, rsi; char *
0x18000470d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004710  mov     rcx, rdi; struct wil::FailureInfo *
0x180004713  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004718  test    al, al
0x18000471a  jz      short loc_180004720
0x18000471c  mov     [rdi+48h], rsi
0x180004720  mov     rbx, [rbx]
0x180004723  mov     al, [rbx+28h]
0x180004726  mov     byte ptr [rbx+28h], 1
0x18000472a  test    al, al
0x18000472c  jnz     short loc_180004747
0x18000472e  mov     rcx, [rbx+8]
0x180004732  mov     rax, [rcx]
0x180004735  mov     rdx, rdi
0x180004738  mov     rax, [rax]
0x18000473b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004740  or      bpl, al
0x180004743  mov     byte ptr [rbx+28h], 0
0x180004747  mov     rbx, [rbx+10h]
0x18000474b  test    rbx, rbx
0x18000474e  jnz     short loc_180004723
0x180004750  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004757  test    rax, rax
0x18000475a  jz      short loc_18000477C
0x18000475c  test    bpl, bpl
0x18000475f  jnz     short loc_180004771
0x180004761  test    byte ptr [rdi+4], 2
0x180004765  jnz     short loc_180004771
0x180004767  xor     ecx, ecx
0x180004769  jmp     short loc_180004773
0x18000476b  add     rbx, 10h
0x18000476f  jmp     short loc_1800046F9
0x180004771  mov     cl, 1
0x180004773  mov     rdx, rdi
0x180004776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000477b  nop
0x18000477c  call    cs:__imp_GetCurrentThreadId
0x180004782  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004788  cmp     ecx, eax
0x18000478a  jz      loc_18000488C
0x180004790  mov     ecx, 1
0x180004795  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000479d  inc     ecx; this
0x18000479f  cmp     ecx, 4
0x1800047a2  jge     loc_180004885
0x1800047a8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800047ae  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800047b3  mov     rbx, rax
0x1800047b6  test    rax, rax
0x1800047b9  jz      loc_18000487B
0x1800047bf  mov     esi, [rax+10h]
0x1800047c2  mov     ebp, 50h ; 'P'
0x1800047c7  cmp     qword ptr [rax+18h], 0
0x1800047cc  jnz     short loc_180004803
0x1800047ce  test    esi, esi
0x1800047d0  jz      short loc_180004803
0x1800047d2  mov     edx, 190h; dwBytes
0x1800047d7  lea     ecx, [rbp-48h]; dwFlags
0x1800047da  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800047df  mov     [rbx+18h], rax
0x1800047e3  test    rax, rax
0x1800047e6  jz      short loc_180004803
0x1800047e8  mov     dword ptr [rbx+20h], 5
0x1800047ef  lea     rcx, [rax+190h]
0x1800047f6  jmp     short loc_1800047FE
0x1800047f8  mov     [rax], bp
0x1800047fb  add     rax, rbp
0x1800047fe  cmp     rax, rcx
0x180004801  jnz     short loc_1800047F8
0x180004803  mov     r9, [rbx+18h]
0x180004807  test    r9, r9
0x18000480a  jz      short loc_18000487B
0x18000480c  test    esi, esi
0x18000480e  jz      short loc_180004841
0x180004810  mov     rcx, r9
0x180004813  movzx   eax, word ptr [rbx+20h]
0x180004817  lea     rdx, [rax+rax*4]
0x18000481b  shl     rdx, 4
0x18000481f  add     rdx, r9
0x180004822  cmp     r9, rdx
0x180004825  jz      short loc_180004841
0x180004827  mov     r8d, [rbx+10h]
0x18000482b  cmp     [rcx+4], r8d
0x18000482f  jbe     short loc_180004839
0x180004831  mov     eax, [rdi+8]
0x180004834  cmp     [rcx+8], eax
0x180004837  jz      short loc_18000487B
0x180004839  add     rcx, rbp
0x18000483c  cmp     rcx, rdx
0x18000483f  jnz     short loc_18000482B
0x180004841  movzx   eax, word ptr [rbx+22h]
0x180004845  inc     eax
0x180004847  movzx   ecx, word ptr [rbx+20h]
0x18000484b  xor     edx, edx
0x18000484d  div     ecx
0x18000484f  mov     [rbx+22h], dx
0x180004853  mov     rax, [rbx+8]
0x180004857  mov     r8d, 1
0x18000485d  lock xadd [rax], r8d
0x180004862  inc     r8d; unsigned int
0x180004865  movzx   eax, dx
0x180004868  lea     rcx, [rax+rax*4]
0x18000486c  shl     rcx, 4
0x180004870  add     rcx, r9; this
0x180004873  mov     rdx, rdi; struct wil::FailureInfo *
0x180004876  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000487b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004885  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000488c  add     rsp, 20h
0x180004890  pop     r14
0x180004892  pop     rdi
0x180004893  pop     rsi
0x180004894  pop     rbp
0x180004895  pop     rbx
0x180004896  retn
```
