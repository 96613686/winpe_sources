# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008e10`
- end: `0x180009017`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180008e10`
- `0x18000950c`
- `0x1800095f0`
- `0x180009d44`
- `0x18000a2a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008efc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008efc`

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
0x180008e10  push    rbx
0x180008e12  push    rbp
0x180008e13  push    rsi
0x180008e14  push    rdi
0x180008e15  push    r14
0x180008e17  sub     rsp, 20h
0x180008e1b  mov     r14, r8
0x180008e1e  mov     rsi, rdx
0x180008e21  mov     rdi, rcx
0x180008e24  mov     byte ptr [rdx], 0
0x180008e27  xor     bpl, bpl
0x180008e2a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008e31  test    rbx, rbx
0x180008e34  jz      loc_180008ED0
0x180008e3a  call    cs:__imp_GetCurrentThreadId
0x180008e40  mov     r9d, eax
0x180008e43  mov     r8d, eax
0x180008e46  shr     r8, 2
0x180008e4a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008e54  mul     r8
0x180008e57  shr     rdx, 3
0x180008e5b  lea     rcx, [rdx+rdx*4]
0x180008e5f  add     rcx, rcx
0x180008e62  sub     r8, rcx
0x180008e65  mov     rbx, [rbx+r8*8]
0x180008e69  jmp     short loc_180008E74
0x180008e6b  cmp     [rbx], r9d
0x180008e6e  jz      short loc_180008EEB
0x180008e70  mov     rbx, [rbx+8]
0x180008e74  test    rbx, rbx
0x180008e77  jnz     short loc_180008E6B
0x180008e79  test    rbx, rbx
0x180008e7c  jz      short loc_180008ED0
0x180008e7e  cmp     qword ptr [rbx], 0
0x180008e82  jz      short loc_180008ED0
0x180008e84  mov     [rsi], bpl
0x180008e87  mov     r9, r14; unsigned __int64
0x180008e8a  mov     r8, rsi; char *
0x180008e8d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008e90  mov     rcx, rdi; struct wil::FailureInfo *
0x180008e93  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008e98  test    al, al
0x180008e9a  jz      short loc_180008EA0
0x180008e9c  mov     [rdi+48h], rsi
0x180008ea0  mov     rbx, [rbx]
0x180008ea3  mov     al, [rbx+28h]
0x180008ea6  mov     byte ptr [rbx+28h], 1
0x180008eaa  test    al, al
0x180008eac  jnz     short loc_180008EC7
0x180008eae  mov     rcx, [rbx+8]
0x180008eb2  mov     rax, [rcx]
0x180008eb5  mov     rdx, rdi
0x180008eb8  mov     rax, [rax]
0x180008ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ec0  or      bpl, al
0x180008ec3  mov     byte ptr [rbx+28h], 0
0x180008ec7  mov     rbx, [rbx+10h]
0x180008ecb  test    rbx, rbx
0x180008ece  jnz     short loc_180008EA3
0x180008ed0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008ed7  test    rax, rax
0x180008eda  jz      short loc_180008EFC
0x180008edc  test    bpl, bpl
0x180008edf  jnz     short loc_180008EF1
0x180008ee1  test    byte ptr [rdi+4], 2
0x180008ee5  jnz     short loc_180008EF1
0x180008ee7  xor     ecx, ecx
0x180008ee9  jmp     short loc_180008EF3
0x180008eeb  add     rbx, 10h
0x180008eef  jmp     short loc_180008E79
0x180008ef1  mov     cl, 1
0x180008ef3  mov     rdx, rdi
0x180008ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008efb  nop
0x180008efc  call    cs:__imp_GetCurrentThreadId
0x180008f02  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008f08  cmp     ecx, eax
0x180008f0a  jz      loc_18000900C
0x180008f10  mov     ecx, 1
0x180008f15  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008f1d  inc     ecx; this
0x180008f1f  cmp     ecx, 4
0x180008f22  jge     loc_180009005
0x180008f28  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008f2e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180008f33  mov     rbx, rax
0x180008f36  test    rax, rax
0x180008f39  jz      loc_180008FFB
0x180008f3f  mov     esi, [rax+10h]
0x180008f42  mov     ebp, 50h ; 'P'
0x180008f47  cmp     qword ptr [rax+18h], 0
0x180008f4c  jnz     short loc_180008F83
0x180008f4e  test    esi, esi
0x180008f50  jz      short loc_180008F83
0x180008f52  mov     edx, 190h; dwBytes
0x180008f57  lea     ecx, [rbp-48h]; dwFlags
0x180008f5a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008f5f  mov     [rbx+18h], rax
0x180008f63  test    rax, rax
0x180008f66  jz      short loc_180008F83
0x180008f68  mov     dword ptr [rbx+20h], 5
0x180008f6f  lea     rcx, [rax+190h]
0x180008f76  jmp     short loc_180008F7E
0x180008f78  mov     [rax], bp
0x180008f7b  add     rax, rbp
0x180008f7e  cmp     rax, rcx
0x180008f81  jnz     short loc_180008F78
0x180008f83  mov     r9, [rbx+18h]
0x180008f87  test    r9, r9
0x180008f8a  jz      short loc_180008FFB
0x180008f8c  test    esi, esi
0x180008f8e  jz      short loc_180008FC1
0x180008f90  mov     rcx, r9
0x180008f93  movzx   eax, word ptr [rbx+20h]
0x180008f97  lea     rdx, [rax+rax*4]
0x180008f9b  shl     rdx, 4
0x180008f9f  add     rdx, r9
0x180008fa2  cmp     r9, rdx
0x180008fa5  jz      short loc_180008FC1
0x180008fa7  mov     r8d, [rbx+10h]
0x180008fab  cmp     [rcx+4], r8d
0x180008faf  jbe     short loc_180008FB9
0x180008fb1  mov     eax, [rdi+8]
0x180008fb4  cmp     [rcx+8], eax
0x180008fb7  jz      short loc_180008FFB
0x180008fb9  add     rcx, rbp
0x180008fbc  cmp     rcx, rdx
0x180008fbf  jnz     short loc_180008FAB
0x180008fc1  movzx   eax, word ptr [rbx+22h]
0x180008fc5  inc     eax
0x180008fc7  movzx   ecx, word ptr [rbx+20h]
0x180008fcb  xor     edx, edx
0x180008fcd  div     ecx
0x180008fcf  mov     [rbx+22h], dx
0x180008fd3  mov     rax, [rbx+8]
0x180008fd7  mov     r8d, 1
0x180008fdd  lock xadd [rax], r8d
0x180008fe2  inc     r8d; unsigned int
0x180008fe5  movzx   eax, dx
0x180008fe8  lea     rcx, [rax+rax*4]
0x180008fec  shl     rcx, 4
0x180008ff0  add     rcx, r9; this
0x180008ff3  mov     rdx, rdi; struct wil::FailureInfo *
0x180008ff6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180008ffb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009005  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000900c  add     rsp, 20h
0x180009010  pop     r14
0x180009012  pop     rdi
0x180009013  pop     rsi
0x180009014  pop     rbp
0x180009015  pop     rbx
0x180009016  retn
```
