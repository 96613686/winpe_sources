# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800035b0`
- end: `0x1800037b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800035b0`
- `0x180003cac`
- `0x180003d90`
- `0x180004608`
- `0x180004970`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000369c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000369c`

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
0x1800035b0  push    rbx
0x1800035b2  push    rbp
0x1800035b3  push    rsi
0x1800035b4  push    rdi
0x1800035b5  push    r14
0x1800035b7  sub     rsp, 20h
0x1800035bb  mov     r14, r8
0x1800035be  mov     rsi, rdx
0x1800035c1  mov     rdi, rcx
0x1800035c4  mov     byte ptr [rdx], 0
0x1800035c7  xor     bpl, bpl
0x1800035ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800035d1  test    rbx, rbx
0x1800035d4  jz      loc_180003670
0x1800035da  call    cs:__imp_GetCurrentThreadId
0x1800035e0  mov     r9d, eax
0x1800035e3  mov     r8d, eax
0x1800035e6  shr     r8, 2
0x1800035ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800035f4  mul     r8
0x1800035f7  shr     rdx, 3
0x1800035fb  lea     rcx, [rdx+rdx*4]
0x1800035ff  add     rcx, rcx
0x180003602  sub     r8, rcx
0x180003605  mov     rbx, [rbx+r8*8]
0x180003609  jmp     short loc_180003614
0x18000360b  cmp     [rbx], r9d
0x18000360e  jz      short loc_18000368B
0x180003610  mov     rbx, [rbx+8]
0x180003614  test    rbx, rbx
0x180003617  jnz     short loc_18000360B
0x180003619  test    rbx, rbx
0x18000361c  jz      short loc_180003670
0x18000361e  cmp     qword ptr [rbx], 0
0x180003622  jz      short loc_180003670
0x180003624  mov     [rsi], bpl
0x180003627  mov     r9, r14; unsigned __int64
0x18000362a  mov     r8, rsi; char *
0x18000362d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003630  mov     rcx, rdi; struct wil::FailureInfo *
0x180003633  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003638  test    al, al
0x18000363a  jz      short loc_180003640
0x18000363c  mov     [rdi+48h], rsi
0x180003640  mov     rbx, [rbx]
0x180003643  mov     al, [rbx+28h]
0x180003646  mov     byte ptr [rbx+28h], 1
0x18000364a  test    al, al
0x18000364c  jnz     short loc_180003667
0x18000364e  mov     rcx, [rbx+8]
0x180003652  mov     rax, [rcx]
0x180003655  mov     rdx, rdi
0x180003658  mov     rax, [rax]
0x18000365b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003660  or      bpl, al
0x180003663  mov     byte ptr [rbx+28h], 0
0x180003667  mov     rbx, [rbx+10h]
0x18000366b  test    rbx, rbx
0x18000366e  jnz     short loc_180003643
0x180003670  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003677  test    rax, rax
0x18000367a  jz      short loc_18000369C
0x18000367c  test    bpl, bpl
0x18000367f  jnz     short loc_180003691
0x180003681  test    byte ptr [rdi+4], 2
0x180003685  jnz     short loc_180003691
0x180003687  xor     ecx, ecx
0x180003689  jmp     short loc_180003693
0x18000368b  add     rbx, 10h
0x18000368f  jmp     short loc_180003619
0x180003691  mov     cl, 1
0x180003693  mov     rdx, rdi
0x180003696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369b  nop
0x18000369c  call    cs:__imp_GetCurrentThreadId
0x1800036a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800036a8  cmp     ecx, eax
0x1800036aa  jz      loc_1800037AC
0x1800036b0  mov     ecx, 1
0x1800036b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800036bd  inc     ecx; this
0x1800036bf  cmp     ecx, 4
0x1800036c2  jge     loc_1800037A5
0x1800036c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800036ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800036d3  mov     rbx, rax
0x1800036d6  test    rax, rax
0x1800036d9  jz      loc_18000379B
0x1800036df  mov     esi, [rax+10h]
0x1800036e2  mov     ebp, 50h ; 'P'
0x1800036e7  cmp     qword ptr [rax+18h], 0
0x1800036ec  jnz     short loc_180003723
0x1800036ee  test    esi, esi
0x1800036f0  jz      short loc_180003723
0x1800036f2  mov     edx, 190h; dwBytes
0x1800036f7  lea     ecx, [rbp-48h]; dwFlags
0x1800036fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800036ff  mov     [rbx+18h], rax
0x180003703  test    rax, rax
0x180003706  jz      short loc_180003723
0x180003708  mov     dword ptr [rbx+20h], 5
0x18000370f  lea     rcx, [rax+190h]
0x180003716  jmp     short loc_18000371E
0x180003718  mov     [rax], bp
0x18000371b  add     rax, rbp
0x18000371e  cmp     rax, rcx
0x180003721  jnz     short loc_180003718
0x180003723  mov     r9, [rbx+18h]
0x180003727  test    r9, r9
0x18000372a  jz      short loc_18000379B
0x18000372c  test    esi, esi
0x18000372e  jz      short loc_180003761
0x180003730  mov     rcx, r9
0x180003733  movzx   eax, word ptr [rbx+20h]
0x180003737  lea     rdx, [rax+rax*4]
0x18000373b  shl     rdx, 4
0x18000373f  add     rdx, r9
0x180003742  cmp     r9, rdx
0x180003745  jz      short loc_180003761
0x180003747  mov     r8d, [rbx+10h]
0x18000374b  cmp     [rcx+4], r8d
0x18000374f  jbe     short loc_180003759
0x180003751  mov     eax, [rdi+8]
0x180003754  cmp     [rcx+8], eax
0x180003757  jz      short loc_18000379B
0x180003759  add     rcx, rbp
0x18000375c  cmp     rcx, rdx
0x18000375f  jnz     short loc_18000374B
0x180003761  movzx   eax, word ptr [rbx+22h]
0x180003765  inc     eax
0x180003767  movzx   ecx, word ptr [rbx+20h]
0x18000376b  xor     edx, edx
0x18000376d  div     ecx
0x18000376f  mov     [rbx+22h], dx
0x180003773  mov     rax, [rbx+8]
0x180003777  mov     r8d, 1
0x18000377d  lock xadd [rax], r8d
0x180003782  inc     r8d; unsigned int
0x180003785  movzx   eax, dx
0x180003788  lea     rcx, [rax+rax*4]
0x18000378c  shl     rcx, 4
0x180003790  add     rcx, r9; this
0x180003793  mov     rdx, rdi; struct wil::FailureInfo *
0x180003796  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000379b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800037a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800037ac  add     rsp, 20h
0x1800037b0  pop     r14
0x1800037b2  pop     rdi
0x1800037b3  pop     rsi
0x1800037b4  pop     rbp
0x1800037b5  pop     rbx
0x1800037b6  retn
```
