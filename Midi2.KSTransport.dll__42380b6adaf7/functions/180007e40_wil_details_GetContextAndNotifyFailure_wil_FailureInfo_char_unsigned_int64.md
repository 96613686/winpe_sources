# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007e40`
- end: `0x180008047`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007e40`
- `0x180008550`
- `0x180008634`
- `0x180009368`
- `0x18000a8a0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f2c`

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
0x180007e40  push    rbx
0x180007e42  push    rbp
0x180007e43  push    rsi
0x180007e44  push    rdi
0x180007e45  push    r14
0x180007e47  sub     rsp, 20h
0x180007e4b  mov     r14, r8
0x180007e4e  mov     rsi, rdx
0x180007e51  mov     rdi, rcx
0x180007e54  mov     byte ptr [rdx], 0
0x180007e57  xor     bpl, bpl
0x180007e5a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007e61  test    rbx, rbx
0x180007e64  jz      loc_180007F00
0x180007e6a  call    cs:__imp_GetCurrentThreadId
0x180007e70  mov     r9d, eax
0x180007e73  mov     r8d, eax
0x180007e76  shr     r8, 2
0x180007e7a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007e84  mul     r8
0x180007e87  shr     rdx, 3
0x180007e8b  lea     rcx, [rdx+rdx*4]
0x180007e8f  add     rcx, rcx
0x180007e92  sub     r8, rcx
0x180007e95  mov     rbx, [rbx+r8*8]
0x180007e99  jmp     short loc_180007EA4
0x180007e9b  cmp     [rbx], r9d
0x180007e9e  jz      short loc_180007F1B
0x180007ea0  mov     rbx, [rbx+8]
0x180007ea4  test    rbx, rbx
0x180007ea7  jnz     short loc_180007E9B
0x180007ea9  test    rbx, rbx
0x180007eac  jz      short loc_180007F00
0x180007eae  cmp     qword ptr [rbx], 0
0x180007eb2  jz      short loc_180007F00
0x180007eb4  mov     [rsi], bpl
0x180007eb7  mov     r9, r14; unsigned __int64
0x180007eba  mov     r8, rsi; char *
0x180007ebd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007ec0  mov     rcx, rdi; struct wil::FailureInfo *
0x180007ec3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007ec8  test    al, al
0x180007eca  jz      short loc_180007ED0
0x180007ecc  mov     [rdi+48h], rsi
0x180007ed0  mov     rbx, [rbx]
0x180007ed3  mov     al, [rbx+28h]
0x180007ed6  mov     byte ptr [rbx+28h], 1
0x180007eda  test    al, al
0x180007edc  jnz     short loc_180007EF7
0x180007ede  mov     rcx, [rbx+8]
0x180007ee2  mov     rax, [rcx]
0x180007ee5  mov     rdx, rdi
0x180007ee8  mov     rax, [rax]
0x180007eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ef0  or      bpl, al
0x180007ef3  mov     byte ptr [rbx+28h], 0
0x180007ef7  mov     rbx, [rbx+10h]
0x180007efb  test    rbx, rbx
0x180007efe  jnz     short loc_180007ED3
0x180007f00  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007f07  test    rax, rax
0x180007f0a  jz      short loc_180007F2C
0x180007f0c  test    bpl, bpl
0x180007f0f  jnz     short loc_180007F21
0x180007f11  test    byte ptr [rdi+4], 2
0x180007f15  jnz     short loc_180007F21
0x180007f17  xor     ecx, ecx
0x180007f19  jmp     short loc_180007F23
0x180007f1b  add     rbx, 10h
0x180007f1f  jmp     short loc_180007EA9
0x180007f21  mov     cl, 1
0x180007f23  mov     rdx, rdi
0x180007f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2b  nop
0x180007f2c  call    cs:__imp_GetCurrentThreadId
0x180007f32  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007f38  cmp     ecx, eax
0x180007f3a  jz      loc_18000803C
0x180007f40  mov     ecx, 1
0x180007f45  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007f4d  inc     ecx; this
0x180007f4f  cmp     ecx, 4
0x180007f52  jge     loc_180008035
0x180007f58  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007f5e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007f63  mov     rbx, rax
0x180007f66  test    rax, rax
0x180007f69  jz      loc_18000802B
0x180007f6f  mov     esi, [rax+10h]
0x180007f72  mov     ebp, 50h ; 'P'
0x180007f77  cmp     qword ptr [rax+18h], 0
0x180007f7c  jnz     short loc_180007FB3
0x180007f7e  test    esi, esi
0x180007f80  jz      short loc_180007FB3
0x180007f82  mov     edx, 190h; dwBytes
0x180007f87  lea     ecx, [rbp-48h]; dwFlags
0x180007f8a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007f8f  mov     [rbx+18h], rax
0x180007f93  test    rax, rax
0x180007f96  jz      short loc_180007FB3
0x180007f98  mov     dword ptr [rbx+20h], 5
0x180007f9f  lea     rcx, [rax+190h]
0x180007fa6  jmp     short loc_180007FAE
0x180007fa8  mov     [rax], bp
0x180007fab  add     rax, rbp
0x180007fae  cmp     rax, rcx
0x180007fb1  jnz     short loc_180007FA8
0x180007fb3  mov     r9, [rbx+18h]
0x180007fb7  test    r9, r9
0x180007fba  jz      short loc_18000802B
0x180007fbc  test    esi, esi
0x180007fbe  jz      short loc_180007FF1
0x180007fc0  mov     rcx, r9
0x180007fc3  movzx   eax, word ptr [rbx+20h]
0x180007fc7  lea     rdx, [rax+rax*4]
0x180007fcb  shl     rdx, 4
0x180007fcf  add     rdx, r9
0x180007fd2  cmp     r9, rdx
0x180007fd5  jz      short loc_180007FF1
0x180007fd7  mov     r8d, [rbx+10h]
0x180007fdb  cmp     [rcx+4], r8d
0x180007fdf  jbe     short loc_180007FE9
0x180007fe1  mov     eax, [rdi+8]
0x180007fe4  cmp     [rcx+8], eax
0x180007fe7  jz      short loc_18000802B
0x180007fe9  add     rcx, rbp
0x180007fec  cmp     rcx, rdx
0x180007fef  jnz     short loc_180007FDB
0x180007ff1  movzx   eax, word ptr [rbx+22h]
0x180007ff5  inc     eax
0x180007ff7  movzx   ecx, word ptr [rbx+20h]
0x180007ffb  xor     edx, edx
0x180007ffd  div     ecx
0x180007fff  mov     [rbx+22h], dx
0x180008003  mov     rax, [rbx+8]
0x180008007  mov     r8d, 1
0x18000800d  lock xadd [rax], r8d
0x180008012  inc     r8d; unsigned int
0x180008015  movzx   eax, dx
0x180008018  lea     rcx, [rax+rax*4]
0x18000801c  shl     rcx, 4
0x180008020  add     rcx, r9; this
0x180008023  mov     rdx, rdi; struct wil::FailureInfo *
0x180008026  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000802b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008035  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000803c  add     rsp, 20h
0x180008040  pop     r14
0x180008042  pop     rdi
0x180008043  pop     rsi
0x180008044  pop     rbp
0x180008045  pop     rbx
0x180008046  retn
```
