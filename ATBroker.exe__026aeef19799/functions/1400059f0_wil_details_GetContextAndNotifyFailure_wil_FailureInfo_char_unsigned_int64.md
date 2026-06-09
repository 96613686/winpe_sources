# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400059f0`
- end: `0x140005bf6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400059f0`
- `0x140006310`
- `0x1400063f4`
- `0x1400075c8`
- `0x140009478`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005a1a`
- `KERNEL32!GetCurrentThreadId` at `0x140005adb`
- `KERNEL32!GetCurrentThreadId` at `0x140005a1a`
- `KERNEL32!GetCurrentThreadId` at `0x140005adb`

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
0x1400059f0  push    rbx
0x1400059f2  push    rbp
0x1400059f3  push    rsi
0x1400059f4  push    rdi
0x1400059f5  push    r14
0x1400059f7  sub     rsp, 20h
0x1400059fb  mov     byte ptr [rdx], 0
0x1400059fe  xor     bpl, bpl
0x140005a01  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140005a08  mov     r14, r8
0x140005a0b  mov     rsi, rdx
0x140005a0e  mov     rdi, rcx
0x140005a11  test    rbx, rbx
0x140005a14  jz      loc_140005AB0
0x140005a1a  call    cs:__imp_GetCurrentThreadId
0x140005a20  mov     r8d, eax
0x140005a23  mov     r9d, eax
0x140005a26  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005a30  shr     r8, 2
0x140005a34  mul     r8
0x140005a37  shr     rdx, 3
0x140005a3b  lea     rcx, [rdx+rdx*4]
0x140005a3f  add     rcx, rcx
0x140005a42  sub     r8, rcx
0x140005a45  mov     rbx, [rbx+r8*8]
0x140005a49  jmp     short loc_140005A54
0x140005a4b  cmp     [rbx], r9d
0x140005a4e  jz      short loc_140005ACB
0x140005a50  mov     rbx, [rbx+8]
0x140005a54  test    rbx, rbx
0x140005a57  jnz     short loc_140005A4B
0x140005a59  test    rbx, rbx
0x140005a5c  jz      short loc_140005AB0
0x140005a5e  cmp     qword ptr [rbx], 0
0x140005a62  jz      short loc_140005AB0
0x140005a64  mov     [rsi], bpl
0x140005a67  mov     r9, r14; unsigned __int64
0x140005a6a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140005a6d  mov     r8, rsi; char *
0x140005a70  mov     rcx, rdi; struct wil::FailureInfo *
0x140005a73  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005a78  test    al, al
0x140005a7a  jz      short loc_140005A80
0x140005a7c  mov     [rdi+48h], rsi
0x140005a80  mov     rbx, [rbx]
0x140005a83  mov     al, [rbx+28h]
0x140005a86  mov     byte ptr [rbx+28h], 1
0x140005a8a  test    al, al
0x140005a8c  jnz     short loc_140005AA7
0x140005a8e  mov     rcx, [rbx+8]
0x140005a92  mov     rdx, rdi
0x140005a95  mov     rax, [rcx]
0x140005a98  mov     rax, [rax]
0x140005a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005aa0  or      bpl, al
0x140005aa3  mov     byte ptr [rbx+28h], 0
0x140005aa7  mov     rbx, [rbx+10h]
0x140005aab  test    rbx, rbx
0x140005aae  jnz     short loc_140005A83
0x140005ab0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140005ab7  test    rax, rax
0x140005aba  jz      short loc_140005ADB
0x140005abc  test    bpl, bpl
0x140005abf  jnz     short loc_140005AD1
0x140005ac1  test    byte ptr [rdi+4], 2
0x140005ac5  jnz     short loc_140005AD1
0x140005ac7  xor     ecx, ecx
0x140005ac9  jmp     short loc_140005AD3
0x140005acb  add     rbx, 10h
0x140005acf  jmp     short loc_140005A59
0x140005ad1  mov     cl, 1
0x140005ad3  mov     rdx, rdi
0x140005ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005adb  call    cs:__imp_GetCurrentThreadId
0x140005ae1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005ae7  cmp     ecx, eax
0x140005ae9  jz      loc_140005BEB
0x140005aef  mov     ecx, 1
0x140005af4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140005afc  inc     ecx; this
0x140005afe  cmp     ecx, 4
0x140005b01  jge     loc_140005BE4
0x140005b07  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005b0d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140005b12  mov     rbx, rax
0x140005b15  test    rax, rax
0x140005b18  jz      loc_140005BDA
0x140005b1e  cmp     qword ptr [rax+18h], 0
0x140005b23  mov     ebp, 50h ; 'P'
0x140005b28  mov     esi, [rax+10h]
0x140005b2b  jnz     short loc_140005B62
0x140005b2d  test    esi, esi
0x140005b2f  jz      short loc_140005B62
0x140005b31  mov     edx, 190h; dwBytes
0x140005b36  lea     ecx, [rbp-48h]; dwFlags
0x140005b39  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005b3e  mov     [rbx+18h], rax
0x140005b42  test    rax, rax
0x140005b45  jz      short loc_140005B62
0x140005b47  mov     dword ptr [rbx+20h], 5
0x140005b4e  lea     rcx, [rax+190h]
0x140005b55  jmp     short loc_140005B5D
0x140005b57  mov     [rax], bp
0x140005b5a  add     rax, rbp
0x140005b5d  cmp     rax, rcx
0x140005b60  jnz     short loc_140005B57
0x140005b62  mov     r9, [rbx+18h]
0x140005b66  test    r9, r9
0x140005b69  jz      short loc_140005BDA
0x140005b6b  test    esi, esi
0x140005b6d  jz      short loc_140005BA0
0x140005b6f  movzx   eax, word ptr [rbx+20h]
0x140005b73  mov     rcx, r9
0x140005b76  lea     rdx, [rax+rax*4]
0x140005b7a  shl     rdx, 4
0x140005b7e  add     rdx, r9
0x140005b81  cmp     r9, rdx
0x140005b84  jz      short loc_140005BA0
0x140005b86  mov     r8d, [rbx+10h]
0x140005b8a  cmp     [rcx+4], r8d
0x140005b8e  jbe     short loc_140005B98
0x140005b90  mov     eax, [rdi+8]
0x140005b93  cmp     [rcx+8], eax
0x140005b96  jz      short loc_140005BDA
0x140005b98  add     rcx, rbp
0x140005b9b  cmp     rcx, rdx
0x140005b9e  jnz     short loc_140005B8A
0x140005ba0  movzx   eax, word ptr [rbx+22h]
0x140005ba4  xor     edx, edx
0x140005ba6  movzx   ecx, word ptr [rbx+20h]
0x140005baa  inc     eax
0x140005bac  div     ecx
0x140005bae  mov     rax, [rbx+8]
0x140005bb2  mov     r8d, 1
0x140005bb8  mov     [rbx+22h], dx
0x140005bbc  lock xadd [rax], r8d
0x140005bc1  movzx   eax, dx
0x140005bc4  inc     r8d; unsigned int
0x140005bc7  mov     rdx, rdi; struct wil::FailureInfo *
0x140005bca  lea     rcx, [rax+rax*4]
0x140005bce  shl     rcx, 4
0x140005bd2  add     rcx, r9; this
0x140005bd5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140005bda  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005be4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140005beb  add     rsp, 20h
0x140005bef  pop     r14
0x140005bf1  pop     rdi
0x140005bf2  pop     rsi
0x140005bf3  pop     rbp
0x140005bf4  pop     rbx
0x140005bf5  retn
```
