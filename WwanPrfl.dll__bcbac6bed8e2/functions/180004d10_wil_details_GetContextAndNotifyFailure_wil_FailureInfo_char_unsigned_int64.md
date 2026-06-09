# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004d10`
- end: `0x180004f17`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004d10`
- `0x18000540c`
- `0x1800054f0`
- `0x180005f68`
- `0x180007a54`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004dfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004dfc`

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
0x180004d10  push    rbx
0x180004d12  push    rbp
0x180004d13  push    rsi
0x180004d14  push    rdi
0x180004d15  push    r14
0x180004d17  sub     rsp, 20h
0x180004d1b  mov     r14, r8
0x180004d1e  mov     rsi, rdx
0x180004d21  mov     rdi, rcx
0x180004d24  mov     byte ptr [rdx], 0
0x180004d27  xor     bpl, bpl
0x180004d2a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004d31  test    rbx, rbx
0x180004d34  jz      loc_180004DD0
0x180004d3a  call    cs:__imp_GetCurrentThreadId
0x180004d40  mov     r9d, eax
0x180004d43  mov     r8d, eax
0x180004d46  shr     r8, 2
0x180004d4a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004d54  mul     r8
0x180004d57  shr     rdx, 3
0x180004d5b  lea     rcx, [rdx+rdx*4]
0x180004d5f  add     rcx, rcx
0x180004d62  sub     r8, rcx
0x180004d65  mov     rbx, [rbx+r8*8]
0x180004d69  jmp     short loc_180004D74
0x180004d6b  cmp     [rbx], r9d
0x180004d6e  jz      short loc_180004DEB
0x180004d70  mov     rbx, [rbx+8]
0x180004d74  test    rbx, rbx
0x180004d77  jnz     short loc_180004D6B
0x180004d79  test    rbx, rbx
0x180004d7c  jz      short loc_180004DD0
0x180004d7e  cmp     qword ptr [rbx], 0
0x180004d82  jz      short loc_180004DD0
0x180004d84  mov     [rsi], bpl
0x180004d87  mov     r9, r14; unsigned __int64
0x180004d8a  mov     r8, rsi; char *
0x180004d8d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004d90  mov     rcx, rdi; struct wil::FailureInfo *
0x180004d93  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004d98  test    al, al
0x180004d9a  jz      short loc_180004DA0
0x180004d9c  mov     [rdi+48h], rsi
0x180004da0  mov     rbx, [rbx]
0x180004da3  mov     al, [rbx+28h]
0x180004da6  mov     byte ptr [rbx+28h], 1
0x180004daa  test    al, al
0x180004dac  jnz     short loc_180004DC7
0x180004dae  mov     rcx, [rbx+8]
0x180004db2  mov     rax, [rcx]
0x180004db5  mov     rdx, rdi
0x180004db8  mov     rax, [rax]
0x180004dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc0  or      bpl, al
0x180004dc3  mov     byte ptr [rbx+28h], 0
0x180004dc7  mov     rbx, [rbx+10h]
0x180004dcb  test    rbx, rbx
0x180004dce  jnz     short loc_180004DA3
0x180004dd0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004dd7  test    rax, rax
0x180004dda  jz      short loc_180004DFC
0x180004ddc  test    bpl, bpl
0x180004ddf  jnz     short loc_180004DF1
0x180004de1  test    byte ptr [rdi+4], 2
0x180004de5  jnz     short loc_180004DF1
0x180004de7  xor     ecx, ecx
0x180004de9  jmp     short loc_180004DF3
0x180004deb  add     rbx, 10h
0x180004def  jmp     short loc_180004D79
0x180004df1  mov     cl, 1
0x180004df3  mov     rdx, rdi
0x180004df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dfb  nop
0x180004dfc  call    cs:__imp_GetCurrentThreadId
0x180004e02  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004e08  cmp     ecx, eax
0x180004e0a  jz      loc_180004F0C
0x180004e10  mov     ecx, 1
0x180004e15  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004e1d  inc     ecx; this
0x180004e1f  cmp     ecx, 4
0x180004e22  jge     loc_180004F05
0x180004e28  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004e2e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004e33  mov     rbx, rax
0x180004e36  test    rax, rax
0x180004e39  jz      loc_180004EFB
0x180004e3f  mov     esi, [rax+10h]
0x180004e42  mov     ebp, 50h ; 'P'
0x180004e47  cmp     qword ptr [rax+18h], 0
0x180004e4c  jnz     short loc_180004E83
0x180004e4e  test    esi, esi
0x180004e50  jz      short loc_180004E83
0x180004e52  mov     edx, 190h; dwBytes
0x180004e57  lea     ecx, [rbp-48h]; dwFlags
0x180004e5a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004e5f  mov     [rbx+18h], rax
0x180004e63  test    rax, rax
0x180004e66  jz      short loc_180004E83
0x180004e68  mov     dword ptr [rbx+20h], 5
0x180004e6f  lea     rcx, [rax+190h]
0x180004e76  jmp     short loc_180004E7E
0x180004e78  mov     [rax], bp
0x180004e7b  add     rax, rbp
0x180004e7e  cmp     rax, rcx
0x180004e81  jnz     short loc_180004E78
0x180004e83  mov     r9, [rbx+18h]
0x180004e87  test    r9, r9
0x180004e8a  jz      short loc_180004EFB
0x180004e8c  test    esi, esi
0x180004e8e  jz      short loc_180004EC1
0x180004e90  mov     rcx, r9
0x180004e93  movzx   eax, word ptr [rbx+20h]
0x180004e97  lea     rdx, [rax+rax*4]
0x180004e9b  shl     rdx, 4
0x180004e9f  add     rdx, r9
0x180004ea2  cmp     r9, rdx
0x180004ea5  jz      short loc_180004EC1
0x180004ea7  mov     r8d, [rbx+10h]
0x180004eab  cmp     [rcx+4], r8d
0x180004eaf  jbe     short loc_180004EB9
0x180004eb1  mov     eax, [rdi+8]
0x180004eb4  cmp     [rcx+8], eax
0x180004eb7  jz      short loc_180004EFB
0x180004eb9  add     rcx, rbp
0x180004ebc  cmp     rcx, rdx
0x180004ebf  jnz     short loc_180004EAB
0x180004ec1  movzx   eax, word ptr [rbx+22h]
0x180004ec5  inc     eax
0x180004ec7  movzx   ecx, word ptr [rbx+20h]
0x180004ecb  xor     edx, edx
0x180004ecd  div     ecx
0x180004ecf  mov     [rbx+22h], dx
0x180004ed3  mov     rax, [rbx+8]
0x180004ed7  mov     r8d, 1
0x180004edd  lock xadd [rax], r8d
0x180004ee2  inc     r8d; unsigned int
0x180004ee5  movzx   eax, dx
0x180004ee8  lea     rcx, [rax+rax*4]
0x180004eec  shl     rcx, 4
0x180004ef0  add     rcx, r9; this
0x180004ef3  mov     rdx, rdi; struct wil::FailureInfo *
0x180004ef6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004efb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004f05  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004f0c  add     rsp, 20h
0x180004f10  pop     r14
0x180004f12  pop     rdi
0x180004f13  pop     rsi
0x180004f14  pop     rbp
0x180004f15  pop     rbx
0x180004f16  retn
```
