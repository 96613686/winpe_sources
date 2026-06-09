# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800038a0`
- end: `0x180003aa6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800038a0`
- `0x180003f98`
- `0x18000407c`
- `0x1800048e8`
- `0x180004c28`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800038ca`
- `KERNEL32!GetCurrentThreadId` at `0x18000398b`
- `KERNEL32!GetCurrentThreadId` at `0x1800038ca`
- `KERNEL32!GetCurrentThreadId` at `0x18000398b`

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
0x1800038a0  push    rbx
0x1800038a2  push    rbp
0x1800038a3  push    rsi
0x1800038a4  push    rdi
0x1800038a5  push    r14
0x1800038a7  sub     rsp, 20h
0x1800038ab  mov     byte ptr [rdx], 0
0x1800038ae  xor     bpl, bpl
0x1800038b1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800038b8  mov     r14, r8
0x1800038bb  mov     rsi, rdx
0x1800038be  mov     rdi, rcx
0x1800038c1  test    rbx, rbx
0x1800038c4  jz      loc_180003960
0x1800038ca  call    cs:__imp_GetCurrentThreadId
0x1800038d0  mov     r8d, eax
0x1800038d3  mov     r9d, eax
0x1800038d6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800038e0  shr     r8, 2
0x1800038e4  mul     r8
0x1800038e7  shr     rdx, 3
0x1800038eb  lea     rcx, [rdx+rdx*4]
0x1800038ef  add     rcx, rcx
0x1800038f2  sub     r8, rcx
0x1800038f5  mov     rbx, [rbx+r8*8]
0x1800038f9  jmp     short loc_180003904
0x1800038fb  cmp     [rbx], r9d
0x1800038fe  jz      short loc_18000397B
0x180003900  mov     rbx, [rbx+8]
0x180003904  test    rbx, rbx
0x180003907  jnz     short loc_1800038FB
0x180003909  test    rbx, rbx
0x18000390c  jz      short loc_180003960
0x18000390e  cmp     qword ptr [rbx], 0
0x180003912  jz      short loc_180003960
0x180003914  mov     [rsi], bpl
0x180003917  mov     r9, r14; unsigned __int64
0x18000391a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000391d  mov     r8, rsi; char *
0x180003920  mov     rcx, rdi; struct wil::FailureInfo *
0x180003923  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003928  test    al, al
0x18000392a  jz      short loc_180003930
0x18000392c  mov     [rdi+48h], rsi
0x180003930  mov     rbx, [rbx]
0x180003933  mov     al, [rbx+28h]
0x180003936  mov     byte ptr [rbx+28h], 1
0x18000393a  test    al, al
0x18000393c  jnz     short loc_180003957
0x18000393e  mov     rcx, [rbx+8]
0x180003942  mov     rdx, rdi
0x180003945  mov     rax, [rcx]
0x180003948  mov     rax, [rax]
0x18000394b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003950  or      bpl, al
0x180003953  mov     byte ptr [rbx+28h], 0
0x180003957  mov     rbx, [rbx+10h]
0x18000395b  test    rbx, rbx
0x18000395e  jnz     short loc_180003933
0x180003960  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003967  test    rax, rax
0x18000396a  jz      short loc_18000398B
0x18000396c  test    bpl, bpl
0x18000396f  jnz     short loc_180003981
0x180003971  test    byte ptr [rdi+4], 2
0x180003975  jnz     short loc_180003981
0x180003977  xor     ecx, ecx
0x180003979  jmp     short loc_180003983
0x18000397b  add     rbx, 10h
0x18000397f  jmp     short loc_180003909
0x180003981  mov     cl, 1
0x180003983  mov     rdx, rdi
0x180003986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000398b  call    cs:__imp_GetCurrentThreadId
0x180003991  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003997  cmp     ecx, eax
0x180003999  jz      loc_180003A9B
0x18000399f  mov     ecx, 1
0x1800039a4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800039ac  inc     ecx; this
0x1800039ae  cmp     ecx, 4
0x1800039b1  jge     loc_180003A94
0x1800039b7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800039bd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800039c2  mov     rbx, rax
0x1800039c5  test    rax, rax
0x1800039c8  jz      loc_180003A8A
0x1800039ce  cmp     qword ptr [rax+18h], 0
0x1800039d3  mov     ebp, 50h ; 'P'
0x1800039d8  mov     esi, [rax+10h]
0x1800039db  jnz     short loc_180003A12
0x1800039dd  test    esi, esi
0x1800039df  jz      short loc_180003A12
0x1800039e1  mov     edx, 190h; dwBytes
0x1800039e6  lea     ecx, [rbp-48h]; dwFlags
0x1800039e9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800039ee  mov     [rbx+18h], rax
0x1800039f2  test    rax, rax
0x1800039f5  jz      short loc_180003A12
0x1800039f7  mov     dword ptr [rbx+20h], 5
0x1800039fe  lea     rcx, [rax+190h]
0x180003a05  jmp     short loc_180003A0D
0x180003a07  mov     [rax], bp
0x180003a0a  add     rax, rbp
0x180003a0d  cmp     rax, rcx
0x180003a10  jnz     short loc_180003A07
0x180003a12  mov     r9, [rbx+18h]
0x180003a16  test    r9, r9
0x180003a19  jz      short loc_180003A8A
0x180003a1b  test    esi, esi
0x180003a1d  jz      short loc_180003A50
0x180003a1f  movzx   eax, word ptr [rbx+20h]
0x180003a23  mov     rcx, r9
0x180003a26  lea     rdx, [rax+rax*4]
0x180003a2a  shl     rdx, 4
0x180003a2e  add     rdx, r9
0x180003a31  cmp     r9, rdx
0x180003a34  jz      short loc_180003A50
0x180003a36  mov     r8d, [rbx+10h]
0x180003a3a  cmp     [rcx+4], r8d
0x180003a3e  jbe     short loc_180003A48
0x180003a40  mov     eax, [rdi+8]
0x180003a43  cmp     [rcx+8], eax
0x180003a46  jz      short loc_180003A8A
0x180003a48  add     rcx, rbp
0x180003a4b  cmp     rcx, rdx
0x180003a4e  jnz     short loc_180003A3A
0x180003a50  movzx   eax, word ptr [rbx+22h]
0x180003a54  xor     edx, edx
0x180003a56  movzx   ecx, word ptr [rbx+20h]
0x180003a5a  inc     eax
0x180003a5c  div     ecx
0x180003a5e  mov     rax, [rbx+8]
0x180003a62  mov     r8d, 1
0x180003a68  mov     [rbx+22h], dx
0x180003a6c  lock xadd [rax], r8d
0x180003a71  movzx   eax, dx
0x180003a74  inc     r8d; unsigned int
0x180003a77  mov     rdx, rdi; struct wil::FailureInfo *
0x180003a7a  lea     rcx, [rax+rax*4]
0x180003a7e  shl     rcx, 4
0x180003a82  add     rcx, r9; this
0x180003a85  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180003a8a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003a94  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003a9b  add     rsp, 20h
0x180003a9f  pop     r14
0x180003aa1  pop     rdi
0x180003aa2  pop     rsi
0x180003aa3  pop     rbp
0x180003aa4  pop     rbx
0x180003aa5  retn
```
