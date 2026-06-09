# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003900`
- end: `0x140003b07`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140003900`
- `0x140003ffc`
- `0x1400040e0`
- `0x140004948`
- `0x140004e40`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000392a`
- `KERNEL32!GetCurrentThreadId` at `0x1400039ec`
- `KERNEL32!GetCurrentThreadId` at `0x14000392a`
- `KERNEL32!GetCurrentThreadId` at `0x1400039ec`

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
0x140003900  push    rbx
0x140003902  push    rbp
0x140003903  push    rsi
0x140003904  push    rdi
0x140003905  push    r14
0x140003907  sub     rsp, 20h
0x14000390b  mov     r14, r8
0x14000390e  mov     rsi, rdx
0x140003911  mov     rdi, rcx
0x140003914  mov     byte ptr [rdx], 0
0x140003917  xor     bpl, bpl
0x14000391a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003921  test    rbx, rbx
0x140003924  jz      loc_1400039C0
0x14000392a  call    cs:__imp_GetCurrentThreadId
0x140003930  mov     r9d, eax
0x140003933  mov     r8d, eax
0x140003936  shr     r8, 2
0x14000393a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003944  mul     r8
0x140003947  shr     rdx, 3
0x14000394b  lea     rcx, [rdx+rdx*4]
0x14000394f  add     rcx, rcx
0x140003952  sub     r8, rcx
0x140003955  mov     rbx, [rbx+r8*8]
0x140003959  jmp     short loc_140003964
0x14000395b  cmp     [rbx], r9d
0x14000395e  jz      short loc_1400039DB
0x140003960  mov     rbx, [rbx+8]
0x140003964  test    rbx, rbx
0x140003967  jnz     short loc_14000395B
0x140003969  test    rbx, rbx
0x14000396c  jz      short loc_1400039C0
0x14000396e  cmp     qword ptr [rbx], 0
0x140003972  jz      short loc_1400039C0
0x140003974  mov     [rsi], bpl
0x140003977  mov     r9, r14; unsigned __int64
0x14000397a  mov     r8, rsi; char *
0x14000397d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140003980  mov     rcx, rdi; struct wil::FailureInfo *
0x140003983  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003988  test    al, al
0x14000398a  jz      short loc_140003990
0x14000398c  mov     [rdi+48h], rsi
0x140003990  mov     rbx, [rbx]
0x140003993  mov     al, [rbx+28h]
0x140003996  mov     byte ptr [rbx+28h], 1
0x14000399a  test    al, al
0x14000399c  jnz     short loc_1400039B7
0x14000399e  mov     rcx, [rbx+8]
0x1400039a2  mov     rax, [rcx]
0x1400039a5  mov     rdx, rdi
0x1400039a8  mov     rax, [rax]
0x1400039ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039b0  or      bpl, al
0x1400039b3  mov     byte ptr [rbx+28h], 0
0x1400039b7  mov     rbx, [rbx+10h]
0x1400039bb  test    rbx, rbx
0x1400039be  jnz     short loc_140003993
0x1400039c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400039c7  test    rax, rax
0x1400039ca  jz      short loc_1400039EC
0x1400039cc  test    bpl, bpl
0x1400039cf  jnz     short loc_1400039E1
0x1400039d1  test    byte ptr [rdi+4], 2
0x1400039d5  jnz     short loc_1400039E1
0x1400039d7  xor     ecx, ecx
0x1400039d9  jmp     short loc_1400039E3
0x1400039db  add     rbx, 10h
0x1400039df  jmp     short loc_140003969
0x1400039e1  mov     cl, 1
0x1400039e3  mov     rdx, rdi
0x1400039e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039eb  nop
0x1400039ec  call    cs:__imp_GetCurrentThreadId
0x1400039f2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400039f8  cmp     ecx, eax
0x1400039fa  jz      loc_140003AFC
0x140003a00  mov     ecx, 1
0x140003a05  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140003a0d  inc     ecx; this
0x140003a0f  cmp     ecx, 4
0x140003a12  jge     loc_140003AF5
0x140003a18  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003a1e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140003a23  mov     rbx, rax
0x140003a26  test    rax, rax
0x140003a29  jz      loc_140003AEB
0x140003a2f  mov     esi, [rax+10h]
0x140003a32  mov     ebp, 50h ; 'P'
0x140003a37  cmp     qword ptr [rax+18h], 0
0x140003a3c  jnz     short loc_140003A73
0x140003a3e  test    esi, esi
0x140003a40  jz      short loc_140003A73
0x140003a42  mov     edx, 190h; dwBytes
0x140003a47  lea     ecx, [rbp-48h]; dwFlags
0x140003a4a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003a4f  mov     [rbx+18h], rax
0x140003a53  test    rax, rax
0x140003a56  jz      short loc_140003A73
0x140003a58  mov     dword ptr [rbx+20h], 5
0x140003a5f  lea     rcx, [rax+190h]
0x140003a66  jmp     short loc_140003A6E
0x140003a68  mov     [rax], bp
0x140003a6b  add     rax, rbp
0x140003a6e  cmp     rax, rcx
0x140003a71  jnz     short loc_140003A68
0x140003a73  mov     r9, [rbx+18h]
0x140003a77  test    r9, r9
0x140003a7a  jz      short loc_140003AEB
0x140003a7c  test    esi, esi
0x140003a7e  jz      short loc_140003AB1
0x140003a80  mov     rcx, r9
0x140003a83  movzx   eax, word ptr [rbx+20h]
0x140003a87  lea     rdx, [rax+rax*4]
0x140003a8b  shl     rdx, 4
0x140003a8f  add     rdx, r9
0x140003a92  cmp     r9, rdx
0x140003a95  jz      short loc_140003AB1
0x140003a97  mov     r8d, [rbx+10h]
0x140003a9b  cmp     [rcx+4], r8d
0x140003a9f  jbe     short loc_140003AA9
0x140003aa1  mov     eax, [rdi+8]
0x140003aa4  cmp     [rcx+8], eax
0x140003aa7  jz      short loc_140003AEB
0x140003aa9  add     rcx, rbp
0x140003aac  cmp     rcx, rdx
0x140003aaf  jnz     short loc_140003A9B
0x140003ab1  movzx   eax, word ptr [rbx+22h]
0x140003ab5  inc     eax
0x140003ab7  movzx   ecx, word ptr [rbx+20h]
0x140003abb  xor     edx, edx
0x140003abd  div     ecx
0x140003abf  mov     [rbx+22h], dx
0x140003ac3  mov     rax, [rbx+8]
0x140003ac7  mov     r8d, 1
0x140003acd  lock xadd [rax], r8d
0x140003ad2  inc     r8d; unsigned int
0x140003ad5  movzx   eax, dx
0x140003ad8  lea     rcx, [rax+rax*4]
0x140003adc  shl     rcx, 4
0x140003ae0  add     rcx, r9; this
0x140003ae3  mov     rdx, rdi; struct wil::FailureInfo *
0x140003ae6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140003aeb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003af5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140003afc  add     rsp, 20h
0x140003b00  pop     r14
0x140003b02  pop     rdi
0x140003b03  pop     rsi
0x140003b04  pop     rbp
0x140003b05  pop     rbx
0x140003b06  retn
```
