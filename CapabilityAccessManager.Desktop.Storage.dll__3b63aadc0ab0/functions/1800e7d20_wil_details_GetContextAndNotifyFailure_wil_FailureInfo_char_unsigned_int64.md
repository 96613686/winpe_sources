# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800e7d20`
- end: `0x1800e7f27`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800e7d20`
- `0x1800e8520`
- `0x1800e8604`
- `0x1800e90b0`
- `0x1800eace4`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e7d4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e7e0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e7d4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e7e0c`

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
0x1800e7d20  push    rbx
0x1800e7d22  push    rbp
0x1800e7d23  push    rsi
0x1800e7d24  push    rdi
0x1800e7d25  push    r14
0x1800e7d27  sub     rsp, 20h
0x1800e7d2b  mov     r14, r8
0x1800e7d2e  mov     rsi, rdx
0x1800e7d31  mov     rdi, rcx
0x1800e7d34  mov     byte ptr [rdx], 0
0x1800e7d37  xor     bpl, bpl
0x1800e7d3a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800e7d41  test    rbx, rbx
0x1800e7d44  jz      loc_1800E7DE0
0x1800e7d4a  call    cs:__imp_GetCurrentThreadId
0x1800e7d50  mov     r9d, eax
0x1800e7d53  mov     r8d, eax
0x1800e7d56  shr     r8, 2
0x1800e7d5a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800e7d64  mul     r8
0x1800e7d67  shr     rdx, 3
0x1800e7d6b  lea     rcx, [rdx+rdx*4]
0x1800e7d6f  add     rcx, rcx
0x1800e7d72  sub     r8, rcx
0x1800e7d75  mov     rbx, [rbx+r8*8]
0x1800e7d79  jmp     short loc_1800E7D84
0x1800e7d7b  cmp     [rbx], r9d
0x1800e7d7e  jz      short loc_1800E7DFB
0x1800e7d80  mov     rbx, [rbx+8]
0x1800e7d84  test    rbx, rbx
0x1800e7d87  jnz     short loc_1800E7D7B
0x1800e7d89  test    rbx, rbx
0x1800e7d8c  jz      short loc_1800E7DE0
0x1800e7d8e  cmp     qword ptr [rbx], 0
0x1800e7d92  jz      short loc_1800E7DE0
0x1800e7d94  mov     [rsi], bpl
0x1800e7d97  mov     r9, r14; unsigned __int64
0x1800e7d9a  mov     r8, rsi; char *
0x1800e7d9d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800e7da0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800e7da3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800e7da8  test    al, al
0x1800e7daa  jz      short loc_1800E7DB0
0x1800e7dac  mov     [rdi+48h], rsi
0x1800e7db0  mov     rbx, [rbx]
0x1800e7db3  mov     al, [rbx+28h]
0x1800e7db6  mov     byte ptr [rbx+28h], 1
0x1800e7dba  test    al, al
0x1800e7dbc  jnz     short loc_1800E7DD7
0x1800e7dbe  mov     rcx, [rbx+8]
0x1800e7dc2  mov     rax, [rcx]
0x1800e7dc5  mov     rdx, rdi
0x1800e7dc8  mov     rax, [rax]
0x1800e7dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7dd0  or      bpl, al
0x1800e7dd3  mov     byte ptr [rbx+28h], 0
0x1800e7dd7  mov     rbx, [rbx+10h]
0x1800e7ddb  test    rbx, rbx
0x1800e7dde  jnz     short loc_1800E7DB3
0x1800e7de0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800e7de7  test    rax, rax
0x1800e7dea  jz      short loc_1800E7E0C
0x1800e7dec  test    bpl, bpl
0x1800e7def  jnz     short loc_1800E7E01
0x1800e7df1  test    byte ptr [rdi+4], 2
0x1800e7df5  jnz     short loc_1800E7E01
0x1800e7df7  xor     ecx, ecx
0x1800e7df9  jmp     short loc_1800E7E03
0x1800e7dfb  add     rbx, 10h
0x1800e7dff  jmp     short loc_1800E7D89
0x1800e7e01  mov     cl, 1
0x1800e7e03  mov     rdx, rdi
0x1800e7e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7e0b  nop
0x1800e7e0c  call    cs:__imp_GetCurrentThreadId
0x1800e7e12  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800e7e18  cmp     ecx, eax
0x1800e7e1a  jz      loc_1800E7F1C
0x1800e7e20  mov     ecx, 1
0x1800e7e25  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800e7e2d  inc     ecx; this
0x1800e7e2f  cmp     ecx, 4
0x1800e7e32  jge     loc_1800E7F15
0x1800e7e38  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800e7e3e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800e7e43  mov     rbx, rax
0x1800e7e46  test    rax, rax
0x1800e7e49  jz      loc_1800E7F0B
0x1800e7e4f  mov     esi, [rax+10h]
0x1800e7e52  mov     ebp, 50h ; 'P'
0x1800e7e57  cmp     qword ptr [rax+18h], 0
0x1800e7e5c  jnz     short loc_1800E7E93
0x1800e7e5e  test    esi, esi
0x1800e7e60  jz      short loc_1800E7E93
0x1800e7e62  mov     edx, 190h; dwBytes
0x1800e7e67  lea     ecx, [rbp-48h]; dwFlags
0x1800e7e6a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800e7e6f  mov     [rbx+18h], rax
0x1800e7e73  test    rax, rax
0x1800e7e76  jz      short loc_1800E7E93
0x1800e7e78  mov     dword ptr [rbx+20h], 5
0x1800e7e7f  lea     rcx, [rax+190h]
0x1800e7e86  jmp     short loc_1800E7E8E
0x1800e7e88  mov     [rax], bp
0x1800e7e8b  add     rax, rbp
0x1800e7e8e  cmp     rax, rcx
0x1800e7e91  jnz     short loc_1800E7E88
0x1800e7e93  mov     r9, [rbx+18h]
0x1800e7e97  test    r9, r9
0x1800e7e9a  jz      short loc_1800E7F0B
0x1800e7e9c  test    esi, esi
0x1800e7e9e  jz      short loc_1800E7ED1
0x1800e7ea0  mov     rcx, r9
0x1800e7ea3  movzx   eax, word ptr [rbx+20h]
0x1800e7ea7  lea     rdx, [rax+rax*4]
0x1800e7eab  shl     rdx, 4
0x1800e7eaf  add     rdx, r9
0x1800e7eb2  cmp     r9, rdx
0x1800e7eb5  jz      short loc_1800E7ED1
0x1800e7eb7  mov     r8d, [rbx+10h]
0x1800e7ebb  cmp     [rcx+4], r8d
0x1800e7ebf  jbe     short loc_1800E7EC9
0x1800e7ec1  mov     eax, [rdi+8]
0x1800e7ec4  cmp     [rcx+8], eax
0x1800e7ec7  jz      short loc_1800E7F0B
0x1800e7ec9  add     rcx, rbp
0x1800e7ecc  cmp     rcx, rdx
0x1800e7ecf  jnz     short loc_1800E7EBB
0x1800e7ed1  movzx   eax, word ptr [rbx+22h]
0x1800e7ed5  inc     eax
0x1800e7ed7  movzx   ecx, word ptr [rbx+20h]
0x1800e7edb  xor     edx, edx
0x1800e7edd  div     ecx
0x1800e7edf  mov     [rbx+22h], dx
0x1800e7ee3  mov     rax, [rbx+8]
0x1800e7ee7  mov     r8d, 1
0x1800e7eed  lock xadd [rax], r8d
0x1800e7ef2  inc     r8d; unsigned int
0x1800e7ef5  movzx   eax, dx
0x1800e7ef8  lea     rcx, [rax+rax*4]
0x1800e7efc  shl     rcx, 4
0x1800e7f00  add     rcx, r9; this
0x1800e7f03  mov     rdx, rdi; struct wil::FailureInfo *
0x1800e7f06  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800e7f0b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800e7f15  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800e7f1c  add     rsp, 20h
0x1800e7f20  pop     r14
0x1800e7f22  pop     rdi
0x1800e7f23  pop     rsi
0x1800e7f24  pop     rbp
0x1800e7f25  pop     rbx
0x1800e7f26  retn
```
