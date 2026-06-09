# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004900`
- end: `0x180004b07`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004900`
- `0x180004ffc`
- `0x1800050e0`
- `0x18000598c`
- `0x180005e40`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000492a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000492a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049ec`

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
0x180004900  push    rbx
0x180004902  push    rbp
0x180004903  push    rsi
0x180004904  push    rdi
0x180004905  push    r14
0x180004907  sub     rsp, 20h
0x18000490b  mov     r14, r8
0x18000490e  mov     rsi, rdx
0x180004911  mov     rdi, rcx
0x180004914  mov     byte ptr [rdx], 0
0x180004917  xor     bpl, bpl
0x18000491a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004921  test    rbx, rbx
0x180004924  jz      loc_1800049C0
0x18000492a  call    cs:__imp_GetCurrentThreadId
0x180004930  mov     r9d, eax
0x180004933  mov     r8d, eax
0x180004936  shr     r8, 2
0x18000493a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004944  mul     r8
0x180004947  shr     rdx, 3
0x18000494b  lea     rcx, [rdx+rdx*4]
0x18000494f  add     rcx, rcx
0x180004952  sub     r8, rcx
0x180004955  mov     rbx, [rbx+r8*8]
0x180004959  jmp     short loc_180004964
0x18000495b  cmp     [rbx], r9d
0x18000495e  jz      short loc_1800049DB
0x180004960  mov     rbx, [rbx+8]
0x180004964  test    rbx, rbx
0x180004967  jnz     short loc_18000495B
0x180004969  test    rbx, rbx
0x18000496c  jz      short loc_1800049C0
0x18000496e  cmp     qword ptr [rbx], 0
0x180004972  jz      short loc_1800049C0
0x180004974  mov     [rsi], bpl
0x180004977  mov     r9, r14; unsigned __int64
0x18000497a  mov     r8, rsi; char *
0x18000497d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004980  mov     rcx, rdi; struct wil::FailureInfo *
0x180004983  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004988  test    al, al
0x18000498a  jz      short loc_180004990
0x18000498c  mov     [rdi+48h], rsi
0x180004990  mov     rbx, [rbx]
0x180004993  mov     al, [rbx+28h]
0x180004996  mov     byte ptr [rbx+28h], 1
0x18000499a  test    al, al
0x18000499c  jnz     short loc_1800049B7
0x18000499e  mov     rcx, [rbx+8]
0x1800049a2  mov     rax, [rcx]
0x1800049a5  mov     rdx, rdi
0x1800049a8  mov     rax, [rax]
0x1800049ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b0  or      bpl, al
0x1800049b3  mov     byte ptr [rbx+28h], 0
0x1800049b7  mov     rbx, [rbx+10h]
0x1800049bb  test    rbx, rbx
0x1800049be  jnz     short loc_180004993
0x1800049c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800049c7  test    rax, rax
0x1800049ca  jz      short loc_1800049EC
0x1800049cc  test    bpl, bpl
0x1800049cf  jnz     short loc_1800049E1
0x1800049d1  test    byte ptr [rdi+4], 2
0x1800049d5  jnz     short loc_1800049E1
0x1800049d7  xor     ecx, ecx
0x1800049d9  jmp     short loc_1800049E3
0x1800049db  add     rbx, 10h
0x1800049df  jmp     short loc_180004969
0x1800049e1  mov     cl, 1
0x1800049e3  mov     rdx, rdi
0x1800049e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049eb  nop
0x1800049ec  call    cs:__imp_GetCurrentThreadId
0x1800049f2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800049f8  cmp     ecx, eax
0x1800049fa  jz      loc_180004AFC
0x180004a00  mov     ecx, 1
0x180004a05  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004a0d  inc     ecx; this
0x180004a0f  cmp     ecx, 4
0x180004a12  jge     loc_180004AF5
0x180004a18  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004a1e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004a23  mov     rbx, rax
0x180004a26  test    rax, rax
0x180004a29  jz      loc_180004AEB
0x180004a2f  mov     esi, [rax+10h]
0x180004a32  mov     ebp, 50h ; 'P'
0x180004a37  cmp     qword ptr [rax+18h], 0
0x180004a3c  jnz     short loc_180004A73
0x180004a3e  test    esi, esi
0x180004a40  jz      short loc_180004A73
0x180004a42  mov     edx, 190h; dwBytes
0x180004a47  lea     ecx, [rbp-48h]; dwFlags
0x180004a4a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004a4f  mov     [rbx+18h], rax
0x180004a53  test    rax, rax
0x180004a56  jz      short loc_180004A73
0x180004a58  mov     dword ptr [rbx+20h], 5
0x180004a5f  lea     rcx, [rax+190h]
0x180004a66  jmp     short loc_180004A6E
0x180004a68  mov     [rax], bp
0x180004a6b  add     rax, rbp
0x180004a6e  cmp     rax, rcx
0x180004a71  jnz     short loc_180004A68
0x180004a73  mov     r9, [rbx+18h]
0x180004a77  test    r9, r9
0x180004a7a  jz      short loc_180004AEB
0x180004a7c  test    esi, esi
0x180004a7e  jz      short loc_180004AB1
0x180004a80  mov     rcx, r9
0x180004a83  movzx   eax, word ptr [rbx+20h]
0x180004a87  lea     rdx, [rax+rax*4]
0x180004a8b  shl     rdx, 4
0x180004a8f  add     rdx, r9
0x180004a92  cmp     r9, rdx
0x180004a95  jz      short loc_180004AB1
0x180004a97  mov     r8d, [rbx+10h]
0x180004a9b  cmp     [rcx+4], r8d
0x180004a9f  jbe     short loc_180004AA9
0x180004aa1  mov     eax, [rdi+8]
0x180004aa4  cmp     [rcx+8], eax
0x180004aa7  jz      short loc_180004AEB
0x180004aa9  add     rcx, rbp
0x180004aac  cmp     rcx, rdx
0x180004aaf  jnz     short loc_180004A9B
0x180004ab1  movzx   eax, word ptr [rbx+22h]
0x180004ab5  inc     eax
0x180004ab7  movzx   ecx, word ptr [rbx+20h]
0x180004abb  xor     edx, edx
0x180004abd  div     ecx
0x180004abf  mov     [rbx+22h], dx
0x180004ac3  mov     rax, [rbx+8]
0x180004ac7  mov     r8d, 1
0x180004acd  lock xadd [rax], r8d
0x180004ad2  inc     r8d; unsigned int
0x180004ad5  movzx   eax, dx
0x180004ad8  lea     rcx, [rax+rax*4]
0x180004adc  shl     rcx, 4
0x180004ae0  add     rcx, r9; this
0x180004ae3  mov     rdx, rdi; struct wil::FailureInfo *
0x180004ae6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004aeb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004af5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004afc  add     rsp, 20h
0x180004b00  pop     r14
0x180004b02  pop     rdi
0x180004b03  pop     rsi
0x180004b04  pop     rbp
0x180004b05  pop     rbx
0x180004b06  retn
```
