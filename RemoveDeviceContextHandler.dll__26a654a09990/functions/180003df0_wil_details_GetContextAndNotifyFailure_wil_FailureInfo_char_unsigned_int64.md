# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003df0`
- end: `0x180003f36`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `326`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003df0`
- `0x1800044cc`
- `0x1800045b0`
- `0x180004e50`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003edb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003edb`

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
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

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
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v7);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x180003df0  push    rbx
0x180003df2  push    rbp
0x180003df3  push    rsi
0x180003df4  push    rdi
0x180003df5  push    r14
0x180003df7  sub     rsp, 20h
0x180003dfb  mov     byte ptr [rdx], 0
0x180003dfe  xor     bpl, bpl
0x180003e01  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003e08  mov     r14, r8
0x180003e0b  mov     rsi, rdx
0x180003e0e  mov     rdi, rcx
0x180003e11  test    rbx, rbx
0x180003e14  jz      loc_180003EB0
0x180003e1a  call    cs:__imp_GetCurrentThreadId
0x180003e20  mov     r8d, eax
0x180003e23  mov     r9d, eax
0x180003e26  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003e30  shr     r8, 2
0x180003e34  mul     r8
0x180003e37  shr     rdx, 3
0x180003e3b  lea     rcx, [rdx+rdx*4]
0x180003e3f  add     rcx, rcx
0x180003e42  sub     r8, rcx
0x180003e45  mov     rbx, [rbx+r8*8]
0x180003e49  jmp     short loc_180003E54
0x180003e4b  cmp     [rbx], r9d
0x180003e4e  jz      short loc_180003ECB
0x180003e50  mov     rbx, [rbx+8]
0x180003e54  test    rbx, rbx
0x180003e57  jnz     short loc_180003E4B
0x180003e59  test    rbx, rbx
0x180003e5c  jz      short loc_180003EB0
0x180003e5e  cmp     qword ptr [rbx], 0
0x180003e62  jz      short loc_180003EB0
0x180003e64  mov     [rsi], bpl
0x180003e67  mov     r9, r14; unsigned __int64
0x180003e6a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003e6d  mov     r8, rsi; char *
0x180003e70  mov     rcx, rdi; struct wil::FailureInfo *
0x180003e73  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003e78  test    al, al
0x180003e7a  jz      short loc_180003E80
0x180003e7c  mov     [rdi+48h], rsi
0x180003e80  mov     rbx, [rbx]
0x180003e83  mov     al, [rbx+28h]
0x180003e86  mov     byte ptr [rbx+28h], 1
0x180003e8a  test    al, al
0x180003e8c  jnz     short loc_180003EA7
0x180003e8e  mov     rcx, [rbx+8]
0x180003e92  mov     rdx, rdi
0x180003e95  mov     rax, [rcx]
0x180003e98  mov     rax, [rax]
0x180003e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea0  or      bpl, al
0x180003ea3  mov     byte ptr [rbx+28h], 0
0x180003ea7  mov     rbx, [rbx+10h]
0x180003eab  test    rbx, rbx
0x180003eae  jnz     short loc_180003E83
0x180003eb0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003eb7  test    rax, rax
0x180003eba  jz      short loc_180003EDB
0x180003ebc  test    bpl, bpl
0x180003ebf  jnz     short loc_180003ED1
0x180003ec1  test    byte ptr [rdi+4], 2
0x180003ec5  jnz     short loc_180003ED1
0x180003ec7  xor     ecx, ecx
0x180003ec9  jmp     short loc_180003ED3
0x180003ecb  add     rbx, 10h
0x180003ecf  jmp     short loc_180003E59
0x180003ed1  mov     cl, 1
0x180003ed3  mov     rdx, rdi
0x180003ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003edb  call    cs:__imp_GetCurrentThreadId
0x180003ee1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003ee7  cmp     ecx, eax
0x180003ee9  jz      short loc_180003F2B
0x180003eeb  mov     ecx, 1
0x180003ef0  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003ef8  inc     ecx; this
0x180003efa  cmp     ecx, 4
0x180003efd  jge     short loc_180003F24
0x180003eff  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003f05  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003f0a  test    rax, rax
0x180003f0d  jz      short loc_180003F1A
0x180003f0f  mov     rdx, rdi; struct wil::FailureInfo *
0x180003f12  mov     rcx, rax; this
0x180003f15  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180003f1a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003f24  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003f2b  add     rsp, 20h
0x180003f2f  pop     r14
0x180003f31  pop     rdi
0x180003f32  pop     rsi
0x180003f33  pop     rbp
0x180003f34  pop     rbx
0x180003f35  retn
```
