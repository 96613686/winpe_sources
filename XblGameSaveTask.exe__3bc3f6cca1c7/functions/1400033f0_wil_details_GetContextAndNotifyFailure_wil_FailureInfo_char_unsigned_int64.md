# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400033f0`
- end: `0x1400035f7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400033f0`
- `0x140003aec`
- `0x140003bd0`
- `0x140004448`
- `0x1400047b0`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000341a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000341a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034dc`

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
0x1400033f0  push    rbx
0x1400033f2  push    rbp
0x1400033f3  push    rsi
0x1400033f4  push    rdi
0x1400033f5  push    r14
0x1400033f7  sub     rsp, 20h
0x1400033fb  mov     r14, r8
0x1400033fe  mov     rsi, rdx
0x140003401  mov     rdi, rcx
0x140003404  mov     byte ptr [rdx], 0
0x140003407  xor     bpl, bpl
0x14000340a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003411  test    rbx, rbx
0x140003414  jz      loc_1400034B0
0x14000341a  call    cs:__imp_GetCurrentThreadId
0x140003420  mov     r9d, eax
0x140003423  mov     r8d, eax
0x140003426  shr     r8, 2
0x14000342a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003434  mul     r8
0x140003437  shr     rdx, 3
0x14000343b  lea     rcx, [rdx+rdx*4]
0x14000343f  add     rcx, rcx
0x140003442  sub     r8, rcx
0x140003445  mov     rbx, [rbx+r8*8]
0x140003449  jmp     short loc_140003454
0x14000344b  cmp     [rbx], r9d
0x14000344e  jz      short loc_1400034CB
0x140003450  mov     rbx, [rbx+8]
0x140003454  test    rbx, rbx
0x140003457  jnz     short loc_14000344B
0x140003459  test    rbx, rbx
0x14000345c  jz      short loc_1400034B0
0x14000345e  cmp     qword ptr [rbx], 0
0x140003462  jz      short loc_1400034B0
0x140003464  mov     [rsi], bpl
0x140003467  mov     r9, r14; unsigned __int64
0x14000346a  mov     r8, rsi; char *
0x14000346d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140003470  mov     rcx, rdi; struct wil::FailureInfo *
0x140003473  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003478  test    al, al
0x14000347a  jz      short loc_140003480
0x14000347c  mov     [rdi+48h], rsi
0x140003480  mov     rbx, [rbx]
0x140003483  mov     al, [rbx+28h]
0x140003486  mov     byte ptr [rbx+28h], 1
0x14000348a  test    al, al
0x14000348c  jnz     short loc_1400034A7
0x14000348e  mov     rcx, [rbx+8]
0x140003492  mov     rax, [rcx]
0x140003495  mov     rdx, rdi
0x140003498  mov     rax, [rax]
0x14000349b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034a0  or      bpl, al
0x1400034a3  mov     byte ptr [rbx+28h], 0
0x1400034a7  mov     rbx, [rbx+10h]
0x1400034ab  test    rbx, rbx
0x1400034ae  jnz     short loc_140003483
0x1400034b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400034b7  test    rax, rax
0x1400034ba  jz      short loc_1400034DC
0x1400034bc  test    bpl, bpl
0x1400034bf  jnz     short loc_1400034D1
0x1400034c1  test    byte ptr [rdi+4], 2
0x1400034c5  jnz     short loc_1400034D1
0x1400034c7  xor     ecx, ecx
0x1400034c9  jmp     short loc_1400034D3
0x1400034cb  add     rbx, 10h
0x1400034cf  jmp     short loc_140003459
0x1400034d1  mov     cl, 1
0x1400034d3  mov     rdx, rdi
0x1400034d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034db  nop
0x1400034dc  call    cs:__imp_GetCurrentThreadId
0x1400034e2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400034e8  cmp     ecx, eax
0x1400034ea  jz      loc_1400035EC
0x1400034f0  mov     ecx, 1
0x1400034f5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400034fd  inc     ecx; this
0x1400034ff  cmp     ecx, 4
0x140003502  jge     loc_1400035E5
0x140003508  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000350e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140003513  mov     rbx, rax
0x140003516  test    rax, rax
0x140003519  jz      loc_1400035DB
0x14000351f  mov     esi, [rax+10h]
0x140003522  mov     ebp, 50h ; 'P'
0x140003527  cmp     qword ptr [rax+18h], 0
0x14000352c  jnz     short loc_140003563
0x14000352e  test    esi, esi
0x140003530  jz      short loc_140003563
0x140003532  mov     edx, 190h; dwBytes
0x140003537  lea     ecx, [rbp-48h]; dwFlags
0x14000353a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000353f  mov     [rbx+18h], rax
0x140003543  test    rax, rax
0x140003546  jz      short loc_140003563
0x140003548  mov     dword ptr [rbx+20h], 5
0x14000354f  lea     rcx, [rax+190h]
0x140003556  jmp     short loc_14000355E
0x140003558  mov     [rax], bp
0x14000355b  add     rax, rbp
0x14000355e  cmp     rax, rcx
0x140003561  jnz     short loc_140003558
0x140003563  mov     r9, [rbx+18h]
0x140003567  test    r9, r9
0x14000356a  jz      short loc_1400035DB
0x14000356c  test    esi, esi
0x14000356e  jz      short loc_1400035A1
0x140003570  mov     rcx, r9
0x140003573  movzx   eax, word ptr [rbx+20h]
0x140003577  lea     rdx, [rax+rax*4]
0x14000357b  shl     rdx, 4
0x14000357f  add     rdx, r9
0x140003582  cmp     r9, rdx
0x140003585  jz      short loc_1400035A1
0x140003587  mov     r8d, [rbx+10h]
0x14000358b  cmp     [rcx+4], r8d
0x14000358f  jbe     short loc_140003599
0x140003591  mov     eax, [rdi+8]
0x140003594  cmp     [rcx+8], eax
0x140003597  jz      short loc_1400035DB
0x140003599  add     rcx, rbp
0x14000359c  cmp     rcx, rdx
0x14000359f  jnz     short loc_14000358B
0x1400035a1  movzx   eax, word ptr [rbx+22h]
0x1400035a5  inc     eax
0x1400035a7  movzx   ecx, word ptr [rbx+20h]
0x1400035ab  xor     edx, edx
0x1400035ad  div     ecx
0x1400035af  mov     [rbx+22h], dx
0x1400035b3  mov     rax, [rbx+8]
0x1400035b7  mov     r8d, 1
0x1400035bd  lock xadd [rax], r8d
0x1400035c2  inc     r8d; unsigned int
0x1400035c5  movzx   eax, dx
0x1400035c8  lea     rcx, [rax+rax*4]
0x1400035cc  shl     rcx, 4
0x1400035d0  add     rcx, r9; this
0x1400035d3  mov     rdx, rdi; struct wil::FailureInfo *
0x1400035d6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400035db  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400035e5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400035ec  add     rsp, 20h
0x1400035f0  pop     r14
0x1400035f2  pop     rdi
0x1400035f3  pop     rsi
0x1400035f4  pop     rbp
0x1400035f5  pop     rbx
0x1400035f6  retn
```
