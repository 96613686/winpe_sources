# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004a30`
- end: `0x180004c36`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004a30`
- `0x1800051b8`
- `0x18000529c`
- `0x180005d58`
- `0x180007368`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004a5a`
- `KERNEL32!GetCurrentThreadId` at `0x180004b1b`
- `KERNEL32!GetCurrentThreadId` at `0x180004a5a`
- `KERNEL32!GetCurrentThreadId` at `0x180004b1b`

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
0x180004a30  push    rbx
0x180004a32  push    rbp
0x180004a33  push    rsi
0x180004a34  push    rdi
0x180004a35  push    r14
0x180004a37  sub     rsp, 20h
0x180004a3b  mov     byte ptr [rdx], 0
0x180004a3e  xor     bpl, bpl
0x180004a41  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004a48  mov     r14, r8
0x180004a4b  mov     rsi, rdx
0x180004a4e  mov     rdi, rcx
0x180004a51  test    rbx, rbx
0x180004a54  jz      loc_180004AF0
0x180004a5a  call    cs:__imp_GetCurrentThreadId
0x180004a60  mov     r8d, eax
0x180004a63  mov     r9d, eax
0x180004a66  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004a70  shr     r8, 2
0x180004a74  mul     r8
0x180004a77  shr     rdx, 3
0x180004a7b  lea     rcx, [rdx+rdx*4]
0x180004a7f  add     rcx, rcx
0x180004a82  sub     r8, rcx
0x180004a85  mov     rbx, [rbx+r8*8]
0x180004a89  jmp     short loc_180004A94
0x180004a8b  cmp     [rbx], r9d
0x180004a8e  jz      short loc_180004B0B
0x180004a90  mov     rbx, [rbx+8]
0x180004a94  test    rbx, rbx
0x180004a97  jnz     short loc_180004A8B
0x180004a99  test    rbx, rbx
0x180004a9c  jz      short loc_180004AF0
0x180004a9e  cmp     qword ptr [rbx], 0
0x180004aa2  jz      short loc_180004AF0
0x180004aa4  mov     [rsi], bpl
0x180004aa7  mov     r9, r14; unsigned __int64
0x180004aaa  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004aad  mov     r8, rsi; char *
0x180004ab0  mov     rcx, rdi; struct wil::FailureInfo *
0x180004ab3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004ab8  test    al, al
0x180004aba  jz      short loc_180004AC0
0x180004abc  mov     [rdi+48h], rsi
0x180004ac0  mov     rbx, [rbx]
0x180004ac3  mov     al, [rbx+28h]
0x180004ac6  mov     byte ptr [rbx+28h], 1
0x180004aca  test    al, al
0x180004acc  jnz     short loc_180004AE7
0x180004ace  mov     rcx, [rbx+8]
0x180004ad2  mov     rdx, rdi
0x180004ad5  mov     rax, [rcx]
0x180004ad8  mov     rax, [rax]
0x180004adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae0  or      bpl, al
0x180004ae3  mov     byte ptr [rbx+28h], 0
0x180004ae7  mov     rbx, [rbx+10h]
0x180004aeb  test    rbx, rbx
0x180004aee  jnz     short loc_180004AC3
0x180004af0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004af7  test    rax, rax
0x180004afa  jz      short loc_180004B1B
0x180004afc  test    bpl, bpl
0x180004aff  jnz     short loc_180004B11
0x180004b01  test    byte ptr [rdi+4], 2
0x180004b05  jnz     short loc_180004B11
0x180004b07  xor     ecx, ecx
0x180004b09  jmp     short loc_180004B13
0x180004b0b  add     rbx, 10h
0x180004b0f  jmp     short loc_180004A99
0x180004b11  mov     cl, 1
0x180004b13  mov     rdx, rdi
0x180004b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b1b  call    cs:__imp_GetCurrentThreadId
0x180004b21  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004b27  cmp     ecx, eax
0x180004b29  jz      loc_180004C2B
0x180004b2f  mov     ecx, 1
0x180004b34  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004b3c  inc     ecx; this
0x180004b3e  cmp     ecx, 4
0x180004b41  jge     loc_180004C24
0x180004b47  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004b4d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004b52  mov     rbx, rax
0x180004b55  test    rax, rax
0x180004b58  jz      loc_180004C1A
0x180004b5e  cmp     qword ptr [rax+18h], 0
0x180004b63  mov     ebp, 50h ; 'P'
0x180004b68  mov     esi, [rax+10h]
0x180004b6b  jnz     short loc_180004BA2
0x180004b6d  test    esi, esi
0x180004b6f  jz      short loc_180004BA2
0x180004b71  mov     edx, 190h; dwBytes
0x180004b76  lea     ecx, [rbp-48h]; dwFlags
0x180004b79  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004b7e  mov     [rbx+18h], rax
0x180004b82  test    rax, rax
0x180004b85  jz      short loc_180004BA2
0x180004b87  mov     dword ptr [rbx+20h], 5
0x180004b8e  lea     rcx, [rax+190h]
0x180004b95  jmp     short loc_180004B9D
0x180004b97  mov     [rax], bp
0x180004b9a  add     rax, rbp
0x180004b9d  cmp     rax, rcx
0x180004ba0  jnz     short loc_180004B97
0x180004ba2  mov     r9, [rbx+18h]
0x180004ba6  test    r9, r9
0x180004ba9  jz      short loc_180004C1A
0x180004bab  test    esi, esi
0x180004bad  jz      short loc_180004BE0
0x180004baf  movzx   eax, word ptr [rbx+20h]
0x180004bb3  mov     rcx, r9
0x180004bb6  lea     rdx, [rax+rax*4]
0x180004bba  shl     rdx, 4
0x180004bbe  add     rdx, r9
0x180004bc1  cmp     r9, rdx
0x180004bc4  jz      short loc_180004BE0
0x180004bc6  mov     r8d, [rbx+10h]
0x180004bca  cmp     [rcx+4], r8d
0x180004bce  jbe     short loc_180004BD8
0x180004bd0  mov     eax, [rdi+8]
0x180004bd3  cmp     [rcx+8], eax
0x180004bd6  jz      short loc_180004C1A
0x180004bd8  add     rcx, rbp
0x180004bdb  cmp     rcx, rdx
0x180004bde  jnz     short loc_180004BCA
0x180004be0  movzx   eax, word ptr [rbx+22h]
0x180004be4  xor     edx, edx
0x180004be6  movzx   ecx, word ptr [rbx+20h]
0x180004bea  inc     eax
0x180004bec  div     ecx
0x180004bee  mov     rax, [rbx+8]
0x180004bf2  mov     r8d, 1
0x180004bf8  mov     [rbx+22h], dx
0x180004bfc  lock xadd [rax], r8d
0x180004c01  movzx   eax, dx
0x180004c04  inc     r8d; unsigned int
0x180004c07  mov     rdx, rdi; struct wil::FailureInfo *
0x180004c0a  lea     rcx, [rax+rax*4]
0x180004c0e  shl     rcx, 4
0x180004c12  add     rcx, r9; this
0x180004c15  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004c1a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004c24  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004c2b  add     rsp, 20h
0x180004c2f  pop     r14
0x180004c31  pop     rdi
0x180004c32  pop     rsi
0x180004c33  pop     rbp
0x180004c34  pop     rbx
0x180004c35  retn
```
