# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400096a0`
- end: `0x1400098aa`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000734c`
- `0x14000923c`
- `0x1400094dc`
- `0x14000959c`
- `0x1400096a0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400096d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009787`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400096d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009787`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder **v10; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
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
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * (CurrentThreadId % 0xA)); ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
      {
        v10 = 0;
        goto LABEL_7;
      }
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
        break;
    }
    v10 = (struct wil::details::ThreadFailureCallbackHolder **)(i + 16);
LABEL_7:
    if ( v10 && *v10 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v10, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v11 = *v10;
      do
      {
        v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (LOBYTE(this) = 0, (*((_BYTE *)v5 + 4) & 2) != 0) )
      LOBYTE(this) = 1;
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
LABEL_34:
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
                goto LABEL_34;
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
0x1400096a0  mov     [rsp+arg_18], rbx
0x1400096a5  push    rbp
0x1400096a6  push    rsi
0x1400096a7  push    rdi
0x1400096a8  push    r14
0x1400096aa  push    r15
0x1400096ac  sub     rsp, 20h
0x1400096b0  mov     r14, r8
0x1400096b3  mov     rsi, rdx
0x1400096b6  mov     rdi, rcx
0x1400096b9  xor     r15d, r15d
0x1400096bc  mov     [rdx], r15b
0x1400096bf  mov     bpl, r15b
0x1400096c2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400096c9  test    rbx, rbx
0x1400096cc  jz      loc_14000975B
0x1400096d2  call    cs:__imp_GetCurrentThreadId
0x1400096d8  mov     r9d, eax
0x1400096db  mov     r8d, eax
0x1400096de  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400096e8  mul     r9
0x1400096eb  shr     rdx, 3
0x1400096ef  lea     rcx, [rdx+rdx*4]
0x1400096f3  add     rcx, rcx
0x1400096f6  sub     r8, rcx
0x1400096f9  mov     rbx, [rbx+r8*8]
0x1400096fd  jmp     short loc_14000970C
0x1400096ff  cmp     [rbx], r9d
0x140009702  jz      loc_140009801
0x140009708  mov     rbx, [rbx+8]
0x14000970c  test    rbx, rbx
0x14000970f  jnz     short loc_1400096FF
0x140009711  mov     rbx, r15
0x140009714  test    rbx, rbx
0x140009717  jz      short loc_14000975B
0x140009719  cmp     [rbx], r15
0x14000971c  jz      short loc_14000975B
0x14000971e  mov     [rsi], r15b
0x140009721  mov     r9, r14; unsigned __int64
0x140009724  mov     r8, rsi; char *
0x140009727  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000972a  mov     rcx, rdi; struct wil::FailureInfo *
0x14000972d  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140009732  test    al, al
0x140009734  jz      short loc_14000973A
0x140009736  mov     [rdi+48h], rsi
0x14000973a  mov     rbx, [rbx]
0x14000973d  mov     rcx, [rbx+8]
0x140009741  mov     rax, [rcx]
0x140009744  mov     rdx, rdi
0x140009747  mov     rax, [rax]
0x14000974a  call    _guard_dispatch_icall
0x14000974f  or      bpl, al
0x140009752  mov     rbx, [rbx+10h]
0x140009756  test    rbx, rbx
0x140009759  jnz     short loc_14000973D
0x14000975b  mov     r14d, 1
0x140009761  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140009768  test    rax, rax
0x14000976b  jz      short loc_140009787
0x14000976d  test    bpl, bpl
0x140009770  jnz     short loc_14000977B
0x140009772  test    byte ptr [rdi+4], 2
0x140009776  mov     cl, r15b
0x140009779  jz      short loc_14000977E
0x14000977b  mov     cl, r14b
0x14000977e  mov     rdx, rdi
0x140009781  call    _guard_dispatch_icall
0x140009786  nop
0x140009787  call    cs:__imp_GetCurrentThreadId
0x14000978d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140009793  cmp     ecx, eax
0x140009795  jz      loc_140009899
0x14000979b  mov     ecx, r14d
0x14000979e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400097a6  add     ecx, r14d; this
0x1400097a9  cmp     ecx, 4
0x1400097ac  jge     loc_140009892
0x1400097b2  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400097b8  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400097bd  mov     rbx, rax
0x1400097c0  test    rax, rax
0x1400097c3  jz      loc_14000988B
0x1400097c9  mov     esi, [rax+10h]
0x1400097cc  mov     ebp, 50h ; 'P'
0x1400097d1  cmp     [rax+18h], r15
0x1400097d5  jnz     short loc_140009815
0x1400097d7  test    esi, esi
0x1400097d9  jz      short loc_140009815
0x1400097db  mov     edx, 190h; dwBytes
0x1400097e0  lea     ecx, [rbp-48h]; dwFlags
0x1400097e3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400097e8  mov     [rbx+18h], rax
0x1400097ec  test    rax, rax
0x1400097ef  jz      short loc_140009815
0x1400097f1  mov     dword ptr [rbx+20h], 5
0x1400097f8  lea     rcx, [rax+190h]
0x1400097ff  jmp     short loc_140009810
0x140009801  add     rbx, 10h
0x140009805  jmp     loc_140009714
0x14000980a  mov     [rax], bp
0x14000980d  add     rax, rbp
0x140009810  cmp     rax, rcx
0x140009813  jnz     short loc_14000980A
0x140009815  mov     r9, [rbx+18h]
0x140009819  test    r9, r9
0x14000981c  jz      short loc_14000988B
0x14000981e  test    esi, esi
0x140009820  jz      short loc_140009853
0x140009822  mov     rcx, r9
0x140009825  movzx   eax, word ptr [rbx+20h]
0x140009829  lea     rdx, [rax+rax*4]
0x14000982d  shl     rdx, 4
0x140009831  add     rdx, r9
0x140009834  cmp     r9, rdx
0x140009837  jz      short loc_140009853
0x140009839  mov     r8d, [rbx+10h]
0x14000983d  cmp     [rcx+4], r8d
0x140009841  jbe     short loc_14000984B
0x140009843  mov     eax, [rdi+8]
0x140009846  cmp     [rcx+8], eax
0x140009849  jz      short loc_14000988B
0x14000984b  add     rcx, rbp
0x14000984e  cmp     rcx, rdx
0x140009851  jnz     short loc_14000983D
0x140009853  movzx   eax, word ptr [rbx+22h]
0x140009857  add     eax, r14d
0x14000985a  movzx   ecx, word ptr [rbx+20h]
0x14000985e  xor     edx, edx
0x140009860  div     ecx
0x140009862  mov     [rbx+22h], dx
0x140009866  mov     rax, [rbx+8]
0x14000986a  mov     r8d, r14d
0x14000986d  lock xadd [rax], r8d
0x140009872  add     r8d, r14d; unsigned int
0x140009875  movzx   eax, dx
0x140009878  lea     rcx, [rax+rax*4]
0x14000987c  shl     rcx, 4
0x140009880  add     rcx, r9; this
0x140009883  mov     rdx, rdi; struct wil::FailureInfo *
0x140009886  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000988b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140009892  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140009899  mov     rbx, [rsp+48h+arg_18]
0x14000989e  add     rsp, 20h
0x1400098a2  pop     r15
0x1400098a4  pop     r14
0x1400098a6  pop     rdi
0x1400098a7  pop     rsi
0x1400098a8  pop     rbp
0x1400098a9  retn
```
