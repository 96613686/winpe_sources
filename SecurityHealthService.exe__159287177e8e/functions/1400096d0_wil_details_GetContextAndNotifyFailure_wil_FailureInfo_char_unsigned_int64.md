# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400096d0`
- end: `0x1400098d7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140006670`
- `0x1400096d0`
- `0x140009aa8`
- `0x140009b8c`
- `0x14000b284`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400096fa`
- `KERNEL32!GetCurrentThreadId` at `0x1400097bc`
- `KERNEL32!GetCurrentThreadId` at `0x1400096fa`
- `KERNEL32!GetCurrentThreadId` at `0x1400097bc`

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
0x1400096d0  push    rbx
0x1400096d2  push    rbp
0x1400096d3  push    rsi
0x1400096d4  push    rdi
0x1400096d5  push    r14
0x1400096d7  sub     rsp, 20h
0x1400096db  mov     r14, r8
0x1400096de  mov     rsi, rdx
0x1400096e1  mov     rdi, rcx
0x1400096e4  mov     byte ptr [rdx], 0
0x1400096e7  xor     bpl, bpl
0x1400096ea  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400096f1  test    rbx, rbx
0x1400096f4  jz      loc_140009790
0x1400096fa  call    cs:__imp_GetCurrentThreadId
0x140009700  mov     r9d, eax
0x140009703  mov     r8d, eax
0x140009706  shr     r8, 2
0x14000970a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140009714  mul     r8
0x140009717  shr     rdx, 3
0x14000971b  lea     rcx, [rdx+rdx*4]
0x14000971f  add     rcx, rcx
0x140009722  sub     r8, rcx
0x140009725  mov     rbx, [rbx+r8*8]
0x140009729  jmp     short loc_140009734
0x14000972b  cmp     [rbx], r9d
0x14000972e  jz      short loc_1400097AB
0x140009730  mov     rbx, [rbx+8]
0x140009734  test    rbx, rbx
0x140009737  jnz     short loc_14000972B
0x140009739  test    rbx, rbx
0x14000973c  jz      short loc_140009790
0x14000973e  cmp     qword ptr [rbx], 0
0x140009742  jz      short loc_140009790
0x140009744  mov     [rsi], bpl
0x140009747  mov     r9, r14; unsigned __int64
0x14000974a  mov     r8, rsi; char *
0x14000974d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140009750  mov     rcx, rdi; struct wil::FailureInfo *
0x140009753  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140009758  test    al, al
0x14000975a  jz      short loc_140009760
0x14000975c  mov     [rdi+48h], rsi
0x140009760  mov     rbx, [rbx]
0x140009763  mov     al, [rbx+28h]
0x140009766  mov     byte ptr [rbx+28h], 1
0x14000976a  test    al, al
0x14000976c  jnz     short loc_140009787
0x14000976e  mov     rcx, [rbx+8]
0x140009772  mov     rax, [rcx]
0x140009775  mov     rdx, rdi
0x140009778  mov     rax, [rax]
0x14000977b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009780  or      bpl, al
0x140009783  mov     byte ptr [rbx+28h], 0
0x140009787  mov     rbx, [rbx+10h]
0x14000978b  test    rbx, rbx
0x14000978e  jnz     short loc_140009763
0x140009790  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140009797  test    rax, rax
0x14000979a  jz      short loc_1400097BC
0x14000979c  test    bpl, bpl
0x14000979f  jnz     short loc_1400097B1
0x1400097a1  test    byte ptr [rdi+4], 2
0x1400097a5  jnz     short loc_1400097B1
0x1400097a7  xor     ecx, ecx
0x1400097a9  jmp     short loc_1400097B3
0x1400097ab  add     rbx, 10h
0x1400097af  jmp     short loc_140009739
0x1400097b1  mov     cl, 1
0x1400097b3  mov     rdx, rdi
0x1400097b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097bb  nop
0x1400097bc  call    cs:__imp_GetCurrentThreadId
0x1400097c2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400097c8  cmp     ecx, eax
0x1400097ca  jz      loc_1400098CC
0x1400097d0  mov     ecx, 1
0x1400097d5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400097dd  inc     ecx; this
0x1400097df  cmp     ecx, 4
0x1400097e2  jge     loc_1400098C5
0x1400097e8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400097ee  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400097f3  mov     rbx, rax
0x1400097f6  test    rax, rax
0x1400097f9  jz      loc_1400098BB
0x1400097ff  mov     esi, [rax+10h]
0x140009802  mov     ebp, 50h ; 'P'
0x140009807  cmp     qword ptr [rax+18h], 0
0x14000980c  jnz     short loc_140009843
0x14000980e  test    esi, esi
0x140009810  jz      short loc_140009843
0x140009812  mov     edx, 190h; dwBytes
0x140009817  lea     ecx, [rbp-48h]; dwFlags
0x14000981a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000981f  mov     [rbx+18h], rax
0x140009823  test    rax, rax
0x140009826  jz      short loc_140009843
0x140009828  mov     dword ptr [rbx+20h], 5
0x14000982f  lea     rcx, [rax+190h]
0x140009836  jmp     short loc_14000983E
0x140009838  mov     [rax], bp
0x14000983b  add     rax, rbp
0x14000983e  cmp     rax, rcx
0x140009841  jnz     short loc_140009838
0x140009843  mov     r9, [rbx+18h]
0x140009847  test    r9, r9
0x14000984a  jz      short loc_1400098BB
0x14000984c  test    esi, esi
0x14000984e  jz      short loc_140009881
0x140009850  mov     rcx, r9
0x140009853  movzx   eax, word ptr [rbx+20h]
0x140009857  lea     rdx, [rax+rax*4]
0x14000985b  shl     rdx, 4
0x14000985f  add     rdx, r9
0x140009862  cmp     r9, rdx
0x140009865  jz      short loc_140009881
0x140009867  mov     r8d, [rbx+10h]
0x14000986b  cmp     [rcx+4], r8d
0x14000986f  jbe     short loc_140009879
0x140009871  mov     eax, [rdi+8]
0x140009874  cmp     [rcx+8], eax
0x140009877  jz      short loc_1400098BB
0x140009879  add     rcx, rbp
0x14000987c  cmp     rcx, rdx
0x14000987f  jnz     short loc_14000986B
0x140009881  movzx   eax, word ptr [rbx+22h]
0x140009885  inc     eax
0x140009887  movzx   ecx, word ptr [rbx+20h]
0x14000988b  xor     edx, edx
0x14000988d  div     ecx
0x14000988f  mov     [rbx+22h], dx
0x140009893  mov     rax, [rbx+8]
0x140009897  mov     r8d, 1
0x14000989d  lock xadd [rax], r8d
0x1400098a2  inc     r8d; unsigned int
0x1400098a5  movzx   eax, dx
0x1400098a8  lea     rcx, [rax+rax*4]
0x1400098ac  shl     rcx, 4
0x1400098b0  add     rcx, r9; this
0x1400098b3  mov     rdx, rdi; struct wil::FailureInfo *
0x1400098b6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400098bb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400098c5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400098cc  add     rsp, 20h
0x1400098d0  pop     r14
0x1400098d2  pop     rdi
0x1400098d3  pop     rsi
0x1400098d4  pop     rbp
0x1400098d5  pop     rbx
0x1400098d6  retn
```
