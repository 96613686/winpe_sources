# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003e20`
- end: `0x180004027`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003e20`
- `0x180004510`
- `0x1800045f4`
- `0x180004e58`
- `0x180005340`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f0c`

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
0x180003e20  push    rbx
0x180003e22  push    rbp
0x180003e23  push    rsi
0x180003e24  push    rdi
0x180003e25  push    r14
0x180003e27  sub     rsp, 20h
0x180003e2b  mov     r14, r8
0x180003e2e  mov     rsi, rdx
0x180003e31  mov     rdi, rcx
0x180003e34  mov     byte ptr [rdx], 0
0x180003e37  xor     bpl, bpl
0x180003e3a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003e41  test    rbx, rbx
0x180003e44  jz      loc_180003EE0
0x180003e4a  call    cs:__imp_GetCurrentThreadId
0x180003e50  mov     r9d, eax
0x180003e53  mov     r8d, eax
0x180003e56  shr     r8, 2
0x180003e5a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003e64  mul     r8
0x180003e67  shr     rdx, 3
0x180003e6b  lea     rcx, [rdx+rdx*4]
0x180003e6f  add     rcx, rcx
0x180003e72  sub     r8, rcx
0x180003e75  mov     rbx, [rbx+r8*8]
0x180003e79  jmp     short loc_180003E84
0x180003e7b  cmp     [rbx], r9d
0x180003e7e  jz      short loc_180003EFB
0x180003e80  mov     rbx, [rbx+8]
0x180003e84  test    rbx, rbx
0x180003e87  jnz     short loc_180003E7B
0x180003e89  test    rbx, rbx
0x180003e8c  jz      short loc_180003EE0
0x180003e8e  cmp     qword ptr [rbx], 0
0x180003e92  jz      short loc_180003EE0
0x180003e94  mov     [rsi], bpl
0x180003e97  mov     r9, r14; unsigned __int64
0x180003e9a  mov     r8, rsi; char *
0x180003e9d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003ea0  mov     rcx, rdi; struct wil::FailureInfo *
0x180003ea3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003ea8  test    al, al
0x180003eaa  jz      short loc_180003EB0
0x180003eac  mov     [rdi+48h], rsi
0x180003eb0  mov     rbx, [rbx]
0x180003eb3  mov     al, [rbx+28h]
0x180003eb6  mov     byte ptr [rbx+28h], 1
0x180003eba  test    al, al
0x180003ebc  jnz     short loc_180003ED7
0x180003ebe  mov     rcx, [rbx+8]
0x180003ec2  mov     rax, [rcx]
0x180003ec5  mov     rdx, rdi
0x180003ec8  mov     rax, [rax]
0x180003ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ed0  or      bpl, al
0x180003ed3  mov     byte ptr [rbx+28h], 0
0x180003ed7  mov     rbx, [rbx+10h]
0x180003edb  test    rbx, rbx
0x180003ede  jnz     short loc_180003EB3
0x180003ee0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003ee7  test    rax, rax
0x180003eea  jz      short loc_180003F0C
0x180003eec  test    bpl, bpl
0x180003eef  jnz     short loc_180003F01
0x180003ef1  test    byte ptr [rdi+4], 2
0x180003ef5  jnz     short loc_180003F01
0x180003ef7  xor     ecx, ecx
0x180003ef9  jmp     short loc_180003F03
0x180003efb  add     rbx, 10h
0x180003eff  jmp     short loc_180003E89
0x180003f01  mov     cl, 1
0x180003f03  mov     rdx, rdi
0x180003f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f0b  nop
0x180003f0c  call    cs:__imp_GetCurrentThreadId
0x180003f12  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003f18  cmp     ecx, eax
0x180003f1a  jz      loc_18000401C
0x180003f20  mov     ecx, 1
0x180003f25  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003f2d  inc     ecx; this
0x180003f2f  cmp     ecx, 4
0x180003f32  jge     loc_180004015
0x180003f38  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003f3e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003f43  mov     rbx, rax
0x180003f46  test    rax, rax
0x180003f49  jz      loc_18000400B
0x180003f4f  mov     esi, [rax+10h]
0x180003f52  mov     ebp, 50h ; 'P'
0x180003f57  cmp     qword ptr [rax+18h], 0
0x180003f5c  jnz     short loc_180003F93
0x180003f5e  test    esi, esi
0x180003f60  jz      short loc_180003F93
0x180003f62  mov     edx, 190h; dwBytes
0x180003f67  lea     ecx, [rbp-48h]; dwFlags
0x180003f6a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003f6f  mov     [rbx+18h], rax
0x180003f73  test    rax, rax
0x180003f76  jz      short loc_180003F93
0x180003f78  mov     dword ptr [rbx+20h], 5
0x180003f7f  lea     rcx, [rax+190h]
0x180003f86  jmp     short loc_180003F8E
0x180003f88  mov     [rax], bp
0x180003f8b  add     rax, rbp
0x180003f8e  cmp     rax, rcx
0x180003f91  jnz     short loc_180003F88
0x180003f93  mov     r9, [rbx+18h]
0x180003f97  test    r9, r9
0x180003f9a  jz      short loc_18000400B
0x180003f9c  test    esi, esi
0x180003f9e  jz      short loc_180003FD1
0x180003fa0  mov     rcx, r9
0x180003fa3  movzx   eax, word ptr [rbx+20h]
0x180003fa7  lea     rdx, [rax+rax*4]
0x180003fab  shl     rdx, 4
0x180003faf  add     rdx, r9
0x180003fb2  cmp     r9, rdx
0x180003fb5  jz      short loc_180003FD1
0x180003fb7  mov     r8d, [rbx+10h]
0x180003fbb  cmp     [rcx+4], r8d
0x180003fbf  jbe     short loc_180003FC9
0x180003fc1  mov     eax, [rdi+8]
0x180003fc4  cmp     [rcx+8], eax
0x180003fc7  jz      short loc_18000400B
0x180003fc9  add     rcx, rbp
0x180003fcc  cmp     rcx, rdx
0x180003fcf  jnz     short loc_180003FBB
0x180003fd1  movzx   eax, word ptr [rbx+22h]
0x180003fd5  inc     eax
0x180003fd7  movzx   ecx, word ptr [rbx+20h]
0x180003fdb  xor     edx, edx
0x180003fdd  div     ecx
0x180003fdf  mov     [rbx+22h], dx
0x180003fe3  mov     rax, [rbx+8]
0x180003fe7  mov     r8d, 1
0x180003fed  lock xadd [rax], r8d
0x180003ff2  inc     r8d; unsigned int
0x180003ff5  movzx   eax, dx
0x180003ff8  lea     rcx, [rax+rax*4]
0x180003ffc  shl     rcx, 4
0x180004000  add     rcx, r9; this
0x180004003  mov     rdx, rdi; struct wil::FailureInfo *
0x180004006  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000400b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004015  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000401c  add     rsp, 20h
0x180004020  pop     r14
0x180004022  pop     rdi
0x180004023  pop     rsi
0x180004024  pop     rbp
0x180004025  pop     rbx
0x180004026  retn
```
