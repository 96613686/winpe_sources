# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004a30`
- end: `0x180004c37`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004a30`
- `0x18000512c`
- `0x180005210`
- `0x180005b98`
- `0x1800071b4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b1c`

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
0x180004a30  push    rbx
0x180004a32  push    rbp
0x180004a33  push    rsi
0x180004a34  push    rdi
0x180004a35  push    r14
0x180004a37  sub     rsp, 20h
0x180004a3b  mov     r14, r8
0x180004a3e  mov     rsi, rdx
0x180004a41  mov     rdi, rcx
0x180004a44  mov     byte ptr [rdx], 0
0x180004a47  xor     bpl, bpl
0x180004a4a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004a51  test    rbx, rbx
0x180004a54  jz      loc_180004AF0
0x180004a5a  call    cs:__imp_GetCurrentThreadId
0x180004a60  mov     r9d, eax
0x180004a63  mov     r8d, eax
0x180004a66  shr     r8, 2
0x180004a6a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004a74  mul     r8
0x180004a77  shr     rdx, 3
0x180004a7b  lea     rcx, [rdx+rdx*4]
0x180004a7f  add     rcx, rcx
0x180004a82  sub     r8, rcx
0x180004a85  mov     rbx, [rbx+r8*8]
0x180004a89  jmp     short loc_180004A94
0x180004a8b  cmp     [rbx], r9d
0x180004a8e  jz      short loc_180004B0B
0x180004a90  mov     rbx, [rbx+8]
0x180004a94  test    rbx, rbx
0x180004a97  jnz     short loc_180004A8B
0x180004a99  test    rbx, rbx
0x180004a9c  jz      short loc_180004AF0
0x180004a9e  cmp     qword ptr [rbx], 0
0x180004aa2  jz      short loc_180004AF0
0x180004aa4  mov     [rsi], bpl
0x180004aa7  mov     r9, r14; unsigned __int64
0x180004aaa  mov     r8, rsi; char *
0x180004aad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004ab0  mov     rcx, rdi; struct wil::FailureInfo *
0x180004ab3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004ab8  test    al, al
0x180004aba  jz      short loc_180004AC0
0x180004abc  mov     [rdi+48h], rsi
0x180004ac0  mov     rbx, [rbx]
0x180004ac3  mov     al, [rbx+28h]
0x180004ac6  mov     byte ptr [rbx+28h], 1
0x180004aca  test    al, al
0x180004acc  jnz     short loc_180004AE7
0x180004ace  mov     rcx, [rbx+8]
0x180004ad2  mov     rax, [rcx]
0x180004ad5  mov     rdx, rdi
0x180004ad8  mov     rax, [rax]
0x180004adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae0  or      bpl, al
0x180004ae3  mov     byte ptr [rbx+28h], 0
0x180004ae7  mov     rbx, [rbx+10h]
0x180004aeb  test    rbx, rbx
0x180004aee  jnz     short loc_180004AC3
0x180004af0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004af7  test    rax, rax
0x180004afa  jz      short loc_180004B1C
0x180004afc  test    bpl, bpl
0x180004aff  jnz     short loc_180004B11
0x180004b01  test    byte ptr [rdi+4], 2
0x180004b05  jnz     short loc_180004B11
0x180004b07  xor     ecx, ecx
0x180004b09  jmp     short loc_180004B13
0x180004b0b  add     rbx, 10h
0x180004b0f  jmp     short loc_180004A99
0x180004b11  mov     cl, 1
0x180004b13  mov     rdx, rdi
0x180004b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b1b  nop
0x180004b1c  call    cs:__imp_GetCurrentThreadId
0x180004b22  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004b28  cmp     ecx, eax
0x180004b2a  jz      loc_180004C2C
0x180004b30  mov     ecx, 1
0x180004b35  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004b3d  inc     ecx; this
0x180004b3f  cmp     ecx, 4
0x180004b42  jge     loc_180004C25
0x180004b48  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004b4e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004b53  mov     rbx, rax
0x180004b56  test    rax, rax
0x180004b59  jz      loc_180004C1B
0x180004b5f  mov     esi, [rax+10h]
0x180004b62  mov     ebp, 50h ; 'P'
0x180004b67  cmp     qword ptr [rax+18h], 0
0x180004b6c  jnz     short loc_180004BA3
0x180004b6e  test    esi, esi
0x180004b70  jz      short loc_180004BA3
0x180004b72  mov     edx, 190h; dwBytes
0x180004b77  lea     ecx, [rbp-48h]; dwFlags
0x180004b7a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004b7f  mov     [rbx+18h], rax
0x180004b83  test    rax, rax
0x180004b86  jz      short loc_180004BA3
0x180004b88  mov     dword ptr [rbx+20h], 5
0x180004b8f  lea     rcx, [rax+190h]
0x180004b96  jmp     short loc_180004B9E
0x180004b98  mov     [rax], bp
0x180004b9b  add     rax, rbp
0x180004b9e  cmp     rax, rcx
0x180004ba1  jnz     short loc_180004B98
0x180004ba3  mov     r9, [rbx+18h]
0x180004ba7  test    r9, r9
0x180004baa  jz      short loc_180004C1B
0x180004bac  test    esi, esi
0x180004bae  jz      short loc_180004BE1
0x180004bb0  mov     rcx, r9
0x180004bb3  movzx   eax, word ptr [rbx+20h]
0x180004bb7  lea     rdx, [rax+rax*4]
0x180004bbb  shl     rdx, 4
0x180004bbf  add     rdx, r9
0x180004bc2  cmp     r9, rdx
0x180004bc5  jz      short loc_180004BE1
0x180004bc7  mov     r8d, [rbx+10h]
0x180004bcb  cmp     [rcx+4], r8d
0x180004bcf  jbe     short loc_180004BD9
0x180004bd1  mov     eax, [rdi+8]
0x180004bd4  cmp     [rcx+8], eax
0x180004bd7  jz      short loc_180004C1B
0x180004bd9  add     rcx, rbp
0x180004bdc  cmp     rcx, rdx
0x180004bdf  jnz     short loc_180004BCB
0x180004be1  movzx   eax, word ptr [rbx+22h]
0x180004be5  inc     eax
0x180004be7  movzx   ecx, word ptr [rbx+20h]
0x180004beb  xor     edx, edx
0x180004bed  div     ecx
0x180004bef  mov     [rbx+22h], dx
0x180004bf3  mov     rax, [rbx+8]
0x180004bf7  mov     r8d, 1
0x180004bfd  lock xadd [rax], r8d
0x180004c02  inc     r8d; unsigned int
0x180004c05  movzx   eax, dx
0x180004c08  lea     rcx, [rax+rax*4]
0x180004c0c  shl     rcx, 4
0x180004c10  add     rcx, r9; this
0x180004c13  mov     rdx, rdi; struct wil::FailureInfo *
0x180004c16  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004c1b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004c25  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004c2c  add     rsp, 20h
0x180004c30  pop     r14
0x180004c32  pop     rdi
0x180004c33  pop     rsi
0x180004c34  pop     rbp
0x180004c35  pop     rbx
0x180004c36  retn
```
