# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004120`
- end: `0x140004327`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140004120`
- `0x14000481c`
- `0x140004900`
- `0x140005178`
- `0x1400054e0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000414a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000420c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000414a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000420c`

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
0x140004120  push    rbx
0x140004122  push    rbp
0x140004123  push    rsi
0x140004124  push    rdi
0x140004125  push    r14
0x140004127  sub     rsp, 20h
0x14000412b  mov     r14, r8
0x14000412e  mov     rsi, rdx
0x140004131  mov     rdi, rcx
0x140004134  mov     byte ptr [rdx], 0
0x140004137  xor     bpl, bpl
0x14000413a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004141  test    rbx, rbx
0x140004144  jz      loc_1400041E0
0x14000414a  call    cs:__imp_GetCurrentThreadId
0x140004150  mov     r9d, eax
0x140004153  mov     r8d, eax
0x140004156  shr     r8, 2
0x14000415a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004164  mul     r8
0x140004167  shr     rdx, 3
0x14000416b  lea     rcx, [rdx+rdx*4]
0x14000416f  add     rcx, rcx
0x140004172  sub     r8, rcx
0x140004175  mov     rbx, [rbx+r8*8]
0x140004179  jmp     short loc_140004184
0x14000417b  cmp     [rbx], r9d
0x14000417e  jz      short loc_1400041FB
0x140004180  mov     rbx, [rbx+8]
0x140004184  test    rbx, rbx
0x140004187  jnz     short loc_14000417B
0x140004189  test    rbx, rbx
0x14000418c  jz      short loc_1400041E0
0x14000418e  cmp     qword ptr [rbx], 0
0x140004192  jz      short loc_1400041E0
0x140004194  mov     [rsi], bpl
0x140004197  mov     r9, r14; unsigned __int64
0x14000419a  mov     r8, rsi; char *
0x14000419d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400041a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400041a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400041a8  test    al, al
0x1400041aa  jz      short loc_1400041B0
0x1400041ac  mov     [rdi+48h], rsi
0x1400041b0  mov     rbx, [rbx]
0x1400041b3  mov     al, [rbx+28h]
0x1400041b6  mov     byte ptr [rbx+28h], 1
0x1400041ba  test    al, al
0x1400041bc  jnz     short loc_1400041D7
0x1400041be  mov     rcx, [rbx+8]
0x1400041c2  mov     rax, [rcx]
0x1400041c5  mov     rdx, rdi
0x1400041c8  mov     rax, [rax]
0x1400041cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041d0  or      bpl, al
0x1400041d3  mov     byte ptr [rbx+28h], 0
0x1400041d7  mov     rbx, [rbx+10h]
0x1400041db  test    rbx, rbx
0x1400041de  jnz     short loc_1400041B3
0x1400041e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400041e7  test    rax, rax
0x1400041ea  jz      short loc_14000420C
0x1400041ec  test    bpl, bpl
0x1400041ef  jnz     short loc_140004201
0x1400041f1  test    byte ptr [rdi+4], 2
0x1400041f5  jnz     short loc_140004201
0x1400041f7  xor     ecx, ecx
0x1400041f9  jmp     short loc_140004203
0x1400041fb  add     rbx, 10h
0x1400041ff  jmp     short loc_140004189
0x140004201  mov     cl, 1
0x140004203  mov     rdx, rdi
0x140004206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000420b  nop
0x14000420c  call    cs:__imp_GetCurrentThreadId
0x140004212  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004218  cmp     ecx, eax
0x14000421a  jz      loc_14000431C
0x140004220  mov     ecx, 1
0x140004225  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000422d  inc     ecx; this
0x14000422f  cmp     ecx, 4
0x140004232  jge     loc_140004315
0x140004238  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000423e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004243  mov     rbx, rax
0x140004246  test    rax, rax
0x140004249  jz      loc_14000430B
0x14000424f  mov     esi, [rax+10h]
0x140004252  mov     ebp, 50h ; 'P'
0x140004257  cmp     qword ptr [rax+18h], 0
0x14000425c  jnz     short loc_140004293
0x14000425e  test    esi, esi
0x140004260  jz      short loc_140004293
0x140004262  mov     edx, 190h; dwBytes
0x140004267  lea     ecx, [rbp-48h]; dwFlags
0x14000426a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000426f  mov     [rbx+18h], rax
0x140004273  test    rax, rax
0x140004276  jz      short loc_140004293
0x140004278  mov     dword ptr [rbx+20h], 5
0x14000427f  lea     rcx, [rax+190h]
0x140004286  jmp     short loc_14000428E
0x140004288  mov     [rax], bp
0x14000428b  add     rax, rbp
0x14000428e  cmp     rax, rcx
0x140004291  jnz     short loc_140004288
0x140004293  mov     r9, [rbx+18h]
0x140004297  test    r9, r9
0x14000429a  jz      short loc_14000430B
0x14000429c  test    esi, esi
0x14000429e  jz      short loc_1400042D1
0x1400042a0  mov     rcx, r9
0x1400042a3  movzx   eax, word ptr [rbx+20h]
0x1400042a7  lea     rdx, [rax+rax*4]
0x1400042ab  shl     rdx, 4
0x1400042af  add     rdx, r9
0x1400042b2  cmp     r9, rdx
0x1400042b5  jz      short loc_1400042D1
0x1400042b7  mov     r8d, [rbx+10h]
0x1400042bb  cmp     [rcx+4], r8d
0x1400042bf  jbe     short loc_1400042C9
0x1400042c1  mov     eax, [rdi+8]
0x1400042c4  cmp     [rcx+8], eax
0x1400042c7  jz      short loc_14000430B
0x1400042c9  add     rcx, rbp
0x1400042cc  cmp     rcx, rdx
0x1400042cf  jnz     short loc_1400042BB
0x1400042d1  movzx   eax, word ptr [rbx+22h]
0x1400042d5  inc     eax
0x1400042d7  movzx   ecx, word ptr [rbx+20h]
0x1400042db  xor     edx, edx
0x1400042dd  div     ecx
0x1400042df  mov     [rbx+22h], dx
0x1400042e3  mov     rax, [rbx+8]
0x1400042e7  mov     r8d, 1
0x1400042ed  lock xadd [rax], r8d
0x1400042f2  inc     r8d; unsigned int
0x1400042f5  movzx   eax, dx
0x1400042f8  lea     rcx, [rax+rax*4]
0x1400042fc  shl     rcx, 4
0x140004300  add     rcx, r9; this
0x140004303  mov     rdx, rdi; struct wil::FailureInfo *
0x140004306  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000430b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004315  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000431c  add     rsp, 20h
0x140004320  pop     r14
0x140004322  pop     rdi
0x140004323  pop     rsi
0x140004324  pop     rbp
0x140004325  pop     rbx
0x140004326  retn
```
