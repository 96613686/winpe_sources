# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140009570`
- end: `0x140009777`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140009570`
- `0x140009c3c`
- `0x140009d20`
- `0x14000ba08`
- `0x14000c4cc`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000959a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000965c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000959a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000965c`

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
0x140009570  push    rbx
0x140009572  push    rbp
0x140009573  push    rsi
0x140009574  push    rdi
0x140009575  push    r14
0x140009577  sub     rsp, 20h
0x14000957b  mov     r14, r8
0x14000957e  mov     rsi, rdx
0x140009581  mov     rdi, rcx
0x140009584  mov     byte ptr [rdx], 0
0x140009587  xor     bpl, bpl
0x14000958a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140009591  test    rbx, rbx
0x140009594  jz      loc_140009630
0x14000959a  call    cs:__imp_GetCurrentThreadId
0x1400095a0  mov     r9d, eax
0x1400095a3  mov     r8d, eax
0x1400095a6  shr     r8, 2
0x1400095aa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400095b4  mul     r8
0x1400095b7  shr     rdx, 3
0x1400095bb  lea     rcx, [rdx+rdx*4]
0x1400095bf  add     rcx, rcx
0x1400095c2  sub     r8, rcx
0x1400095c5  mov     rbx, [rbx+r8*8]
0x1400095c9  jmp     short loc_1400095D4
0x1400095cb  cmp     [rbx], r9d
0x1400095ce  jz      short loc_14000964B
0x1400095d0  mov     rbx, [rbx+8]
0x1400095d4  test    rbx, rbx
0x1400095d7  jnz     short loc_1400095CB
0x1400095d9  test    rbx, rbx
0x1400095dc  jz      short loc_140009630
0x1400095de  cmp     qword ptr [rbx], 0
0x1400095e2  jz      short loc_140009630
0x1400095e4  mov     [rsi], bpl
0x1400095e7  mov     r9, r14; unsigned __int64
0x1400095ea  mov     r8, rsi; char *
0x1400095ed  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400095f0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400095f3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400095f8  test    al, al
0x1400095fa  jz      short loc_140009600
0x1400095fc  mov     [rdi+48h], rsi
0x140009600  mov     rbx, [rbx]
0x140009603  mov     al, [rbx+28h]
0x140009606  mov     byte ptr [rbx+28h], 1
0x14000960a  test    al, al
0x14000960c  jnz     short loc_140009627
0x14000960e  mov     rcx, [rbx+8]
0x140009612  mov     rax, [rcx]
0x140009615  mov     rdx, rdi
0x140009618  mov     rax, [rax]
0x14000961b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009620  or      bpl, al
0x140009623  mov     byte ptr [rbx+28h], 0
0x140009627  mov     rbx, [rbx+10h]
0x14000962b  test    rbx, rbx
0x14000962e  jnz     short loc_140009603
0x140009630  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140009637  test    rax, rax
0x14000963a  jz      short loc_14000965C
0x14000963c  test    bpl, bpl
0x14000963f  jnz     short loc_140009651
0x140009641  test    byte ptr [rdi+4], 2
0x140009645  jnz     short loc_140009651
0x140009647  xor     ecx, ecx
0x140009649  jmp     short loc_140009653
0x14000964b  add     rbx, 10h
0x14000964f  jmp     short loc_1400095D9
0x140009651  mov     cl, 1
0x140009653  mov     rdx, rdi
0x140009656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000965b  nop
0x14000965c  call    cs:__imp_GetCurrentThreadId
0x140009662  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140009668  cmp     ecx, eax
0x14000966a  jz      loc_14000976C
0x140009670  mov     ecx, 1
0x140009675  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000967d  inc     ecx; this
0x14000967f  cmp     ecx, 4
0x140009682  jge     loc_140009765
0x140009688  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000968e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140009693  mov     rbx, rax
0x140009696  test    rax, rax
0x140009699  jz      loc_14000975B
0x14000969f  mov     esi, [rax+10h]
0x1400096a2  mov     ebp, 50h ; 'P'
0x1400096a7  cmp     qword ptr [rax+18h], 0
0x1400096ac  jnz     short loc_1400096E3
0x1400096ae  test    esi, esi
0x1400096b0  jz      short loc_1400096E3
0x1400096b2  mov     edx, 190h; dwBytes
0x1400096b7  lea     ecx, [rbp-48h]; dwFlags
0x1400096ba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400096bf  mov     [rbx+18h], rax
0x1400096c3  test    rax, rax
0x1400096c6  jz      short loc_1400096E3
0x1400096c8  mov     dword ptr [rbx+20h], 5
0x1400096cf  lea     rcx, [rax+190h]
0x1400096d6  jmp     short loc_1400096DE
0x1400096d8  mov     [rax], bp
0x1400096db  add     rax, rbp
0x1400096de  cmp     rax, rcx
0x1400096e1  jnz     short loc_1400096D8
0x1400096e3  mov     r9, [rbx+18h]
0x1400096e7  test    r9, r9
0x1400096ea  jz      short loc_14000975B
0x1400096ec  test    esi, esi
0x1400096ee  jz      short loc_140009721
0x1400096f0  mov     rcx, r9
0x1400096f3  movzx   eax, word ptr [rbx+20h]
0x1400096f7  lea     rdx, [rax+rax*4]
0x1400096fb  shl     rdx, 4
0x1400096ff  add     rdx, r9
0x140009702  cmp     r9, rdx
0x140009705  jz      short loc_140009721
0x140009707  mov     r8d, [rbx+10h]
0x14000970b  cmp     [rcx+4], r8d
0x14000970f  jbe     short loc_140009719
0x140009711  mov     eax, [rdi+8]
0x140009714  cmp     [rcx+8], eax
0x140009717  jz      short loc_14000975B
0x140009719  add     rcx, rbp
0x14000971c  cmp     rcx, rdx
0x14000971f  jnz     short loc_14000970B
0x140009721  movzx   eax, word ptr [rbx+22h]
0x140009725  inc     eax
0x140009727  movzx   ecx, word ptr [rbx+20h]
0x14000972b  xor     edx, edx
0x14000972d  div     ecx
0x14000972f  mov     [rbx+22h], dx
0x140009733  mov     rax, [rbx+8]
0x140009737  mov     r8d, 1
0x14000973d  lock xadd [rax], r8d
0x140009742  inc     r8d; unsigned int
0x140009745  movzx   eax, dx
0x140009748  lea     rcx, [rax+rax*4]
0x14000974c  shl     rcx, 4
0x140009750  add     rcx, r9; this
0x140009753  mov     rdx, rdi; struct wil::FailureInfo *
0x140009756  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000975b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140009765  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000976c  add     rsp, 20h
0x140009770  pop     r14
0x140009772  pop     rdi
0x140009773  pop     rsi
0x140009774  pop     rbp
0x140009775  pop     rbx
0x140009776  retn
```
