# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800050a0`
- end: `0x1800052a7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800050a0`
- `0x180005800`
- `0x1800058e4`
- `0x18000627c`
- `0x180006968`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000518c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000518c`

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
0x1800050a0  push    rbx
0x1800050a2  push    rbp
0x1800050a3  push    rsi
0x1800050a4  push    rdi
0x1800050a5  push    r14
0x1800050a7  sub     rsp, 20h
0x1800050ab  mov     r14, r8
0x1800050ae  mov     rsi, rdx
0x1800050b1  mov     rdi, rcx
0x1800050b4  mov     byte ptr [rdx], 0
0x1800050b7  xor     bpl, bpl
0x1800050ba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800050c1  test    rbx, rbx
0x1800050c4  jz      loc_180005160
0x1800050ca  call    cs:__imp_GetCurrentThreadId
0x1800050d0  mov     r9d, eax
0x1800050d3  mov     r8d, eax
0x1800050d6  shr     r8, 2
0x1800050da  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800050e4  mul     r8
0x1800050e7  shr     rdx, 3
0x1800050eb  lea     rcx, [rdx+rdx*4]
0x1800050ef  add     rcx, rcx
0x1800050f2  sub     r8, rcx
0x1800050f5  mov     rbx, [rbx+r8*8]
0x1800050f9  jmp     short loc_180005104
0x1800050fb  cmp     [rbx], r9d
0x1800050fe  jz      short loc_18000517B
0x180005100  mov     rbx, [rbx+8]
0x180005104  test    rbx, rbx
0x180005107  jnz     short loc_1800050FB
0x180005109  test    rbx, rbx
0x18000510c  jz      short loc_180005160
0x18000510e  cmp     qword ptr [rbx], 0
0x180005112  jz      short loc_180005160
0x180005114  mov     [rsi], bpl
0x180005117  mov     r9, r14; unsigned __int64
0x18000511a  mov     r8, rsi; char *
0x18000511d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005120  mov     rcx, rdi; struct wil::FailureInfo *
0x180005123  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005128  test    al, al
0x18000512a  jz      short loc_180005130
0x18000512c  mov     [rdi+48h], rsi
0x180005130  mov     rbx, [rbx]
0x180005133  mov     al, [rbx+28h]
0x180005136  mov     byte ptr [rbx+28h], 1
0x18000513a  test    al, al
0x18000513c  jnz     short loc_180005157
0x18000513e  mov     rcx, [rbx+8]
0x180005142  mov     rax, [rcx]
0x180005145  mov     rdx, rdi
0x180005148  mov     rax, [rax]
0x18000514b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005150  or      bpl, al
0x180005153  mov     byte ptr [rbx+28h], 0
0x180005157  mov     rbx, [rbx+10h]
0x18000515b  test    rbx, rbx
0x18000515e  jnz     short loc_180005133
0x180005160  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005167  test    rax, rax
0x18000516a  jz      short loc_18000518C
0x18000516c  test    bpl, bpl
0x18000516f  jnz     short loc_180005181
0x180005171  test    byte ptr [rdi+4], 2
0x180005175  jnz     short loc_180005181
0x180005177  xor     ecx, ecx
0x180005179  jmp     short loc_180005183
0x18000517b  add     rbx, 10h
0x18000517f  jmp     short loc_180005109
0x180005181  mov     cl, 1
0x180005183  mov     rdx, rdi
0x180005186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518b  nop
0x18000518c  call    cs:__imp_GetCurrentThreadId
0x180005192  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005198  cmp     ecx, eax
0x18000519a  jz      loc_18000529C
0x1800051a0  mov     ecx, 1
0x1800051a5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800051ad  inc     ecx; this
0x1800051af  cmp     ecx, 4
0x1800051b2  jge     loc_180005295
0x1800051b8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800051be  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800051c3  mov     rbx, rax
0x1800051c6  test    rax, rax
0x1800051c9  jz      loc_18000528B
0x1800051cf  mov     esi, [rax+10h]
0x1800051d2  mov     ebp, 50h ; 'P'
0x1800051d7  cmp     qword ptr [rax+18h], 0
0x1800051dc  jnz     short loc_180005213
0x1800051de  test    esi, esi
0x1800051e0  jz      short loc_180005213
0x1800051e2  mov     edx, 190h; dwBytes
0x1800051e7  lea     ecx, [rbp-48h]; dwFlags
0x1800051ea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800051ef  mov     [rbx+18h], rax
0x1800051f3  test    rax, rax
0x1800051f6  jz      short loc_180005213
0x1800051f8  mov     dword ptr [rbx+20h], 5
0x1800051ff  lea     rcx, [rax+190h]
0x180005206  jmp     short loc_18000520E
0x180005208  mov     [rax], bp
0x18000520b  add     rax, rbp
0x18000520e  cmp     rax, rcx
0x180005211  jnz     short loc_180005208
0x180005213  mov     r9, [rbx+18h]
0x180005217  test    r9, r9
0x18000521a  jz      short loc_18000528B
0x18000521c  test    esi, esi
0x18000521e  jz      short loc_180005251
0x180005220  mov     rcx, r9
0x180005223  movzx   eax, word ptr [rbx+20h]
0x180005227  lea     rdx, [rax+rax*4]
0x18000522b  shl     rdx, 4
0x18000522f  add     rdx, r9
0x180005232  cmp     r9, rdx
0x180005235  jz      short loc_180005251
0x180005237  mov     r8d, [rbx+10h]
0x18000523b  cmp     [rcx+4], r8d
0x18000523f  jbe     short loc_180005249
0x180005241  mov     eax, [rdi+8]
0x180005244  cmp     [rcx+8], eax
0x180005247  jz      short loc_18000528B
0x180005249  add     rcx, rbp
0x18000524c  cmp     rcx, rdx
0x18000524f  jnz     short loc_18000523B
0x180005251  movzx   eax, word ptr [rbx+22h]
0x180005255  inc     eax
0x180005257  movzx   ecx, word ptr [rbx+20h]
0x18000525b  xor     edx, edx
0x18000525d  div     ecx
0x18000525f  mov     [rbx+22h], dx
0x180005263  mov     rax, [rbx+8]
0x180005267  mov     r8d, 1
0x18000526d  lock xadd [rax], r8d
0x180005272  inc     r8d; unsigned int
0x180005275  movzx   eax, dx
0x180005278  lea     rcx, [rax+rax*4]
0x18000527c  shl     rcx, 4
0x180005280  add     rcx, r9; this
0x180005283  mov     rdx, rdi; struct wil::FailureInfo *
0x180005286  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000528b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005295  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000529c  add     rsp, 20h
0x1800052a0  pop     r14
0x1800052a2  pop     rdi
0x1800052a3  pop     rsi
0x1800052a4  pop     rbp
0x1800052a5  pop     rbx
0x1800052a6  retn
```
