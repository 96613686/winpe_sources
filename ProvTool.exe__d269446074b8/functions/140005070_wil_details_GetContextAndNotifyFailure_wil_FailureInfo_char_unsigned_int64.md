# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140005070`
- end: `0x1400051b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140005070`
- `0x1400056ac`
- `0x140005790`
- `0x140007df8`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000509a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000515c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000509a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000515c`

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
0x140005070  push    rbx
0x140005072  push    rbp
0x140005073  push    rsi
0x140005074  push    rdi
0x140005075  push    r14
0x140005077  sub     rsp, 20h
0x14000507b  mov     r14, r8
0x14000507e  mov     rsi, rdx
0x140005081  mov     rdi, rcx
0x140005084  mov     byte ptr [rdx], 0
0x140005087  xor     bpl, bpl
0x14000508a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140005091  test    rbx, rbx
0x140005094  jz      loc_140005130
0x14000509a  call    cs:__imp_GetCurrentThreadId
0x1400050a0  mov     r9d, eax
0x1400050a3  mov     r8d, eax
0x1400050a6  shr     r8, 2
0x1400050aa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400050b4  mul     r8
0x1400050b7  shr     rdx, 3
0x1400050bb  lea     rcx, [rdx+rdx*4]
0x1400050bf  add     rcx, rcx
0x1400050c2  sub     r8, rcx
0x1400050c5  mov     rbx, [rbx+r8*8]
0x1400050c9  jmp     short loc_1400050D4
0x1400050cb  cmp     [rbx], r9d
0x1400050ce  jz      short loc_14000514B
0x1400050d0  mov     rbx, [rbx+8]
0x1400050d4  test    rbx, rbx
0x1400050d7  jnz     short loc_1400050CB
0x1400050d9  test    rbx, rbx
0x1400050dc  jz      short loc_140005130
0x1400050de  cmp     qword ptr [rbx], 0
0x1400050e2  jz      short loc_140005130
0x1400050e4  mov     [rsi], bpl
0x1400050e7  mov     r9, r14; unsigned __int64
0x1400050ea  mov     r8, rsi; char *
0x1400050ed  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400050f0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400050f3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400050f8  test    al, al
0x1400050fa  jz      short loc_140005100
0x1400050fc  mov     [rdi+48h], rsi
0x140005100  mov     rbx, [rbx]
0x140005103  mov     al, [rbx+28h]
0x140005106  mov     byte ptr [rbx+28h], 1
0x14000510a  test    al, al
0x14000510c  jnz     short loc_140005127
0x14000510e  mov     rcx, [rbx+8]
0x140005112  mov     rax, [rcx]
0x140005115  mov     rdx, rdi
0x140005118  mov     rax, [rax]
0x14000511b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005120  or      bpl, al
0x140005123  mov     byte ptr [rbx+28h], 0
0x140005127  mov     rbx, [rbx+10h]
0x14000512b  test    rbx, rbx
0x14000512e  jnz     short loc_140005103
0x140005130  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140005137  test    rax, rax
0x14000513a  jz      short loc_14000515C
0x14000513c  test    bpl, bpl
0x14000513f  jnz     short loc_140005151
0x140005141  test    byte ptr [rdi+4], 2
0x140005145  jnz     short loc_140005151
0x140005147  xor     ecx, ecx
0x140005149  jmp     short loc_140005153
0x14000514b  add     rbx, 10h
0x14000514f  jmp     short loc_1400050D9
0x140005151  mov     cl, 1
0x140005153  mov     rdx, rdi
0x140005156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000515b  nop
0x14000515c  call    cs:__imp_GetCurrentThreadId
0x140005162  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005168  cmp     ecx, eax
0x14000516a  jz      short loc_1400051AC
0x14000516c  mov     ecx, 1
0x140005171  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140005179  inc     ecx; this
0x14000517b  cmp     ecx, 4
0x14000517e  jge     short loc_1400051A5
0x140005180  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005186  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000518b  test    rax, rax
0x14000518e  jz      short loc_14000519B
0x140005190  mov     rdx, rdi; struct wil::FailureInfo *
0x140005193  mov     rcx, rax; this
0x140005196  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x14000519b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400051a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400051ac  add     rsp, 20h
0x1400051b0  pop     r14
0x1400051b2  pop     rdi
0x1400051b3  pop     rsi
0x1400051b4  pop     rbp
0x1400051b5  pop     rbx
0x1400051b6  retn
```
