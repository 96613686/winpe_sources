# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003920`
- end: `0x140003b26`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140003920`
- `0x140004018`
- `0x1400040fc`
- `0x140004abc`
- `0x140005190`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000394a`
- `KERNEL32!GetCurrentThreadId` at `0x140003a0b`
- `KERNEL32!GetCurrentThreadId` at `0x14000394a`
- `KERNEL32!GetCurrentThreadId` at `0x140003a0b`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
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
  volatile signed __int32 *v25; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
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
            v25 = (volatile signed __int32 *)*((_QWORD *)v17 + 1);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v7,
              _InterlockedIncrement(v25));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v7 + 2) )
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
0x140003920  push    rbx
0x140003922  push    rbp
0x140003923  push    rsi
0x140003924  push    rdi
0x140003925  push    r14
0x140003927  sub     rsp, 20h
0x14000392b  mov     byte ptr [rdx], 0
0x14000392e  xor     bpl, bpl
0x140003931  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003938  mov     r14, r8
0x14000393b  mov     rsi, rdx
0x14000393e  mov     rdi, rcx
0x140003941  test    rbx, rbx
0x140003944  jz      loc_1400039E0
0x14000394a  call    cs:__imp_GetCurrentThreadId
0x140003950  mov     r8d, eax
0x140003953  mov     r9d, eax
0x140003956  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003960  shr     r8, 2
0x140003964  mul     r8
0x140003967  shr     rdx, 3
0x14000396b  lea     rcx, [rdx+rdx*4]
0x14000396f  add     rcx, rcx
0x140003972  sub     r8, rcx
0x140003975  mov     rbx, [rbx+r8*8]
0x140003979  jmp     short loc_140003984
0x14000397b  cmp     [rbx], r9d
0x14000397e  jz      short loc_1400039FB
0x140003980  mov     rbx, [rbx+8]
0x140003984  test    rbx, rbx
0x140003987  jnz     short loc_14000397B
0x140003989  test    rbx, rbx
0x14000398c  jz      short loc_1400039E0
0x14000398e  cmp     qword ptr [rbx], 0
0x140003992  jz      short loc_1400039E0
0x140003994  mov     [rsi], bpl
0x140003997  mov     r9, r14; unsigned __int64
0x14000399a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000399d  mov     r8, rsi; char *
0x1400039a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400039a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400039a8  test    al, al
0x1400039aa  jz      short loc_1400039B0
0x1400039ac  mov     [rdi+48h], rsi
0x1400039b0  mov     rbx, [rbx]
0x1400039b3  mov     al, [rbx+28h]
0x1400039b6  mov     byte ptr [rbx+28h], 1
0x1400039ba  test    al, al
0x1400039bc  jnz     short loc_1400039D7
0x1400039be  mov     rcx, [rbx+8]
0x1400039c2  mov     rdx, rdi
0x1400039c5  mov     rax, [rcx]
0x1400039c8  mov     rax, [rax]
0x1400039cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039d0  or      bpl, al
0x1400039d3  mov     byte ptr [rbx+28h], 0
0x1400039d7  mov     rbx, [rbx+10h]
0x1400039db  test    rbx, rbx
0x1400039de  jnz     short loc_1400039B3
0x1400039e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400039e7  test    rax, rax
0x1400039ea  jz      short loc_140003A0B
0x1400039ec  test    bpl, bpl
0x1400039ef  jnz     short loc_140003A01
0x1400039f1  test    byte ptr [rdi+4], 2
0x1400039f5  jnz     short loc_140003A01
0x1400039f7  xor     ecx, ecx
0x1400039f9  jmp     short loc_140003A03
0x1400039fb  add     rbx, 10h
0x1400039ff  jmp     short loc_140003989
0x140003a01  mov     cl, 1
0x140003a03  mov     rdx, rdi
0x140003a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a0b  call    cs:__imp_GetCurrentThreadId
0x140003a11  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003a17  cmp     ecx, eax
0x140003a19  jz      loc_140003B1B
0x140003a1f  mov     ecx, 1
0x140003a24  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140003a2c  inc     ecx; this
0x140003a2e  cmp     ecx, 4
0x140003a31  jge     loc_140003B14
0x140003a37  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003a3d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140003a42  mov     rbx, rax
0x140003a45  test    rax, rax
0x140003a48  jz      loc_140003B0A
0x140003a4e  cmp     qword ptr [rax+18h], 0
0x140003a53  mov     ebp, 50h ; 'P'
0x140003a58  mov     esi, [rax+10h]
0x140003a5b  jnz     short loc_140003A92
0x140003a5d  test    esi, esi
0x140003a5f  jz      short loc_140003A92
0x140003a61  mov     edx, 190h; dwBytes
0x140003a66  lea     ecx, [rbp-48h]; dwFlags
0x140003a69  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003a6e  mov     [rbx+18h], rax
0x140003a72  test    rax, rax
0x140003a75  jz      short loc_140003A92
0x140003a77  mov     dword ptr [rbx+20h], 5
0x140003a7e  lea     rcx, [rax+190h]
0x140003a85  jmp     short loc_140003A8D
0x140003a87  mov     [rax], bp
0x140003a8a  add     rax, rbp
0x140003a8d  cmp     rax, rcx
0x140003a90  jnz     short loc_140003A87
0x140003a92  mov     r9, [rbx+18h]
0x140003a96  test    r9, r9
0x140003a99  jz      short loc_140003B0A
0x140003a9b  test    esi, esi
0x140003a9d  jz      short loc_140003AD0
0x140003a9f  movzx   eax, word ptr [rbx+20h]
0x140003aa3  mov     rcx, r9
0x140003aa6  lea     rdx, [rax+rax*4]
0x140003aaa  shl     rdx, 4
0x140003aae  add     rdx, r9
0x140003ab1  cmp     r9, rdx
0x140003ab4  jz      short loc_140003AD0
0x140003ab6  mov     r8d, [rbx+10h]
0x140003aba  cmp     [rcx+4], r8d
0x140003abe  jbe     short loc_140003AC8
0x140003ac0  mov     eax, [rdi+8]
0x140003ac3  cmp     [rcx+8], eax
0x140003ac6  jz      short loc_140003B0A
0x140003ac8  add     rcx, rbp
0x140003acb  cmp     rcx, rdx
0x140003ace  jnz     short loc_140003ABA
0x140003ad0  movzx   eax, word ptr [rbx+22h]
0x140003ad4  xor     edx, edx
0x140003ad6  movzx   ecx, word ptr [rbx+20h]
0x140003ada  inc     eax
0x140003adc  div     ecx
0x140003ade  mov     rax, [rbx+8]
0x140003ae2  mov     r8d, 1
0x140003ae8  mov     [rbx+22h], dx
0x140003aec  lock xadd [rax], r8d
0x140003af1  movzx   eax, dx
0x140003af4  inc     r8d; unsigned int
0x140003af7  mov     rdx, rdi; struct wil::FailureInfo *
0x140003afa  lea     rcx, [rax+rax*4]
0x140003afe  shl     rcx, 4
0x140003b02  add     rcx, r9; this
0x140003b05  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140003b0a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003b14  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140003b1b  add     rsp, 20h
0x140003b1f  pop     r14
0x140003b21  pop     rdi
0x140003b22  pop     rsi
0x140003b23  pop     rbp
0x140003b24  pop     rbx
0x140003b25  retn
```
