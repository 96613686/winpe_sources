# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006220`
- end: `0x180006427`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006220`
- `0x18000691c`
- `0x180006a00`
- `0x18000772c`
- `0x1800089b0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000624a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000630c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000624a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000630c`

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
0x180006220  push    rbx
0x180006222  push    rbp
0x180006223  push    rsi
0x180006224  push    rdi
0x180006225  push    r14
0x180006227  sub     rsp, 20h
0x18000622b  mov     r14, r8
0x18000622e  mov     rsi, rdx
0x180006231  mov     rdi, rcx
0x180006234  mov     byte ptr [rdx], 0
0x180006237  xor     bpl, bpl
0x18000623a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006241  test    rbx, rbx
0x180006244  jz      loc_1800062E0
0x18000624a  call    cs:__imp_GetCurrentThreadId
0x180006250  mov     r9d, eax
0x180006253  mov     r8d, eax
0x180006256  shr     r8, 2
0x18000625a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006264  mul     r8
0x180006267  shr     rdx, 3
0x18000626b  lea     rcx, [rdx+rdx*4]
0x18000626f  add     rcx, rcx
0x180006272  sub     r8, rcx
0x180006275  mov     rbx, [rbx+r8*8]
0x180006279  jmp     short loc_180006284
0x18000627b  cmp     [rbx], r9d
0x18000627e  jz      short loc_1800062FB
0x180006280  mov     rbx, [rbx+8]
0x180006284  test    rbx, rbx
0x180006287  jnz     short loc_18000627B
0x180006289  test    rbx, rbx
0x18000628c  jz      short loc_1800062E0
0x18000628e  cmp     qword ptr [rbx], 0
0x180006292  jz      short loc_1800062E0
0x180006294  mov     [rsi], bpl
0x180006297  mov     r9, r14; unsigned __int64
0x18000629a  mov     r8, rsi; char *
0x18000629d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800062a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800062a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800062a8  test    al, al
0x1800062aa  jz      short loc_1800062B0
0x1800062ac  mov     [rdi+48h], rsi
0x1800062b0  mov     rbx, [rbx]
0x1800062b3  mov     al, [rbx+28h]
0x1800062b6  mov     byte ptr [rbx+28h], 1
0x1800062ba  test    al, al
0x1800062bc  jnz     short loc_1800062D7
0x1800062be  mov     rcx, [rbx+8]
0x1800062c2  mov     rax, [rcx]
0x1800062c5  mov     rdx, rdi
0x1800062c8  mov     rax, [rax]
0x1800062cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062d0  or      bpl, al
0x1800062d3  mov     byte ptr [rbx+28h], 0
0x1800062d7  mov     rbx, [rbx+10h]
0x1800062db  test    rbx, rbx
0x1800062de  jnz     short loc_1800062B3
0x1800062e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800062e7  test    rax, rax
0x1800062ea  jz      short loc_18000630C
0x1800062ec  test    bpl, bpl
0x1800062ef  jnz     short loc_180006301
0x1800062f1  test    byte ptr [rdi+4], 2
0x1800062f5  jnz     short loc_180006301
0x1800062f7  xor     ecx, ecx
0x1800062f9  jmp     short loc_180006303
0x1800062fb  add     rbx, 10h
0x1800062ff  jmp     short loc_180006289
0x180006301  mov     cl, 1
0x180006303  mov     rdx, rdi
0x180006306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000630b  nop
0x18000630c  call    cs:__imp_GetCurrentThreadId
0x180006312  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006318  cmp     ecx, eax
0x18000631a  jz      loc_18000641C
0x180006320  mov     ecx, 1
0x180006325  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000632d  inc     ecx; this
0x18000632f  cmp     ecx, 4
0x180006332  jge     loc_180006415
0x180006338  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000633e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006343  mov     rbx, rax
0x180006346  test    rax, rax
0x180006349  jz      loc_18000640B
0x18000634f  mov     esi, [rax+10h]
0x180006352  mov     ebp, 50h ; 'P'
0x180006357  cmp     qword ptr [rax+18h], 0
0x18000635c  jnz     short loc_180006393
0x18000635e  test    esi, esi
0x180006360  jz      short loc_180006393
0x180006362  mov     edx, 190h; dwBytes
0x180006367  lea     ecx, [rbp-48h]; dwFlags
0x18000636a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000636f  mov     [rbx+18h], rax
0x180006373  test    rax, rax
0x180006376  jz      short loc_180006393
0x180006378  mov     dword ptr [rbx+20h], 5
0x18000637f  lea     rcx, [rax+190h]
0x180006386  jmp     short loc_18000638E
0x180006388  mov     [rax], bp
0x18000638b  add     rax, rbp
0x18000638e  cmp     rax, rcx
0x180006391  jnz     short loc_180006388
0x180006393  mov     r9, [rbx+18h]
0x180006397  test    r9, r9
0x18000639a  jz      short loc_18000640B
0x18000639c  test    esi, esi
0x18000639e  jz      short loc_1800063D1
0x1800063a0  mov     rcx, r9
0x1800063a3  movzx   eax, word ptr [rbx+20h]
0x1800063a7  lea     rdx, [rax+rax*4]
0x1800063ab  shl     rdx, 4
0x1800063af  add     rdx, r9
0x1800063b2  cmp     r9, rdx
0x1800063b5  jz      short loc_1800063D1
0x1800063b7  mov     r8d, [rbx+10h]
0x1800063bb  cmp     [rcx+4], r8d
0x1800063bf  jbe     short loc_1800063C9
0x1800063c1  mov     eax, [rdi+8]
0x1800063c4  cmp     [rcx+8], eax
0x1800063c7  jz      short loc_18000640B
0x1800063c9  add     rcx, rbp
0x1800063cc  cmp     rcx, rdx
0x1800063cf  jnz     short loc_1800063BB
0x1800063d1  movzx   eax, word ptr [rbx+22h]
0x1800063d5  inc     eax
0x1800063d7  movzx   ecx, word ptr [rbx+20h]
0x1800063db  xor     edx, edx
0x1800063dd  div     ecx
0x1800063df  mov     [rbx+22h], dx
0x1800063e3  mov     rax, [rbx+8]
0x1800063e7  mov     r8d, 1
0x1800063ed  lock xadd [rax], r8d
0x1800063f2  inc     r8d; unsigned int
0x1800063f5  movzx   eax, dx
0x1800063f8  lea     rcx, [rax+rax*4]
0x1800063fc  shl     rcx, 4
0x180006400  add     rcx, r9; this
0x180006403  mov     rdx, rdi; struct wil::FailureInfo *
0x180006406  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000640b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006415  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000641c  add     rsp, 20h
0x180006420  pop     r14
0x180006422  pop     rdi
0x180006423  pop     rsi
0x180006424  pop     rbp
0x180006425  pop     rbx
0x180006426  retn
```
