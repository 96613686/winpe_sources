# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400034b0`
- end: `0x1400036b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400034b0`
- `0x140003bac`
- `0x140003c90`
- `0x140004508`
- `0x140004854`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000359c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000359c`

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
0x1400034b0  push    rbx
0x1400034b2  push    rbp
0x1400034b3  push    rsi
0x1400034b4  push    rdi
0x1400034b5  push    r14
0x1400034b7  sub     rsp, 20h
0x1400034bb  mov     r14, r8
0x1400034be  mov     rsi, rdx
0x1400034c1  mov     rdi, rcx
0x1400034c4  mov     byte ptr [rdx], 0
0x1400034c7  xor     bpl, bpl
0x1400034ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400034d1  test    rbx, rbx
0x1400034d4  jz      loc_140003570
0x1400034da  call    cs:__imp_GetCurrentThreadId
0x1400034e0  mov     r9d, eax
0x1400034e3  mov     r8d, eax
0x1400034e6  shr     r8, 2
0x1400034ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400034f4  mul     r8
0x1400034f7  shr     rdx, 3
0x1400034fb  lea     rcx, [rdx+rdx*4]
0x1400034ff  add     rcx, rcx
0x140003502  sub     r8, rcx
0x140003505  mov     rbx, [rbx+r8*8]
0x140003509  jmp     short loc_140003514
0x14000350b  cmp     [rbx], r9d
0x14000350e  jz      short loc_14000358B
0x140003510  mov     rbx, [rbx+8]
0x140003514  test    rbx, rbx
0x140003517  jnz     short loc_14000350B
0x140003519  test    rbx, rbx
0x14000351c  jz      short loc_140003570
0x14000351e  cmp     qword ptr [rbx], 0
0x140003522  jz      short loc_140003570
0x140003524  mov     [rsi], bpl
0x140003527  mov     r9, r14; unsigned __int64
0x14000352a  mov     r8, rsi; char *
0x14000352d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140003530  mov     rcx, rdi; struct wil::FailureInfo *
0x140003533  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003538  test    al, al
0x14000353a  jz      short loc_140003540
0x14000353c  mov     [rdi+48h], rsi
0x140003540  mov     rbx, [rbx]
0x140003543  mov     al, [rbx+28h]
0x140003546  mov     byte ptr [rbx+28h], 1
0x14000354a  test    al, al
0x14000354c  jnz     short loc_140003567
0x14000354e  mov     rcx, [rbx+8]
0x140003552  mov     rax, [rcx]
0x140003555  mov     rdx, rdi
0x140003558  mov     rax, [rax]
0x14000355b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003560  or      bpl, al
0x140003563  mov     byte ptr [rbx+28h], 0
0x140003567  mov     rbx, [rbx+10h]
0x14000356b  test    rbx, rbx
0x14000356e  jnz     short loc_140003543
0x140003570  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140003577  test    rax, rax
0x14000357a  jz      short loc_14000359C
0x14000357c  test    bpl, bpl
0x14000357f  jnz     short loc_140003591
0x140003581  test    byte ptr [rdi+4], 2
0x140003585  jnz     short loc_140003591
0x140003587  xor     ecx, ecx
0x140003589  jmp     short loc_140003593
0x14000358b  add     rbx, 10h
0x14000358f  jmp     short loc_140003519
0x140003591  mov     cl, 1
0x140003593  mov     rdx, rdi
0x140003596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000359b  nop
0x14000359c  call    cs:__imp_GetCurrentThreadId
0x1400035a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400035a8  cmp     ecx, eax
0x1400035aa  jz      loc_1400036AC
0x1400035b0  mov     ecx, 1
0x1400035b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400035bd  inc     ecx; this
0x1400035bf  cmp     ecx, 4
0x1400035c2  jge     loc_1400036A5
0x1400035c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400035ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400035d3  mov     rbx, rax
0x1400035d6  test    rax, rax
0x1400035d9  jz      loc_14000369B
0x1400035df  mov     esi, [rax+10h]
0x1400035e2  mov     ebp, 50h ; 'P'
0x1400035e7  cmp     qword ptr [rax+18h], 0
0x1400035ec  jnz     short loc_140003623
0x1400035ee  test    esi, esi
0x1400035f0  jz      short loc_140003623
0x1400035f2  mov     edx, 190h; dwBytes
0x1400035f7  lea     ecx, [rbp-48h]; dwFlags
0x1400035fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400035ff  mov     [rbx+18h], rax
0x140003603  test    rax, rax
0x140003606  jz      short loc_140003623
0x140003608  mov     dword ptr [rbx+20h], 5
0x14000360f  lea     rcx, [rax+190h]
0x140003616  jmp     short loc_14000361E
0x140003618  mov     [rax], bp
0x14000361b  add     rax, rbp
0x14000361e  cmp     rax, rcx
0x140003621  jnz     short loc_140003618
0x140003623  mov     r9, [rbx+18h]
0x140003627  test    r9, r9
0x14000362a  jz      short loc_14000369B
0x14000362c  test    esi, esi
0x14000362e  jz      short loc_140003661
0x140003630  mov     rcx, r9
0x140003633  movzx   eax, word ptr [rbx+20h]
0x140003637  lea     rdx, [rax+rax*4]
0x14000363b  shl     rdx, 4
0x14000363f  add     rdx, r9
0x140003642  cmp     r9, rdx
0x140003645  jz      short loc_140003661
0x140003647  mov     r8d, [rbx+10h]
0x14000364b  cmp     [rcx+4], r8d
0x14000364f  jbe     short loc_140003659
0x140003651  mov     eax, [rdi+8]
0x140003654  cmp     [rcx+8], eax
0x140003657  jz      short loc_14000369B
0x140003659  add     rcx, rbp
0x14000365c  cmp     rcx, rdx
0x14000365f  jnz     short loc_14000364B
0x140003661  movzx   eax, word ptr [rbx+22h]
0x140003665  inc     eax
0x140003667  movzx   ecx, word ptr [rbx+20h]
0x14000366b  xor     edx, edx
0x14000366d  div     ecx
0x14000366f  mov     [rbx+22h], dx
0x140003673  mov     rax, [rbx+8]
0x140003677  mov     r8d, 1
0x14000367d  lock xadd [rax], r8d
0x140003682  inc     r8d; unsigned int
0x140003685  movzx   eax, dx
0x140003688  lea     rcx, [rax+rax*4]
0x14000368c  shl     rcx, 4
0x140003690  add     rcx, r9; this
0x140003693  mov     rdx, rdi; struct wil::FailureInfo *
0x140003696  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000369b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400036a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400036ac  add     rsp, 20h
0x1400036b0  pop     r14
0x1400036b2  pop     rdi
0x1400036b3  pop     rsi
0x1400036b4  pop     rbp
0x1400036b5  pop     rbx
0x1400036b6  retn
```
