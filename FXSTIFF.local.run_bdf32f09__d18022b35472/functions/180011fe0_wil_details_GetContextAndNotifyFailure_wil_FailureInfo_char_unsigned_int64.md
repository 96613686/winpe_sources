# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180011fe0`
- end: `0x180012127`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180011fe0`
- `0x18001261c`
- `0x180012700`
- `0x180014c60`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001200a`
- `KERNEL32!GetCurrentThreadId` at `0x1800120cc`
- `KERNEL32!GetCurrentThreadId` at `0x18001200a`
- `KERNEL32!GetCurrentThreadId` at `0x1800120cc`

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
0x180011fe0  push    rbx
0x180011fe2  push    rbp
0x180011fe3  push    rsi
0x180011fe4  push    rdi
0x180011fe5  push    r14
0x180011fe7  sub     rsp, 20h
0x180011feb  mov     r14, r8
0x180011fee  mov     rsi, rdx
0x180011ff1  mov     rdi, rcx
0x180011ff4  mov     byte ptr [rdx], 0
0x180011ff7  xor     bpl, bpl
0x180011ffa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012001  test    rbx, rbx
0x180012004  jz      loc_1800120A0
0x18001200a  call    cs:__imp_GetCurrentThreadId
0x180012010  mov     r9d, eax
0x180012013  mov     r8d, eax
0x180012016  shr     r8, 2
0x18001201a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180012024  mul     r8
0x180012027  shr     rdx, 3
0x18001202b  lea     rcx, [rdx+rdx*4]
0x18001202f  add     rcx, rcx
0x180012032  sub     r8, rcx
0x180012035  mov     rbx, [rbx+r8*8]
0x180012039  jmp     short loc_180012044
0x18001203b  cmp     [rbx], r9d
0x18001203e  jz      short loc_1800120BB
0x180012040  mov     rbx, [rbx+8]
0x180012044  test    rbx, rbx
0x180012047  jnz     short loc_18001203B
0x180012049  test    rbx, rbx
0x18001204c  jz      short loc_1800120A0
0x18001204e  cmp     qword ptr [rbx], 0
0x180012052  jz      short loc_1800120A0
0x180012054  mov     [rsi], bpl
0x180012057  mov     r9, r14; unsigned __int64
0x18001205a  mov     r8, rsi; char *
0x18001205d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180012060  mov     rcx, rdi; struct wil::FailureInfo *
0x180012063  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180012068  test    al, al
0x18001206a  jz      short loc_180012070
0x18001206c  mov     [rdi+48h], rsi
0x180012070  mov     rbx, [rbx]
0x180012073  mov     al, [rbx+28h]
0x180012076  mov     byte ptr [rbx+28h], 1
0x18001207a  test    al, al
0x18001207c  jnz     short loc_180012097
0x18001207e  mov     rcx, [rbx+8]
0x180012082  mov     rax, [rcx]
0x180012085  mov     rdx, rdi
0x180012088  mov     rax, [rax]
0x18001208b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012090  or      bpl, al
0x180012093  mov     byte ptr [rbx+28h], 0
0x180012097  mov     rbx, [rbx+10h]
0x18001209b  test    rbx, rbx
0x18001209e  jnz     short loc_180012073
0x1800120a0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800120a7  test    rax, rax
0x1800120aa  jz      short loc_1800120CC
0x1800120ac  test    bpl, bpl
0x1800120af  jnz     short loc_1800120C1
0x1800120b1  test    byte ptr [rdi+4], 2
0x1800120b5  jnz     short loc_1800120C1
0x1800120b7  xor     ecx, ecx
0x1800120b9  jmp     short loc_1800120C3
0x1800120bb  add     rbx, 10h
0x1800120bf  jmp     short loc_180012049
0x1800120c1  mov     cl, 1
0x1800120c3  mov     rdx, rdi
0x1800120c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120cb  nop
0x1800120cc  call    cs:__imp_GetCurrentThreadId
0x1800120d2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800120d8  cmp     ecx, eax
0x1800120da  jz      short loc_18001211C
0x1800120dc  mov     ecx, 1
0x1800120e1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800120e9  inc     ecx; this
0x1800120eb  cmp     ecx, 4
0x1800120ee  jge     short loc_180012115
0x1800120f0  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800120f6  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800120fb  test    rax, rax
0x1800120fe  jz      short loc_18001210B
0x180012100  mov     rdx, rdi; struct wil::FailureInfo *
0x180012103  mov     rcx, rax; this
0x180012106  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18001210b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180012115  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001211c  add     rsp, 20h
0x180012120  pop     r14
0x180012122  pop     rdi
0x180012123  pop     rsi
0x180012124  pop     rbp
0x180012125  pop     rbx
0x180012126  retn
```
