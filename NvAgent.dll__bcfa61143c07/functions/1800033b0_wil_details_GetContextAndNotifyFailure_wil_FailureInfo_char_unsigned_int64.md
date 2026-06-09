# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800033b0`
- end: `0x1800035b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800033b0`
- `0x180003aac`
- `0x180003b90`
- `0x1800043f8`
- `0x180004760`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000349c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000349c`

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
0x1800033b0  push    rbx
0x1800033b2  push    rbp
0x1800033b3  push    rsi
0x1800033b4  push    rdi
0x1800033b5  push    r14
0x1800033b7  sub     rsp, 20h
0x1800033bb  mov     r14, r8
0x1800033be  mov     rsi, rdx
0x1800033c1  mov     rdi, rcx
0x1800033c4  mov     byte ptr [rdx], 0
0x1800033c7  xor     bpl, bpl
0x1800033ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800033d1  test    rbx, rbx
0x1800033d4  jz      loc_180003470
0x1800033da  call    cs:__imp_GetCurrentThreadId
0x1800033e0  mov     r9d, eax
0x1800033e3  mov     r8d, eax
0x1800033e6  shr     r8, 2
0x1800033ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800033f4  mul     r8
0x1800033f7  shr     rdx, 3
0x1800033fb  lea     rcx, [rdx+rdx*4]
0x1800033ff  add     rcx, rcx
0x180003402  sub     r8, rcx
0x180003405  mov     rbx, [rbx+r8*8]
0x180003409  jmp     short loc_180003414
0x18000340b  cmp     [rbx], r9d
0x18000340e  jz      short loc_18000348B
0x180003410  mov     rbx, [rbx+8]
0x180003414  test    rbx, rbx
0x180003417  jnz     short loc_18000340B
0x180003419  test    rbx, rbx
0x18000341c  jz      short loc_180003470
0x18000341e  cmp     qword ptr [rbx], 0
0x180003422  jz      short loc_180003470
0x180003424  mov     [rsi], bpl
0x180003427  mov     r9, r14; unsigned __int64
0x18000342a  mov     r8, rsi; char *
0x18000342d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003430  mov     rcx, rdi; struct wil::FailureInfo *
0x180003433  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003438  test    al, al
0x18000343a  jz      short loc_180003440
0x18000343c  mov     [rdi+48h], rsi
0x180003440  mov     rbx, [rbx]
0x180003443  mov     al, [rbx+28h]
0x180003446  mov     byte ptr [rbx+28h], 1
0x18000344a  test    al, al
0x18000344c  jnz     short loc_180003467
0x18000344e  mov     rcx, [rbx+8]
0x180003452  mov     rax, [rcx]
0x180003455  mov     rdx, rdi
0x180003458  mov     rax, [rax]
0x18000345b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003460  or      bpl, al
0x180003463  mov     byte ptr [rbx+28h], 0
0x180003467  mov     rbx, [rbx+10h]
0x18000346b  test    rbx, rbx
0x18000346e  jnz     short loc_180003443
0x180003470  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003477  test    rax, rax
0x18000347a  jz      short loc_18000349C
0x18000347c  test    bpl, bpl
0x18000347f  jnz     short loc_180003491
0x180003481  test    byte ptr [rdi+4], 2
0x180003485  jnz     short loc_180003491
0x180003487  xor     ecx, ecx
0x180003489  jmp     short loc_180003493
0x18000348b  add     rbx, 10h
0x18000348f  jmp     short loc_180003419
0x180003491  mov     cl, 1
0x180003493  mov     rdx, rdi
0x180003496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000349b  nop
0x18000349c  call    cs:__imp_GetCurrentThreadId
0x1800034a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800034a8  cmp     ecx, eax
0x1800034aa  jz      loc_1800035AC
0x1800034b0  mov     ecx, 1
0x1800034b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800034bd  inc     ecx; this
0x1800034bf  cmp     ecx, 4
0x1800034c2  jge     loc_1800035A5
0x1800034c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800034ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800034d3  mov     rbx, rax
0x1800034d6  test    rax, rax
0x1800034d9  jz      loc_18000359B
0x1800034df  mov     esi, [rax+10h]
0x1800034e2  mov     ebp, 50h ; 'P'
0x1800034e7  cmp     qword ptr [rax+18h], 0
0x1800034ec  jnz     short loc_180003523
0x1800034ee  test    esi, esi
0x1800034f0  jz      short loc_180003523
0x1800034f2  mov     edx, 190h; dwBytes
0x1800034f7  lea     ecx, [rbp-48h]; dwFlags
0x1800034fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800034ff  mov     [rbx+18h], rax
0x180003503  test    rax, rax
0x180003506  jz      short loc_180003523
0x180003508  mov     dword ptr [rbx+20h], 5
0x18000350f  lea     rcx, [rax+190h]
0x180003516  jmp     short loc_18000351E
0x180003518  mov     [rax], bp
0x18000351b  add     rax, rbp
0x18000351e  cmp     rax, rcx
0x180003521  jnz     short loc_180003518
0x180003523  mov     r9, [rbx+18h]
0x180003527  test    r9, r9
0x18000352a  jz      short loc_18000359B
0x18000352c  test    esi, esi
0x18000352e  jz      short loc_180003561
0x180003530  mov     rcx, r9
0x180003533  movzx   eax, word ptr [rbx+20h]
0x180003537  lea     rdx, [rax+rax*4]
0x18000353b  shl     rdx, 4
0x18000353f  add     rdx, r9
0x180003542  cmp     r9, rdx
0x180003545  jz      short loc_180003561
0x180003547  mov     r8d, [rbx+10h]
0x18000354b  cmp     [rcx+4], r8d
0x18000354f  jbe     short loc_180003559
0x180003551  mov     eax, [rdi+8]
0x180003554  cmp     [rcx+8], eax
0x180003557  jz      short loc_18000359B
0x180003559  add     rcx, rbp
0x18000355c  cmp     rcx, rdx
0x18000355f  jnz     short loc_18000354B
0x180003561  movzx   eax, word ptr [rbx+22h]
0x180003565  inc     eax
0x180003567  movzx   ecx, word ptr [rbx+20h]
0x18000356b  xor     edx, edx
0x18000356d  div     ecx
0x18000356f  mov     [rbx+22h], dx
0x180003573  mov     rax, [rbx+8]
0x180003577  mov     r8d, 1
0x18000357d  lock xadd [rax], r8d
0x180003582  inc     r8d; unsigned int
0x180003585  movzx   eax, dx
0x180003588  lea     rcx, [rax+rax*4]
0x18000358c  shl     rcx, 4
0x180003590  add     rcx, r9; this
0x180003593  mov     rdx, rdi; struct wil::FailureInfo *
0x180003596  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000359b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800035a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800035ac  add     rsp, 20h
0x1800035b0  pop     r14
0x1800035b2  pop     rdi
0x1800035b3  pop     rsi
0x1800035b4  pop     rbp
0x1800035b5  pop     rbx
0x1800035b6  retn
```
