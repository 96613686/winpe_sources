# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005150`
- end: `0x180005357`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005150`
- `0x18000584c`
- `0x180005930`
- `0x18000665c`
- `0x1800078f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000517a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000523c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000517a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000523c`

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
0x180005150  push    rbx
0x180005152  push    rbp
0x180005153  push    rsi
0x180005154  push    rdi
0x180005155  push    r14
0x180005157  sub     rsp, 20h
0x18000515b  mov     r14, r8
0x18000515e  mov     rsi, rdx
0x180005161  mov     rdi, rcx
0x180005164  mov     byte ptr [rdx], 0
0x180005167  xor     bpl, bpl
0x18000516a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005171  test    rbx, rbx
0x180005174  jz      loc_180005210
0x18000517a  call    cs:__imp_GetCurrentThreadId
0x180005180  mov     r9d, eax
0x180005183  mov     r8d, eax
0x180005186  shr     r8, 2
0x18000518a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005194  mul     r8
0x180005197  shr     rdx, 3
0x18000519b  lea     rcx, [rdx+rdx*4]
0x18000519f  add     rcx, rcx
0x1800051a2  sub     r8, rcx
0x1800051a5  mov     rbx, [rbx+r8*8]
0x1800051a9  jmp     short loc_1800051B4
0x1800051ab  cmp     [rbx], r9d
0x1800051ae  jz      short loc_18000522B
0x1800051b0  mov     rbx, [rbx+8]
0x1800051b4  test    rbx, rbx
0x1800051b7  jnz     short loc_1800051AB
0x1800051b9  test    rbx, rbx
0x1800051bc  jz      short loc_180005210
0x1800051be  cmp     qword ptr [rbx], 0
0x1800051c2  jz      short loc_180005210
0x1800051c4  mov     [rsi], bpl
0x1800051c7  mov     r9, r14; unsigned __int64
0x1800051ca  mov     r8, rsi; char *
0x1800051cd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800051d0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800051d3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800051d8  test    al, al
0x1800051da  jz      short loc_1800051E0
0x1800051dc  mov     [rdi+48h], rsi
0x1800051e0  mov     rbx, [rbx]
0x1800051e3  mov     al, [rbx+28h]
0x1800051e6  mov     byte ptr [rbx+28h], 1
0x1800051ea  test    al, al
0x1800051ec  jnz     short loc_180005207
0x1800051ee  mov     rcx, [rbx+8]
0x1800051f2  mov     rax, [rcx]
0x1800051f5  mov     rdx, rdi
0x1800051f8  mov     rax, [rax]
0x1800051fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005200  or      bpl, al
0x180005203  mov     byte ptr [rbx+28h], 0
0x180005207  mov     rbx, [rbx+10h]
0x18000520b  test    rbx, rbx
0x18000520e  jnz     short loc_1800051E3
0x180005210  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005217  test    rax, rax
0x18000521a  jz      short loc_18000523C
0x18000521c  test    bpl, bpl
0x18000521f  jnz     short loc_180005231
0x180005221  test    byte ptr [rdi+4], 2
0x180005225  jnz     short loc_180005231
0x180005227  xor     ecx, ecx
0x180005229  jmp     short loc_180005233
0x18000522b  add     rbx, 10h
0x18000522f  jmp     short loc_1800051B9
0x180005231  mov     cl, 1
0x180005233  mov     rdx, rdi
0x180005236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523b  nop
0x18000523c  call    cs:__imp_GetCurrentThreadId
0x180005242  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005248  cmp     ecx, eax
0x18000524a  jz      loc_18000534C
0x180005250  mov     ecx, 1
0x180005255  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000525d  inc     ecx; this
0x18000525f  cmp     ecx, 4
0x180005262  jge     loc_180005345
0x180005268  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000526e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005273  mov     rbx, rax
0x180005276  test    rax, rax
0x180005279  jz      loc_18000533B
0x18000527f  mov     esi, [rax+10h]
0x180005282  mov     ebp, 50h ; 'P'
0x180005287  cmp     qword ptr [rax+18h], 0
0x18000528c  jnz     short loc_1800052C3
0x18000528e  test    esi, esi
0x180005290  jz      short loc_1800052C3
0x180005292  mov     edx, 190h; dwBytes
0x180005297  lea     ecx, [rbp-48h]; dwFlags
0x18000529a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000529f  mov     [rbx+18h], rax
0x1800052a3  test    rax, rax
0x1800052a6  jz      short loc_1800052C3
0x1800052a8  mov     dword ptr [rbx+20h], 5
0x1800052af  lea     rcx, [rax+190h]
0x1800052b6  jmp     short loc_1800052BE
0x1800052b8  mov     [rax], bp
0x1800052bb  add     rax, rbp
0x1800052be  cmp     rax, rcx
0x1800052c1  jnz     short loc_1800052B8
0x1800052c3  mov     r9, [rbx+18h]
0x1800052c7  test    r9, r9
0x1800052ca  jz      short loc_18000533B
0x1800052cc  test    esi, esi
0x1800052ce  jz      short loc_180005301
0x1800052d0  mov     rcx, r9
0x1800052d3  movzx   eax, word ptr [rbx+20h]
0x1800052d7  lea     rdx, [rax+rax*4]
0x1800052db  shl     rdx, 4
0x1800052df  add     rdx, r9
0x1800052e2  cmp     r9, rdx
0x1800052e5  jz      short loc_180005301
0x1800052e7  mov     r8d, [rbx+10h]
0x1800052eb  cmp     [rcx+4], r8d
0x1800052ef  jbe     short loc_1800052F9
0x1800052f1  mov     eax, [rdi+8]
0x1800052f4  cmp     [rcx+8], eax
0x1800052f7  jz      short loc_18000533B
0x1800052f9  add     rcx, rbp
0x1800052fc  cmp     rcx, rdx
0x1800052ff  jnz     short loc_1800052EB
0x180005301  movzx   eax, word ptr [rbx+22h]
0x180005305  inc     eax
0x180005307  movzx   ecx, word ptr [rbx+20h]
0x18000530b  xor     edx, edx
0x18000530d  div     ecx
0x18000530f  mov     [rbx+22h], dx
0x180005313  mov     rax, [rbx+8]
0x180005317  mov     r8d, 1
0x18000531d  lock xadd [rax], r8d
0x180005322  inc     r8d; unsigned int
0x180005325  movzx   eax, dx
0x180005328  lea     rcx, [rax+rax*4]
0x18000532c  shl     rcx, 4
0x180005330  add     rcx, r9; this
0x180005333  mov     rdx, rdi; struct wil::FailureInfo *
0x180005336  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000533b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005345  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000534c  add     rsp, 20h
0x180005350  pop     r14
0x180005352  pop     rdi
0x180005353  pop     rsi
0x180005354  pop     rbp
0x180005355  pop     rbx
0x180005356  retn
```
