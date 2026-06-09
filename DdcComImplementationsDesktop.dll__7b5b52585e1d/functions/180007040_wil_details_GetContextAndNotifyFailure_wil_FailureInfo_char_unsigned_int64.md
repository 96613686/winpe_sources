# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007040`
- end: `0x180007247`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007040`
- `0x18000773c`
- `0x180007820`
- `0x1800081a8`
- `0x1800095c4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000706a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000712c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000706a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000712c`

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
0x180007040  push    rbx
0x180007042  push    rbp
0x180007043  push    rsi
0x180007044  push    rdi
0x180007045  push    r14
0x180007047  sub     rsp, 20h
0x18000704b  mov     r14, r8
0x18000704e  mov     rsi, rdx
0x180007051  mov     rdi, rcx
0x180007054  mov     byte ptr [rdx], 0
0x180007057  xor     bpl, bpl
0x18000705a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007061  test    rbx, rbx
0x180007064  jz      loc_180007100
0x18000706a  call    cs:__imp_GetCurrentThreadId
0x180007070  mov     r9d, eax
0x180007073  mov     r8d, eax
0x180007076  shr     r8, 2
0x18000707a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007084  mul     r8
0x180007087  shr     rdx, 3
0x18000708b  lea     rcx, [rdx+rdx*4]
0x18000708f  add     rcx, rcx
0x180007092  sub     r8, rcx
0x180007095  mov     rbx, [rbx+r8*8]
0x180007099  jmp     short loc_1800070A4
0x18000709b  cmp     [rbx], r9d
0x18000709e  jz      short loc_18000711B
0x1800070a0  mov     rbx, [rbx+8]
0x1800070a4  test    rbx, rbx
0x1800070a7  jnz     short loc_18000709B
0x1800070a9  test    rbx, rbx
0x1800070ac  jz      short loc_180007100
0x1800070ae  cmp     qword ptr [rbx], 0
0x1800070b2  jz      short loc_180007100
0x1800070b4  mov     [rsi], bpl
0x1800070b7  mov     r9, r14; unsigned __int64
0x1800070ba  mov     r8, rsi; char *
0x1800070bd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800070c0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800070c3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800070c8  test    al, al
0x1800070ca  jz      short loc_1800070D0
0x1800070cc  mov     [rdi+48h], rsi
0x1800070d0  mov     rbx, [rbx]
0x1800070d3  mov     al, [rbx+28h]
0x1800070d6  mov     byte ptr [rbx+28h], 1
0x1800070da  test    al, al
0x1800070dc  jnz     short loc_1800070F7
0x1800070de  mov     rcx, [rbx+8]
0x1800070e2  mov     rax, [rcx]
0x1800070e5  mov     rdx, rdi
0x1800070e8  mov     rax, [rax]
0x1800070eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070f0  or      bpl, al
0x1800070f3  mov     byte ptr [rbx+28h], 0
0x1800070f7  mov     rbx, [rbx+10h]
0x1800070fb  test    rbx, rbx
0x1800070fe  jnz     short loc_1800070D3
0x180007100  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007107  test    rax, rax
0x18000710a  jz      short loc_18000712C
0x18000710c  test    bpl, bpl
0x18000710f  jnz     short loc_180007121
0x180007111  test    byte ptr [rdi+4], 2
0x180007115  jnz     short loc_180007121
0x180007117  xor     ecx, ecx
0x180007119  jmp     short loc_180007123
0x18000711b  add     rbx, 10h
0x18000711f  jmp     short loc_1800070A9
0x180007121  mov     cl, 1
0x180007123  mov     rdx, rdi
0x180007126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000712b  nop
0x18000712c  call    cs:__imp_GetCurrentThreadId
0x180007132  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007138  cmp     ecx, eax
0x18000713a  jz      loc_18000723C
0x180007140  mov     ecx, 1
0x180007145  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000714d  inc     ecx; this
0x18000714f  cmp     ecx, 4
0x180007152  jge     loc_180007235
0x180007158  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000715e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007163  mov     rbx, rax
0x180007166  test    rax, rax
0x180007169  jz      loc_18000722B
0x18000716f  mov     esi, [rax+10h]
0x180007172  mov     ebp, 50h ; 'P'
0x180007177  cmp     qword ptr [rax+18h], 0
0x18000717c  jnz     short loc_1800071B3
0x18000717e  test    esi, esi
0x180007180  jz      short loc_1800071B3
0x180007182  mov     edx, 190h; dwBytes
0x180007187  lea     ecx, [rbp-48h]; dwFlags
0x18000718a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000718f  mov     [rbx+18h], rax
0x180007193  test    rax, rax
0x180007196  jz      short loc_1800071B3
0x180007198  mov     dword ptr [rbx+20h], 5
0x18000719f  lea     rcx, [rax+190h]
0x1800071a6  jmp     short loc_1800071AE
0x1800071a8  mov     [rax], bp
0x1800071ab  add     rax, rbp
0x1800071ae  cmp     rax, rcx
0x1800071b1  jnz     short loc_1800071A8
0x1800071b3  mov     r9, [rbx+18h]
0x1800071b7  test    r9, r9
0x1800071ba  jz      short loc_18000722B
0x1800071bc  test    esi, esi
0x1800071be  jz      short loc_1800071F1
0x1800071c0  mov     rcx, r9
0x1800071c3  movzx   eax, word ptr [rbx+20h]
0x1800071c7  lea     rdx, [rax+rax*4]
0x1800071cb  shl     rdx, 4
0x1800071cf  add     rdx, r9
0x1800071d2  cmp     r9, rdx
0x1800071d5  jz      short loc_1800071F1
0x1800071d7  mov     r8d, [rbx+10h]
0x1800071db  cmp     [rcx+4], r8d
0x1800071df  jbe     short loc_1800071E9
0x1800071e1  mov     eax, [rdi+8]
0x1800071e4  cmp     [rcx+8], eax
0x1800071e7  jz      short loc_18000722B
0x1800071e9  add     rcx, rbp
0x1800071ec  cmp     rcx, rdx
0x1800071ef  jnz     short loc_1800071DB
0x1800071f1  movzx   eax, word ptr [rbx+22h]
0x1800071f5  inc     eax
0x1800071f7  movzx   ecx, word ptr [rbx+20h]
0x1800071fb  xor     edx, edx
0x1800071fd  div     ecx
0x1800071ff  mov     [rbx+22h], dx
0x180007203  mov     rax, [rbx+8]
0x180007207  mov     r8d, 1
0x18000720d  lock xadd [rax], r8d
0x180007212  inc     r8d; unsigned int
0x180007215  movzx   eax, dx
0x180007218  lea     rcx, [rax+rax*4]
0x18000721c  shl     rcx, 4
0x180007220  add     rcx, r9; this
0x180007223  mov     rdx, rdi; struct wil::FailureInfo *
0x180007226  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000722b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007235  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000723c  add     rsp, 20h
0x180007240  pop     r14
0x180007242  pop     rdi
0x180007243  pop     rsi
0x180007244  pop     rbp
0x180007245  pop     rbx
0x180007246  retn
```
