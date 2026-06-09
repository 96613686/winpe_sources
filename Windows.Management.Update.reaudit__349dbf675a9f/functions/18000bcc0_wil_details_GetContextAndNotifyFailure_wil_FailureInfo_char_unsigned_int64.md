# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000bcc0`
- end: `0x18000be2e`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `366`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000bcc0`
- `0x18000c358`
- `0x18000c450`
- `0x18000f49c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bcf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bdbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bcf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bdbc`

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
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * (CurrentThreadId % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v5);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x18000bcc0  mov     rax, rsp
0x18000bcc3  mov     [rax+8], rbx
0x18000bcc7  mov     [rax+10h], rbp
0x18000bccb  mov     [rax+18h], rsi
0x18000bccf  mov     [rax+20h], rdi
0x18000bcd3  push    r14
0x18000bcd5  sub     rsp, 20h
0x18000bcd9  mov     r14, r8
0x18000bcdc  mov     rsi, rdx
0x18000bcdf  mov     rdi, rcx
0x18000bce2  mov     byte ptr [rdx], 0
0x18000bce5  xor     bpl, bpl
0x18000bce8  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000bcef  test    rbx, rbx
0x18000bcf2  jz      loc_18000BD90
0x18000bcf8  call    cs:__imp_GetCurrentThreadId
0x18000bcff  nop     dword ptr [rax+rax+00h]
0x18000bd04  mov     r9d, eax
0x18000bd07  mov     r8d, eax
0x18000bd0a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000bd14  mul     r9
0x18000bd17  shr     rdx, 3
0x18000bd1b  lea     rcx, [rdx+rdx*4]
0x18000bd1f  add     rcx, rcx
0x18000bd22  sub     r8, rcx
0x18000bd25  mov     rbx, [rbx+r8*8]
0x18000bd29  jmp     short loc_18000BD34
0x18000bd2b  cmp     [rbx], r9d
0x18000bd2e  jz      short loc_18000BDAB
0x18000bd30  mov     rbx, [rbx+8]
0x18000bd34  test    rbx, rbx
0x18000bd37  jnz     short loc_18000BD2B
0x18000bd39  test    rbx, rbx
0x18000bd3c  jz      short loc_18000BD90
0x18000bd3e  cmp     qword ptr [rbx], 0
0x18000bd42  jz      short loc_18000BD90
0x18000bd44  mov     [rsi], bpl
0x18000bd47  mov     r9, r14; unsigned __int64
0x18000bd4a  mov     r8, rsi; char *
0x18000bd4d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000bd50  mov     rcx, rdi; struct wil::FailureInfo *
0x18000bd53  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000bd58  test    al, al
0x18000bd5a  jz      short loc_18000BD60
0x18000bd5c  mov     [rdi+48h], rsi
0x18000bd60  mov     rbx, [rbx]
0x18000bd63  mov     al, [rbx+28h]
0x18000bd66  mov     byte ptr [rbx+28h], 1
0x18000bd6a  test    al, al
0x18000bd6c  jnz     short loc_18000BD87
0x18000bd6e  mov     rcx, [rbx+8]
0x18000bd72  mov     rax, [rcx]
0x18000bd75  mov     rdx, rdi
0x18000bd78  mov     rax, [rax]
0x18000bd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd80  or      bpl, al
0x18000bd83  mov     byte ptr [rbx+28h], 0
0x18000bd87  mov     rbx, [rbx+10h]
0x18000bd8b  test    rbx, rbx
0x18000bd8e  jnz     short loc_18000BD63
0x18000bd90  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000bd97  test    rax, rax
0x18000bd9a  jz      short loc_18000BDBC
0x18000bd9c  test    bpl, bpl
0x18000bd9f  jnz     short loc_18000BDB1
0x18000bda1  test    byte ptr [rdi+4], 2
0x18000bda5  jnz     short loc_18000BDB1
0x18000bda7  xor     ecx, ecx
0x18000bda9  jmp     short loc_18000BDB3
0x18000bdab  add     rbx, 10h
0x18000bdaf  jmp     short loc_18000BD39
0x18000bdb1  mov     cl, 1
0x18000bdb3  mov     rdx, rdi
0x18000bdb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdbb  nop
0x18000bdbc  call    cs:__imp_GetCurrentThreadId
0x18000bdc3  nop     dword ptr [rax+rax+00h]
0x18000bdc8  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000bdce  cmp     ecx, eax
0x18000bdd0  jz      short loc_18000BE12
0x18000bdd2  mov     ecx, 1
0x18000bdd7  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000bddf  inc     ecx; this
0x18000bde1  cmp     ecx, 4
0x18000bde4  jge     short loc_18000BE0B
0x18000bde6  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000bdec  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000bdf1  test    rax, rax
0x18000bdf4  jz      short loc_18000BE01
0x18000bdf6  mov     rdx, rdi; struct wil::FailureInfo *
0x18000bdf9  mov     rcx, rax; this
0x18000bdfc  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000be01  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000be0b  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000be12  mov     rbx, [rsp+28h+arg_0]
0x18000be17  mov     rbp, [rsp+28h+arg_8]
0x18000be1c  mov     rsi, [rsp+28h+arg_10]
0x18000be21  mov     rdi, [rsp+28h+arg_18]
0x18000be26  add     rsp, 20h
0x18000be2a  pop     r14
0x18000be2c  retn
```
