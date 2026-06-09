# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003910`
- end: `0x140003b1a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001714`
- `0x1400034ac`
- `0x14000374c`
- `0x14000380c`
- `0x140003910`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003942`
- `KERNEL32!GetCurrentThreadId` at `0x1400039f7`
- `KERNEL32!GetCurrentThreadId` at `0x140003942`
- `KERNEL32!GetCurrentThreadId` at `0x1400039f7`

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
0x140003910  mov     [rsp+arg_18], rbx
0x140003915  push    rbp
0x140003916  push    rsi
0x140003917  push    rdi
0x140003918  push    r14
0x14000391a  push    r15
0x14000391c  sub     rsp, 20h
0x140003920  mov     r14, r8
0x140003923  mov     rsi, rdx
0x140003926  mov     rdi, rcx
0x140003929  xor     r15d, r15d
0x14000392c  mov     [rdx], r15b
0x14000392f  mov     bpl, r15b
0x140003932  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003939  test    rbx, rbx
0x14000393c  jz      loc_1400039CB
0x140003942  call    cs:__imp_GetCurrentThreadId
0x140003948  mov     r9d, eax
0x14000394b  mov     r8d, eax
0x14000394e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003958  mul     r9
0x14000395b  shr     rdx, 3
0x14000395f  lea     rcx, [rdx+rdx*4]
0x140003963  add     rcx, rcx
0x140003966  sub     r8, rcx
0x140003969  mov     rbx, [rbx+r8*8]
0x14000396d  jmp     short loc_14000397C
0x14000396f  cmp     [rbx], r9d
0x140003972  jz      loc_140003A71
0x140003978  mov     rbx, [rbx+8]
0x14000397c  test    rbx, rbx
0x14000397f  jnz     short loc_14000396F
0x140003981  mov     rbx, r15
0x140003984  test    rbx, rbx
0x140003987  jz      short loc_1400039CB
0x140003989  cmp     [rbx], r15
0x14000398c  jz      short loc_1400039CB
0x14000398e  mov     [rsi], r15b
0x140003991  mov     r9, r14; unsigned __int64
0x140003994  mov     r8, rsi; char *
0x140003997  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000399a  mov     rcx, rdi; struct wil::FailureInfo *
0x14000399d  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400039a2  test    al, al
0x1400039a4  jz      short loc_1400039AA
0x1400039a6  mov     [rdi+48h], rsi
0x1400039aa  mov     rbx, [rbx]
0x1400039ad  mov     rcx, [rbx+8]
0x1400039b1  mov     rax, [rcx]
0x1400039b4  mov     rdx, rdi
0x1400039b7  mov     rax, [rax]
0x1400039ba  call    _guard_dispatch_icall
0x1400039bf  or      bpl, al
0x1400039c2  mov     rbx, [rbx+10h]
0x1400039c6  test    rbx, rbx
0x1400039c9  jnz     short loc_1400039AD
0x1400039cb  mov     r14d, 1
0x1400039d1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400039d8  test    rax, rax
0x1400039db  jz      short loc_1400039F7
0x1400039dd  test    bpl, bpl
0x1400039e0  jnz     short loc_1400039EB
0x1400039e2  test    byte ptr [rdi+4], 2
0x1400039e6  mov     cl, r15b
0x1400039e9  jz      short loc_1400039EE
0x1400039eb  mov     cl, r14b
0x1400039ee  mov     rdx, rdi
0x1400039f1  call    _guard_dispatch_icall
0x1400039f6  nop
0x1400039f7  call    cs:__imp_GetCurrentThreadId
0x1400039fd  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003a03  cmp     ecx, eax
0x140003a05  jz      loc_140003B09
0x140003a0b  mov     ecx, r14d
0x140003a0e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140003a16  add     ecx, r14d; this
0x140003a19  cmp     ecx, 4
0x140003a1c  jge     loc_140003B02
0x140003a22  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003a28  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140003a2d  mov     rbx, rax
0x140003a30  test    rax, rax
0x140003a33  jz      loc_140003AFB
0x140003a39  mov     esi, [rax+10h]
0x140003a3c  mov     ebp, 50h ; 'P'
0x140003a41  cmp     [rax+18h], r15
0x140003a45  jnz     short loc_140003A85
0x140003a47  test    esi, esi
0x140003a49  jz      short loc_140003A85
0x140003a4b  mov     edx, 190h; dwBytes
0x140003a50  lea     ecx, [rbp-48h]; dwFlags
0x140003a53  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003a58  mov     [rbx+18h], rax
0x140003a5c  test    rax, rax
0x140003a5f  jz      short loc_140003A85
0x140003a61  mov     dword ptr [rbx+20h], 5
0x140003a68  lea     rcx, [rax+190h]
0x140003a6f  jmp     short loc_140003A80
0x140003a71  add     rbx, 10h
0x140003a75  jmp     loc_140003984
0x140003a7a  mov     [rax], bp
0x140003a7d  add     rax, rbp
0x140003a80  cmp     rax, rcx
0x140003a83  jnz     short loc_140003A7A
0x140003a85  mov     r9, [rbx+18h]
0x140003a89  test    r9, r9
0x140003a8c  jz      short loc_140003AFB
0x140003a8e  test    esi, esi
0x140003a90  jz      short loc_140003AC3
0x140003a92  mov     rcx, r9
0x140003a95  movzx   eax, word ptr [rbx+20h]
0x140003a99  lea     rdx, [rax+rax*4]
0x140003a9d  shl     rdx, 4
0x140003aa1  add     rdx, r9
0x140003aa4  cmp     r9, rdx
0x140003aa7  jz      short loc_140003AC3
0x140003aa9  mov     r8d, [rbx+10h]
0x140003aad  cmp     [rcx+4], r8d
0x140003ab1  jbe     short loc_140003ABB
0x140003ab3  mov     eax, [rdi+8]
0x140003ab6  cmp     [rcx+8], eax
0x140003ab9  jz      short loc_140003AFB
0x140003abb  add     rcx, rbp
0x140003abe  cmp     rcx, rdx
0x140003ac1  jnz     short loc_140003AAD
0x140003ac3  movzx   eax, word ptr [rbx+22h]
0x140003ac7  add     eax, r14d
0x140003aca  movzx   ecx, word ptr [rbx+20h]
0x140003ace  xor     edx, edx
0x140003ad0  div     ecx
0x140003ad2  mov     [rbx+22h], dx
0x140003ad6  mov     rax, [rbx+8]
0x140003ada  mov     r8d, r14d
0x140003add  lock xadd [rax], r8d
0x140003ae2  add     r8d, r14d; unsigned int
0x140003ae5  movzx   eax, dx
0x140003ae8  lea     rcx, [rax+rax*4]
0x140003aec  shl     rcx, 4
0x140003af0  add     rcx, r9; this
0x140003af3  mov     rdx, rdi; struct wil::FailureInfo *
0x140003af6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140003afb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003b02  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140003b09  mov     rbx, [rsp+48h+arg_18]
0x140003b0e  add     rsp, 20h
0x140003b12  pop     r15
0x140003b14  pop     r14
0x140003b16  pop     rdi
0x140003b17  pop     rsi
0x140003b18  pop     rbp
0x140003b19  retn
```
