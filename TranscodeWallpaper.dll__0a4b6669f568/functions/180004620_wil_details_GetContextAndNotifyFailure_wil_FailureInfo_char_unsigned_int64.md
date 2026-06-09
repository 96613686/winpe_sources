# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004620`
- end: `0x180004827`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004620`
- `0x180004d1c`
- `0x180004e00`
- `0x180005678`
- `0x180005bc4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000464a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000470c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000464a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000470c`

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
0x180004620  push    rbx
0x180004622  push    rbp
0x180004623  push    rsi
0x180004624  push    rdi
0x180004625  push    r14
0x180004627  sub     rsp, 20h
0x18000462b  mov     r14, r8
0x18000462e  mov     rsi, rdx
0x180004631  mov     rdi, rcx
0x180004634  mov     byte ptr [rdx], 0
0x180004637  xor     bpl, bpl
0x18000463a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004641  test    rbx, rbx
0x180004644  jz      loc_1800046E0
0x18000464a  call    cs:__imp_GetCurrentThreadId
0x180004650  mov     r9d, eax
0x180004653  mov     r8d, eax
0x180004656  shr     r8, 2
0x18000465a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004664  mul     r8
0x180004667  shr     rdx, 3
0x18000466b  lea     rcx, [rdx+rdx*4]
0x18000466f  add     rcx, rcx
0x180004672  sub     r8, rcx
0x180004675  mov     rbx, [rbx+r8*8]
0x180004679  jmp     short loc_180004684
0x18000467b  cmp     [rbx], r9d
0x18000467e  jz      short loc_1800046FB
0x180004680  mov     rbx, [rbx+8]
0x180004684  test    rbx, rbx
0x180004687  jnz     short loc_18000467B
0x180004689  test    rbx, rbx
0x18000468c  jz      short loc_1800046E0
0x18000468e  cmp     qword ptr [rbx], 0
0x180004692  jz      short loc_1800046E0
0x180004694  mov     [rsi], bpl
0x180004697  mov     r9, r14; unsigned __int64
0x18000469a  mov     r8, rsi; char *
0x18000469d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800046a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800046a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800046a8  test    al, al
0x1800046aa  jz      short loc_1800046B0
0x1800046ac  mov     [rdi+48h], rsi
0x1800046b0  mov     rbx, [rbx]
0x1800046b3  mov     al, [rbx+28h]
0x1800046b6  mov     byte ptr [rbx+28h], 1
0x1800046ba  test    al, al
0x1800046bc  jnz     short loc_1800046D7
0x1800046be  mov     rcx, [rbx+8]
0x1800046c2  mov     rax, [rcx]
0x1800046c5  mov     rdx, rdi
0x1800046c8  mov     rax, [rax]
0x1800046cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d0  or      bpl, al
0x1800046d3  mov     byte ptr [rbx+28h], 0
0x1800046d7  mov     rbx, [rbx+10h]
0x1800046db  test    rbx, rbx
0x1800046de  jnz     short loc_1800046B3
0x1800046e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800046e7  test    rax, rax
0x1800046ea  jz      short loc_18000470C
0x1800046ec  test    bpl, bpl
0x1800046ef  jnz     short loc_180004701
0x1800046f1  test    byte ptr [rdi+4], 2
0x1800046f5  jnz     short loc_180004701
0x1800046f7  xor     ecx, ecx
0x1800046f9  jmp     short loc_180004703
0x1800046fb  add     rbx, 10h
0x1800046ff  jmp     short loc_180004689
0x180004701  mov     cl, 1
0x180004703  mov     rdx, rdi
0x180004706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000470b  nop
0x18000470c  call    cs:__imp_GetCurrentThreadId
0x180004712  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004718  cmp     ecx, eax
0x18000471a  jz      loc_18000481C
0x180004720  mov     ecx, 1
0x180004725  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000472d  inc     ecx; this
0x18000472f  cmp     ecx, 4
0x180004732  jge     loc_180004815
0x180004738  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000473e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004743  mov     rbx, rax
0x180004746  test    rax, rax
0x180004749  jz      loc_18000480B
0x18000474f  mov     esi, [rax+10h]
0x180004752  mov     ebp, 50h ; 'P'
0x180004757  cmp     qword ptr [rax+18h], 0
0x18000475c  jnz     short loc_180004793
0x18000475e  test    esi, esi
0x180004760  jz      short loc_180004793
0x180004762  mov     edx, 190h; dwBytes
0x180004767  lea     ecx, [rbp-48h]; dwFlags
0x18000476a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000476f  mov     [rbx+18h], rax
0x180004773  test    rax, rax
0x180004776  jz      short loc_180004793
0x180004778  mov     dword ptr [rbx+20h], 5
0x18000477f  lea     rcx, [rax+190h]
0x180004786  jmp     short loc_18000478E
0x180004788  mov     [rax], bp
0x18000478b  add     rax, rbp
0x18000478e  cmp     rax, rcx
0x180004791  jnz     short loc_180004788
0x180004793  mov     r9, [rbx+18h]
0x180004797  test    r9, r9
0x18000479a  jz      short loc_18000480B
0x18000479c  test    esi, esi
0x18000479e  jz      short loc_1800047D1
0x1800047a0  mov     rcx, r9
0x1800047a3  movzx   eax, word ptr [rbx+20h]
0x1800047a7  lea     rdx, [rax+rax*4]
0x1800047ab  shl     rdx, 4
0x1800047af  add     rdx, r9
0x1800047b2  cmp     r9, rdx
0x1800047b5  jz      short loc_1800047D1
0x1800047b7  mov     r8d, [rbx+10h]
0x1800047bb  cmp     [rcx+4], r8d
0x1800047bf  jbe     short loc_1800047C9
0x1800047c1  mov     eax, [rdi+8]
0x1800047c4  cmp     [rcx+8], eax
0x1800047c7  jz      short loc_18000480B
0x1800047c9  add     rcx, rbp
0x1800047cc  cmp     rcx, rdx
0x1800047cf  jnz     short loc_1800047BB
0x1800047d1  movzx   eax, word ptr [rbx+22h]
0x1800047d5  inc     eax
0x1800047d7  movzx   ecx, word ptr [rbx+20h]
0x1800047db  xor     edx, edx
0x1800047dd  div     ecx
0x1800047df  mov     [rbx+22h], dx
0x1800047e3  mov     rax, [rbx+8]
0x1800047e7  mov     r8d, 1
0x1800047ed  lock xadd [rax], r8d
0x1800047f2  inc     r8d; unsigned int
0x1800047f5  movzx   eax, dx
0x1800047f8  lea     rcx, [rax+rax*4]
0x1800047fc  shl     rcx, 4
0x180004800  add     rcx, r9; this
0x180004803  mov     rdx, rdi; struct wil::FailureInfo *
0x180004806  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000480b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004815  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000481c  add     rsp, 20h
0x180004820  pop     r14
0x180004822  pop     rdi
0x180004823  pop     rsi
0x180004824  pop     rbp
0x180004825  pop     rbx
0x180004826  retn
```
