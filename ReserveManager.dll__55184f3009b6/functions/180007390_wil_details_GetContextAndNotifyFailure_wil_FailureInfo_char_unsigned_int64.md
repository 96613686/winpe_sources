# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007390`
- end: `0x1800075a0`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007390`
- `0x180007b60`
- `0x180007c44`
- `0x1800088e0`
- `0x18000a210`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800073c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007485`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800073c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007485`

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
0x180007390  push    rbx
0x180007392  push    rbp
0x180007393  push    rsi
0x180007394  push    rdi
0x180007395  push    r14
0x180007397  sub     rsp, 30h
0x18000739b  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800073a4  mov     r14, r8
0x1800073a7  mov     rsi, rdx
0x1800073aa  mov     rdi, rcx
0x1800073ad  mov     byte ptr [rdx], 0
0x1800073b0  xor     bpl, bpl
0x1800073b3  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800073ba  test    rbx, rbx
0x1800073bd  jz      loc_180007459
0x1800073c3  call    cs:__imp_GetCurrentThreadId
0x1800073c9  mov     r9d, eax
0x1800073cc  mov     r8d, eax
0x1800073cf  shr     r8, 2
0x1800073d3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800073dd  mul     r8
0x1800073e0  shr     rdx, 3
0x1800073e4  lea     rcx, [rdx+rdx*4]
0x1800073e8  add     rcx, rcx
0x1800073eb  sub     r8, rcx
0x1800073ee  mov     rbx, [rbx+r8*8]
0x1800073f2  jmp     short loc_1800073FD
0x1800073f4  cmp     [rbx], r9d
0x1800073f7  jz      short loc_180007474
0x1800073f9  mov     rbx, [rbx+8]
0x1800073fd  test    rbx, rbx
0x180007400  jnz     short loc_1800073F4
0x180007402  test    rbx, rbx
0x180007405  jz      short loc_180007459
0x180007407  cmp     qword ptr [rbx], 0
0x18000740b  jz      short loc_180007459
0x18000740d  mov     [rsi], bpl
0x180007410  mov     r9, r14; unsigned __int64
0x180007413  mov     r8, rsi; char *
0x180007416  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007419  mov     rcx, rdi; struct wil::FailureInfo *
0x18000741c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007421  test    al, al
0x180007423  jz      short loc_180007429
0x180007425  mov     [rdi+48h], rsi
0x180007429  mov     rbx, [rbx]
0x18000742c  mov     al, [rbx+28h]
0x18000742f  mov     byte ptr [rbx+28h], 1
0x180007433  test    al, al
0x180007435  jnz     short loc_180007450
0x180007437  mov     rcx, [rbx+8]
0x18000743b  mov     rax, [rcx]
0x18000743e  mov     rdx, rdi
0x180007441  mov     rax, [rax]
0x180007444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007449  or      bpl, al
0x18000744c  mov     byte ptr [rbx+28h], 0
0x180007450  mov     rbx, [rbx+10h]
0x180007454  test    rbx, rbx
0x180007457  jnz     short loc_18000742C
0x180007459  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007460  test    rax, rax
0x180007463  jz      short loc_180007485
0x180007465  test    bpl, bpl
0x180007468  jnz     short loc_18000747A
0x18000746a  test    byte ptr [rdi+4], 2
0x18000746e  jnz     short loc_18000747A
0x180007470  xor     ecx, ecx
0x180007472  jmp     short loc_18000747C
0x180007474  add     rbx, 10h
0x180007478  jmp     short loc_180007402
0x18000747a  mov     cl, 1
0x18000747c  mov     rdx, rdi
0x18000747f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007484  nop
0x180007485  call    cs:__imp_GetCurrentThreadId
0x18000748b  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007491  cmp     ecx, eax
0x180007493  jz      loc_180007595
0x180007499  mov     ecx, 1
0x18000749e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800074a6  inc     ecx; this
0x1800074a8  cmp     ecx, 4
0x1800074ab  jge     loc_18000758E
0x1800074b1  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800074b7  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800074bc  mov     rbx, rax
0x1800074bf  test    rax, rax
0x1800074c2  jz      loc_180007584
0x1800074c8  mov     esi, [rax+10h]
0x1800074cb  mov     ebp, 50h ; 'P'
0x1800074d0  cmp     qword ptr [rax+18h], 0
0x1800074d5  jnz     short loc_18000750C
0x1800074d7  test    esi, esi
0x1800074d9  jz      short loc_18000750C
0x1800074db  mov     edx, 190h; dwBytes
0x1800074e0  lea     ecx, [rbp-48h]; dwFlags
0x1800074e3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800074e8  mov     [rbx+18h], rax
0x1800074ec  test    rax, rax
0x1800074ef  jz      short loc_18000750C
0x1800074f1  mov     dword ptr [rbx+20h], 5
0x1800074f8  lea     rcx, [rax+190h]
0x1800074ff  jmp     short loc_180007507
0x180007501  mov     [rax], bp
0x180007504  add     rax, rbp
0x180007507  cmp     rax, rcx
0x18000750a  jnz     short loc_180007501
0x18000750c  mov     r9, [rbx+18h]
0x180007510  test    r9, r9
0x180007513  jz      short loc_180007584
0x180007515  test    esi, esi
0x180007517  jz      short loc_18000754A
0x180007519  mov     rcx, r9
0x18000751c  movzx   eax, word ptr [rbx+20h]
0x180007520  lea     rdx, [rax+rax*4]
0x180007524  shl     rdx, 4
0x180007528  add     rdx, r9
0x18000752b  cmp     r9, rdx
0x18000752e  jz      short loc_18000754A
0x180007530  mov     r8d, [rbx+10h]
0x180007534  cmp     [rcx+4], r8d
0x180007538  jbe     short loc_180007542
0x18000753a  mov     eax, [rdi+8]
0x18000753d  cmp     [rcx+8], eax
0x180007540  jz      short loc_180007584
0x180007542  add     rcx, rbp
0x180007545  cmp     rcx, rdx
0x180007548  jnz     short loc_180007534
0x18000754a  movzx   eax, word ptr [rbx+22h]
0x18000754e  inc     eax
0x180007550  movzx   ecx, word ptr [rbx+20h]
0x180007554  xor     edx, edx
0x180007556  div     ecx
0x180007558  mov     [rbx+22h], dx
0x18000755c  mov     rax, [rbx+8]
0x180007560  mov     r8d, 1
0x180007566  lock xadd [rax], r8d
0x18000756b  inc     r8d; unsigned int
0x18000756e  movzx   eax, dx
0x180007571  lea     rcx, [rax+rax*4]
0x180007575  shl     rcx, 4
0x180007579  add     rcx, r9; this
0x18000757c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000757f  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007584  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000758e  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007595  add     rsp, 30h
0x180007599  pop     r14
0x18000759b  pop     rdi
0x18000759c  pop     rsi
0x18000759d  pop     rbp
0x18000759e  pop     rbx
0x18000759f  retn
```
