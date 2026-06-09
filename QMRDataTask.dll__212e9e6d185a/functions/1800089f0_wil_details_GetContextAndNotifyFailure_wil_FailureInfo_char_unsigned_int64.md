# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800089f0`
- end: `0x180008b37`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800089f0`
- `0x18000a9e8`
- `0x18000aacc`
- `0x18000e810`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008a1a`
- `KERNEL32!GetCurrentThreadId` at `0x180008adc`
- `KERNEL32!GetCurrentThreadId` at `0x180008a1a`
- `KERNEL32!GetCurrentThreadId` at `0x180008adc`

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
0x1800089f0  push    rbx
0x1800089f2  push    rbp
0x1800089f3  push    rsi
0x1800089f4  push    rdi
0x1800089f5  push    r14
0x1800089f7  sub     rsp, 20h
0x1800089fb  mov     r14, r8
0x1800089fe  mov     rsi, rdx
0x180008a01  mov     rdi, rcx
0x180008a04  mov     byte ptr [rdx], 0
0x180008a07  xor     bpl, bpl
0x180008a0a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008a11  test    rbx, rbx
0x180008a14  jz      loc_180008AB0
0x180008a1a  call    cs:__imp_GetCurrentThreadId
0x180008a20  mov     r9d, eax
0x180008a23  mov     r8d, eax
0x180008a26  shr     r8, 2
0x180008a2a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008a34  mul     r8
0x180008a37  shr     rdx, 3
0x180008a3b  lea     rcx, [rdx+rdx*4]
0x180008a3f  add     rcx, rcx
0x180008a42  sub     r8, rcx
0x180008a45  mov     rbx, [rbx+r8*8]
0x180008a49  jmp     short loc_180008A54
0x180008a4b  cmp     [rbx], r9d
0x180008a4e  jz      short loc_180008ACB
0x180008a50  mov     rbx, [rbx+8]
0x180008a54  test    rbx, rbx
0x180008a57  jnz     short loc_180008A4B
0x180008a59  test    rbx, rbx
0x180008a5c  jz      short loc_180008AB0
0x180008a5e  cmp     qword ptr [rbx], 0
0x180008a62  jz      short loc_180008AB0
0x180008a64  mov     [rsi], bpl
0x180008a67  mov     r9, r14; unsigned __int64
0x180008a6a  mov     r8, rsi; char *
0x180008a6d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008a70  mov     rcx, rdi; struct wil::FailureInfo *
0x180008a73  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008a78  test    al, al
0x180008a7a  jz      short loc_180008A80
0x180008a7c  mov     [rdi+48h], rsi
0x180008a80  mov     rbx, [rbx]
0x180008a83  mov     al, [rbx+28h]
0x180008a86  mov     byte ptr [rbx+28h], 1
0x180008a8a  test    al, al
0x180008a8c  jnz     short loc_180008AA7
0x180008a8e  mov     rcx, [rbx+8]
0x180008a92  mov     rax, [rcx]
0x180008a95  mov     rdx, rdi
0x180008a98  mov     rax, [rax]
0x180008a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa0  or      bpl, al
0x180008aa3  mov     byte ptr [rbx+28h], 0
0x180008aa7  mov     rbx, [rbx+10h]
0x180008aab  test    rbx, rbx
0x180008aae  jnz     short loc_180008A83
0x180008ab0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008ab7  test    rax, rax
0x180008aba  jz      short loc_180008ADC
0x180008abc  test    bpl, bpl
0x180008abf  jnz     short loc_180008AD1
0x180008ac1  test    byte ptr [rdi+4], 2
0x180008ac5  jnz     short loc_180008AD1
0x180008ac7  xor     ecx, ecx
0x180008ac9  jmp     short loc_180008AD3
0x180008acb  add     rbx, 10h
0x180008acf  jmp     short loc_180008A59
0x180008ad1  mov     cl, 1
0x180008ad3  mov     rdx, rdi
0x180008ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008adb  nop
0x180008adc  call    cs:__imp_GetCurrentThreadId
0x180008ae2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008ae8  cmp     ecx, eax
0x180008aea  jz      short loc_180008B2C
0x180008aec  mov     ecx, 1
0x180008af1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008af9  inc     ecx; this
0x180008afb  cmp     ecx, 4
0x180008afe  jge     short loc_180008B25
0x180008b00  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008b06  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180008b0b  test    rax, rax
0x180008b0e  jz      short loc_180008B1B
0x180008b10  mov     rdx, rdi; struct wil::FailureInfo *
0x180008b13  mov     rcx, rax; this
0x180008b16  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180008b1b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008b25  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008b2c  add     rsp, 20h
0x180008b30  pop     r14
0x180008b32  pop     rdi
0x180008b33  pop     rsi
0x180008b34  pop     rbp
0x180008b35  pop     rbx
0x180008b36  retn
```
