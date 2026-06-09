# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004790`
- end: `0x180004997`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004790`
- `0x180004e8c`
- `0x180004f70`
- `0x1800058f8`
- `0x180006ea4`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000487c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000487c`

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
0x180004790  push    rbx
0x180004792  push    rbp
0x180004793  push    rsi
0x180004794  push    rdi
0x180004795  push    r14
0x180004797  sub     rsp, 20h
0x18000479b  mov     r14, r8
0x18000479e  mov     rsi, rdx
0x1800047a1  mov     rdi, rcx
0x1800047a4  mov     byte ptr [rdx], 0
0x1800047a7  xor     bpl, bpl
0x1800047aa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800047b1  test    rbx, rbx
0x1800047b4  jz      loc_180004850
0x1800047ba  call    cs:__imp_GetCurrentThreadId
0x1800047c0  mov     r9d, eax
0x1800047c3  mov     r8d, eax
0x1800047c6  shr     r8, 2
0x1800047ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800047d4  mul     r8
0x1800047d7  shr     rdx, 3
0x1800047db  lea     rcx, [rdx+rdx*4]
0x1800047df  add     rcx, rcx
0x1800047e2  sub     r8, rcx
0x1800047e5  mov     rbx, [rbx+r8*8]
0x1800047e9  jmp     short loc_1800047F4
0x1800047eb  cmp     [rbx], r9d
0x1800047ee  jz      short loc_18000486B
0x1800047f0  mov     rbx, [rbx+8]
0x1800047f4  test    rbx, rbx
0x1800047f7  jnz     short loc_1800047EB
0x1800047f9  test    rbx, rbx
0x1800047fc  jz      short loc_180004850
0x1800047fe  cmp     qword ptr [rbx], 0
0x180004802  jz      short loc_180004850
0x180004804  mov     [rsi], bpl
0x180004807  mov     r9, r14; unsigned __int64
0x18000480a  mov     r8, rsi; char *
0x18000480d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004810  mov     rcx, rdi; struct wil::FailureInfo *
0x180004813  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004818  test    al, al
0x18000481a  jz      short loc_180004820
0x18000481c  mov     [rdi+48h], rsi
0x180004820  mov     rbx, [rbx]
0x180004823  mov     al, [rbx+28h]
0x180004826  mov     byte ptr [rbx+28h], 1
0x18000482a  test    al, al
0x18000482c  jnz     short loc_180004847
0x18000482e  mov     rcx, [rbx+8]
0x180004832  mov     rax, [rcx]
0x180004835  mov     rdx, rdi
0x180004838  mov     rax, [rax]
0x18000483b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004840  or      bpl, al
0x180004843  mov     byte ptr [rbx+28h], 0
0x180004847  mov     rbx, [rbx+10h]
0x18000484b  test    rbx, rbx
0x18000484e  jnz     short loc_180004823
0x180004850  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004857  test    rax, rax
0x18000485a  jz      short loc_18000487C
0x18000485c  test    bpl, bpl
0x18000485f  jnz     short loc_180004871
0x180004861  test    byte ptr [rdi+4], 2
0x180004865  jnz     short loc_180004871
0x180004867  xor     ecx, ecx
0x180004869  jmp     short loc_180004873
0x18000486b  add     rbx, 10h
0x18000486f  jmp     short loc_1800047F9
0x180004871  mov     cl, 1
0x180004873  mov     rdx, rdi
0x180004876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487b  nop
0x18000487c  call    cs:__imp_GetCurrentThreadId
0x180004882  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004888  cmp     ecx, eax
0x18000488a  jz      loc_18000498C
0x180004890  mov     ecx, 1
0x180004895  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000489d  inc     ecx; this
0x18000489f  cmp     ecx, 4
0x1800048a2  jge     loc_180004985
0x1800048a8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800048ae  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800048b3  mov     rbx, rax
0x1800048b6  test    rax, rax
0x1800048b9  jz      loc_18000497B
0x1800048bf  mov     esi, [rax+10h]
0x1800048c2  mov     ebp, 50h ; 'P'
0x1800048c7  cmp     qword ptr [rax+18h], 0
0x1800048cc  jnz     short loc_180004903
0x1800048ce  test    esi, esi
0x1800048d0  jz      short loc_180004903
0x1800048d2  mov     edx, 190h; dwBytes
0x1800048d7  lea     ecx, [rbp-48h]; dwFlags
0x1800048da  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800048df  mov     [rbx+18h], rax
0x1800048e3  test    rax, rax
0x1800048e6  jz      short loc_180004903
0x1800048e8  mov     dword ptr [rbx+20h], 5
0x1800048ef  lea     rcx, [rax+190h]
0x1800048f6  jmp     short loc_1800048FE
0x1800048f8  mov     [rax], bp
0x1800048fb  add     rax, rbp
0x1800048fe  cmp     rax, rcx
0x180004901  jnz     short loc_1800048F8
0x180004903  mov     r9, [rbx+18h]
0x180004907  test    r9, r9
0x18000490a  jz      short loc_18000497B
0x18000490c  test    esi, esi
0x18000490e  jz      short loc_180004941
0x180004910  mov     rcx, r9
0x180004913  movzx   eax, word ptr [rbx+20h]
0x180004917  lea     rdx, [rax+rax*4]
0x18000491b  shl     rdx, 4
0x18000491f  add     rdx, r9
0x180004922  cmp     r9, rdx
0x180004925  jz      short loc_180004941
0x180004927  mov     r8d, [rbx+10h]
0x18000492b  cmp     [rcx+4], r8d
0x18000492f  jbe     short loc_180004939
0x180004931  mov     eax, [rdi+8]
0x180004934  cmp     [rcx+8], eax
0x180004937  jz      short loc_18000497B
0x180004939  add     rcx, rbp
0x18000493c  cmp     rcx, rdx
0x18000493f  jnz     short loc_18000492B
0x180004941  movzx   eax, word ptr [rbx+22h]
0x180004945  inc     eax
0x180004947  movzx   ecx, word ptr [rbx+20h]
0x18000494b  xor     edx, edx
0x18000494d  div     ecx
0x18000494f  mov     [rbx+22h], dx
0x180004953  mov     rax, [rbx+8]
0x180004957  mov     r8d, 1
0x18000495d  lock xadd [rax], r8d
0x180004962  inc     r8d; unsigned int
0x180004965  movzx   eax, dx
0x180004968  lea     rcx, [rax+rax*4]
0x18000496c  shl     rcx, 4
0x180004970  add     rcx, r9; this
0x180004973  mov     rdx, rdi; struct wil::FailureInfo *
0x180004976  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000497b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004985  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000498c  add     rsp, 20h
0x180004990  pop     r14
0x180004992  pop     rdi
0x180004993  pop     rsi
0x180004994  pop     rbp
0x180004995  pop     rbx
0x180004996  retn
```
