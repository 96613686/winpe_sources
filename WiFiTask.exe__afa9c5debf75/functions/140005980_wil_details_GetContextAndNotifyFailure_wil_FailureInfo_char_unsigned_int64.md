# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140005980`
- end: `0x140005b87`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140005980`
- `0x14000684c`
- `0x140006930`
- `0x140007d2c`
- `0x140009b4c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400059aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005a6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400059aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005a6c`

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
0x140005980  push    rbx
0x140005982  push    rbp
0x140005983  push    rsi
0x140005984  push    rdi
0x140005985  push    r14
0x140005987  sub     rsp, 20h
0x14000598b  mov     r14, r8
0x14000598e  mov     rsi, rdx
0x140005991  mov     rdi, rcx
0x140005994  mov     byte ptr [rdx], 0
0x140005997  xor     bpl, bpl
0x14000599a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400059a1  test    rbx, rbx
0x1400059a4  jz      loc_140005A40
0x1400059aa  call    cs:__imp_GetCurrentThreadId
0x1400059b0  mov     r9d, eax
0x1400059b3  mov     r8d, eax
0x1400059b6  shr     r8, 2
0x1400059ba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400059c4  mul     r8
0x1400059c7  shr     rdx, 3
0x1400059cb  lea     rcx, [rdx+rdx*4]
0x1400059cf  add     rcx, rcx
0x1400059d2  sub     r8, rcx
0x1400059d5  mov     rbx, [rbx+r8*8]
0x1400059d9  jmp     short loc_1400059E4
0x1400059db  cmp     [rbx], r9d
0x1400059de  jz      short loc_140005A5B
0x1400059e0  mov     rbx, [rbx+8]
0x1400059e4  test    rbx, rbx
0x1400059e7  jnz     short loc_1400059DB
0x1400059e9  test    rbx, rbx
0x1400059ec  jz      short loc_140005A40
0x1400059ee  cmp     qword ptr [rbx], 0
0x1400059f2  jz      short loc_140005A40
0x1400059f4  mov     [rsi], bpl
0x1400059f7  mov     r9, r14; unsigned __int64
0x1400059fa  mov     r8, rsi; char *
0x1400059fd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140005a00  mov     rcx, rdi; struct wil::FailureInfo *
0x140005a03  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005a08  test    al, al
0x140005a0a  jz      short loc_140005A10
0x140005a0c  mov     [rdi+48h], rsi
0x140005a10  mov     rbx, [rbx]
0x140005a13  mov     al, [rbx+28h]
0x140005a16  mov     byte ptr [rbx+28h], 1
0x140005a1a  test    al, al
0x140005a1c  jnz     short loc_140005A37
0x140005a1e  mov     rcx, [rbx+8]
0x140005a22  mov     rax, [rcx]
0x140005a25  mov     rdx, rdi
0x140005a28  mov     rax, [rax]
0x140005a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a30  or      bpl, al
0x140005a33  mov     byte ptr [rbx+28h], 0
0x140005a37  mov     rbx, [rbx+10h]
0x140005a3b  test    rbx, rbx
0x140005a3e  jnz     short loc_140005A13
0x140005a40  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140005a47  test    rax, rax
0x140005a4a  jz      short loc_140005A6C
0x140005a4c  test    bpl, bpl
0x140005a4f  jnz     short loc_140005A61
0x140005a51  test    byte ptr [rdi+4], 2
0x140005a55  jnz     short loc_140005A61
0x140005a57  xor     ecx, ecx
0x140005a59  jmp     short loc_140005A63
0x140005a5b  add     rbx, 10h
0x140005a5f  jmp     short loc_1400059E9
0x140005a61  mov     cl, 1
0x140005a63  mov     rdx, rdi
0x140005a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a6b  nop
0x140005a6c  call    cs:__imp_GetCurrentThreadId
0x140005a72  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005a78  cmp     ecx, eax
0x140005a7a  jz      loc_140005B7C
0x140005a80  mov     ecx, 1
0x140005a85  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140005a8d  inc     ecx; this
0x140005a8f  cmp     ecx, 4
0x140005a92  jge     loc_140005B75
0x140005a98  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005a9e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140005aa3  mov     rbx, rax
0x140005aa6  test    rax, rax
0x140005aa9  jz      loc_140005B6B
0x140005aaf  mov     esi, [rax+10h]
0x140005ab2  mov     ebp, 50h ; 'P'
0x140005ab7  cmp     qword ptr [rax+18h], 0
0x140005abc  jnz     short loc_140005AF3
0x140005abe  test    esi, esi
0x140005ac0  jz      short loc_140005AF3
0x140005ac2  mov     edx, 190h; dwBytes
0x140005ac7  lea     ecx, [rbp-48h]; dwFlags
0x140005aca  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005acf  mov     [rbx+18h], rax
0x140005ad3  test    rax, rax
0x140005ad6  jz      short loc_140005AF3
0x140005ad8  mov     dword ptr [rbx+20h], 5
0x140005adf  lea     rcx, [rax+190h]
0x140005ae6  jmp     short loc_140005AEE
0x140005ae8  mov     [rax], bp
0x140005aeb  add     rax, rbp
0x140005aee  cmp     rax, rcx
0x140005af1  jnz     short loc_140005AE8
0x140005af3  mov     r9, [rbx+18h]
0x140005af7  test    r9, r9
0x140005afa  jz      short loc_140005B6B
0x140005afc  test    esi, esi
0x140005afe  jz      short loc_140005B31
0x140005b00  mov     rcx, r9
0x140005b03  movzx   eax, word ptr [rbx+20h]
0x140005b07  lea     rdx, [rax+rax*4]
0x140005b0b  shl     rdx, 4
0x140005b0f  add     rdx, r9
0x140005b12  cmp     r9, rdx
0x140005b15  jz      short loc_140005B31
0x140005b17  mov     r8d, [rbx+10h]
0x140005b1b  cmp     [rcx+4], r8d
0x140005b1f  jbe     short loc_140005B29
0x140005b21  mov     eax, [rdi+8]
0x140005b24  cmp     [rcx+8], eax
0x140005b27  jz      short loc_140005B6B
0x140005b29  add     rcx, rbp
0x140005b2c  cmp     rcx, rdx
0x140005b2f  jnz     short loc_140005B1B
0x140005b31  movzx   eax, word ptr [rbx+22h]
0x140005b35  inc     eax
0x140005b37  movzx   ecx, word ptr [rbx+20h]
0x140005b3b  xor     edx, edx
0x140005b3d  div     ecx
0x140005b3f  mov     [rbx+22h], dx
0x140005b43  mov     rax, [rbx+8]
0x140005b47  mov     r8d, 1
0x140005b4d  lock xadd [rax], r8d
0x140005b52  inc     r8d; unsigned int
0x140005b55  movzx   eax, dx
0x140005b58  lea     rcx, [rax+rax*4]
0x140005b5c  shl     rcx, 4
0x140005b60  add     rcx, r9; this
0x140005b63  mov     rdx, rdi; struct wil::FailureInfo *
0x140005b66  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140005b6b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005b75  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140005b7c  add     rsp, 20h
0x140005b80  pop     r14
0x140005b82  pop     rdi
0x140005b83  pop     rsi
0x140005b84  pop     rbp
0x140005b85  pop     rbx
0x140005b86  retn
```
