# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180020aa0`
- end: `0x180020bde`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `318`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800206b0`
- `0x1800208ec`
- `0x1800209a4`
- `0x180020aa0`
- `0x180027910`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180020ad4`
- `KERNEL32!GetCurrentThreadId` at `0x180020b73`
- `KERNEL32!GetCurrentThreadId` at `0x180020ad4`
- `KERNEL32!GetCurrentThreadId` at `0x180020b73`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  unsigned __int64 CurrentThreadId; // r10
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
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xA)); i; i = *(_QWORD *)(i + 16) )
    {
      if ( *(_DWORD *)(i + 8) == (_DWORD)CurrentThreadId )
        goto LABEL_7;
    }
  }
  i = 0;
LABEL_7:
  if ( i && *(_QWORD *)i )
  {
    *(_BYTE *)a2 = 0;
    if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
           this,
           *(struct wil::details::ThreadFailureCallbackHolder **)i,
           (char *)a2,
           (unsigned __int64)a3) )
    {
      *((_QWORD *)this + 8) = a2;
    }
    v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
    do
    {
      v11 = (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), this);
      v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      v3 |= v11;
    }
    while ( v10 );
  }
  if ( wil::details::g_pfnTelemetryCallback )
    wil::details::g_pfnTelemetryCallback(v3, this);
  v12 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v12 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v12;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14, v13);
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, this);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x180020aa0  mov     rax, rsp
0x180020aa3  mov     [rax+8], rbx
0x180020aa7  mov     [rax+10h], rbp
0x180020aab  mov     [rax+18h], rsi
0x180020aaf  mov     [rax+20h], rdi
0x180020ab3  push    r14
0x180020ab5  sub     rsp, 20h
0x180020ab9  mov     byte ptr [rdx], 0
0x180020abc  xor     bpl, bpl
0x180020abf  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180020ac6  mov     r14, r8
0x180020ac9  mov     rsi, rdx
0x180020acc  mov     rdi, rcx
0x180020acf  test    rbx, rbx
0x180020ad2  jz      short loc_180020B10
0x180020ad4  call    cs:__imp_GetCurrentThreadId
0x180020ada  mov     r9d, eax
0x180020add  mov     r10d, eax
0x180020ae0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180020aea  mul     r10
0x180020aed  shr     rdx, 3
0x180020af1  lea     rcx, [rdx+rdx*4]
0x180020af5  add     rcx, rcx
0x180020af8  sub     r9, rcx
0x180020afb  mov     rbx, [rbx+r9*8]
0x180020aff  jmp     short loc_180020B0B
0x180020b01  cmp     [rbx+8], r10d
0x180020b05  jz      short loc_180020B12
0x180020b07  mov     rbx, [rbx+10h]
0x180020b0b  test    rbx, rbx
0x180020b0e  jnz     short loc_180020B01
0x180020b10  xor     ebx, ebx
0x180020b12  test    rbx, rbx
0x180020b15  jz      short loc_180020B5B
0x180020b17  cmp     qword ptr [rbx], 0
0x180020b1b  jz      short loc_180020B5B
0x180020b1d  mov     byte ptr [rsi], 0
0x180020b20  mov     r9, r14; unsigned __int64
0x180020b23  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180020b26  mov     r8, rsi; char *
0x180020b29  mov     rcx, rdi; struct wil::FailureInfo *
0x180020b2c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180020b31  test    al, al
0x180020b33  jz      short loc_180020B39
0x180020b35  mov     [rdi+40h], rsi
0x180020b39  mov     rbx, [rbx]
0x180020b3c  mov     rcx, [rbx+8]
0x180020b40  mov     rdx, rdi
0x180020b43  mov     rax, [rcx]
0x180020b46  mov     rax, [rax]
0x180020b49  call    cs:__guard_dispatch_icall_fptr
0x180020b4f  mov     rbx, [rbx+10h]
0x180020b53  or      bpl, al
0x180020b56  test    rbx, rbx
0x180020b59  jnz     short loc_180020B3C
0x180020b5b  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@ZEA; void (*wil::details::g_pfnTelemetryCallback)(bool,wil::FailureInfo const &)
0x180020b62  test    rax, rax
0x180020b65  jz      short loc_180020B73
0x180020b67  mov     rdx, rdi
0x180020b6a  mov     cl, bpl
0x180020b6d  call    cs:__guard_dispatch_icall_fptr
0x180020b73  call    cs:__imp_GetCurrentThreadId
0x180020b79  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180020b7f  cmp     ecx, eax
0x180020b81  jz      short loc_180020BC3
0x180020b83  mov     ecx, 1
0x180020b88  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180020b90  inc     ecx; this
0x180020b92  cmp     ecx, 4
0x180020b95  jge     short loc_180020BBC
0x180020b97  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180020b9d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180020ba2  test    rax, rax
0x180020ba5  jz      short loc_180020BB2
0x180020ba7  mov     rdx, rdi; struct wil::FailureInfo *
0x180020baa  mov     rcx, rax; this
0x180020bad  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180020bb2  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180020bbc  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180020bc3  mov     rbx, [rsp+28h+arg_0]
0x180020bc8  mov     rbp, [rsp+28h+arg_8]
0x180020bcd  mov     rsi, [rsp+28h+arg_10]
0x180020bd2  mov     rdi, [rsp+28h+arg_18]
0x180020bd7  add     rsp, 20h
0x180020bdb  pop     r14
0x180020bdd  retn
```
