# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800041a0`
- end: `0x1800043b3`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `531`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004754`
- `0x180004840`
- `0x1800054f8`
- `0x180006894`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800041ca`
- `KERNEL32!GetCurrentThreadId` at `0x180004291`
- `KERNEL32!GetCurrentThreadId` at `0x1800041ca`
- `KERNEL32!GetCurrentThreadId` at `0x180004291`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
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
  volatile signed __int32 *v25; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
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
            v25 = (volatile signed __int32 *)*((_QWORD *)v17 + 1);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v7,
              _InterlockedIncrement(v25));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v7 + 2) )
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
0x1800041a0  push    rbx
0x1800041a2  push    rbp
0x1800041a3  push    rsi
0x1800041a4  push    rdi
0x1800041a5  push    r14
0x1800041a7  sub     rsp, 20h
0x1800041ab  mov     byte ptr [rdx], 0
0x1800041ae  xor     bpl, bpl
0x1800041b1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800041b8  mov     r14, r8
0x1800041bb  mov     rsi, rdx
0x1800041be  mov     rdi, rcx
0x1800041c1  test    rbx, rbx
0x1800041c4  jz      loc_180004266
0x1800041ca  call    cs:__imp_GetCurrentThreadId
0x1800041d1  nop     dword ptr [rax+rax+00h]
0x1800041d6  mov     r8d, eax
0x1800041d9  mov     r9d, eax
0x1800041dc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800041e6  shr     r8, 2
0x1800041ea  mul     r8
0x1800041ed  shr     rdx, 3
0x1800041f1  lea     rcx, [rdx+rdx*4]
0x1800041f5  add     rcx, rcx
0x1800041f8  sub     r8, rcx
0x1800041fb  mov     rbx, [rbx+r8*8]
0x1800041ff  jmp     short loc_18000420A
0x180004201  cmp     [rbx], r9d
0x180004204  jz      short loc_180004281
0x180004206  mov     rbx, [rbx+8]
0x18000420a  test    rbx, rbx
0x18000420d  jnz     short loc_180004201
0x18000420f  test    rbx, rbx
0x180004212  jz      short loc_180004266
0x180004214  cmp     qword ptr [rbx], 0
0x180004218  jz      short loc_180004266
0x18000421a  mov     [rsi], bpl
0x18000421d  mov     r9, r14; unsigned __int64
0x180004220  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004223  mov     r8, rsi; char *
0x180004226  mov     rcx, rdi; struct wil::FailureInfo *
0x180004229  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000422e  test    al, al
0x180004230  jz      short loc_180004236
0x180004232  mov     [rdi+48h], rsi
0x180004236  mov     rbx, [rbx]
0x180004239  mov     al, [rbx+28h]
0x18000423c  mov     byte ptr [rbx+28h], 1
0x180004240  test    al, al
0x180004242  jnz     short loc_18000425D
0x180004244  mov     rcx, [rbx+8]
0x180004248  mov     rdx, rdi
0x18000424b  mov     rax, [rcx]
0x18000424e  mov     rax, [rax]
0x180004251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004256  or      bpl, al
0x180004259  mov     byte ptr [rbx+28h], 0
0x18000425d  mov     rbx, [rbx+10h]
0x180004261  test    rbx, rbx
0x180004264  jnz     short loc_180004239
0x180004266  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000426d  test    rax, rax
0x180004270  jz      short loc_180004291
0x180004272  test    bpl, bpl
0x180004275  jnz     short loc_180004287
0x180004277  test    byte ptr [rdi+4], 2
0x18000427b  jnz     short loc_180004287
0x18000427d  xor     ecx, ecx
0x18000427f  jmp     short loc_180004289
0x180004281  add     rbx, 10h
0x180004285  jmp     short loc_18000420F
0x180004287  mov     cl, 1
0x180004289  mov     rdx, rdi
0x18000428c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004291  call    cs:__imp_GetCurrentThreadId
0x180004298  nop     dword ptr [rax+rax+00h]
0x18000429d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800042a3  cmp     ecx, eax
0x1800042a5  jz      loc_1800043A7
0x1800042ab  mov     ecx, 1
0x1800042b0  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800042b8  inc     ecx; this
0x1800042ba  cmp     ecx, 4
0x1800042bd  jge     loc_1800043A0
0x1800042c3  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800042c9  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800042ce  mov     rbx, rax
0x1800042d1  test    rax, rax
0x1800042d4  jz      loc_180004396
0x1800042da  cmp     qword ptr [rax+18h], 0
0x1800042df  mov     ebp, 50h ; 'P'
0x1800042e4  mov     esi, [rax+10h]
0x1800042e7  jnz     short loc_18000431E
0x1800042e9  test    esi, esi
0x1800042eb  jz      short loc_18000431E
0x1800042ed  mov     edx, 190h; dwBytes
0x1800042f2  lea     ecx, [rbp-48h]; dwFlags
0x1800042f5  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800042fa  mov     [rbx+18h], rax
0x1800042fe  test    rax, rax
0x180004301  jz      short loc_18000431E
0x180004303  mov     dword ptr [rbx+20h], 5
0x18000430a  lea     rcx, [rax+190h]
0x180004311  jmp     short loc_180004319
0x180004313  mov     [rax], bp
0x180004316  add     rax, rbp
0x180004319  cmp     rax, rcx
0x18000431c  jnz     short loc_180004313
0x18000431e  mov     r9, [rbx+18h]
0x180004322  test    r9, r9
0x180004325  jz      short loc_180004396
0x180004327  test    esi, esi
0x180004329  jz      short loc_18000435C
0x18000432b  movzx   eax, word ptr [rbx+20h]
0x18000432f  mov     rcx, r9
0x180004332  lea     rdx, [rax+rax*4]
0x180004336  shl     rdx, 4
0x18000433a  add     rdx, r9
0x18000433d  cmp     r9, rdx
0x180004340  jz      short loc_18000435C
0x180004342  mov     r8d, [rbx+10h]
0x180004346  cmp     [rcx+4], r8d
0x18000434a  jbe     short loc_180004354
0x18000434c  mov     eax, [rdi+8]
0x18000434f  cmp     [rcx+8], eax
0x180004352  jz      short loc_180004396
0x180004354  add     rcx, rbp
0x180004357  cmp     rcx, rdx
0x18000435a  jnz     short loc_180004346
0x18000435c  movzx   eax, word ptr [rbx+22h]
0x180004360  xor     edx, edx
0x180004362  movzx   ecx, word ptr [rbx+20h]
0x180004366  inc     eax
0x180004368  div     ecx
0x18000436a  mov     rax, [rbx+8]
0x18000436e  mov     r8d, 1
0x180004374  mov     [rbx+22h], dx
0x180004378  lock xadd [rax], r8d
0x18000437d  movzx   eax, dx
0x180004380  inc     r8d; unsigned int
0x180004383  mov     rdx, rdi; struct wil::FailureInfo *
0x180004386  lea     rcx, [rax+rax*4]
0x18000438a  shl     rcx, 4
0x18000438e  add     rcx, r9; this
0x180004391  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004396  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800043a0  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800043a7  add     rsp, 20h
0x1800043ab  pop     r14
0x1800043ad  pop     rdi
0x1800043ae  pop     rsi
0x1800043af  pop     rbp
0x1800043b0  pop     rbx
0x1800043b1  retn
```
