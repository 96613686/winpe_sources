# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000e640`
- end: `0x18000e860`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `544`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000e640`
- `0x18000fe70`
- `0x18000ff70`
- `0x180012bf0`
- `0x180013eb0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e66a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e73e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e66a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e73e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // si
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
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

  v5 = this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = *(wil::details **)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA));
    if ( this )
    {
      while ( *(_DWORD *)this != (_DWORD)CurrentThreadId )
      {
        this = (wil::details *)*((_QWORD *)this + 1);
        if ( !this )
          goto LABEL_5;
      }
      v9 = (struct wil::details::ThreadFailureCallbackHolder **)((char *)this + 16);
    }
    else
    {
LABEL_5:
      v9 = 0;
    }
    if ( v9 && *v9 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v9, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v10 = *v9;
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
              do
              {
                *v19 = 80;
                v19 += 40;
              }
              while ( v19 != v20 );
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_35:
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
                goto LABEL_35;
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
0x18000e640  push    rbx
0x18000e642  push    rbp
0x18000e643  push    rsi
0x18000e644  push    rdi
0x18000e645  push    r14
0x18000e647  sub     rsp, 20h
0x18000e64b  mov     rbp, r8
0x18000e64e  mov     r14, rdx
0x18000e651  mov     rdi, rcx
0x18000e654  mov     byte ptr [rdx], 0
0x18000e657  xor     sil, sil
0x18000e65a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000e661  test    rbx, rbx
0x18000e664  jz      loc_18000E711
0x18000e66a  call    cs:__imp_GetCurrentThreadId
0x18000e671  nop     dword ptr [rax+rax+00h]
0x18000e676  mov     r9d, eax
0x18000e679  mov     r8d, eax
0x18000e67c  shr     r8, 2
0x18000e680  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000e68a  mul     r8
0x18000e68d  shr     rdx, 3
0x18000e691  lea     rcx, [rdx+rdx*4]
0x18000e695  add     rcx, rcx
0x18000e698  sub     r8, rcx
0x18000e69b  mov     rcx, [rbx+r8*8]
0x18000e69f  test    rcx, rcx
0x18000e6a2  jz      short loc_18000E6B6
0x18000e6a4  cmp     [rcx], r9d
0x18000e6a7  jz      loc_18000E72C
0x18000e6ad  mov     rcx, [rcx+8]
0x18000e6b1  test    rcx, rcx
0x18000e6b4  jnz     short loc_18000E6A4
0x18000e6b6  xor     ebx, ebx
0x18000e6b8  test    rbx, rbx
0x18000e6bb  jz      short loc_18000E711
0x18000e6bd  cmp     qword ptr [rbx], 0
0x18000e6c1  jz      short loc_18000E711
0x18000e6c3  mov     [r14], sil
0x18000e6c6  mov     r9, rbp; unsigned __int64
0x18000e6c9  mov     r8, r14; char *
0x18000e6cc  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000e6cf  mov     rcx, rdi; struct wil::FailureInfo *
0x18000e6d2  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000e6d7  test    al, al
0x18000e6d9  jz      short loc_18000E6DF
0x18000e6db  mov     [rdi+48h], r14
0x18000e6df  mov     rbx, [rbx]
0x18000e6e2  movzx   eax, byte ptr [rbx+28h]
0x18000e6e6  mov     byte ptr [rbx+28h], 1
0x18000e6ea  test    al, al
0x18000e6ec  jnz     short loc_18000E708
0x18000e6ee  mov     rcx, [rbx+8]
0x18000e6f2  mov     rax, [rcx]
0x18000e6f5  mov     rdx, rdi
0x18000e6f8  mov     rax, [rax]
0x18000e6fb  call    cs:__guard_dispatch_icall_fptr
0x18000e701  or      sil, al
0x18000e704  mov     byte ptr [rbx+28h], 0
0x18000e708  mov     rbx, [rbx+10h]
0x18000e70c  test    rbx, rbx
0x18000e70f  jnz     short loc_18000E6E2
0x18000e711  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000e718  test    rax, rax
0x18000e71b  jz      short loc_18000E73E
0x18000e71d  test    sil, sil
0x18000e720  jnz     short loc_18000E732
0x18000e722  test    byte ptr [rdi+4], 2
0x18000e726  jnz     short loc_18000E732
0x18000e728  xor     ecx, ecx
0x18000e72a  jmp     short loc_18000E734
0x18000e72c  lea     rbx, [rcx+10h]
0x18000e730  jmp     short loc_18000E6B8
0x18000e732  mov     cl, 1
0x18000e734  mov     rdx, rdi
0x18000e737  call    cs:__guard_dispatch_icall_fptr
0x18000e73d  nop
0x18000e73e  call    cs:__imp_GetCurrentThreadId
0x18000e745  nop     dword ptr [rax+rax+00h]
0x18000e74a  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000e750  cmp     ecx, eax
0x18000e752  jz      loc_18000E854
0x18000e758  mov     ebp, 1
0x18000e75d  mov     ecx, ebp
0x18000e75f  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000e767  inc     ecx; this
0x18000e769  cmp     ecx, 4
0x18000e76c  jge     loc_18000E84D
0x18000e772  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000e778  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000e77d  mov     rbx, rax
0x18000e780  test    rax, rax
0x18000e783  jz      loc_18000E843
0x18000e789  mov     esi, [rax+10h]
0x18000e78c  cmp     qword ptr [rax+18h], 0
0x18000e791  jnz     short loc_18000E7D0
0x18000e793  test    esi, esi
0x18000e795  jz      short loc_18000E7D0
0x18000e797  mov     edx, 190h; dwBytes
0x18000e79c  mov     ecx, 8; dwFlags
0x18000e7a1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e7a6  mov     [rbx+18h], rax
0x18000e7aa  test    rax, rax
0x18000e7ad  jz      short loc_18000E7D0
0x18000e7af  mov     dword ptr [rbx+20h], 5
0x18000e7b6  lea     rcx, [rax+190h]
0x18000e7bd  cmp     rax, rcx
0x18000e7c0  jz      short loc_18000E7D0
0x18000e7c2  mov     word ptr [rax], 50h ; 'P'
0x18000e7c7  add     rax, 50h ; 'P'
0x18000e7cb  cmp     rax, rcx
0x18000e7ce  jnz     short loc_18000E7C2
0x18000e7d0  mov     r9, [rbx+18h]
0x18000e7d4  test    r9, r9
0x18000e7d7  jz      short loc_18000E843
0x18000e7d9  test    esi, esi
0x18000e7db  jz      short loc_18000E80F
0x18000e7dd  mov     rcx, r9
0x18000e7e0  movzx   eax, word ptr [rbx+20h]
0x18000e7e4  lea     rdx, [rax+rax*4]
0x18000e7e8  shl     rdx, 4
0x18000e7ec  add     rdx, r9
0x18000e7ef  cmp     r9, rdx
0x18000e7f2  jz      short loc_18000E80F
0x18000e7f4  mov     r8d, [rbx+10h]
0x18000e7f8  cmp     [rcx+4], r8d
0x18000e7fc  jbe     short loc_18000E806
0x18000e7fe  mov     eax, [rdi+8]
0x18000e801  cmp     [rcx+8], eax
0x18000e804  jz      short loc_18000E843
0x18000e806  add     rcx, 50h ; 'P'
0x18000e80a  cmp     rcx, rdx
0x18000e80d  jnz     short loc_18000E7F8
0x18000e80f  movzx   eax, word ptr [rbx+22h]
0x18000e813  inc     eax
0x18000e815  movzx   ecx, word ptr [rbx+20h]
0x18000e819  xor     edx, edx
0x18000e81b  div     ecx
0x18000e81d  mov     [rbx+22h], dx
0x18000e821  mov     rax, [rbx+8]
0x18000e825  lock xadd [rax], ebp
0x18000e829  lea     r8d, [rbp+1]; unsigned int
0x18000e82d  movzx   eax, dx
0x18000e830  lea     rcx, [rax+rax*4]
0x18000e834  shl     rcx, 4
0x18000e838  add     rcx, r9; this
0x18000e83b  mov     rdx, rdi; struct wil::FailureInfo *
0x18000e83e  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000e843  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000e84d  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000e854  add     rsp, 20h
0x18000e858  pop     r14
0x18000e85a  pop     rdi
0x18000e85b  pop     rsi
0x18000e85c  pop     rbp
0x18000e85d  pop     rbx
0x18000e85e  retn
```
