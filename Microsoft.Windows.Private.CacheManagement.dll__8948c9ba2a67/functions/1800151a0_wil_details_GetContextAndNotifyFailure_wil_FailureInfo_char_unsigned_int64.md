# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800151a0`
- end: `0x1800153b0`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(wil::details *this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180012e70`
- `0x180014bf0`
- `0x180014f70`
- `0x180015040`
- `0x1800151a0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800151d2`
- `KERNEL32!GetCurrentThreadId` at `0x18001528c`
- `KERNEL32!GetCurrentThreadId` at `0x1800151d2`
- `KERNEL32!GetCurrentThreadId` at `0x18001528c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // si
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  DWORD v11; // eax
  bool v12; // dl
  wil::details_abi *v13; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v15; // r8
  struct wil::details_abi::ThreadLocalData *v16; // rbx
  int v17; // esi
  _WORD *v18; // rax
  _WORD *v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned __int16 v23; // dx

  v5 = this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = *(wil::details **)(v7 + 8 * (CurrentThreadId % 0xA));
    if ( this )
    {
      while ( *(_DWORD *)this != (_DWORD)CurrentThreadId )
      {
        this = (wil::details *)*((_QWORD *)this + 1);
        if ( !this )
          goto LABEL_5;
      }
      v9 = (struct wil::details::ThreadFailureCallbackHolder **)((char *)this + 16);
    }
    else
    {
LABEL_5:
      v9 = 0;
    }
    if ( v9 && *v9 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v9, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v10 = *v9;
      do
      {
        v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
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
  v11 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v11 )
  {
    v13 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v13 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v11;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v13, v12);
      v16 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v17 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v17 )
          {
            v18 = wil::details::ProcessHeapAlloc(8u, 0x190u, v15);
            *((_QWORD *)v16 + 3) = v18;
            if ( v18 )
            {
              *((_DWORD *)v16 + 8) = 5;
              v19 = v18 + 200;
              do
              {
                *v18 = 80;
                v18 += 40;
              }
              while ( v18 != v19 );
            }
          }
        }
        v20 = *((_QWORD *)v16 + 3);
        if ( v20 )
        {
          if ( !v17 || (v21 = *((_QWORD *)v16 + 3), v22 = v20 + 80LL * *((unsigned __int16 *)v16 + 16), v20 == v22) )
          {
LABEL_33:
            v23 = ((unsigned int)*((unsigned __int16 *)v16 + 17) + 1) % *((unsigned __int16 *)v16 + 16);
            *((_WORD *)v16 + 17) = v23;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v20 + 80LL * v23),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v16 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v21 + 4) <= *((_DWORD *)v16 + 4) || *(_DWORD *)(v21 + 8) != *((_DWORD *)v5 + 2) )
            {
              v21 += 80;
              if ( v21 == v22 )
                goto LABEL_33;
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
0x1800151a0  mov     [rsp+arg_18], rbx
0x1800151a5  push    rbp
0x1800151a6  push    rsi
0x1800151a7  push    rdi
0x1800151a8  push    r14
0x1800151aa  push    r15
0x1800151ac  sub     rsp, 20h
0x1800151b0  mov     rbp, r8
0x1800151b3  mov     r14, rdx
0x1800151b6  mov     rdi, rcx
0x1800151b9  mov     byte ptr [rdx], 0
0x1800151bc  xor     sil, sil
0x1800151bf  xor     r15d, r15d
0x1800151c2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800151c9  test    rbx, rbx
0x1800151cc  jz      loc_18001525F
0x1800151d2  call    cs:__imp_GetCurrentThreadId
0x1800151d8  mov     r9d, eax
0x1800151db  mov     r8d, eax
0x1800151de  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800151e8  mul     r9
0x1800151eb  shr     rdx, 3
0x1800151ef  lea     rcx, [rdx+rdx*4]
0x1800151f3  add     rcx, rcx
0x1800151f6  sub     r8, rcx
0x1800151f9  mov     rcx, [rbx+r8*8]
0x1800151fd  test    rcx, rcx
0x180015200  jz      short loc_180015210
0x180015202  cmp     [rcx], r9d
0x180015205  jz      short loc_18001527A
0x180015207  mov     rcx, [rcx+8]
0x18001520b  test    rcx, rcx
0x18001520e  jnz     short loc_180015202
0x180015210  mov     rbx, r15
0x180015213  test    rbx, rbx
0x180015216  jz      short loc_18001525F
0x180015218  cmp     [rbx], r15
0x18001521b  jz      short loc_18001525F
0x18001521d  mov     [r14], sil
0x180015220  mov     r9, rbp; unsigned __int64
0x180015223  mov     r8, r14; char *
0x180015226  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180015229  mov     rcx, rdi; struct wil::FailureInfo *
0x18001522c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180015231  test    al, al
0x180015233  jz      short loc_180015239
0x180015235  mov     [rdi+48h], r14
0x180015239  mov     rbx, [rbx]
0x18001523c  nop     dword ptr [rax+00h]
0x180015240  mov     rcx, [rbx+8]
0x180015244  mov     rax, [rcx]
0x180015247  mov     rdx, rdi
0x18001524a  mov     rax, [rax]
0x18001524d  call    cs:__guard_dispatch_icall_fptr
0x180015253  or      sil, al
0x180015256  mov     rbx, [rbx+10h]
0x18001525a  test    rbx, rbx
0x18001525d  jnz     short loc_180015240
0x18001525f  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180015266  test    rax, rax
0x180015269  jz      short loc_18001528C
0x18001526b  test    sil, sil
0x18001526e  jnz     short loc_180015280
0x180015270  test    byte ptr [rdi+4], 2
0x180015274  jnz     short loc_180015280
0x180015276  xor     ecx, ecx
0x180015278  jmp     short loc_180015282
0x18001527a  lea     rbx, [rcx+10h]
0x18001527e  jmp     short loc_180015213
0x180015280  mov     cl, 1
0x180015282  mov     rdx, rdi
0x180015285  call    cs:__guard_dispatch_icall_fptr
0x18001528b  nop
0x18001528c  call    cs:__imp_GetCurrentThreadId
0x180015292  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180015298  cmp     ecx, eax
0x18001529a  jz      loc_18001539F
0x1800152a0  mov     ebp, 1
0x1800152a5  mov     ecx, ebp
0x1800152a7  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800152af  inc     ecx; this
0x1800152b1  cmp     ecx, 4
0x1800152b4  jge     loc_180015398
0x1800152ba  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800152c0  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800152c5  mov     rbx, rax
0x1800152c8  test    rax, rax
0x1800152cb  jz      loc_180015391
0x1800152d1  mov     esi, [rax+10h]
0x1800152d4  cmp     qword ptr [rax+18h], 0
0x1800152d9  jnz     short loc_18001531E
0x1800152db  test    esi, esi
0x1800152dd  jz      short loc_18001531E
0x1800152df  mov     edx, 190h; dwBytes
0x1800152e4  mov     ecx, 8; dwFlags
0x1800152e9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800152ee  mov     [rbx+18h], rax
0x1800152f2  test    rax, rax
0x1800152f5  jz      short loc_18001531E
0x1800152f7  mov     dword ptr [rbx+20h], 5
0x1800152fe  lea     rcx, [rax+190h]
0x180015305  cmp     rax, rcx
0x180015308  jz      short loc_18001531E
0x18001530a  nop     word ptr [rax+rax+00h]
0x180015310  mov     word ptr [rax], 50h ; 'P'
0x180015315  add     rax, 50h ; 'P'
0x180015319  cmp     rax, rcx
0x18001531c  jnz     short loc_180015310
0x18001531e  mov     r9, [rbx+18h]
0x180015322  test    r9, r9
0x180015325  jz      short loc_180015391
0x180015327  test    esi, esi
0x180015329  jz      short loc_18001535D
0x18001532b  mov     rcx, r9
0x18001532e  movzx   eax, word ptr [rbx+20h]
0x180015332  lea     rdx, [rax+rax*4]
0x180015336  shl     rdx, 4
0x18001533a  add     rdx, r9
0x18001533d  cmp     r9, rdx
0x180015340  jz      short loc_18001535D
0x180015342  mov     r8d, [rbx+10h]
0x180015346  cmp     [rcx+4], r8d
0x18001534a  jbe     short loc_180015354
0x18001534c  mov     eax, [rdi+8]
0x18001534f  cmp     [rcx+8], eax
0x180015352  jz      short loc_180015391
0x180015354  add     rcx, 50h ; 'P'
0x180015358  cmp     rcx, rdx
0x18001535b  jnz     short loc_180015346
0x18001535d  movzx   ecx, word ptr [rbx+20h]
0x180015361  movzx   eax, word ptr [rbx+22h]
0x180015365  inc     eax
0x180015367  xor     edx, edx
0x180015369  div     ecx
0x18001536b  mov     [rbx+22h], dx
0x18001536f  mov     rax, [rbx+8]
0x180015373  lock xadd [rax], ebp
0x180015377  lea     r8d, [rbp+1]; unsigned int
0x18001537b  movzx   eax, dx
0x18001537e  lea     rcx, [rax+rax*4]
0x180015382  shl     rcx, 4
0x180015386  add     rcx, r9; this
0x180015389  mov     rdx, rdi; struct wil::FailureInfo *
0x18001538c  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180015391  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180015398  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001539f  mov     rbx, [rsp+48h+arg_18]
0x1800153a4  add     rsp, 20h
0x1800153a8  pop     r15
0x1800153aa  pop     r14
0x1800153ac  pop     rdi
0x1800153ad  pop     rsi
0x1800153ae  pop     rbp
0x1800153af  retn
```
