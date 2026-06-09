# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800035f0`
- end: `0x1800037f7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800035f0`
- `0x180003cec`
- `0x180003dd0`
- `0x180004648`
- `0x1800049b0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000361a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000361a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036dc`

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
0x1800035f0  push    rbx
0x1800035f2  push    rbp
0x1800035f3  push    rsi
0x1800035f4  push    rdi
0x1800035f5  push    r14
0x1800035f7  sub     rsp, 20h
0x1800035fb  mov     r14, r8
0x1800035fe  mov     rsi, rdx
0x180003601  mov     rdi, rcx
0x180003604  mov     byte ptr [rdx], 0
0x180003607  xor     bpl, bpl
0x18000360a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003611  test    rbx, rbx
0x180003614  jz      loc_1800036B0
0x18000361a  call    cs:__imp_GetCurrentThreadId
0x180003620  mov     r9d, eax
0x180003623  mov     r8d, eax
0x180003626  shr     r8, 2
0x18000362a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003634  mul     r8
0x180003637  shr     rdx, 3
0x18000363b  lea     rcx, [rdx+rdx*4]
0x18000363f  add     rcx, rcx
0x180003642  sub     r8, rcx
0x180003645  mov     rbx, [rbx+r8*8]
0x180003649  jmp     short loc_180003654
0x18000364b  cmp     [rbx], r9d
0x18000364e  jz      short loc_1800036CB
0x180003650  mov     rbx, [rbx+8]
0x180003654  test    rbx, rbx
0x180003657  jnz     short loc_18000364B
0x180003659  test    rbx, rbx
0x18000365c  jz      short loc_1800036B0
0x18000365e  cmp     qword ptr [rbx], 0
0x180003662  jz      short loc_1800036B0
0x180003664  mov     [rsi], bpl
0x180003667  mov     r9, r14; unsigned __int64
0x18000366a  mov     r8, rsi; char *
0x18000366d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003670  mov     rcx, rdi; struct wil::FailureInfo *
0x180003673  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003678  test    al, al
0x18000367a  jz      short loc_180003680
0x18000367c  mov     [rdi+48h], rsi
0x180003680  mov     rbx, [rbx]
0x180003683  mov     al, [rbx+28h]
0x180003686  mov     byte ptr [rbx+28h], 1
0x18000368a  test    al, al
0x18000368c  jnz     short loc_1800036A7
0x18000368e  mov     rcx, [rbx+8]
0x180003692  mov     rax, [rcx]
0x180003695  mov     rdx, rdi
0x180003698  mov     rax, [rax]
0x18000369b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036a0  or      bpl, al
0x1800036a3  mov     byte ptr [rbx+28h], 0
0x1800036a7  mov     rbx, [rbx+10h]
0x1800036ab  test    rbx, rbx
0x1800036ae  jnz     short loc_180003683
0x1800036b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800036b7  test    rax, rax
0x1800036ba  jz      short loc_1800036DC
0x1800036bc  test    bpl, bpl
0x1800036bf  jnz     short loc_1800036D1
0x1800036c1  test    byte ptr [rdi+4], 2
0x1800036c5  jnz     short loc_1800036D1
0x1800036c7  xor     ecx, ecx
0x1800036c9  jmp     short loc_1800036D3
0x1800036cb  add     rbx, 10h
0x1800036cf  jmp     short loc_180003659
0x1800036d1  mov     cl, 1
0x1800036d3  mov     rdx, rdi
0x1800036d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036db  nop
0x1800036dc  call    cs:__imp_GetCurrentThreadId
0x1800036e2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800036e8  cmp     ecx, eax
0x1800036ea  jz      loc_1800037EC
0x1800036f0  mov     ecx, 1
0x1800036f5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800036fd  inc     ecx; this
0x1800036ff  cmp     ecx, 4
0x180003702  jge     loc_1800037E5
0x180003708  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000370e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003713  mov     rbx, rax
0x180003716  test    rax, rax
0x180003719  jz      loc_1800037DB
0x18000371f  mov     esi, [rax+10h]
0x180003722  mov     ebp, 50h ; 'P'
0x180003727  cmp     qword ptr [rax+18h], 0
0x18000372c  jnz     short loc_180003763
0x18000372e  test    esi, esi
0x180003730  jz      short loc_180003763
0x180003732  mov     edx, 190h; dwBytes
0x180003737  lea     ecx, [rbp-48h]; dwFlags
0x18000373a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000373f  mov     [rbx+18h], rax
0x180003743  test    rax, rax
0x180003746  jz      short loc_180003763
0x180003748  mov     dword ptr [rbx+20h], 5
0x18000374f  lea     rcx, [rax+190h]
0x180003756  jmp     short loc_18000375E
0x180003758  mov     [rax], bp
0x18000375b  add     rax, rbp
0x18000375e  cmp     rax, rcx
0x180003761  jnz     short loc_180003758
0x180003763  mov     r9, [rbx+18h]
0x180003767  test    r9, r9
0x18000376a  jz      short loc_1800037DB
0x18000376c  test    esi, esi
0x18000376e  jz      short loc_1800037A1
0x180003770  mov     rcx, r9
0x180003773  movzx   eax, word ptr [rbx+20h]
0x180003777  lea     rdx, [rax+rax*4]
0x18000377b  shl     rdx, 4
0x18000377f  add     rdx, r9
0x180003782  cmp     r9, rdx
0x180003785  jz      short loc_1800037A1
0x180003787  mov     r8d, [rbx+10h]
0x18000378b  cmp     [rcx+4], r8d
0x18000378f  jbe     short loc_180003799
0x180003791  mov     eax, [rdi+8]
0x180003794  cmp     [rcx+8], eax
0x180003797  jz      short loc_1800037DB
0x180003799  add     rcx, rbp
0x18000379c  cmp     rcx, rdx
0x18000379f  jnz     short loc_18000378B
0x1800037a1  movzx   eax, word ptr [rbx+22h]
0x1800037a5  inc     eax
0x1800037a7  movzx   ecx, word ptr [rbx+20h]
0x1800037ab  xor     edx, edx
0x1800037ad  div     ecx
0x1800037af  mov     [rbx+22h], dx
0x1800037b3  mov     rax, [rbx+8]
0x1800037b7  mov     r8d, 1
0x1800037bd  lock xadd [rax], r8d
0x1800037c2  inc     r8d; unsigned int
0x1800037c5  movzx   eax, dx
0x1800037c8  lea     rcx, [rax+rax*4]
0x1800037cc  shl     rcx, 4
0x1800037d0  add     rcx, r9; this
0x1800037d3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800037d6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800037db  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800037e5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800037ec  add     rsp, 20h
0x1800037f0  pop     r14
0x1800037f2  pop     rdi
0x1800037f3  pop     rsi
0x1800037f4  pop     rbp
0x1800037f5  pop     rbx
0x1800037f6  retn
```
