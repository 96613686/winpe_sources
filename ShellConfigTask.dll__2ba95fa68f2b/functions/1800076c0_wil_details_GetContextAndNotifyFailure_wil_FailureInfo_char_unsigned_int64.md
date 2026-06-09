# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800076c0`
- end: `0x1800078c7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800076c0`
- `0x180007e10`
- `0x180007ef4`
- `0x18000882c`
- `0x18000ac04`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077ac`

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
0x1800076c0  push    rbx
0x1800076c2  push    rbp
0x1800076c3  push    rsi
0x1800076c4  push    rdi
0x1800076c5  push    r14
0x1800076c7  sub     rsp, 20h
0x1800076cb  mov     r14, r8
0x1800076ce  mov     rsi, rdx
0x1800076d1  mov     rdi, rcx
0x1800076d4  mov     byte ptr [rdx], 0
0x1800076d7  xor     bpl, bpl
0x1800076da  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800076e1  test    rbx, rbx
0x1800076e4  jz      loc_180007780
0x1800076ea  call    cs:__imp_GetCurrentThreadId
0x1800076f0  mov     r9d, eax
0x1800076f3  mov     r8d, eax
0x1800076f6  shr     r8, 2
0x1800076fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007704  mul     r8
0x180007707  shr     rdx, 3
0x18000770b  lea     rcx, [rdx+rdx*4]
0x18000770f  add     rcx, rcx
0x180007712  sub     r8, rcx
0x180007715  mov     rbx, [rbx+r8*8]
0x180007719  jmp     short loc_180007724
0x18000771b  cmp     [rbx], r9d
0x18000771e  jz      short loc_18000779B
0x180007720  mov     rbx, [rbx+8]
0x180007724  test    rbx, rbx
0x180007727  jnz     short loc_18000771B
0x180007729  test    rbx, rbx
0x18000772c  jz      short loc_180007780
0x18000772e  cmp     qword ptr [rbx], 0
0x180007732  jz      short loc_180007780
0x180007734  mov     [rsi], bpl
0x180007737  mov     r9, r14; unsigned __int64
0x18000773a  mov     r8, rsi; char *
0x18000773d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007740  mov     rcx, rdi; struct wil::FailureInfo *
0x180007743  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007748  test    al, al
0x18000774a  jz      short loc_180007750
0x18000774c  mov     [rdi+48h], rsi
0x180007750  mov     rbx, [rbx]
0x180007753  mov     al, [rbx+28h]
0x180007756  mov     byte ptr [rbx+28h], 1
0x18000775a  test    al, al
0x18000775c  jnz     short loc_180007777
0x18000775e  mov     rcx, [rbx+8]
0x180007762  mov     rax, [rcx]
0x180007765  mov     rdx, rdi
0x180007768  mov     rax, [rax]
0x18000776b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007770  or      bpl, al
0x180007773  mov     byte ptr [rbx+28h], 0
0x180007777  mov     rbx, [rbx+10h]
0x18000777b  test    rbx, rbx
0x18000777e  jnz     short loc_180007753
0x180007780  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007787  test    rax, rax
0x18000778a  jz      short loc_1800077AC
0x18000778c  test    bpl, bpl
0x18000778f  jnz     short loc_1800077A1
0x180007791  test    byte ptr [rdi+4], 2
0x180007795  jnz     short loc_1800077A1
0x180007797  xor     ecx, ecx
0x180007799  jmp     short loc_1800077A3
0x18000779b  add     rbx, 10h
0x18000779f  jmp     short loc_180007729
0x1800077a1  mov     cl, 1
0x1800077a3  mov     rdx, rdi
0x1800077a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ab  nop
0x1800077ac  call    cs:__imp_GetCurrentThreadId
0x1800077b2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800077b8  cmp     ecx, eax
0x1800077ba  jz      loc_1800078BC
0x1800077c0  mov     ecx, 1
0x1800077c5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800077cd  inc     ecx; this
0x1800077cf  cmp     ecx, 4
0x1800077d2  jge     loc_1800078B5
0x1800077d8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800077de  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800077e3  mov     rbx, rax
0x1800077e6  test    rax, rax
0x1800077e9  jz      loc_1800078AB
0x1800077ef  mov     esi, [rax+10h]
0x1800077f2  mov     ebp, 50h ; 'P'
0x1800077f7  cmp     qword ptr [rax+18h], 0
0x1800077fc  jnz     short loc_180007833
0x1800077fe  test    esi, esi
0x180007800  jz      short loc_180007833
0x180007802  mov     edx, 190h; dwBytes
0x180007807  lea     ecx, [rbp-48h]; dwFlags
0x18000780a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000780f  mov     [rbx+18h], rax
0x180007813  test    rax, rax
0x180007816  jz      short loc_180007833
0x180007818  mov     dword ptr [rbx+20h], 5
0x18000781f  lea     rcx, [rax+190h]
0x180007826  jmp     short loc_18000782E
0x180007828  mov     [rax], bp
0x18000782b  add     rax, rbp
0x18000782e  cmp     rax, rcx
0x180007831  jnz     short loc_180007828
0x180007833  mov     r9, [rbx+18h]
0x180007837  test    r9, r9
0x18000783a  jz      short loc_1800078AB
0x18000783c  test    esi, esi
0x18000783e  jz      short loc_180007871
0x180007840  mov     rcx, r9
0x180007843  movzx   eax, word ptr [rbx+20h]
0x180007847  lea     rdx, [rax+rax*4]
0x18000784b  shl     rdx, 4
0x18000784f  add     rdx, r9
0x180007852  cmp     r9, rdx
0x180007855  jz      short loc_180007871
0x180007857  mov     r8d, [rbx+10h]
0x18000785b  cmp     [rcx+4], r8d
0x18000785f  jbe     short loc_180007869
0x180007861  mov     eax, [rdi+8]
0x180007864  cmp     [rcx+8], eax
0x180007867  jz      short loc_1800078AB
0x180007869  add     rcx, rbp
0x18000786c  cmp     rcx, rdx
0x18000786f  jnz     short loc_18000785B
0x180007871  movzx   eax, word ptr [rbx+22h]
0x180007875  inc     eax
0x180007877  movzx   ecx, word ptr [rbx+20h]
0x18000787b  xor     edx, edx
0x18000787d  div     ecx
0x18000787f  mov     [rbx+22h], dx
0x180007883  mov     rax, [rbx+8]
0x180007887  mov     r8d, 1
0x18000788d  lock xadd [rax], r8d
0x180007892  inc     r8d; unsigned int
0x180007895  movzx   eax, dx
0x180007898  lea     rcx, [rax+rax*4]
0x18000789c  shl     rcx, 4
0x1800078a0  add     rcx, r9; this
0x1800078a3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800078a6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800078ab  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800078b5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800078bc  add     rsp, 20h
0x1800078c0  pop     r14
0x1800078c2  pop     rdi
0x1800078c3  pop     rsi
0x1800078c4  pop     rbp
0x1800078c5  pop     rbx
0x1800078c6  retn
```
