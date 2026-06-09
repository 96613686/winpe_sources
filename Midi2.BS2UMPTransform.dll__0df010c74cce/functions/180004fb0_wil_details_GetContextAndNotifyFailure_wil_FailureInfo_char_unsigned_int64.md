# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004fb0`
- end: `0x1800051b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004fb0`
- `0x1800056ac`
- `0x180005790`
- `0x1800064bc`
- `0x180007740`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000509c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000509c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180004fb0  push    rbx
0x180004fb2  push    rbp
0x180004fb3  push    rsi
0x180004fb4  push    rdi
0x180004fb5  push    r14
0x180004fb7  sub     rsp, 20h
0x180004fbb  mov     r14, r8
0x180004fbe  mov     rsi, rdx
0x180004fc1  mov     rdi, rcx
0x180004fc4  mov     byte ptr [rdx], 0
0x180004fc7  xor     bpl, bpl
0x180004fca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004fd1  test    rbx, rbx
0x180004fd4  jz      loc_180005070
0x180004fda  call    cs:__imp_GetCurrentThreadId
0x180004fe0  mov     r9d, eax
0x180004fe3  mov     r8d, eax
0x180004fe6  shr     r8, 2
0x180004fea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004ff4  mul     r8
0x180004ff7  shr     rdx, 3
0x180004ffb  lea     rcx, [rdx+rdx*4]
0x180004fff  add     rcx, rcx
0x180005002  sub     r8, rcx
0x180005005  mov     rbx, [rbx+r8*8]
0x180005009  jmp     short loc_180005014
0x18000500b  cmp     [rbx], r9d
0x18000500e  jz      short loc_18000508B
0x180005010  mov     rbx, [rbx+8]
0x180005014  test    rbx, rbx
0x180005017  jnz     short loc_18000500B
0x180005019  test    rbx, rbx
0x18000501c  jz      short loc_180005070
0x18000501e  cmp     qword ptr [rbx], 0
0x180005022  jz      short loc_180005070
0x180005024  mov     [rsi], bpl
0x180005027  mov     r9, r14; unsigned __int64
0x18000502a  mov     r8, rsi; char *
0x18000502d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005030  mov     rcx, rdi; struct wil::FailureInfo *
0x180005033  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005038  test    al, al
0x18000503a  jz      short loc_180005040
0x18000503c  mov     [rdi+48h], rsi
0x180005040  mov     rbx, [rbx]
0x180005043  mov     al, [rbx+28h]
0x180005046  mov     byte ptr [rbx+28h], 1
0x18000504a  test    al, al
0x18000504c  jnz     short loc_180005067
0x18000504e  mov     rcx, [rbx+8]
0x180005052  mov     rax, [rcx]
0x180005055  mov     rdx, rdi
0x180005058  mov     rax, [rax]
0x18000505b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005060  or      bpl, al
0x180005063  mov     byte ptr [rbx+28h], 0
0x180005067  mov     rbx, [rbx+10h]
0x18000506b  test    rbx, rbx
0x18000506e  jnz     short loc_180005043
0x180005070  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005077  test    rax, rax
0x18000507a  jz      short loc_18000509C
0x18000507c  test    bpl, bpl
0x18000507f  jnz     short loc_180005091
0x180005081  test    byte ptr [rdi+4], 2
0x180005085  jnz     short loc_180005091
0x180005087  xor     ecx, ecx
0x180005089  jmp     short loc_180005093
0x18000508b  add     rbx, 10h
0x18000508f  jmp     short loc_180005019
0x180005091  mov     cl, 1
0x180005093  mov     rdx, rdi
0x180005096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000509b  nop
0x18000509c  call    cs:__imp_GetCurrentThreadId
0x1800050a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800050a8  cmp     ecx, eax
0x1800050aa  jz      loc_1800051AC
0x1800050b0  mov     ecx, 1
0x1800050b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800050bd  inc     ecx; this
0x1800050bf  cmp     ecx, 4
0x1800050c2  jge     loc_1800051A5
0x1800050c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800050ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800050d3  mov     rbx, rax
0x1800050d6  test    rax, rax
0x1800050d9  jz      loc_18000519B
0x1800050df  mov     esi, [rax+10h]
0x1800050e2  mov     ebp, 50h ; 'P'
0x1800050e7  cmp     qword ptr [rax+18h], 0
0x1800050ec  jnz     short loc_180005123
0x1800050ee  test    esi, esi
0x1800050f0  jz      short loc_180005123
0x1800050f2  mov     edx, 190h; dwBytes
0x1800050f7  lea     ecx, [rbp-48h]; dwFlags
0x1800050fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800050ff  mov     [rbx+18h], rax
0x180005103  test    rax, rax
0x180005106  jz      short loc_180005123
0x180005108  mov     dword ptr [rbx+20h], 5
0x18000510f  lea     rcx, [rax+190h]
0x180005116  jmp     short loc_18000511E
0x180005118  mov     [rax], bp
0x18000511b  add     rax, rbp
0x18000511e  cmp     rax, rcx
0x180005121  jnz     short loc_180005118
0x180005123  mov     r9, [rbx+18h]
0x180005127  test    r9, r9
0x18000512a  jz      short loc_18000519B
0x18000512c  test    esi, esi
0x18000512e  jz      short loc_180005161
0x180005130  mov     rcx, r9
0x180005133  movzx   eax, word ptr [rbx+20h]
0x180005137  lea     rdx, [rax+rax*4]
0x18000513b  shl     rdx, 4
0x18000513f  add     rdx, r9
0x180005142  cmp     r9, rdx
0x180005145  jz      short loc_180005161
0x180005147  mov     r8d, [rbx+10h]
0x18000514b  cmp     [rcx+4], r8d
0x18000514f  jbe     short loc_180005159
0x180005151  mov     eax, [rdi+8]
0x180005154  cmp     [rcx+8], eax
0x180005157  jz      short loc_18000519B
0x180005159  add     rcx, rbp
0x18000515c  cmp     rcx, rdx
0x18000515f  jnz     short loc_18000514B
0x180005161  movzx   eax, word ptr [rbx+22h]
0x180005165  inc     eax
0x180005167  movzx   ecx, word ptr [rbx+20h]
0x18000516b  xor     edx, edx
0x18000516d  div     ecx
0x18000516f  mov     [rbx+22h], dx
0x180005173  mov     rax, [rbx+8]
0x180005177  mov     r8d, 1
0x18000517d  lock xadd [rax], r8d
0x180005182  inc     r8d; unsigned int
0x180005185  movzx   eax, dx
0x180005188  lea     rcx, [rax+rax*4]
0x18000518c  shl     rcx, 4
0x180005190  add     rcx, r9; this
0x180005193  mov     rdx, rdi; struct wil::FailureInfo *
0x180005196  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000519b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800051a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800051ac  add     rsp, 20h
0x1800051b0  pop     r14
0x1800051b2  pop     rdi
0x1800051b3  pop     rsi
0x1800051b4  pop     rbp
0x1800051b5  pop     rbx
0x1800051b6  retn
```
