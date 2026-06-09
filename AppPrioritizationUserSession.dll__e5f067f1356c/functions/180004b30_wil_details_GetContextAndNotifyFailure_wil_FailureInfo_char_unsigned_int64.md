# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004b30`
- end: `0x180004d37`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004b30`
- `0x180005280`
- `0x180005364`
- `0x180005c44`
- `0x1800062b0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c1c`

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
0x180004b30  push    rbx
0x180004b32  push    rbp
0x180004b33  push    rsi
0x180004b34  push    rdi
0x180004b35  push    r14
0x180004b37  sub     rsp, 20h
0x180004b3b  mov     r14, r8
0x180004b3e  mov     rsi, rdx
0x180004b41  mov     rdi, rcx
0x180004b44  mov     byte ptr [rdx], 0
0x180004b47  xor     bpl, bpl
0x180004b4a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004b51  test    rbx, rbx
0x180004b54  jz      loc_180004BF0
0x180004b5a  call    cs:__imp_GetCurrentThreadId
0x180004b60  mov     r9d, eax
0x180004b63  mov     r8d, eax
0x180004b66  shr     r8, 2
0x180004b6a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004b74  mul     r8
0x180004b77  shr     rdx, 3
0x180004b7b  lea     rcx, [rdx+rdx*4]
0x180004b7f  add     rcx, rcx
0x180004b82  sub     r8, rcx
0x180004b85  mov     rbx, [rbx+r8*8]
0x180004b89  jmp     short loc_180004B94
0x180004b8b  cmp     [rbx], r9d
0x180004b8e  jz      short loc_180004C0B
0x180004b90  mov     rbx, [rbx+8]
0x180004b94  test    rbx, rbx
0x180004b97  jnz     short loc_180004B8B
0x180004b99  test    rbx, rbx
0x180004b9c  jz      short loc_180004BF0
0x180004b9e  cmp     qword ptr [rbx], 0
0x180004ba2  jz      short loc_180004BF0
0x180004ba4  mov     [rsi], bpl
0x180004ba7  mov     r9, r14; unsigned __int64
0x180004baa  mov     r8, rsi; char *
0x180004bad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004bb0  mov     rcx, rdi; struct wil::FailureInfo *
0x180004bb3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004bb8  test    al, al
0x180004bba  jz      short loc_180004BC0
0x180004bbc  mov     [rdi+48h], rsi
0x180004bc0  mov     rbx, [rbx]
0x180004bc3  mov     al, [rbx+28h]
0x180004bc6  mov     byte ptr [rbx+28h], 1
0x180004bca  test    al, al
0x180004bcc  jnz     short loc_180004BE7
0x180004bce  mov     rcx, [rbx+8]
0x180004bd2  mov     rax, [rcx]
0x180004bd5  mov     rdx, rdi
0x180004bd8  mov     rax, [rax]
0x180004bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be0  or      bpl, al
0x180004be3  mov     byte ptr [rbx+28h], 0
0x180004be7  mov     rbx, [rbx+10h]
0x180004beb  test    rbx, rbx
0x180004bee  jnz     short loc_180004BC3
0x180004bf0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004bf7  test    rax, rax
0x180004bfa  jz      short loc_180004C1C
0x180004bfc  test    bpl, bpl
0x180004bff  jnz     short loc_180004C11
0x180004c01  test    byte ptr [rdi+4], 2
0x180004c05  jnz     short loc_180004C11
0x180004c07  xor     ecx, ecx
0x180004c09  jmp     short loc_180004C13
0x180004c0b  add     rbx, 10h
0x180004c0f  jmp     short loc_180004B99
0x180004c11  mov     cl, 1
0x180004c13  mov     rdx, rdi
0x180004c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1b  nop
0x180004c1c  call    cs:__imp_GetCurrentThreadId
0x180004c22  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004c28  cmp     ecx, eax
0x180004c2a  jz      loc_180004D2C
0x180004c30  mov     ecx, 1
0x180004c35  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004c3d  inc     ecx; this
0x180004c3f  cmp     ecx, 4
0x180004c42  jge     loc_180004D25
0x180004c48  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004c4e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004c53  mov     rbx, rax
0x180004c56  test    rax, rax
0x180004c59  jz      loc_180004D1B
0x180004c5f  mov     esi, [rax+10h]
0x180004c62  mov     ebp, 50h ; 'P'
0x180004c67  cmp     qword ptr [rax+18h], 0
0x180004c6c  jnz     short loc_180004CA3
0x180004c6e  test    esi, esi
0x180004c70  jz      short loc_180004CA3
0x180004c72  mov     edx, 190h; dwBytes
0x180004c77  lea     ecx, [rbp-48h]; dwFlags
0x180004c7a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004c7f  mov     [rbx+18h], rax
0x180004c83  test    rax, rax
0x180004c86  jz      short loc_180004CA3
0x180004c88  mov     dword ptr [rbx+20h], 5
0x180004c8f  lea     rcx, [rax+190h]
0x180004c96  jmp     short loc_180004C9E
0x180004c98  mov     [rax], bp
0x180004c9b  add     rax, rbp
0x180004c9e  cmp     rax, rcx
0x180004ca1  jnz     short loc_180004C98
0x180004ca3  mov     r9, [rbx+18h]
0x180004ca7  test    r9, r9
0x180004caa  jz      short loc_180004D1B
0x180004cac  test    esi, esi
0x180004cae  jz      short loc_180004CE1
0x180004cb0  mov     rcx, r9
0x180004cb3  movzx   eax, word ptr [rbx+20h]
0x180004cb7  lea     rdx, [rax+rax*4]
0x180004cbb  shl     rdx, 4
0x180004cbf  add     rdx, r9
0x180004cc2  cmp     r9, rdx
0x180004cc5  jz      short loc_180004CE1
0x180004cc7  mov     r8d, [rbx+10h]
0x180004ccb  cmp     [rcx+4], r8d
0x180004ccf  jbe     short loc_180004CD9
0x180004cd1  mov     eax, [rdi+8]
0x180004cd4  cmp     [rcx+8], eax
0x180004cd7  jz      short loc_180004D1B
0x180004cd9  add     rcx, rbp
0x180004cdc  cmp     rcx, rdx
0x180004cdf  jnz     short loc_180004CCB
0x180004ce1  movzx   eax, word ptr [rbx+22h]
0x180004ce5  inc     eax
0x180004ce7  movzx   ecx, word ptr [rbx+20h]
0x180004ceb  xor     edx, edx
0x180004ced  div     ecx
0x180004cef  mov     [rbx+22h], dx
0x180004cf3  mov     rax, [rbx+8]
0x180004cf7  mov     r8d, 1
0x180004cfd  lock xadd [rax], r8d
0x180004d02  inc     r8d; unsigned int
0x180004d05  movzx   eax, dx
0x180004d08  lea     rcx, [rax+rax*4]
0x180004d0c  shl     rcx, 4
0x180004d10  add     rcx, r9; this
0x180004d13  mov     rdx, rdi; struct wil::FailureInfo *
0x180004d16  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004d1b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004d25  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004d2c  add     rsp, 20h
0x180004d30  pop     r14
0x180004d32  pop     rdi
0x180004d33  pop     rsi
0x180004d34  pop     rbp
0x180004d35  pop     rbx
0x180004d36  retn
```
