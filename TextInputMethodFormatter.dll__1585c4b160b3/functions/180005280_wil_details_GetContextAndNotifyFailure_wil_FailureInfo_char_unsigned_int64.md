# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005280`
- end: `0x180005487`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005280`
- `0x180005b70`
- `0x180005c54`
- `0x1800065d8`
- `0x180006b04`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000536c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000536c`

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
0x180005280  push    rbx
0x180005282  push    rbp
0x180005283  push    rsi
0x180005284  push    rdi
0x180005285  push    r14
0x180005287  sub     rsp, 20h
0x18000528b  mov     r14, r8
0x18000528e  mov     rsi, rdx
0x180005291  mov     rdi, rcx
0x180005294  mov     byte ptr [rdx], 0
0x180005297  xor     bpl, bpl
0x18000529a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800052a1  test    rbx, rbx
0x1800052a4  jz      loc_180005340
0x1800052aa  call    cs:__imp_GetCurrentThreadId
0x1800052b0  mov     r9d, eax
0x1800052b3  mov     r8d, eax
0x1800052b6  shr     r8, 2
0x1800052ba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800052c4  mul     r8
0x1800052c7  shr     rdx, 3
0x1800052cb  lea     rcx, [rdx+rdx*4]
0x1800052cf  add     rcx, rcx
0x1800052d2  sub     r8, rcx
0x1800052d5  mov     rbx, [rbx+r8*8]
0x1800052d9  jmp     short loc_1800052E4
0x1800052db  cmp     [rbx], r9d
0x1800052de  jz      short loc_18000535B
0x1800052e0  mov     rbx, [rbx+8]
0x1800052e4  test    rbx, rbx
0x1800052e7  jnz     short loc_1800052DB
0x1800052e9  test    rbx, rbx
0x1800052ec  jz      short loc_180005340
0x1800052ee  cmp     qword ptr [rbx], 0
0x1800052f2  jz      short loc_180005340
0x1800052f4  mov     [rsi], bpl
0x1800052f7  mov     r9, r14; unsigned __int64
0x1800052fa  mov     r8, rsi; char *
0x1800052fd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005300  mov     rcx, rdi; struct wil::FailureInfo *
0x180005303  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005308  test    al, al
0x18000530a  jz      short loc_180005310
0x18000530c  mov     [rdi+48h], rsi
0x180005310  mov     rbx, [rbx]
0x180005313  mov     al, [rbx+28h]
0x180005316  mov     byte ptr [rbx+28h], 1
0x18000531a  test    al, al
0x18000531c  jnz     short loc_180005337
0x18000531e  mov     rcx, [rbx+8]
0x180005322  mov     rax, [rcx]
0x180005325  mov     rdx, rdi
0x180005328  mov     rax, [rax]
0x18000532b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005330  or      bpl, al
0x180005333  mov     byte ptr [rbx+28h], 0
0x180005337  mov     rbx, [rbx+10h]
0x18000533b  test    rbx, rbx
0x18000533e  jnz     short loc_180005313
0x180005340  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005347  test    rax, rax
0x18000534a  jz      short loc_18000536C
0x18000534c  test    bpl, bpl
0x18000534f  jnz     short loc_180005361
0x180005351  test    byte ptr [rdi+4], 2
0x180005355  jnz     short loc_180005361
0x180005357  xor     ecx, ecx
0x180005359  jmp     short loc_180005363
0x18000535b  add     rbx, 10h
0x18000535f  jmp     short loc_1800052E9
0x180005361  mov     cl, 1
0x180005363  mov     rdx, rdi
0x180005366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000536b  nop
0x18000536c  call    cs:__imp_GetCurrentThreadId
0x180005372  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005378  cmp     ecx, eax
0x18000537a  jz      loc_18000547C
0x180005380  mov     ecx, 1
0x180005385  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000538d  inc     ecx; this
0x18000538f  cmp     ecx, 4
0x180005392  jge     loc_180005475
0x180005398  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000539e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800053a3  mov     rbx, rax
0x1800053a6  test    rax, rax
0x1800053a9  jz      loc_18000546B
0x1800053af  mov     esi, [rax+10h]
0x1800053b2  mov     ebp, 50h ; 'P'
0x1800053b7  cmp     qword ptr [rax+18h], 0
0x1800053bc  jnz     short loc_1800053F3
0x1800053be  test    esi, esi
0x1800053c0  jz      short loc_1800053F3
0x1800053c2  mov     edx, 190h; dwBytes
0x1800053c7  lea     ecx, [rbp-48h]; dwFlags
0x1800053ca  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800053cf  mov     [rbx+18h], rax
0x1800053d3  test    rax, rax
0x1800053d6  jz      short loc_1800053F3
0x1800053d8  mov     dword ptr [rbx+20h], 5
0x1800053df  lea     rcx, [rax+190h]
0x1800053e6  jmp     short loc_1800053EE
0x1800053e8  mov     [rax], bp
0x1800053eb  add     rax, rbp
0x1800053ee  cmp     rax, rcx
0x1800053f1  jnz     short loc_1800053E8
0x1800053f3  mov     r9, [rbx+18h]
0x1800053f7  test    r9, r9
0x1800053fa  jz      short loc_18000546B
0x1800053fc  test    esi, esi
0x1800053fe  jz      short loc_180005431
0x180005400  mov     rcx, r9
0x180005403  movzx   eax, word ptr [rbx+20h]
0x180005407  lea     rdx, [rax+rax*4]
0x18000540b  shl     rdx, 4
0x18000540f  add     rdx, r9
0x180005412  cmp     r9, rdx
0x180005415  jz      short loc_180005431
0x180005417  mov     r8d, [rbx+10h]
0x18000541b  cmp     [rcx+4], r8d
0x18000541f  jbe     short loc_180005429
0x180005421  mov     eax, [rdi+8]
0x180005424  cmp     [rcx+8], eax
0x180005427  jz      short loc_18000546B
0x180005429  add     rcx, rbp
0x18000542c  cmp     rcx, rdx
0x18000542f  jnz     short loc_18000541B
0x180005431  movzx   eax, word ptr [rbx+22h]
0x180005435  inc     eax
0x180005437  movzx   ecx, word ptr [rbx+20h]
0x18000543b  xor     edx, edx
0x18000543d  div     ecx
0x18000543f  mov     [rbx+22h], dx
0x180005443  mov     rax, [rbx+8]
0x180005447  mov     r8d, 1
0x18000544d  lock xadd [rax], r8d
0x180005452  inc     r8d; unsigned int
0x180005455  movzx   eax, dx
0x180005458  lea     rcx, [rax+rax*4]
0x18000545c  shl     rcx, 4
0x180005460  add     rcx, r9; this
0x180005463  mov     rdx, rdi; struct wil::FailureInfo *
0x180005466  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000546b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005475  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000547c  add     rsp, 20h
0x180005480  pop     r14
0x180005482  pop     rdi
0x180005483  pop     rsi
0x180005484  pop     rbp
0x180005485  pop     rbx
0x180005486  retn
```
