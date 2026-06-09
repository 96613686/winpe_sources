# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180015d20`
- end: `0x180015f27`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180015d20`
- `0x18001641c`
- `0x180016500`
- `0x180016e88`
- `0x1800182a4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015d4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015e0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015d4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015e0c`

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
0x180015d20  push    rbx
0x180015d22  push    rbp
0x180015d23  push    rsi
0x180015d24  push    rdi
0x180015d25  push    r14
0x180015d27  sub     rsp, 20h
0x180015d2b  mov     r14, r8
0x180015d2e  mov     rsi, rdx
0x180015d31  mov     rdi, rcx
0x180015d34  mov     byte ptr [rdx], 0
0x180015d37  xor     bpl, bpl
0x180015d3a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180015d41  test    rbx, rbx
0x180015d44  jz      loc_180015DE0
0x180015d4a  call    cs:__imp_GetCurrentThreadId
0x180015d50  mov     r9d, eax
0x180015d53  mov     r8d, eax
0x180015d56  shr     r8, 2
0x180015d5a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180015d64  mul     r8
0x180015d67  shr     rdx, 3
0x180015d6b  lea     rcx, [rdx+rdx*4]
0x180015d6f  add     rcx, rcx
0x180015d72  sub     r8, rcx
0x180015d75  mov     rbx, [rbx+r8*8]
0x180015d79  jmp     short loc_180015D84
0x180015d7b  cmp     [rbx], r9d
0x180015d7e  jz      short loc_180015DFB
0x180015d80  mov     rbx, [rbx+8]
0x180015d84  test    rbx, rbx
0x180015d87  jnz     short loc_180015D7B
0x180015d89  test    rbx, rbx
0x180015d8c  jz      short loc_180015DE0
0x180015d8e  cmp     qword ptr [rbx], 0
0x180015d92  jz      short loc_180015DE0
0x180015d94  mov     [rsi], bpl
0x180015d97  mov     r9, r14; unsigned __int64
0x180015d9a  mov     r8, rsi; char *
0x180015d9d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180015da0  mov     rcx, rdi; struct wil::FailureInfo *
0x180015da3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180015da8  test    al, al
0x180015daa  jz      short loc_180015DB0
0x180015dac  mov     [rdi+48h], rsi
0x180015db0  mov     rbx, [rbx]
0x180015db3  mov     al, [rbx+28h]
0x180015db6  mov     byte ptr [rbx+28h], 1
0x180015dba  test    al, al
0x180015dbc  jnz     short loc_180015DD7
0x180015dbe  mov     rcx, [rbx+8]
0x180015dc2  mov     rax, [rcx]
0x180015dc5  mov     rdx, rdi
0x180015dc8  mov     rax, [rax]
0x180015dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dd0  or      bpl, al
0x180015dd3  mov     byte ptr [rbx+28h], 0
0x180015dd7  mov     rbx, [rbx+10h]
0x180015ddb  test    rbx, rbx
0x180015dde  jnz     short loc_180015DB3
0x180015de0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180015de7  test    rax, rax
0x180015dea  jz      short loc_180015E0C
0x180015dec  test    bpl, bpl
0x180015def  jnz     short loc_180015E01
0x180015df1  test    byte ptr [rdi+4], 2
0x180015df5  jnz     short loc_180015E01
0x180015df7  xor     ecx, ecx
0x180015df9  jmp     short loc_180015E03
0x180015dfb  add     rbx, 10h
0x180015dff  jmp     short loc_180015D89
0x180015e01  mov     cl, 1
0x180015e03  mov     rdx, rdi
0x180015e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e0b  nop
0x180015e0c  call    cs:__imp_GetCurrentThreadId
0x180015e12  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180015e18  cmp     ecx, eax
0x180015e1a  jz      loc_180015F1C
0x180015e20  mov     ecx, 1
0x180015e25  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180015e2d  inc     ecx; this
0x180015e2f  cmp     ecx, 4
0x180015e32  jge     loc_180015F15
0x180015e38  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180015e3e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180015e43  mov     rbx, rax
0x180015e46  test    rax, rax
0x180015e49  jz      loc_180015F0B
0x180015e4f  mov     esi, [rax+10h]
0x180015e52  mov     ebp, 50h ; 'P'
0x180015e57  cmp     qword ptr [rax+18h], 0
0x180015e5c  jnz     short loc_180015E93
0x180015e5e  test    esi, esi
0x180015e60  jz      short loc_180015E93
0x180015e62  mov     edx, 190h; dwBytes
0x180015e67  lea     ecx, [rbp-48h]; dwFlags
0x180015e6a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015e6f  mov     [rbx+18h], rax
0x180015e73  test    rax, rax
0x180015e76  jz      short loc_180015E93
0x180015e78  mov     dword ptr [rbx+20h], 5
0x180015e7f  lea     rcx, [rax+190h]
0x180015e86  jmp     short loc_180015E8E
0x180015e88  mov     [rax], bp
0x180015e8b  add     rax, rbp
0x180015e8e  cmp     rax, rcx
0x180015e91  jnz     short loc_180015E88
0x180015e93  mov     r9, [rbx+18h]
0x180015e97  test    r9, r9
0x180015e9a  jz      short loc_180015F0B
0x180015e9c  test    esi, esi
0x180015e9e  jz      short loc_180015ED1
0x180015ea0  mov     rcx, r9
0x180015ea3  movzx   eax, word ptr [rbx+20h]
0x180015ea7  lea     rdx, [rax+rax*4]
0x180015eab  shl     rdx, 4
0x180015eaf  add     rdx, r9
0x180015eb2  cmp     r9, rdx
0x180015eb5  jz      short loc_180015ED1
0x180015eb7  mov     r8d, [rbx+10h]
0x180015ebb  cmp     [rcx+4], r8d
0x180015ebf  jbe     short loc_180015EC9
0x180015ec1  mov     eax, [rdi+8]
0x180015ec4  cmp     [rcx+8], eax
0x180015ec7  jz      short loc_180015F0B
0x180015ec9  add     rcx, rbp
0x180015ecc  cmp     rcx, rdx
0x180015ecf  jnz     short loc_180015EBB
0x180015ed1  movzx   eax, word ptr [rbx+22h]
0x180015ed5  inc     eax
0x180015ed7  movzx   ecx, word ptr [rbx+20h]
0x180015edb  xor     edx, edx
0x180015edd  div     ecx
0x180015edf  mov     [rbx+22h], dx
0x180015ee3  mov     rax, [rbx+8]
0x180015ee7  mov     r8d, 1
0x180015eed  lock xadd [rax], r8d
0x180015ef2  inc     r8d; unsigned int
0x180015ef5  movzx   eax, dx
0x180015ef8  lea     rcx, [rax+rax*4]
0x180015efc  shl     rcx, 4
0x180015f00  add     rcx, r9; this
0x180015f03  mov     rdx, rdi; struct wil::FailureInfo *
0x180015f06  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180015f0b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180015f15  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180015f1c  add     rsp, 20h
0x180015f20  pop     r14
0x180015f22  pop     rdi
0x180015f23  pop     rsi
0x180015f24  pop     rbp
0x180015f25  pop     rbx
0x180015f26  retn
```
