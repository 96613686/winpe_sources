# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180019c70`
- end: `0x180019e77`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180019c70`
- `0x18001a324`
- `0x18001a408`
- `0x18001bf38`
- `0x18001c550`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180019c9a`
- `KERNEL32!GetCurrentThreadId` at `0x180019d5c`
- `KERNEL32!GetCurrentThreadId` at `0x180019c9a`
- `KERNEL32!GetCurrentThreadId` at `0x180019d5c`

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
0x180019c70  push    rbx
0x180019c72  push    rbp
0x180019c73  push    rsi
0x180019c74  push    rdi
0x180019c75  push    r14
0x180019c77  sub     rsp, 20h
0x180019c7b  mov     r14, r8
0x180019c7e  mov     rsi, rdx
0x180019c81  mov     rdi, rcx
0x180019c84  mov     byte ptr [rdx], 0
0x180019c87  xor     bpl, bpl
0x180019c8a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180019c91  test    rbx, rbx
0x180019c94  jz      loc_180019D30
0x180019c9a  call    cs:__imp_GetCurrentThreadId
0x180019ca0  mov     r9d, eax
0x180019ca3  mov     r8d, eax
0x180019ca6  shr     r8, 2
0x180019caa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180019cb4  mul     r8
0x180019cb7  shr     rdx, 3
0x180019cbb  lea     rcx, [rdx+rdx*4]
0x180019cbf  add     rcx, rcx
0x180019cc2  sub     r8, rcx
0x180019cc5  mov     rbx, [rbx+r8*8]
0x180019cc9  jmp     short loc_180019CD4
0x180019ccb  cmp     [rbx], r9d
0x180019cce  jz      short loc_180019D4B
0x180019cd0  mov     rbx, [rbx+8]
0x180019cd4  test    rbx, rbx
0x180019cd7  jnz     short loc_180019CCB
0x180019cd9  test    rbx, rbx
0x180019cdc  jz      short loc_180019D30
0x180019cde  cmp     qword ptr [rbx], 0
0x180019ce2  jz      short loc_180019D30
0x180019ce4  mov     [rsi], bpl
0x180019ce7  mov     r9, r14; unsigned __int64
0x180019cea  mov     r8, rsi; char *
0x180019ced  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180019cf0  mov     rcx, rdi; struct wil::FailureInfo *
0x180019cf3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180019cf8  test    al, al
0x180019cfa  jz      short loc_180019D00
0x180019cfc  mov     [rdi+48h], rsi
0x180019d00  mov     rbx, [rbx]
0x180019d03  mov     al, [rbx+28h]
0x180019d06  mov     byte ptr [rbx+28h], 1
0x180019d0a  test    al, al
0x180019d0c  jnz     short loc_180019D27
0x180019d0e  mov     rcx, [rbx+8]
0x180019d12  mov     rax, [rcx]
0x180019d15  mov     rdx, rdi
0x180019d18  mov     rax, [rax]
0x180019d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d20  or      bpl, al
0x180019d23  mov     byte ptr [rbx+28h], 0
0x180019d27  mov     rbx, [rbx+10h]
0x180019d2b  test    rbx, rbx
0x180019d2e  jnz     short loc_180019D03
0x180019d30  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180019d37  test    rax, rax
0x180019d3a  jz      short loc_180019D5C
0x180019d3c  test    bpl, bpl
0x180019d3f  jnz     short loc_180019D51
0x180019d41  test    byte ptr [rdi+4], 2
0x180019d45  jnz     short loc_180019D51
0x180019d47  xor     ecx, ecx
0x180019d49  jmp     short loc_180019D53
0x180019d4b  add     rbx, 10h
0x180019d4f  jmp     short loc_180019CD9
0x180019d51  mov     cl, 1
0x180019d53  mov     rdx, rdi
0x180019d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d5b  nop
0x180019d5c  call    cs:__imp_GetCurrentThreadId
0x180019d62  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180019d68  cmp     ecx, eax
0x180019d6a  jz      loc_180019E6C
0x180019d70  mov     ecx, 1
0x180019d75  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180019d7d  inc     ecx; this
0x180019d7f  cmp     ecx, 4
0x180019d82  jge     loc_180019E65
0x180019d88  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180019d8e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180019d93  mov     rbx, rax
0x180019d96  test    rax, rax
0x180019d99  jz      loc_180019E5B
0x180019d9f  mov     esi, [rax+10h]
0x180019da2  mov     ebp, 50h ; 'P'
0x180019da7  cmp     qword ptr [rax+18h], 0
0x180019dac  jnz     short loc_180019DE3
0x180019dae  test    esi, esi
0x180019db0  jz      short loc_180019DE3
0x180019db2  mov     edx, 190h; dwBytes
0x180019db7  lea     ecx, [rbp-48h]; dwFlags
0x180019dba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180019dbf  mov     [rbx+18h], rax
0x180019dc3  test    rax, rax
0x180019dc6  jz      short loc_180019DE3
0x180019dc8  mov     dword ptr [rbx+20h], 5
0x180019dcf  lea     rcx, [rax+190h]
0x180019dd6  jmp     short loc_180019DDE
0x180019dd8  mov     [rax], bp
0x180019ddb  add     rax, rbp
0x180019dde  cmp     rax, rcx
0x180019de1  jnz     short loc_180019DD8
0x180019de3  mov     r9, [rbx+18h]
0x180019de7  test    r9, r9
0x180019dea  jz      short loc_180019E5B
0x180019dec  test    esi, esi
0x180019dee  jz      short loc_180019E21
0x180019df0  mov     rcx, r9
0x180019df3  movzx   eax, word ptr [rbx+20h]
0x180019df7  lea     rdx, [rax+rax*4]
0x180019dfb  shl     rdx, 4
0x180019dff  add     rdx, r9
0x180019e02  cmp     r9, rdx
0x180019e05  jz      short loc_180019E21
0x180019e07  mov     r8d, [rbx+10h]
0x180019e0b  cmp     [rcx+4], r8d
0x180019e0f  jbe     short loc_180019E19
0x180019e11  mov     eax, [rdi+8]
0x180019e14  cmp     [rcx+8], eax
0x180019e17  jz      short loc_180019E5B
0x180019e19  add     rcx, rbp
0x180019e1c  cmp     rcx, rdx
0x180019e1f  jnz     short loc_180019E0B
0x180019e21  movzx   eax, word ptr [rbx+22h]
0x180019e25  inc     eax
0x180019e27  movzx   ecx, word ptr [rbx+20h]
0x180019e2b  xor     edx, edx
0x180019e2d  div     ecx
0x180019e2f  mov     [rbx+22h], dx
0x180019e33  mov     rax, [rbx+8]
0x180019e37  mov     r8d, 1
0x180019e3d  lock xadd [rax], r8d
0x180019e42  inc     r8d; unsigned int
0x180019e45  movzx   eax, dx
0x180019e48  lea     rcx, [rax+rax*4]
0x180019e4c  shl     rcx, 4
0x180019e50  add     rcx, r9; this
0x180019e53  mov     rdx, rdi; struct wil::FailureInfo *
0x180019e56  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180019e5b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180019e65  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180019e6c  add     rsp, 20h
0x180019e70  pop     r14
0x180019e72  pop     rdi
0x180019e73  pop     rsi
0x180019e74  pop     rbp
0x180019e75  pop     rbx
0x180019e76  retn
```
