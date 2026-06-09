# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800049f0`
- end: `0x180004bf7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800049f0`
- `0x180005190`
- `0x180005274`
- `0x180005bac`
- `0x180006304`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004adc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004adc`

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
0x1800049f0  push    rbx
0x1800049f2  push    rbp
0x1800049f3  push    rsi
0x1800049f4  push    rdi
0x1800049f5  push    r14
0x1800049f7  sub     rsp, 20h
0x1800049fb  mov     r14, r8
0x1800049fe  mov     rsi, rdx
0x180004a01  mov     rdi, rcx
0x180004a04  mov     byte ptr [rdx], 0
0x180004a07  xor     bpl, bpl
0x180004a0a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004a11  test    rbx, rbx
0x180004a14  jz      loc_180004AB0
0x180004a1a  call    cs:__imp_GetCurrentThreadId
0x180004a20  mov     r9d, eax
0x180004a23  mov     r8d, eax
0x180004a26  shr     r8, 2
0x180004a2a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004a34  mul     r8
0x180004a37  shr     rdx, 3
0x180004a3b  lea     rcx, [rdx+rdx*4]
0x180004a3f  add     rcx, rcx
0x180004a42  sub     r8, rcx
0x180004a45  mov     rbx, [rbx+r8*8]
0x180004a49  jmp     short loc_180004A54
0x180004a4b  cmp     [rbx], r9d
0x180004a4e  jz      short loc_180004ACB
0x180004a50  mov     rbx, [rbx+8]
0x180004a54  test    rbx, rbx
0x180004a57  jnz     short loc_180004A4B
0x180004a59  test    rbx, rbx
0x180004a5c  jz      short loc_180004AB0
0x180004a5e  cmp     qword ptr [rbx], 0
0x180004a62  jz      short loc_180004AB0
0x180004a64  mov     [rsi], bpl
0x180004a67  mov     r9, r14; unsigned __int64
0x180004a6a  mov     r8, rsi; char *
0x180004a6d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004a70  mov     rcx, rdi; struct wil::FailureInfo *
0x180004a73  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004a78  test    al, al
0x180004a7a  jz      short loc_180004A80
0x180004a7c  mov     [rdi+48h], rsi
0x180004a80  mov     rbx, [rbx]
0x180004a83  mov     al, [rbx+28h]
0x180004a86  mov     byte ptr [rbx+28h], 1
0x180004a8a  test    al, al
0x180004a8c  jnz     short loc_180004AA7
0x180004a8e  mov     rcx, [rbx+8]
0x180004a92  mov     rax, [rcx]
0x180004a95  mov     rdx, rdi
0x180004a98  mov     rax, [rax]
0x180004a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa0  or      bpl, al
0x180004aa3  mov     byte ptr [rbx+28h], 0
0x180004aa7  mov     rbx, [rbx+10h]
0x180004aab  test    rbx, rbx
0x180004aae  jnz     short loc_180004A83
0x180004ab0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004ab7  test    rax, rax
0x180004aba  jz      short loc_180004ADC
0x180004abc  test    bpl, bpl
0x180004abf  jnz     short loc_180004AD1
0x180004ac1  test    byte ptr [rdi+4], 2
0x180004ac5  jnz     short loc_180004AD1
0x180004ac7  xor     ecx, ecx
0x180004ac9  jmp     short loc_180004AD3
0x180004acb  add     rbx, 10h
0x180004acf  jmp     short loc_180004A59
0x180004ad1  mov     cl, 1
0x180004ad3  mov     rdx, rdi
0x180004ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004adb  nop
0x180004adc  call    cs:__imp_GetCurrentThreadId
0x180004ae2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004ae8  cmp     ecx, eax
0x180004aea  jz      loc_180004BEC
0x180004af0  mov     ecx, 1
0x180004af5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004afd  inc     ecx; this
0x180004aff  cmp     ecx, 4
0x180004b02  jge     loc_180004BE5
0x180004b08  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004b0e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004b13  mov     rbx, rax
0x180004b16  test    rax, rax
0x180004b19  jz      loc_180004BDB
0x180004b1f  mov     esi, [rax+10h]
0x180004b22  mov     ebp, 50h ; 'P'
0x180004b27  cmp     qword ptr [rax+18h], 0
0x180004b2c  jnz     short loc_180004B63
0x180004b2e  test    esi, esi
0x180004b30  jz      short loc_180004B63
0x180004b32  mov     edx, 190h; dwBytes
0x180004b37  lea     ecx, [rbp-48h]; dwFlags
0x180004b3a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004b3f  mov     [rbx+18h], rax
0x180004b43  test    rax, rax
0x180004b46  jz      short loc_180004B63
0x180004b48  mov     dword ptr [rbx+20h], 5
0x180004b4f  lea     rcx, [rax+190h]
0x180004b56  jmp     short loc_180004B5E
0x180004b58  mov     [rax], bp
0x180004b5b  add     rax, rbp
0x180004b5e  cmp     rax, rcx
0x180004b61  jnz     short loc_180004B58
0x180004b63  mov     r9, [rbx+18h]
0x180004b67  test    r9, r9
0x180004b6a  jz      short loc_180004BDB
0x180004b6c  test    esi, esi
0x180004b6e  jz      short loc_180004BA1
0x180004b70  mov     rcx, r9
0x180004b73  movzx   eax, word ptr [rbx+20h]
0x180004b77  lea     rdx, [rax+rax*4]
0x180004b7b  shl     rdx, 4
0x180004b7f  add     rdx, r9
0x180004b82  cmp     r9, rdx
0x180004b85  jz      short loc_180004BA1
0x180004b87  mov     r8d, [rbx+10h]
0x180004b8b  cmp     [rcx+4], r8d
0x180004b8f  jbe     short loc_180004B99
0x180004b91  mov     eax, [rdi+8]
0x180004b94  cmp     [rcx+8], eax
0x180004b97  jz      short loc_180004BDB
0x180004b99  add     rcx, rbp
0x180004b9c  cmp     rcx, rdx
0x180004b9f  jnz     short loc_180004B8B
0x180004ba1  movzx   eax, word ptr [rbx+22h]
0x180004ba5  inc     eax
0x180004ba7  movzx   ecx, word ptr [rbx+20h]
0x180004bab  xor     edx, edx
0x180004bad  div     ecx
0x180004baf  mov     [rbx+22h], dx
0x180004bb3  mov     rax, [rbx+8]
0x180004bb7  mov     r8d, 1
0x180004bbd  lock xadd [rax], r8d
0x180004bc2  inc     r8d; unsigned int
0x180004bc5  movzx   eax, dx
0x180004bc8  lea     rcx, [rax+rax*4]
0x180004bcc  shl     rcx, 4
0x180004bd0  add     rcx, r9; this
0x180004bd3  mov     rdx, rdi; struct wil::FailureInfo *
0x180004bd6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004bdb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004be5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004bec  add     rsp, 20h
0x180004bf0  pop     r14
0x180004bf2  pop     rdi
0x180004bf3  pop     rsi
0x180004bf4  pop     rbp
0x180004bf5  pop     rbx
0x180004bf6  retn
```
