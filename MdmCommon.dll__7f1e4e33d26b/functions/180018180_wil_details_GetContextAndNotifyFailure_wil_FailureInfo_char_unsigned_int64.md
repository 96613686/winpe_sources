# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180018180`
- end: `0x180018387`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180018180`
- `0x1800185c0`
- `0x1800186a4`
- `0x1800189d8`
- `0x180018e60`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800181aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001826c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800181aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001826c`

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
0x180018180  push    rbx
0x180018182  push    rbp
0x180018183  push    rsi
0x180018184  push    rdi
0x180018185  push    r14
0x180018187  sub     rsp, 20h
0x18001818b  mov     r14, r8
0x18001818e  mov     rsi, rdx
0x180018191  mov     rdi, rcx
0x180018194  mov     byte ptr [rdx], 0
0x180018197  xor     bpl, bpl
0x18001819a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800181a1  test    rbx, rbx
0x1800181a4  jz      loc_180018240
0x1800181aa  call    cs:__imp_GetCurrentThreadId
0x1800181b0  mov     r9d, eax
0x1800181b3  mov     r8d, eax
0x1800181b6  shr     r8, 2
0x1800181ba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800181c4  mul     r8
0x1800181c7  shr     rdx, 3
0x1800181cb  lea     rcx, [rdx+rdx*4]
0x1800181cf  add     rcx, rcx
0x1800181d2  sub     r8, rcx
0x1800181d5  mov     rbx, [rbx+r8*8]
0x1800181d9  jmp     short loc_1800181E4
0x1800181db  cmp     [rbx], r9d
0x1800181de  jz      short loc_18001825B
0x1800181e0  mov     rbx, [rbx+8]
0x1800181e4  test    rbx, rbx
0x1800181e7  jnz     short loc_1800181DB
0x1800181e9  test    rbx, rbx
0x1800181ec  jz      short loc_180018240
0x1800181ee  cmp     qword ptr [rbx], 0
0x1800181f2  jz      short loc_180018240
0x1800181f4  mov     [rsi], bpl
0x1800181f7  mov     r9, r14; unsigned __int64
0x1800181fa  mov     r8, rsi; char *
0x1800181fd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180018200  mov     rcx, rdi; struct wil::FailureInfo *
0x180018203  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180018208  test    al, al
0x18001820a  jz      short loc_180018210
0x18001820c  mov     [rdi+48h], rsi
0x180018210  mov     rbx, [rbx]
0x180018213  mov     al, [rbx+28h]
0x180018216  mov     byte ptr [rbx+28h], 1
0x18001821a  test    al, al
0x18001821c  jnz     short loc_180018237
0x18001821e  mov     rcx, [rbx+8]
0x180018222  mov     rax, [rcx]
0x180018225  mov     rdx, rdi
0x180018228  mov     rax, [rax]
0x18001822b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018230  or      bpl, al
0x180018233  mov     byte ptr [rbx+28h], 0
0x180018237  mov     rbx, [rbx+10h]
0x18001823b  test    rbx, rbx
0x18001823e  jnz     short loc_180018213
0x180018240  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180018247  test    rax, rax
0x18001824a  jz      short loc_18001826C
0x18001824c  test    bpl, bpl
0x18001824f  jnz     short loc_180018261
0x180018251  test    byte ptr [rdi+4], 2
0x180018255  jnz     short loc_180018261
0x180018257  xor     ecx, ecx
0x180018259  jmp     short loc_180018263
0x18001825b  add     rbx, 10h
0x18001825f  jmp     short loc_1800181E9
0x180018261  mov     cl, 1
0x180018263  mov     rdx, rdi
0x180018266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001826b  nop
0x18001826c  call    cs:__imp_GetCurrentThreadId
0x180018272  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180018278  cmp     ecx, eax
0x18001827a  jz      loc_18001837C
0x180018280  mov     ecx, 1
0x180018285  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001828d  inc     ecx; this
0x18001828f  cmp     ecx, 4
0x180018292  jge     loc_180018375
0x180018298  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001829e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800182a3  mov     rbx, rax
0x1800182a6  test    rax, rax
0x1800182a9  jz      loc_18001836B
0x1800182af  mov     esi, [rax+10h]
0x1800182b2  mov     ebp, 50h ; 'P'
0x1800182b7  cmp     qword ptr [rax+18h], 0
0x1800182bc  jnz     short loc_1800182F3
0x1800182be  test    esi, esi
0x1800182c0  jz      short loc_1800182F3
0x1800182c2  mov     edx, 190h; dwBytes
0x1800182c7  lea     ecx, [rbp-48h]; dwFlags
0x1800182ca  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800182cf  mov     [rbx+18h], rax
0x1800182d3  test    rax, rax
0x1800182d6  jz      short loc_1800182F3
0x1800182d8  mov     dword ptr [rbx+20h], 5
0x1800182df  lea     rcx, [rax+190h]
0x1800182e6  jmp     short loc_1800182EE
0x1800182e8  mov     [rax], bp
0x1800182eb  add     rax, rbp
0x1800182ee  cmp     rax, rcx
0x1800182f1  jnz     short loc_1800182E8
0x1800182f3  mov     r9, [rbx+18h]
0x1800182f7  test    r9, r9
0x1800182fa  jz      short loc_18001836B
0x1800182fc  test    esi, esi
0x1800182fe  jz      short loc_180018331
0x180018300  mov     rcx, r9
0x180018303  movzx   eax, word ptr [rbx+20h]
0x180018307  lea     rdx, [rax+rax*4]
0x18001830b  shl     rdx, 4
0x18001830f  add     rdx, r9
0x180018312  cmp     r9, rdx
0x180018315  jz      short loc_180018331
0x180018317  mov     r8d, [rbx+10h]
0x18001831b  cmp     [rcx+4], r8d
0x18001831f  jbe     short loc_180018329
0x180018321  mov     eax, [rdi+8]
0x180018324  cmp     [rcx+8], eax
0x180018327  jz      short loc_18001836B
0x180018329  add     rcx, rbp
0x18001832c  cmp     rcx, rdx
0x18001832f  jnz     short loc_18001831B
0x180018331  movzx   eax, word ptr [rbx+22h]
0x180018335  inc     eax
0x180018337  movzx   ecx, word ptr [rbx+20h]
0x18001833b  xor     edx, edx
0x18001833d  div     ecx
0x18001833f  mov     [rbx+22h], dx
0x180018343  mov     rax, [rbx+8]
0x180018347  mov     r8d, 1
0x18001834d  lock xadd [rax], r8d
0x180018352  inc     r8d; unsigned int
0x180018355  movzx   eax, dx
0x180018358  lea     rcx, [rax+rax*4]
0x18001835c  shl     rcx, 4
0x180018360  add     rcx, r9; this
0x180018363  mov     rdx, rdi; struct wil::FailureInfo *
0x180018366  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001836b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180018375  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001837c  add     rsp, 20h
0x180018380  pop     r14
0x180018382  pop     rdi
0x180018383  pop     rsi
0x180018384  pop     rbp
0x180018385  pop     rbx
0x180018386  retn
```
