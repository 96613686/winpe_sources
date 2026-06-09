# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18001ca30`
- end: `0x18001cc37`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001ca30`
- `0x18001d12c`
- `0x18001d210`
- `0x18001e448`
- `0x18001e7d0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb1c`

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
0x18001ca30  push    rbx
0x18001ca32  push    rbp
0x18001ca33  push    rsi
0x18001ca34  push    rdi
0x18001ca35  push    r14
0x18001ca37  sub     rsp, 20h
0x18001ca3b  mov     r14, r8
0x18001ca3e  mov     rsi, rdx
0x18001ca41  mov     rdi, rcx
0x18001ca44  mov     byte ptr [rdx], 0
0x18001ca47  xor     bpl, bpl
0x18001ca4a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001ca51  test    rbx, rbx
0x18001ca54  jz      loc_18001CAF0
0x18001ca5a  call    cs:__imp_GetCurrentThreadId
0x18001ca60  mov     r9d, eax
0x18001ca63  mov     r8d, eax
0x18001ca66  shr     r8, 2
0x18001ca6a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001ca74  mul     r8
0x18001ca77  shr     rdx, 3
0x18001ca7b  lea     rcx, [rdx+rdx*4]
0x18001ca7f  add     rcx, rcx
0x18001ca82  sub     r8, rcx
0x18001ca85  mov     rbx, [rbx+r8*8]
0x18001ca89  jmp     short loc_18001CA94
0x18001ca8b  cmp     [rbx], r9d
0x18001ca8e  jz      short loc_18001CB0B
0x18001ca90  mov     rbx, [rbx+8]
0x18001ca94  test    rbx, rbx
0x18001ca97  jnz     short loc_18001CA8B
0x18001ca99  test    rbx, rbx
0x18001ca9c  jz      short loc_18001CAF0
0x18001ca9e  cmp     qword ptr [rbx], 0
0x18001caa2  jz      short loc_18001CAF0
0x18001caa4  mov     [rsi], bpl
0x18001caa7  mov     r9, r14; unsigned __int64
0x18001caaa  mov     r8, rsi; char *
0x18001caad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18001cab0  mov     rcx, rdi; struct wil::FailureInfo *
0x18001cab3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001cab8  test    al, al
0x18001caba  jz      short loc_18001CAC0
0x18001cabc  mov     [rdi+48h], rsi
0x18001cac0  mov     rbx, [rbx]
0x18001cac3  mov     al, [rbx+28h]
0x18001cac6  mov     byte ptr [rbx+28h], 1
0x18001caca  test    al, al
0x18001cacc  jnz     short loc_18001CAE7
0x18001cace  mov     rcx, [rbx+8]
0x18001cad2  mov     rax, [rcx]
0x18001cad5  mov     rdx, rdi
0x18001cad8  mov     rax, [rax]
0x18001cadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cae0  or      bpl, al
0x18001cae3  mov     byte ptr [rbx+28h], 0
0x18001cae7  mov     rbx, [rbx+10h]
0x18001caeb  test    rbx, rbx
0x18001caee  jnz     short loc_18001CAC3
0x18001caf0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001caf7  test    rax, rax
0x18001cafa  jz      short loc_18001CB1C
0x18001cafc  test    bpl, bpl
0x18001caff  jnz     short loc_18001CB11
0x18001cb01  test    byte ptr [rdi+4], 2
0x18001cb05  jnz     short loc_18001CB11
0x18001cb07  xor     ecx, ecx
0x18001cb09  jmp     short loc_18001CB13
0x18001cb0b  add     rbx, 10h
0x18001cb0f  jmp     short loc_18001CA99
0x18001cb11  mov     cl, 1
0x18001cb13  mov     rdx, rdi
0x18001cb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb1b  nop
0x18001cb1c  call    cs:__imp_GetCurrentThreadId
0x18001cb22  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001cb28  cmp     ecx, eax
0x18001cb2a  jz      loc_18001CC2C
0x18001cb30  mov     ecx, 1
0x18001cb35  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001cb3d  inc     ecx; this
0x18001cb3f  cmp     ecx, 4
0x18001cb42  jge     loc_18001CC25
0x18001cb48  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001cb4e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18001cb53  mov     rbx, rax
0x18001cb56  test    rax, rax
0x18001cb59  jz      loc_18001CC1B
0x18001cb5f  mov     esi, [rax+10h]
0x18001cb62  mov     ebp, 50h ; 'P'
0x18001cb67  cmp     qword ptr [rax+18h], 0
0x18001cb6c  jnz     short loc_18001CBA3
0x18001cb6e  test    esi, esi
0x18001cb70  jz      short loc_18001CBA3
0x18001cb72  mov     edx, 190h; dwBytes
0x18001cb77  lea     ecx, [rbp-48h]; dwFlags
0x18001cb7a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001cb7f  mov     [rbx+18h], rax
0x18001cb83  test    rax, rax
0x18001cb86  jz      short loc_18001CBA3
0x18001cb88  mov     dword ptr [rbx+20h], 5
0x18001cb8f  lea     rcx, [rax+190h]
0x18001cb96  jmp     short loc_18001CB9E
0x18001cb98  mov     [rax], bp
0x18001cb9b  add     rax, rbp
0x18001cb9e  cmp     rax, rcx
0x18001cba1  jnz     short loc_18001CB98
0x18001cba3  mov     r9, [rbx+18h]
0x18001cba7  test    r9, r9
0x18001cbaa  jz      short loc_18001CC1B
0x18001cbac  test    esi, esi
0x18001cbae  jz      short loc_18001CBE1
0x18001cbb0  mov     rcx, r9
0x18001cbb3  movzx   eax, word ptr [rbx+20h]
0x18001cbb7  lea     rdx, [rax+rax*4]
0x18001cbbb  shl     rdx, 4
0x18001cbbf  add     rdx, r9
0x18001cbc2  cmp     r9, rdx
0x18001cbc5  jz      short loc_18001CBE1
0x18001cbc7  mov     r8d, [rbx+10h]
0x18001cbcb  cmp     [rcx+4], r8d
0x18001cbcf  jbe     short loc_18001CBD9
0x18001cbd1  mov     eax, [rdi+8]
0x18001cbd4  cmp     [rcx+8], eax
0x18001cbd7  jz      short loc_18001CC1B
0x18001cbd9  add     rcx, rbp
0x18001cbdc  cmp     rcx, rdx
0x18001cbdf  jnz     short loc_18001CBCB
0x18001cbe1  movzx   eax, word ptr [rbx+22h]
0x18001cbe5  inc     eax
0x18001cbe7  movzx   ecx, word ptr [rbx+20h]
0x18001cbeb  xor     edx, edx
0x18001cbed  div     ecx
0x18001cbef  mov     [rbx+22h], dx
0x18001cbf3  mov     rax, [rbx+8]
0x18001cbf7  mov     r8d, 1
0x18001cbfd  lock xadd [rax], r8d
0x18001cc02  inc     r8d; unsigned int
0x18001cc05  movzx   eax, dx
0x18001cc08  lea     rcx, [rax+rax*4]
0x18001cc0c  shl     rcx, 4
0x18001cc10  add     rcx, r9; this
0x18001cc13  mov     rdx, rdi; struct wil::FailureInfo *
0x18001cc16  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001cc1b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001cc25  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001cc2c  add     rsp, 20h
0x18001cc30  pop     r14
0x18001cc32  pop     rdi
0x18001cc33  pop     rsi
0x18001cc34  pop     rbp
0x18001cc35  pop     rbx
0x18001cc36  retn
```
