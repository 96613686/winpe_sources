# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006860`
- end: `0x180006a67`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006860`
- `0x180006f5c`
- `0x180007040`
- `0x180007d6c`
- `0x180008ff0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000688a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000694c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000688a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000694c`

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
0x180006860  push    rbx
0x180006862  push    rbp
0x180006863  push    rsi
0x180006864  push    rdi
0x180006865  push    r14
0x180006867  sub     rsp, 20h
0x18000686b  mov     r14, r8
0x18000686e  mov     rsi, rdx
0x180006871  mov     rdi, rcx
0x180006874  mov     byte ptr [rdx], 0
0x180006877  xor     bpl, bpl
0x18000687a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006881  test    rbx, rbx
0x180006884  jz      loc_180006920
0x18000688a  call    cs:__imp_GetCurrentThreadId
0x180006890  mov     r9d, eax
0x180006893  mov     r8d, eax
0x180006896  shr     r8, 2
0x18000689a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800068a4  mul     r8
0x1800068a7  shr     rdx, 3
0x1800068ab  lea     rcx, [rdx+rdx*4]
0x1800068af  add     rcx, rcx
0x1800068b2  sub     r8, rcx
0x1800068b5  mov     rbx, [rbx+r8*8]
0x1800068b9  jmp     short loc_1800068C4
0x1800068bb  cmp     [rbx], r9d
0x1800068be  jz      short loc_18000693B
0x1800068c0  mov     rbx, [rbx+8]
0x1800068c4  test    rbx, rbx
0x1800068c7  jnz     short loc_1800068BB
0x1800068c9  test    rbx, rbx
0x1800068cc  jz      short loc_180006920
0x1800068ce  cmp     qword ptr [rbx], 0
0x1800068d2  jz      short loc_180006920
0x1800068d4  mov     [rsi], bpl
0x1800068d7  mov     r9, r14; unsigned __int64
0x1800068da  mov     r8, rsi; char *
0x1800068dd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800068e0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800068e3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800068e8  test    al, al
0x1800068ea  jz      short loc_1800068F0
0x1800068ec  mov     [rdi+48h], rsi
0x1800068f0  mov     rbx, [rbx]
0x1800068f3  mov     al, [rbx+28h]
0x1800068f6  mov     byte ptr [rbx+28h], 1
0x1800068fa  test    al, al
0x1800068fc  jnz     short loc_180006917
0x1800068fe  mov     rcx, [rbx+8]
0x180006902  mov     rax, [rcx]
0x180006905  mov     rdx, rdi
0x180006908  mov     rax, [rax]
0x18000690b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006910  or      bpl, al
0x180006913  mov     byte ptr [rbx+28h], 0
0x180006917  mov     rbx, [rbx+10h]
0x18000691b  test    rbx, rbx
0x18000691e  jnz     short loc_1800068F3
0x180006920  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006927  test    rax, rax
0x18000692a  jz      short loc_18000694C
0x18000692c  test    bpl, bpl
0x18000692f  jnz     short loc_180006941
0x180006931  test    byte ptr [rdi+4], 2
0x180006935  jnz     short loc_180006941
0x180006937  xor     ecx, ecx
0x180006939  jmp     short loc_180006943
0x18000693b  add     rbx, 10h
0x18000693f  jmp     short loc_1800068C9
0x180006941  mov     cl, 1
0x180006943  mov     rdx, rdi
0x180006946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000694b  nop
0x18000694c  call    cs:__imp_GetCurrentThreadId
0x180006952  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006958  cmp     ecx, eax
0x18000695a  jz      loc_180006A5C
0x180006960  mov     ecx, 1
0x180006965  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000696d  inc     ecx; this
0x18000696f  cmp     ecx, 4
0x180006972  jge     loc_180006A55
0x180006978  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000697e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006983  mov     rbx, rax
0x180006986  test    rax, rax
0x180006989  jz      loc_180006A4B
0x18000698f  mov     esi, [rax+10h]
0x180006992  mov     ebp, 50h ; 'P'
0x180006997  cmp     qword ptr [rax+18h], 0
0x18000699c  jnz     short loc_1800069D3
0x18000699e  test    esi, esi
0x1800069a0  jz      short loc_1800069D3
0x1800069a2  mov     edx, 190h; dwBytes
0x1800069a7  lea     ecx, [rbp-48h]; dwFlags
0x1800069aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800069af  mov     [rbx+18h], rax
0x1800069b3  test    rax, rax
0x1800069b6  jz      short loc_1800069D3
0x1800069b8  mov     dword ptr [rbx+20h], 5
0x1800069bf  lea     rcx, [rax+190h]
0x1800069c6  jmp     short loc_1800069CE
0x1800069c8  mov     [rax], bp
0x1800069cb  add     rax, rbp
0x1800069ce  cmp     rax, rcx
0x1800069d1  jnz     short loc_1800069C8
0x1800069d3  mov     r9, [rbx+18h]
0x1800069d7  test    r9, r9
0x1800069da  jz      short loc_180006A4B
0x1800069dc  test    esi, esi
0x1800069de  jz      short loc_180006A11
0x1800069e0  mov     rcx, r9
0x1800069e3  movzx   eax, word ptr [rbx+20h]
0x1800069e7  lea     rdx, [rax+rax*4]
0x1800069eb  shl     rdx, 4
0x1800069ef  add     rdx, r9
0x1800069f2  cmp     r9, rdx
0x1800069f5  jz      short loc_180006A11
0x1800069f7  mov     r8d, [rbx+10h]
0x1800069fb  cmp     [rcx+4], r8d
0x1800069ff  jbe     short loc_180006A09
0x180006a01  mov     eax, [rdi+8]
0x180006a04  cmp     [rcx+8], eax
0x180006a07  jz      short loc_180006A4B
0x180006a09  add     rcx, rbp
0x180006a0c  cmp     rcx, rdx
0x180006a0f  jnz     short loc_1800069FB
0x180006a11  movzx   eax, word ptr [rbx+22h]
0x180006a15  inc     eax
0x180006a17  movzx   ecx, word ptr [rbx+20h]
0x180006a1b  xor     edx, edx
0x180006a1d  div     ecx
0x180006a1f  mov     [rbx+22h], dx
0x180006a23  mov     rax, [rbx+8]
0x180006a27  mov     r8d, 1
0x180006a2d  lock xadd [rax], r8d
0x180006a32  inc     r8d; unsigned int
0x180006a35  movzx   eax, dx
0x180006a38  lea     rcx, [rax+rax*4]
0x180006a3c  shl     rcx, 4
0x180006a40  add     rcx, r9; this
0x180006a43  mov     rdx, rdi; struct wil::FailureInfo *
0x180006a46  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180006a4b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006a55  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006a5c  add     rsp, 20h
0x180006a60  pop     r14
0x180006a62  pop     rdi
0x180006a63  pop     rsi
0x180006a64  pop     rbp
0x180006a65  pop     rbx
0x180006a66  retn
```
