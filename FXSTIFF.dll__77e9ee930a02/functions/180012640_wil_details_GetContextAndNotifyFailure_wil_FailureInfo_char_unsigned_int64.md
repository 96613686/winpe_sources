# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180012640`
- end: `0x180012794`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180012640`
- `0x180012cb8`
- `0x180012da4`
- `0x1800155a4`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001266a`
- `KERNEL32!GetCurrentThreadId` at `0x180012732`
- `KERNEL32!GetCurrentThreadId` at `0x18001266a`
- `KERNEL32!GetCurrentThreadId` at `0x180012732`

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
0x180012640  push    rbx
0x180012642  push    rbp
0x180012643  push    rsi
0x180012644  push    rdi
0x180012645  push    r14
0x180012647  sub     rsp, 20h
0x18001264b  mov     r14, r8
0x18001264e  mov     rsi, rdx
0x180012651  mov     rdi, rcx
0x180012654  mov     byte ptr [rdx], 0
0x180012657  xor     bpl, bpl
0x18001265a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012661  test    rbx, rbx
0x180012664  jz      loc_180012706
0x18001266a  call    cs:__imp_GetCurrentThreadId
0x180012671  nop     dword ptr [rax+rax+00h]
0x180012676  mov     r9d, eax
0x180012679  mov     r8d, eax
0x18001267c  shr     r8, 2
0x180012680  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001268a  mul     r8
0x18001268d  shr     rdx, 3
0x180012691  lea     rcx, [rdx+rdx*4]
0x180012695  add     rcx, rcx
0x180012698  sub     r8, rcx
0x18001269b  mov     rbx, [rbx+r8*8]
0x18001269f  jmp     short loc_1800126AA
0x1800126a1  cmp     [rbx], r9d
0x1800126a4  jz      short loc_180012721
0x1800126a6  mov     rbx, [rbx+8]
0x1800126aa  test    rbx, rbx
0x1800126ad  jnz     short loc_1800126A1
0x1800126af  test    rbx, rbx
0x1800126b2  jz      short loc_180012706
0x1800126b4  cmp     qword ptr [rbx], 0
0x1800126b8  jz      short loc_180012706
0x1800126ba  mov     [rsi], bpl
0x1800126bd  mov     r9, r14; unsigned __int64
0x1800126c0  mov     r8, rsi; char *
0x1800126c3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800126c6  mov     rcx, rdi; struct wil::FailureInfo *
0x1800126c9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800126ce  test    al, al
0x1800126d0  jz      short loc_1800126D6
0x1800126d2  mov     [rdi+48h], rsi
0x1800126d6  mov     rbx, [rbx]
0x1800126d9  mov     al, [rbx+28h]
0x1800126dc  mov     byte ptr [rbx+28h], 1
0x1800126e0  test    al, al
0x1800126e2  jnz     short loc_1800126FD
0x1800126e4  mov     rcx, [rbx+8]
0x1800126e8  mov     rax, [rcx]
0x1800126eb  mov     rdx, rdi
0x1800126ee  mov     rax, [rax]
0x1800126f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126f6  or      bpl, al
0x1800126f9  mov     byte ptr [rbx+28h], 0
0x1800126fd  mov     rbx, [rbx+10h]
0x180012701  test    rbx, rbx
0x180012704  jnz     short loc_1800126D9
0x180012706  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001270d  test    rax, rax
0x180012710  jz      short loc_180012732
0x180012712  test    bpl, bpl
0x180012715  jnz     short loc_180012727
0x180012717  test    byte ptr [rdi+4], 2
0x18001271b  jnz     short loc_180012727
0x18001271d  xor     ecx, ecx
0x18001271f  jmp     short loc_180012729
0x180012721  add     rbx, 10h
0x180012725  jmp     short loc_1800126AF
0x180012727  mov     cl, 1
0x180012729  mov     rdx, rdi
0x18001272c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012731  nop
0x180012732  call    cs:__imp_GetCurrentThreadId
0x180012739  nop     dword ptr [rax+rax+00h]
0x18001273e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180012744  cmp     ecx, eax
0x180012746  jz      short loc_180012788
0x180012748  mov     ecx, 1
0x18001274d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180012755  inc     ecx; this
0x180012757  cmp     ecx, 4
0x18001275a  jge     short loc_180012781
0x18001275c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180012762  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180012767  test    rax, rax
0x18001276a  jz      short loc_180012777
0x18001276c  mov     rdx, rdi; struct wil::FailureInfo *
0x18001276f  mov     rcx, rax; this
0x180012772  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180012777  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180012781  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180012788  add     rsp, 20h
0x18001278c  pop     r14
0x18001278e  pop     rdi
0x18001278f  pop     rsi
0x180012790  pop     rbp
0x180012791  pop     rbx
0x180012792  retn
```
