# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800044c0`
- end: `0x1800046c7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800044c0`
- `0x180004bbc`
- `0x180004ca0`
- `0x180005518`
- `0x180005a10`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045ac`

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
0x1800044c0  push    rbx
0x1800044c2  push    rbp
0x1800044c3  push    rsi
0x1800044c4  push    rdi
0x1800044c5  push    r14
0x1800044c7  sub     rsp, 20h
0x1800044cb  mov     r14, r8
0x1800044ce  mov     rsi, rdx
0x1800044d1  mov     rdi, rcx
0x1800044d4  mov     byte ptr [rdx], 0
0x1800044d7  xor     bpl, bpl
0x1800044da  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800044e1  test    rbx, rbx
0x1800044e4  jz      loc_180004580
0x1800044ea  call    cs:__imp_GetCurrentThreadId
0x1800044f0  mov     r9d, eax
0x1800044f3  mov     r8d, eax
0x1800044f6  shr     r8, 2
0x1800044fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004504  mul     r8
0x180004507  shr     rdx, 3
0x18000450b  lea     rcx, [rdx+rdx*4]
0x18000450f  add     rcx, rcx
0x180004512  sub     r8, rcx
0x180004515  mov     rbx, [rbx+r8*8]
0x180004519  jmp     short loc_180004524
0x18000451b  cmp     [rbx], r9d
0x18000451e  jz      short loc_18000459B
0x180004520  mov     rbx, [rbx+8]
0x180004524  test    rbx, rbx
0x180004527  jnz     short loc_18000451B
0x180004529  test    rbx, rbx
0x18000452c  jz      short loc_180004580
0x18000452e  cmp     qword ptr [rbx], 0
0x180004532  jz      short loc_180004580
0x180004534  mov     [rsi], bpl
0x180004537  mov     r9, r14; unsigned __int64
0x18000453a  mov     r8, rsi; char *
0x18000453d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004540  mov     rcx, rdi; struct wil::FailureInfo *
0x180004543  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004548  test    al, al
0x18000454a  jz      short loc_180004550
0x18000454c  mov     [rdi+48h], rsi
0x180004550  mov     rbx, [rbx]
0x180004553  mov     al, [rbx+28h]
0x180004556  mov     byte ptr [rbx+28h], 1
0x18000455a  test    al, al
0x18000455c  jnz     short loc_180004577
0x18000455e  mov     rcx, [rbx+8]
0x180004562  mov     rax, [rcx]
0x180004565  mov     rdx, rdi
0x180004568  mov     rax, [rax]
0x18000456b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004570  or      bpl, al
0x180004573  mov     byte ptr [rbx+28h], 0
0x180004577  mov     rbx, [rbx+10h]
0x18000457b  test    rbx, rbx
0x18000457e  jnz     short loc_180004553
0x180004580  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004587  test    rax, rax
0x18000458a  jz      short loc_1800045AC
0x18000458c  test    bpl, bpl
0x18000458f  jnz     short loc_1800045A1
0x180004591  test    byte ptr [rdi+4], 2
0x180004595  jnz     short loc_1800045A1
0x180004597  xor     ecx, ecx
0x180004599  jmp     short loc_1800045A3
0x18000459b  add     rbx, 10h
0x18000459f  jmp     short loc_180004529
0x1800045a1  mov     cl, 1
0x1800045a3  mov     rdx, rdi
0x1800045a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ab  nop
0x1800045ac  call    cs:__imp_GetCurrentThreadId
0x1800045b2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800045b8  cmp     ecx, eax
0x1800045ba  jz      loc_1800046BC
0x1800045c0  mov     ecx, 1
0x1800045c5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800045cd  inc     ecx; this
0x1800045cf  cmp     ecx, 4
0x1800045d2  jge     loc_1800046B5
0x1800045d8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800045de  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800045e3  mov     rbx, rax
0x1800045e6  test    rax, rax
0x1800045e9  jz      loc_1800046AB
0x1800045ef  mov     esi, [rax+10h]
0x1800045f2  mov     ebp, 50h ; 'P'
0x1800045f7  cmp     qword ptr [rax+18h], 0
0x1800045fc  jnz     short loc_180004633
0x1800045fe  test    esi, esi
0x180004600  jz      short loc_180004633
0x180004602  mov     edx, 190h; dwBytes
0x180004607  lea     ecx, [rbp-48h]; dwFlags
0x18000460a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000460f  mov     [rbx+18h], rax
0x180004613  test    rax, rax
0x180004616  jz      short loc_180004633
0x180004618  mov     dword ptr [rbx+20h], 5
0x18000461f  lea     rcx, [rax+190h]
0x180004626  jmp     short loc_18000462E
0x180004628  mov     [rax], bp
0x18000462b  add     rax, rbp
0x18000462e  cmp     rax, rcx
0x180004631  jnz     short loc_180004628
0x180004633  mov     r9, [rbx+18h]
0x180004637  test    r9, r9
0x18000463a  jz      short loc_1800046AB
0x18000463c  test    esi, esi
0x18000463e  jz      short loc_180004671
0x180004640  mov     rcx, r9
0x180004643  movzx   eax, word ptr [rbx+20h]
0x180004647  lea     rdx, [rax+rax*4]
0x18000464b  shl     rdx, 4
0x18000464f  add     rdx, r9
0x180004652  cmp     r9, rdx
0x180004655  jz      short loc_180004671
0x180004657  mov     r8d, [rbx+10h]
0x18000465b  cmp     [rcx+4], r8d
0x18000465f  jbe     short loc_180004669
0x180004661  mov     eax, [rdi+8]
0x180004664  cmp     [rcx+8], eax
0x180004667  jz      short loc_1800046AB
0x180004669  add     rcx, rbp
0x18000466c  cmp     rcx, rdx
0x18000466f  jnz     short loc_18000465B
0x180004671  movzx   eax, word ptr [rbx+22h]
0x180004675  inc     eax
0x180004677  movzx   ecx, word ptr [rbx+20h]
0x18000467b  xor     edx, edx
0x18000467d  div     ecx
0x18000467f  mov     [rbx+22h], dx
0x180004683  mov     rax, [rbx+8]
0x180004687  mov     r8d, 1
0x18000468d  lock xadd [rax], r8d
0x180004692  inc     r8d; unsigned int
0x180004695  movzx   eax, dx
0x180004698  lea     rcx, [rax+rax*4]
0x18000469c  shl     rcx, 4
0x1800046a0  add     rcx, r9; this
0x1800046a3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800046a6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800046ab  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800046b5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800046bc  add     rsp, 20h
0x1800046c0  pop     r14
0x1800046c2  pop     rdi
0x1800046c3  pop     rsi
0x1800046c4  pop     rbp
0x1800046c5  pop     rbx
0x1800046c6  retn
```
