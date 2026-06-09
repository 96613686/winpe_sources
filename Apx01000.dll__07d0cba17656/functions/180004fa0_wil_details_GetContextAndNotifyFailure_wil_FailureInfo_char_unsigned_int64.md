# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004fa0`
- end: `0x1800051a7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004fa0`
- `0x18000569c`
- `0x180005780`
- `0x1800061f8`
- `0x1800078b4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000508c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000508c`

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
0x180004fa0  push    rbx
0x180004fa2  push    rbp
0x180004fa3  push    rsi
0x180004fa4  push    rdi
0x180004fa5  push    r14
0x180004fa7  sub     rsp, 20h
0x180004fab  mov     r14, r8
0x180004fae  mov     rsi, rdx
0x180004fb1  mov     rdi, rcx
0x180004fb4  mov     byte ptr [rdx], 0
0x180004fb7  xor     bpl, bpl
0x180004fba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004fc1  test    rbx, rbx
0x180004fc4  jz      loc_180005060
0x180004fca  call    cs:__imp_GetCurrentThreadId
0x180004fd0  mov     r9d, eax
0x180004fd3  mov     r8d, eax
0x180004fd6  shr     r8, 2
0x180004fda  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004fe4  mul     r8
0x180004fe7  shr     rdx, 3
0x180004feb  lea     rcx, [rdx+rdx*4]
0x180004fef  add     rcx, rcx
0x180004ff2  sub     r8, rcx
0x180004ff5  mov     rbx, [rbx+r8*8]
0x180004ff9  jmp     short loc_180005004
0x180004ffb  cmp     [rbx], r9d
0x180004ffe  jz      short loc_18000507B
0x180005000  mov     rbx, [rbx+8]
0x180005004  test    rbx, rbx
0x180005007  jnz     short loc_180004FFB
0x180005009  test    rbx, rbx
0x18000500c  jz      short loc_180005060
0x18000500e  cmp     qword ptr [rbx], 0
0x180005012  jz      short loc_180005060
0x180005014  mov     [rsi], bpl
0x180005017  mov     r9, r14; unsigned __int64
0x18000501a  mov     r8, rsi; char *
0x18000501d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005020  mov     rcx, rdi; struct wil::FailureInfo *
0x180005023  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005028  test    al, al
0x18000502a  jz      short loc_180005030
0x18000502c  mov     [rdi+48h], rsi
0x180005030  mov     rbx, [rbx]
0x180005033  mov     al, [rbx+28h]
0x180005036  mov     byte ptr [rbx+28h], 1
0x18000503a  test    al, al
0x18000503c  jnz     short loc_180005057
0x18000503e  mov     rcx, [rbx+8]
0x180005042  mov     rax, [rcx]
0x180005045  mov     rdx, rdi
0x180005048  mov     rax, [rax]
0x18000504b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005050  or      bpl, al
0x180005053  mov     byte ptr [rbx+28h], 0
0x180005057  mov     rbx, [rbx+10h]
0x18000505b  test    rbx, rbx
0x18000505e  jnz     short loc_180005033
0x180005060  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005067  test    rax, rax
0x18000506a  jz      short loc_18000508C
0x18000506c  test    bpl, bpl
0x18000506f  jnz     short loc_180005081
0x180005071  test    byte ptr [rdi+4], 2
0x180005075  jnz     short loc_180005081
0x180005077  xor     ecx, ecx
0x180005079  jmp     short loc_180005083
0x18000507b  add     rbx, 10h
0x18000507f  jmp     short loc_180005009
0x180005081  mov     cl, 1
0x180005083  mov     rdx, rdi
0x180005086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000508b  nop
0x18000508c  call    cs:__imp_GetCurrentThreadId
0x180005092  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005098  cmp     ecx, eax
0x18000509a  jz      loc_18000519C
0x1800050a0  mov     ecx, 1
0x1800050a5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800050ad  inc     ecx; this
0x1800050af  cmp     ecx, 4
0x1800050b2  jge     loc_180005195
0x1800050b8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800050be  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800050c3  mov     rbx, rax
0x1800050c6  test    rax, rax
0x1800050c9  jz      loc_18000518B
0x1800050cf  mov     esi, [rax+10h]
0x1800050d2  mov     ebp, 50h ; 'P'
0x1800050d7  cmp     qword ptr [rax+18h], 0
0x1800050dc  jnz     short loc_180005113
0x1800050de  test    esi, esi
0x1800050e0  jz      short loc_180005113
0x1800050e2  mov     edx, 190h; dwBytes
0x1800050e7  lea     ecx, [rbp-48h]; dwFlags
0x1800050ea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800050ef  mov     [rbx+18h], rax
0x1800050f3  test    rax, rax
0x1800050f6  jz      short loc_180005113
0x1800050f8  mov     dword ptr [rbx+20h], 5
0x1800050ff  lea     rcx, [rax+190h]
0x180005106  jmp     short loc_18000510E
0x180005108  mov     [rax], bp
0x18000510b  add     rax, rbp
0x18000510e  cmp     rax, rcx
0x180005111  jnz     short loc_180005108
0x180005113  mov     r9, [rbx+18h]
0x180005117  test    r9, r9
0x18000511a  jz      short loc_18000518B
0x18000511c  test    esi, esi
0x18000511e  jz      short loc_180005151
0x180005120  mov     rcx, r9
0x180005123  movzx   eax, word ptr [rbx+20h]
0x180005127  lea     rdx, [rax+rax*4]
0x18000512b  shl     rdx, 4
0x18000512f  add     rdx, r9
0x180005132  cmp     r9, rdx
0x180005135  jz      short loc_180005151
0x180005137  mov     r8d, [rbx+10h]
0x18000513b  cmp     [rcx+4], r8d
0x18000513f  jbe     short loc_180005149
0x180005141  mov     eax, [rdi+8]
0x180005144  cmp     [rcx+8], eax
0x180005147  jz      short loc_18000518B
0x180005149  add     rcx, rbp
0x18000514c  cmp     rcx, rdx
0x18000514f  jnz     short loc_18000513B
0x180005151  movzx   eax, word ptr [rbx+22h]
0x180005155  inc     eax
0x180005157  movzx   ecx, word ptr [rbx+20h]
0x18000515b  xor     edx, edx
0x18000515d  div     ecx
0x18000515f  mov     [rbx+22h], dx
0x180005163  mov     rax, [rbx+8]
0x180005167  mov     r8d, 1
0x18000516d  lock xadd [rax], r8d
0x180005172  inc     r8d; unsigned int
0x180005175  movzx   eax, dx
0x180005178  lea     rcx, [rax+rax*4]
0x18000517c  shl     rcx, 4
0x180005180  add     rcx, r9; this
0x180005183  mov     rdx, rdi; struct wil::FailureInfo *
0x180005186  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000518b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005195  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000519c  add     rsp, 20h
0x1800051a0  pop     r14
0x1800051a2  pop     rdi
0x1800051a3  pop     rsi
0x1800051a4  pop     rbp
0x1800051a5  pop     rbx
0x1800051a6  retn
```
