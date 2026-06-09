# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140009be0`
- end: `0x140009de6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140005cd0`
- `0x140009be0`
- `0x14000a2d8`
- `0x14000a3bc`
- `0x14000c028`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140009c0a`
- `KERNEL32!GetCurrentThreadId` at `0x140009ccb`
- `KERNEL32!GetCurrentThreadId` at `0x140009c0a`
- `KERNEL32!GetCurrentThreadId` at `0x140009ccb`

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
0x140009be0  push    rbx
0x140009be2  push    rbp
0x140009be3  push    rsi
0x140009be4  push    rdi
0x140009be5  push    r14
0x140009be7  sub     rsp, 20h
0x140009beb  mov     byte ptr [rdx], 0
0x140009bee  xor     bpl, bpl
0x140009bf1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140009bf8  mov     r14, r8
0x140009bfb  mov     rsi, rdx
0x140009bfe  mov     rdi, rcx
0x140009c01  test    rbx, rbx
0x140009c04  jz      loc_140009CA0
0x140009c0a  call    cs:__imp_GetCurrentThreadId
0x140009c10  mov     r8d, eax
0x140009c13  mov     r9d, eax
0x140009c16  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140009c20  shr     r8, 2
0x140009c24  mul     r8
0x140009c27  shr     rdx, 3
0x140009c2b  lea     rcx, [rdx+rdx*4]
0x140009c2f  add     rcx, rcx
0x140009c32  sub     r8, rcx
0x140009c35  mov     rbx, [rbx+r8*8]
0x140009c39  jmp     short loc_140009C44
0x140009c3b  cmp     [rbx], r9d
0x140009c3e  jz      short loc_140009CBB
0x140009c40  mov     rbx, [rbx+8]
0x140009c44  test    rbx, rbx
0x140009c47  jnz     short loc_140009C3B
0x140009c49  test    rbx, rbx
0x140009c4c  jz      short loc_140009CA0
0x140009c4e  cmp     qword ptr [rbx], 0
0x140009c52  jz      short loc_140009CA0
0x140009c54  mov     [rsi], bpl
0x140009c57  mov     r9, r14; unsigned __int64
0x140009c5a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140009c5d  mov     r8, rsi; char *
0x140009c60  mov     rcx, rdi; struct wil::FailureInfo *
0x140009c63  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140009c68  test    al, al
0x140009c6a  jz      short loc_140009C70
0x140009c6c  mov     [rdi+48h], rsi
0x140009c70  mov     rbx, [rbx]
0x140009c73  mov     al, [rbx+28h]
0x140009c76  mov     byte ptr [rbx+28h], 1
0x140009c7a  test    al, al
0x140009c7c  jnz     short loc_140009C97
0x140009c7e  mov     rcx, [rbx+8]
0x140009c82  mov     rdx, rdi
0x140009c85  mov     rax, [rcx]
0x140009c88  mov     rax, [rax]
0x140009c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c90  or      bpl, al
0x140009c93  mov     byte ptr [rbx+28h], 0
0x140009c97  mov     rbx, [rbx+10h]
0x140009c9b  test    rbx, rbx
0x140009c9e  jnz     short loc_140009C73
0x140009ca0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140009ca7  test    rax, rax
0x140009caa  jz      short loc_140009CCB
0x140009cac  test    bpl, bpl
0x140009caf  jnz     short loc_140009CC1
0x140009cb1  test    byte ptr [rdi+4], 2
0x140009cb5  jnz     short loc_140009CC1
0x140009cb7  xor     ecx, ecx
0x140009cb9  jmp     short loc_140009CC3
0x140009cbb  add     rbx, 10h
0x140009cbf  jmp     short loc_140009C49
0x140009cc1  mov     cl, 1
0x140009cc3  mov     rdx, rdi
0x140009cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ccb  call    cs:__imp_GetCurrentThreadId
0x140009cd1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140009cd7  cmp     ecx, eax
0x140009cd9  jz      loc_140009DDB
0x140009cdf  mov     ecx, 1
0x140009ce4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140009cec  inc     ecx; this
0x140009cee  cmp     ecx, 4
0x140009cf1  jge     loc_140009DD4
0x140009cf7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140009cfd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140009d02  mov     rbx, rax
0x140009d05  test    rax, rax
0x140009d08  jz      loc_140009DCA
0x140009d0e  cmp     qword ptr [rax+18h], 0
0x140009d13  mov     ebp, 50h ; 'P'
0x140009d18  mov     esi, [rax+10h]
0x140009d1b  jnz     short loc_140009D52
0x140009d1d  test    esi, esi
0x140009d1f  jz      short loc_140009D52
0x140009d21  mov     edx, 190h; dwBytes
0x140009d26  lea     ecx, [rbp-48h]; dwFlags
0x140009d29  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009d2e  mov     [rbx+18h], rax
0x140009d32  test    rax, rax
0x140009d35  jz      short loc_140009D52
0x140009d37  mov     dword ptr [rbx+20h], 5
0x140009d3e  lea     rcx, [rax+190h]
0x140009d45  jmp     short loc_140009D4D
0x140009d47  mov     [rax], bp
0x140009d4a  add     rax, rbp
0x140009d4d  cmp     rax, rcx
0x140009d50  jnz     short loc_140009D47
0x140009d52  mov     r9, [rbx+18h]
0x140009d56  test    r9, r9
0x140009d59  jz      short loc_140009DCA
0x140009d5b  test    esi, esi
0x140009d5d  jz      short loc_140009D90
0x140009d5f  movzx   eax, word ptr [rbx+20h]
0x140009d63  mov     rcx, r9
0x140009d66  lea     rdx, [rax+rax*4]
0x140009d6a  shl     rdx, 4
0x140009d6e  add     rdx, r9
0x140009d71  cmp     r9, rdx
0x140009d74  jz      short loc_140009D90
0x140009d76  mov     r8d, [rbx+10h]
0x140009d7a  cmp     [rcx+4], r8d
0x140009d7e  jbe     short loc_140009D88
0x140009d80  mov     eax, [rdi+8]
0x140009d83  cmp     [rcx+8], eax
0x140009d86  jz      short loc_140009DCA
0x140009d88  add     rcx, rbp
0x140009d8b  cmp     rcx, rdx
0x140009d8e  jnz     short loc_140009D7A
0x140009d90  movzx   eax, word ptr [rbx+22h]
0x140009d94  xor     edx, edx
0x140009d96  movzx   ecx, word ptr [rbx+20h]
0x140009d9a  inc     eax
0x140009d9c  div     ecx
0x140009d9e  mov     rax, [rbx+8]
0x140009da2  mov     r8d, 1
0x140009da8  mov     [rbx+22h], dx
0x140009dac  lock xadd [rax], r8d
0x140009db1  movzx   eax, dx
0x140009db4  inc     r8d; unsigned int
0x140009db7  mov     rdx, rdi; struct wil::FailureInfo *
0x140009dba  lea     rcx, [rax+rax*4]
0x140009dbe  shl     rcx, 4
0x140009dc2  add     rcx, r9; this
0x140009dc5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140009dca  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140009dd4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140009ddb  add     rsp, 20h
0x140009ddf  pop     r14
0x140009de1  pop     rdi
0x140009de2  pop     rsi
0x140009de3  pop     rbp
0x140009de4  pop     rbx
0x140009de5  retn
```
