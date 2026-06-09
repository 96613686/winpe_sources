# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800060b0`
- end: `0x1800062b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800060b0`
- `0x1800067ac`
- `0x180006890`
- `0x180007358`
- `0x180008d14`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000619c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000619c`

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
0x1800060b0  push    rbx
0x1800060b2  push    rbp
0x1800060b3  push    rsi
0x1800060b4  push    rdi
0x1800060b5  push    r14
0x1800060b7  sub     rsp, 20h
0x1800060bb  mov     r14, r8
0x1800060be  mov     rsi, rdx
0x1800060c1  mov     rdi, rcx
0x1800060c4  mov     byte ptr [rdx], 0
0x1800060c7  xor     bpl, bpl
0x1800060ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800060d1  test    rbx, rbx
0x1800060d4  jz      loc_180006170
0x1800060da  call    cs:__imp_GetCurrentThreadId
0x1800060e0  mov     r9d, eax
0x1800060e3  mov     r8d, eax
0x1800060e6  shr     r8, 2
0x1800060ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800060f4  mul     r8
0x1800060f7  shr     rdx, 3
0x1800060fb  lea     rcx, [rdx+rdx*4]
0x1800060ff  add     rcx, rcx
0x180006102  sub     r8, rcx
0x180006105  mov     rbx, [rbx+r8*8]
0x180006109  jmp     short loc_180006114
0x18000610b  cmp     [rbx], r9d
0x18000610e  jz      short loc_18000618B
0x180006110  mov     rbx, [rbx+8]
0x180006114  test    rbx, rbx
0x180006117  jnz     short loc_18000610B
0x180006119  test    rbx, rbx
0x18000611c  jz      short loc_180006170
0x18000611e  cmp     qword ptr [rbx], 0
0x180006122  jz      short loc_180006170
0x180006124  mov     [rsi], bpl
0x180006127  mov     r9, r14; unsigned __int64
0x18000612a  mov     r8, rsi; char *
0x18000612d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006130  mov     rcx, rdi; struct wil::FailureInfo *
0x180006133  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006138  test    al, al
0x18000613a  jz      short loc_180006140
0x18000613c  mov     [rdi+48h], rsi
0x180006140  mov     rbx, [rbx]
0x180006143  mov     al, [rbx+28h]
0x180006146  mov     byte ptr [rbx+28h], 1
0x18000614a  test    al, al
0x18000614c  jnz     short loc_180006167
0x18000614e  mov     rcx, [rbx+8]
0x180006152  mov     rax, [rcx]
0x180006155  mov     rdx, rdi
0x180006158  mov     rax, [rax]
0x18000615b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006160  or      bpl, al
0x180006163  mov     byte ptr [rbx+28h], 0
0x180006167  mov     rbx, [rbx+10h]
0x18000616b  test    rbx, rbx
0x18000616e  jnz     short loc_180006143
0x180006170  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006177  test    rax, rax
0x18000617a  jz      short loc_18000619C
0x18000617c  test    bpl, bpl
0x18000617f  jnz     short loc_180006191
0x180006181  test    byte ptr [rdi+4], 2
0x180006185  jnz     short loc_180006191
0x180006187  xor     ecx, ecx
0x180006189  jmp     short loc_180006193
0x18000618b  add     rbx, 10h
0x18000618f  jmp     short loc_180006119
0x180006191  mov     cl, 1
0x180006193  mov     rdx, rdi
0x180006196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000619b  nop
0x18000619c  call    cs:__imp_GetCurrentThreadId
0x1800061a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800061a8  cmp     ecx, eax
0x1800061aa  jz      loc_1800062AC
0x1800061b0  mov     ecx, 1
0x1800061b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800061bd  inc     ecx; this
0x1800061bf  cmp     ecx, 4
0x1800061c2  jge     loc_1800062A5
0x1800061c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800061ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800061d3  mov     rbx, rax
0x1800061d6  test    rax, rax
0x1800061d9  jz      loc_18000629B
0x1800061df  mov     esi, [rax+10h]
0x1800061e2  mov     ebp, 50h ; 'P'
0x1800061e7  cmp     qword ptr [rax+18h], 0
0x1800061ec  jnz     short loc_180006223
0x1800061ee  test    esi, esi
0x1800061f0  jz      short loc_180006223
0x1800061f2  mov     edx, 190h; dwBytes
0x1800061f7  lea     ecx, [rbp-48h]; dwFlags
0x1800061fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800061ff  mov     [rbx+18h], rax
0x180006203  test    rax, rax
0x180006206  jz      short loc_180006223
0x180006208  mov     dword ptr [rbx+20h], 5
0x18000620f  lea     rcx, [rax+190h]
0x180006216  jmp     short loc_18000621E
0x180006218  mov     [rax], bp
0x18000621b  add     rax, rbp
0x18000621e  cmp     rax, rcx
0x180006221  jnz     short loc_180006218
0x180006223  mov     r9, [rbx+18h]
0x180006227  test    r9, r9
0x18000622a  jz      short loc_18000629B
0x18000622c  test    esi, esi
0x18000622e  jz      short loc_180006261
0x180006230  mov     rcx, r9
0x180006233  movzx   eax, word ptr [rbx+20h]
0x180006237  lea     rdx, [rax+rax*4]
0x18000623b  shl     rdx, 4
0x18000623f  add     rdx, r9
0x180006242  cmp     r9, rdx
0x180006245  jz      short loc_180006261
0x180006247  mov     r8d, [rbx+10h]
0x18000624b  cmp     [rcx+4], r8d
0x18000624f  jbe     short loc_180006259
0x180006251  mov     eax, [rdi+8]
0x180006254  cmp     [rcx+8], eax
0x180006257  jz      short loc_18000629B
0x180006259  add     rcx, rbp
0x18000625c  cmp     rcx, rdx
0x18000625f  jnz     short loc_18000624B
0x180006261  movzx   eax, word ptr [rbx+22h]
0x180006265  inc     eax
0x180006267  movzx   ecx, word ptr [rbx+20h]
0x18000626b  xor     edx, edx
0x18000626d  div     ecx
0x18000626f  mov     [rbx+22h], dx
0x180006273  mov     rax, [rbx+8]
0x180006277  mov     r8d, 1
0x18000627d  lock xadd [rax], r8d
0x180006282  inc     r8d; unsigned int
0x180006285  movzx   eax, dx
0x180006288  lea     rcx, [rax+rax*4]
0x18000628c  shl     rcx, 4
0x180006290  add     rcx, r9; this
0x180006293  mov     rdx, rdi; struct wil::FailureInfo *
0x180006296  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000629b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800062a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800062ac  add     rsp, 20h
0x1800062b0  pop     r14
0x1800062b2  pop     rdi
0x1800062b3  pop     rsi
0x1800062b4  pop     rbp
0x1800062b5  pop     rbx
0x1800062b6  retn
```
