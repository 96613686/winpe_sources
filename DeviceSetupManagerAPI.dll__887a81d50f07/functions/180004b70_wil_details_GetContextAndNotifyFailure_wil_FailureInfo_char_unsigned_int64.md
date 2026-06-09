# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004b70`
- end: `0x180004d77`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004b70`
- `0x18000526c`
- `0x180005350`
- `0x180005cd8`
- `0x1800070f4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c5c`

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
0x180004b70  push    rbx
0x180004b72  push    rbp
0x180004b73  push    rsi
0x180004b74  push    rdi
0x180004b75  push    r14
0x180004b77  sub     rsp, 20h
0x180004b7b  mov     r14, r8
0x180004b7e  mov     rsi, rdx
0x180004b81  mov     rdi, rcx
0x180004b84  mov     byte ptr [rdx], 0
0x180004b87  xor     bpl, bpl
0x180004b8a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004b91  test    rbx, rbx
0x180004b94  jz      loc_180004C30
0x180004b9a  call    cs:__imp_GetCurrentThreadId
0x180004ba0  mov     r9d, eax
0x180004ba3  mov     r8d, eax
0x180004ba6  shr     r8, 2
0x180004baa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004bb4  mul     r8
0x180004bb7  shr     rdx, 3
0x180004bbb  lea     rcx, [rdx+rdx*4]
0x180004bbf  add     rcx, rcx
0x180004bc2  sub     r8, rcx
0x180004bc5  mov     rbx, [rbx+r8*8]
0x180004bc9  jmp     short loc_180004BD4
0x180004bcb  cmp     [rbx], r9d
0x180004bce  jz      short loc_180004C4B
0x180004bd0  mov     rbx, [rbx+8]
0x180004bd4  test    rbx, rbx
0x180004bd7  jnz     short loc_180004BCB
0x180004bd9  test    rbx, rbx
0x180004bdc  jz      short loc_180004C30
0x180004bde  cmp     qword ptr [rbx], 0
0x180004be2  jz      short loc_180004C30
0x180004be4  mov     [rsi], bpl
0x180004be7  mov     r9, r14; unsigned __int64
0x180004bea  mov     r8, rsi; char *
0x180004bed  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004bf0  mov     rcx, rdi; struct wil::FailureInfo *
0x180004bf3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004bf8  test    al, al
0x180004bfa  jz      short loc_180004C00
0x180004bfc  mov     [rdi+48h], rsi
0x180004c00  mov     rbx, [rbx]
0x180004c03  mov     al, [rbx+28h]
0x180004c06  mov     byte ptr [rbx+28h], 1
0x180004c0a  test    al, al
0x180004c0c  jnz     short loc_180004C27
0x180004c0e  mov     rcx, [rbx+8]
0x180004c12  mov     rax, [rcx]
0x180004c15  mov     rdx, rdi
0x180004c18  mov     rax, [rax]
0x180004c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c20  or      bpl, al
0x180004c23  mov     byte ptr [rbx+28h], 0
0x180004c27  mov     rbx, [rbx+10h]
0x180004c2b  test    rbx, rbx
0x180004c2e  jnz     short loc_180004C03
0x180004c30  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004c37  test    rax, rax
0x180004c3a  jz      short loc_180004C5C
0x180004c3c  test    bpl, bpl
0x180004c3f  jnz     short loc_180004C51
0x180004c41  test    byte ptr [rdi+4], 2
0x180004c45  jnz     short loc_180004C51
0x180004c47  xor     ecx, ecx
0x180004c49  jmp     short loc_180004C53
0x180004c4b  add     rbx, 10h
0x180004c4f  jmp     short loc_180004BD9
0x180004c51  mov     cl, 1
0x180004c53  mov     rdx, rdi
0x180004c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c5b  nop
0x180004c5c  call    cs:__imp_GetCurrentThreadId
0x180004c62  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004c68  cmp     ecx, eax
0x180004c6a  jz      loc_180004D6C
0x180004c70  mov     ecx, 1
0x180004c75  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004c7d  inc     ecx; this
0x180004c7f  cmp     ecx, 4
0x180004c82  jge     loc_180004D65
0x180004c88  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004c8e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004c93  mov     rbx, rax
0x180004c96  test    rax, rax
0x180004c99  jz      loc_180004D5B
0x180004c9f  mov     esi, [rax+10h]
0x180004ca2  mov     ebp, 50h ; 'P'
0x180004ca7  cmp     qword ptr [rax+18h], 0
0x180004cac  jnz     short loc_180004CE3
0x180004cae  test    esi, esi
0x180004cb0  jz      short loc_180004CE3
0x180004cb2  mov     edx, 190h; dwBytes
0x180004cb7  lea     ecx, [rbp-48h]; dwFlags
0x180004cba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004cbf  mov     [rbx+18h], rax
0x180004cc3  test    rax, rax
0x180004cc6  jz      short loc_180004CE3
0x180004cc8  mov     dword ptr [rbx+20h], 5
0x180004ccf  lea     rcx, [rax+190h]
0x180004cd6  jmp     short loc_180004CDE
0x180004cd8  mov     [rax], bp
0x180004cdb  add     rax, rbp
0x180004cde  cmp     rax, rcx
0x180004ce1  jnz     short loc_180004CD8
0x180004ce3  mov     r9, [rbx+18h]
0x180004ce7  test    r9, r9
0x180004cea  jz      short loc_180004D5B
0x180004cec  test    esi, esi
0x180004cee  jz      short loc_180004D21
0x180004cf0  mov     rcx, r9
0x180004cf3  movzx   eax, word ptr [rbx+20h]
0x180004cf7  lea     rdx, [rax+rax*4]
0x180004cfb  shl     rdx, 4
0x180004cff  add     rdx, r9
0x180004d02  cmp     r9, rdx
0x180004d05  jz      short loc_180004D21
0x180004d07  mov     r8d, [rbx+10h]
0x180004d0b  cmp     [rcx+4], r8d
0x180004d0f  jbe     short loc_180004D19
0x180004d11  mov     eax, [rdi+8]
0x180004d14  cmp     [rcx+8], eax
0x180004d17  jz      short loc_180004D5B
0x180004d19  add     rcx, rbp
0x180004d1c  cmp     rcx, rdx
0x180004d1f  jnz     short loc_180004D0B
0x180004d21  movzx   eax, word ptr [rbx+22h]
0x180004d25  inc     eax
0x180004d27  movzx   ecx, word ptr [rbx+20h]
0x180004d2b  xor     edx, edx
0x180004d2d  div     ecx
0x180004d2f  mov     [rbx+22h], dx
0x180004d33  mov     rax, [rbx+8]
0x180004d37  mov     r8d, 1
0x180004d3d  lock xadd [rax], r8d
0x180004d42  inc     r8d; unsigned int
0x180004d45  movzx   eax, dx
0x180004d48  lea     rcx, [rax+rax*4]
0x180004d4c  shl     rcx, 4
0x180004d50  add     rcx, r9; this
0x180004d53  mov     rdx, rdi; struct wil::FailureInfo *
0x180004d56  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004d5b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004d65  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004d6c  add     rsp, 20h
0x180004d70  pop     r14
0x180004d72  pop     rdi
0x180004d73  pop     rsi
0x180004d74  pop     rbp
0x180004d75  pop     rbx
0x180004d76  retn
```
