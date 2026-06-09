# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800254e0`
- end: `0x1800256f3`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `531`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800254e0`
- `0x180025cfc`
- `0x180025de0`
- `0x180026880`
- `0x180027de8`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002550a`
- `KERNEL32!GetCurrentThreadId` at `0x1800255d1`
- `KERNEL32!GetCurrentThreadId` at `0x18002550a`
- `KERNEL32!GetCurrentThreadId` at `0x1800255d1`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  unsigned __int64 v7; // rdi
  DWORD CurrentThreadId; // r9d
  unsigned __int64 v9; // r8
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder **v11; // rbx
  char v12; // al
  DWORD v13; // eax
  wil::details_abi *v14; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  struct wil::details_abi::ThreadLocalData *v16; // rbx
  int v17; // esi
  _WORD *v18; // rax
  _WORD *v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned __int16 v23; // dx
  volatile signed __int32 *v24; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = (unsigned __int64)CurrentThreadId >> 2;
    this = 10 * (v9 / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * (v9 % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             (struct wil::FailureInfo *)v7,
             *(struct wil::details::ThreadFailureCallbackHolder ***)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *(_QWORD *)(v7 + 72) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder ***)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v3 |= (**(__int64 (__fastcall ***)(struct wil::details::ThreadFailureCallbackHolder *, unsigned __int64))v11[1])(
                  v11[1],
                  v7);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder **)v11[2];
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*(_BYTE *)(v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
  }
  v13 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v13 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v13;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14);
      v16 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v17 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v17 )
          {
            v18 = wil::details::ProcessHeapAlloc(8u, 0x190u);
            *((_QWORD *)v16 + 3) = v18;
            if ( v18 )
            {
              *((_DWORD *)v16 + 8) = 5;
              v19 = v18 + 200;
              while ( v18 != v19 )
              {
                *v18 = 80;
                v18 += 40;
              }
            }
          }
        }
        v20 = *((_QWORD *)v16 + 3);
        if ( v20 )
        {
          if ( !v17 || (v21 = *((_QWORD *)v16 + 3), v22 = v20 + 80LL * *((unsigned __int16 *)v16 + 16), v20 == v22) )
          {
LABEL_36:
            v23 = ((unsigned int)*((unsigned __int16 *)v16 + 17) + 1) % *((unsigned __int16 *)v16 + 16);
            v24 = (volatile signed __int32 *)*((_QWORD *)v16 + 1);
            *((_WORD *)v16 + 17) = v23;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v20 + 80LL * v23),
              (const struct wil::FailureInfo *)v7,
              _InterlockedIncrement(v24));
          }
          else
          {
            while ( *(_DWORD *)(v21 + 4) <= *((_DWORD *)v16 + 4) || *(_DWORD *)(v21 + 8) != *(_DWORD *)(v7 + 8) )
            {
              v21 += 80;
              if ( v21 == v22 )
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
0x1800254e0  push    rbx
0x1800254e2  push    rbp
0x1800254e3  push    rsi
0x1800254e4  push    rdi
0x1800254e5  push    r14
0x1800254e7  sub     rsp, 20h
0x1800254eb  mov     byte ptr [rdx], 0
0x1800254ee  xor     bpl, bpl
0x1800254f1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800254f8  mov     r14, r8
0x1800254fb  mov     rsi, rdx
0x1800254fe  mov     rdi, rcx
0x180025501  test    rbx, rbx
0x180025504  jz      loc_1800255A6
0x18002550a  call    cs:__imp_GetCurrentThreadId
0x180025511  nop     dword ptr [rax+rax+00h]
0x180025516  mov     r8d, eax
0x180025519  mov     r9d, eax
0x18002551c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180025526  shr     r8, 2
0x18002552a  mul     r8
0x18002552d  shr     rdx, 3
0x180025531  lea     rcx, [rdx+rdx*4]
0x180025535  add     rcx, rcx
0x180025538  sub     r8, rcx
0x18002553b  mov     rbx, [rbx+r8*8]
0x18002553f  jmp     short loc_18002554A
0x180025541  cmp     [rbx], r9d
0x180025544  jz      short loc_1800255C1
0x180025546  mov     rbx, [rbx+8]
0x18002554a  test    rbx, rbx
0x18002554d  jnz     short loc_180025541
0x18002554f  test    rbx, rbx
0x180025552  jz      short loc_1800255A6
0x180025554  cmp     qword ptr [rbx], 0
0x180025558  jz      short loc_1800255A6
0x18002555a  mov     [rsi], bpl
0x18002555d  mov     r9, r14; unsigned __int64
0x180025560  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180025563  mov     r8, rsi; char *
0x180025566  mov     rcx, rdi; struct wil::FailureInfo *
0x180025569  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002556e  test    al, al
0x180025570  jz      short loc_180025576
0x180025572  mov     [rdi+48h], rsi
0x180025576  mov     rbx, [rbx]
0x180025579  mov     al, [rbx+28h]
0x18002557c  mov     byte ptr [rbx+28h], 1
0x180025580  test    al, al
0x180025582  jnz     short loc_18002559D
0x180025584  mov     rcx, [rbx+8]
0x180025588  mov     rdx, rdi
0x18002558b  mov     rax, [rcx]
0x18002558e  mov     rax, [rax]
0x180025591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025596  or      bpl, al
0x180025599  mov     byte ptr [rbx+28h], 0
0x18002559d  mov     rbx, [rbx+10h]
0x1800255a1  test    rbx, rbx
0x1800255a4  jnz     short loc_180025579
0x1800255a6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800255ad  test    rax, rax
0x1800255b0  jz      short loc_1800255D1
0x1800255b2  test    bpl, bpl
0x1800255b5  jnz     short loc_1800255C7
0x1800255b7  test    byte ptr [rdi+4], 2
0x1800255bb  jnz     short loc_1800255C7
0x1800255bd  xor     ecx, ecx
0x1800255bf  jmp     short loc_1800255C9
0x1800255c1  add     rbx, 10h
0x1800255c5  jmp     short loc_18002554F
0x1800255c7  mov     cl, 1
0x1800255c9  mov     rdx, rdi
0x1800255cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255d1  call    cs:__imp_GetCurrentThreadId
0x1800255d8  nop     dword ptr [rax+rax+00h]
0x1800255dd  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800255e3  cmp     ecx, eax
0x1800255e5  jz      loc_1800256E7
0x1800255eb  mov     ecx, 1
0x1800255f0  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800255f8  inc     ecx; this
0x1800255fa  cmp     ecx, 4
0x1800255fd  jge     loc_1800256E0
0x180025603  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180025609  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18002560e  mov     rbx, rax
0x180025611  test    rax, rax
0x180025614  jz      loc_1800256D6
0x18002561a  cmp     qword ptr [rax+18h], 0
0x18002561f  mov     ebp, 50h ; 'P'
0x180025624  mov     esi, [rax+10h]
0x180025627  jnz     short loc_18002565E
0x180025629  test    esi, esi
0x18002562b  jz      short loc_18002565E
0x18002562d  mov     edx, 190h; dwBytes
0x180025632  lea     ecx, [rbp-48h]; dwFlags
0x180025635  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002563a  mov     [rbx+18h], rax
0x18002563e  test    rax, rax
0x180025641  jz      short loc_18002565E
0x180025643  mov     dword ptr [rbx+20h], 5
0x18002564a  lea     rcx, [rax+190h]
0x180025651  jmp     short loc_180025659
0x180025653  mov     [rax], bp
0x180025656  add     rax, rbp
0x180025659  cmp     rax, rcx
0x18002565c  jnz     short loc_180025653
0x18002565e  mov     r9, [rbx+18h]
0x180025662  test    r9, r9
0x180025665  jz      short loc_1800256D6
0x180025667  test    esi, esi
0x180025669  jz      short loc_18002569C
0x18002566b  movzx   eax, word ptr [rbx+20h]
0x18002566f  mov     rcx, r9
0x180025672  lea     rdx, [rax+rax*4]
0x180025676  shl     rdx, 4
0x18002567a  add     rdx, r9
0x18002567d  cmp     r9, rdx
0x180025680  jz      short loc_18002569C
0x180025682  mov     r8d, [rbx+10h]
0x180025686  cmp     [rcx+4], r8d
0x18002568a  jbe     short loc_180025694
0x18002568c  mov     eax, [rdi+8]
0x18002568f  cmp     [rcx+8], eax
0x180025692  jz      short loc_1800256D6
0x180025694  add     rcx, rbp
0x180025697  cmp     rcx, rdx
0x18002569a  jnz     short loc_180025686
0x18002569c  movzx   eax, word ptr [rbx+22h]
0x1800256a0  xor     edx, edx
0x1800256a2  movzx   ecx, word ptr [rbx+20h]
0x1800256a6  inc     eax
0x1800256a8  div     ecx
0x1800256aa  mov     rax, [rbx+8]
0x1800256ae  mov     r8d, 1
0x1800256b4  mov     [rbx+22h], dx
0x1800256b8  lock xadd [rax], r8d
0x1800256bd  movzx   eax, dx
0x1800256c0  inc     r8d; unsigned int
0x1800256c3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800256c6  lea     rcx, [rax+rax*4]
0x1800256ca  shl     rcx, 4
0x1800256ce  add     rcx, r9; this
0x1800256d1  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800256d6  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800256e0  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800256e7  add     rsp, 20h
0x1800256eb  pop     r14
0x1800256ed  pop     rdi
0x1800256ee  pop     rsi
0x1800256ef  pop     rbp
0x1800256f0  pop     rbx
0x1800256f1  retn
```
