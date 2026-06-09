# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007c00`
- end: `0x180007e07`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007c00`
- `0x1800083cc`
- `0x1800084b0`
- `0x180008e98`
- `0x18000a624`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007cec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007cec`

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
0x180007c00  push    rbx
0x180007c02  push    rbp
0x180007c03  push    rsi
0x180007c04  push    rdi
0x180007c05  push    r14
0x180007c07  sub     rsp, 20h
0x180007c0b  mov     r14, r8
0x180007c0e  mov     rsi, rdx
0x180007c11  mov     rdi, rcx
0x180007c14  mov     byte ptr [rdx], 0
0x180007c17  xor     bpl, bpl
0x180007c1a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007c21  test    rbx, rbx
0x180007c24  jz      loc_180007CC0
0x180007c2a  call    cs:__imp_GetCurrentThreadId
0x180007c30  mov     r9d, eax
0x180007c33  mov     r8d, eax
0x180007c36  shr     r8, 2
0x180007c3a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007c44  mul     r8
0x180007c47  shr     rdx, 3
0x180007c4b  lea     rcx, [rdx+rdx*4]
0x180007c4f  add     rcx, rcx
0x180007c52  sub     r8, rcx
0x180007c55  mov     rbx, [rbx+r8*8]
0x180007c59  jmp     short loc_180007C64
0x180007c5b  cmp     [rbx], r9d
0x180007c5e  jz      short loc_180007CDB
0x180007c60  mov     rbx, [rbx+8]
0x180007c64  test    rbx, rbx
0x180007c67  jnz     short loc_180007C5B
0x180007c69  test    rbx, rbx
0x180007c6c  jz      short loc_180007CC0
0x180007c6e  cmp     qword ptr [rbx], 0
0x180007c72  jz      short loc_180007CC0
0x180007c74  mov     [rsi], bpl
0x180007c77  mov     r9, r14; unsigned __int64
0x180007c7a  mov     r8, rsi; char *
0x180007c7d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007c80  mov     rcx, rdi; struct wil::FailureInfo *
0x180007c83  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007c88  test    al, al
0x180007c8a  jz      short loc_180007C90
0x180007c8c  mov     [rdi+48h], rsi
0x180007c90  mov     rbx, [rbx]
0x180007c93  mov     al, [rbx+28h]
0x180007c96  mov     byte ptr [rbx+28h], 1
0x180007c9a  test    al, al
0x180007c9c  jnz     short loc_180007CB7
0x180007c9e  mov     rcx, [rbx+8]
0x180007ca2  mov     rax, [rcx]
0x180007ca5  mov     rdx, rdi
0x180007ca8  mov     rax, [rax]
0x180007cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb0  or      bpl, al
0x180007cb3  mov     byte ptr [rbx+28h], 0
0x180007cb7  mov     rbx, [rbx+10h]
0x180007cbb  test    rbx, rbx
0x180007cbe  jnz     short loc_180007C93
0x180007cc0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007cc7  test    rax, rax
0x180007cca  jz      short loc_180007CEC
0x180007ccc  test    bpl, bpl
0x180007ccf  jnz     short loc_180007CE1
0x180007cd1  test    byte ptr [rdi+4], 2
0x180007cd5  jnz     short loc_180007CE1
0x180007cd7  xor     ecx, ecx
0x180007cd9  jmp     short loc_180007CE3
0x180007cdb  add     rbx, 10h
0x180007cdf  jmp     short loc_180007C69
0x180007ce1  mov     cl, 1
0x180007ce3  mov     rdx, rdi
0x180007ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ceb  nop
0x180007cec  call    cs:__imp_GetCurrentThreadId
0x180007cf2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007cf8  cmp     ecx, eax
0x180007cfa  jz      loc_180007DFC
0x180007d00  mov     ecx, 1
0x180007d05  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007d0d  inc     ecx; this
0x180007d0f  cmp     ecx, 4
0x180007d12  jge     loc_180007DF5
0x180007d18  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007d1e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007d23  mov     rbx, rax
0x180007d26  test    rax, rax
0x180007d29  jz      loc_180007DEB
0x180007d2f  mov     esi, [rax+10h]
0x180007d32  mov     ebp, 50h ; 'P'
0x180007d37  cmp     qword ptr [rax+18h], 0
0x180007d3c  jnz     short loc_180007D73
0x180007d3e  test    esi, esi
0x180007d40  jz      short loc_180007D73
0x180007d42  mov     edx, 190h; dwBytes
0x180007d47  lea     ecx, [rbp-48h]; dwFlags
0x180007d4a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007d4f  mov     [rbx+18h], rax
0x180007d53  test    rax, rax
0x180007d56  jz      short loc_180007D73
0x180007d58  mov     dword ptr [rbx+20h], 5
0x180007d5f  lea     rcx, [rax+190h]
0x180007d66  jmp     short loc_180007D6E
0x180007d68  mov     [rax], bp
0x180007d6b  add     rax, rbp
0x180007d6e  cmp     rax, rcx
0x180007d71  jnz     short loc_180007D68
0x180007d73  mov     r9, [rbx+18h]
0x180007d77  test    r9, r9
0x180007d7a  jz      short loc_180007DEB
0x180007d7c  test    esi, esi
0x180007d7e  jz      short loc_180007DB1
0x180007d80  mov     rcx, r9
0x180007d83  movzx   eax, word ptr [rbx+20h]
0x180007d87  lea     rdx, [rax+rax*4]
0x180007d8b  shl     rdx, 4
0x180007d8f  add     rdx, r9
0x180007d92  cmp     r9, rdx
0x180007d95  jz      short loc_180007DB1
0x180007d97  mov     r8d, [rbx+10h]
0x180007d9b  cmp     [rcx+4], r8d
0x180007d9f  jbe     short loc_180007DA9
0x180007da1  mov     eax, [rdi+8]
0x180007da4  cmp     [rcx+8], eax
0x180007da7  jz      short loc_180007DEB
0x180007da9  add     rcx, rbp
0x180007dac  cmp     rcx, rdx
0x180007daf  jnz     short loc_180007D9B
0x180007db1  movzx   eax, word ptr [rbx+22h]
0x180007db5  inc     eax
0x180007db7  movzx   ecx, word ptr [rbx+20h]
0x180007dbb  xor     edx, edx
0x180007dbd  div     ecx
0x180007dbf  mov     [rbx+22h], dx
0x180007dc3  mov     rax, [rbx+8]
0x180007dc7  mov     r8d, 1
0x180007dcd  lock xadd [rax], r8d
0x180007dd2  inc     r8d; unsigned int
0x180007dd5  movzx   eax, dx
0x180007dd8  lea     rcx, [rax+rax*4]
0x180007ddc  shl     rcx, 4
0x180007de0  add     rcx, r9; this
0x180007de3  mov     rdx, rdi; struct wil::FailureInfo *
0x180007de6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007deb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007df5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007dfc  add     rsp, 20h
0x180007e00  pop     r14
0x180007e02  pop     rdi
0x180007e03  pop     rsi
0x180007e04  pop     rbp
0x180007e05  pop     rbx
0x180007e06  retn
```
