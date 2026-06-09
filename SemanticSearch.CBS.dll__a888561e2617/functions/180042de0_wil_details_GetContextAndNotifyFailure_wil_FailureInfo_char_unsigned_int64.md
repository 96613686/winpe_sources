# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180042de0`
- end: `0x180042ff0`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006f50`
- `0x180042830`
- `0x180042bb0`
- `0x180042c80`
- `0x180042de0`
- `0x18005e260`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180042e12`
- `KERNEL32!GetCurrentThreadId` at `0x180042ecc`
- `KERNEL32!GetCurrentThreadId` at `0x180042e12`
- `KERNEL32!GetCurrentThreadId` at `0x180042ecc`

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
  DWORD v11; // eax
  bool v12; // dl
  wil::details_abi *v13; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v15; // r8
  struct wil::details_abi::ThreadLocalData *v16; // rbx
  int v17; // esi
  _WORD *v18; // rax
  _WORD *v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned __int16 v23; // dx

  v5 = this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = *(wil::details **)(v7 + 8 * (CurrentThreadId % 0xA));
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
        v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
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
  v11 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v11 )
  {
    v13 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v13 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v11;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v13, v12);
      v16 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v17 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v17 )
          {
            v18 = wil::details::ProcessHeapAlloc(8u, 0x190u, v15);
            *((_QWORD *)v16 + 3) = v18;
            if ( v18 )
            {
              *((_DWORD *)v16 + 8) = 5;
              v19 = v18 + 200;
              do
              {
                *v18 = 80;
                v18 += 40;
              }
              while ( v18 != v19 );
            }
          }
        }
        v20 = *((_QWORD *)v16 + 3);
        if ( v20 )
        {
          if ( !v17 || (v21 = *((_QWORD *)v16 + 3), v22 = v20 + 80LL * *((unsigned __int16 *)v16 + 16), v20 == v22) )
          {
LABEL_33:
            v23 = ((unsigned int)*((unsigned __int16 *)v16 + 17) + 1) % *((unsigned __int16 *)v16 + 16);
            *((_WORD *)v16 + 17) = v23;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v20 + 80LL * v23),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v16 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v21 + 4) <= *((_DWORD *)v16 + 4) || *(_DWORD *)(v21 + 8) != *((_DWORD *)v5 + 2) )
            {
              v21 += 80;
              if ( v21 == v22 )
                goto LABEL_33;
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
0x180042de0  mov     [rsp+arg_18], rbx
0x180042de5  push    rbp
0x180042de6  push    rsi
0x180042de7  push    rdi
0x180042de8  push    r14
0x180042dea  push    r15
0x180042dec  sub     rsp, 20h
0x180042df0  mov     rbp, r8
0x180042df3  mov     r14, rdx
0x180042df6  mov     rdi, rcx
0x180042df9  mov     byte ptr [rdx], 0
0x180042dfc  xor     sil, sil
0x180042dff  xor     r15d, r15d
0x180042e02  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180042e09  test    rbx, rbx
0x180042e0c  jz      loc_180042E9F
0x180042e12  call    cs:__imp_GetCurrentThreadId
0x180042e18  mov     r9d, eax
0x180042e1b  mov     r8d, eax
0x180042e1e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180042e28  mul     r9
0x180042e2b  shr     rdx, 3
0x180042e2f  lea     rcx, [rdx+rdx*4]
0x180042e33  add     rcx, rcx
0x180042e36  sub     r8, rcx
0x180042e39  mov     rcx, [rbx+r8*8]
0x180042e3d  test    rcx, rcx
0x180042e40  jz      short loc_180042E50
0x180042e42  cmp     [rcx], r9d
0x180042e45  jz      short loc_180042EBA
0x180042e47  mov     rcx, [rcx+8]
0x180042e4b  test    rcx, rcx
0x180042e4e  jnz     short loc_180042E42
0x180042e50  mov     rbx, r15
0x180042e53  test    rbx, rbx
0x180042e56  jz      short loc_180042E9F
0x180042e58  cmp     [rbx], r15
0x180042e5b  jz      short loc_180042E9F
0x180042e5d  mov     [r14], sil
0x180042e60  mov     r9, rbp; unsigned __int64
0x180042e63  mov     r8, r14; char *
0x180042e66  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180042e69  mov     rcx, rdi; struct wil::FailureInfo *
0x180042e6c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180042e71  test    al, al
0x180042e73  jz      short loc_180042E79
0x180042e75  mov     [rdi+48h], r14
0x180042e79  mov     rbx, [rbx]
0x180042e7c  nop     dword ptr [rax+00h]
0x180042e80  mov     rcx, [rbx+8]
0x180042e84  mov     rax, [rcx]
0x180042e87  mov     rdx, rdi
0x180042e8a  mov     rax, [rax]
0x180042e8d  call    cs:__guard_dispatch_icall_fptr
0x180042e93  or      sil, al
0x180042e96  mov     rbx, [rbx+10h]
0x180042e9a  test    rbx, rbx
0x180042e9d  jnz     short loc_180042E80
0x180042e9f  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180042ea6  test    rax, rax
0x180042ea9  jz      short loc_180042ECC
0x180042eab  test    sil, sil
0x180042eae  jnz     short loc_180042EC0
0x180042eb0  test    byte ptr [rdi+4], 2
0x180042eb4  jnz     short loc_180042EC0
0x180042eb6  xor     ecx, ecx
0x180042eb8  jmp     short loc_180042EC2
0x180042eba  lea     rbx, [rcx+10h]
0x180042ebe  jmp     short loc_180042E53
0x180042ec0  mov     cl, 1
0x180042ec2  mov     rdx, rdi
0x180042ec5  call    cs:__guard_dispatch_icall_fptr
0x180042ecb  nop
0x180042ecc  call    cs:__imp_GetCurrentThreadId
0x180042ed2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180042ed8  cmp     ecx, eax
0x180042eda  jz      loc_180042FDF
0x180042ee0  mov     ebp, 1
0x180042ee5  mov     ecx, ebp
0x180042ee7  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180042eef  inc     ecx; this
0x180042ef1  cmp     ecx, 4
0x180042ef4  jge     loc_180042FD8
0x180042efa  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180042f00  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180042f05  mov     rbx, rax
0x180042f08  test    rax, rax
0x180042f0b  jz      loc_180042FD1
0x180042f11  mov     esi, [rax+10h]
0x180042f14  cmp     qword ptr [rax+18h], 0
0x180042f19  jnz     short loc_180042F5E
0x180042f1b  test    esi, esi
0x180042f1d  jz      short loc_180042F5E
0x180042f1f  mov     edx, 190h; dwBytes
0x180042f24  mov     ecx, 8; dwFlags
0x180042f29  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180042f2e  mov     [rbx+18h], rax
0x180042f32  test    rax, rax
0x180042f35  jz      short loc_180042F5E
0x180042f37  mov     dword ptr [rbx+20h], 5
0x180042f3e  lea     rcx, [rax+190h]
0x180042f45  cmp     rax, rcx
0x180042f48  jz      short loc_180042F5E
0x180042f4a  nop     word ptr [rax+rax+00h]
0x180042f50  mov     word ptr [rax], 50h ; 'P'
0x180042f55  add     rax, 50h ; 'P'
0x180042f59  cmp     rax, rcx
0x180042f5c  jnz     short loc_180042F50
0x180042f5e  mov     r9, [rbx+18h]
0x180042f62  test    r9, r9
0x180042f65  jz      short loc_180042FD1
0x180042f67  test    esi, esi
0x180042f69  jz      short loc_180042F9D
0x180042f6b  mov     rcx, r9
0x180042f6e  movzx   eax, word ptr [rbx+20h]
0x180042f72  lea     rdx, [rax+rax*4]
0x180042f76  shl     rdx, 4
0x180042f7a  add     rdx, r9
0x180042f7d  cmp     r9, rdx
0x180042f80  jz      short loc_180042F9D
0x180042f82  mov     r8d, [rbx+10h]
0x180042f86  cmp     [rcx+4], r8d
0x180042f8a  jbe     short loc_180042F94
0x180042f8c  mov     eax, [rdi+8]
0x180042f8f  cmp     [rcx+8], eax
0x180042f92  jz      short loc_180042FD1
0x180042f94  add     rcx, 50h ; 'P'
0x180042f98  cmp     rcx, rdx
0x180042f9b  jnz     short loc_180042F86
0x180042f9d  movzx   ecx, word ptr [rbx+20h]
0x180042fa1  movzx   eax, word ptr [rbx+22h]
0x180042fa5  inc     eax
0x180042fa7  xor     edx, edx
0x180042fa9  div     ecx
0x180042fab  mov     [rbx+22h], dx
0x180042faf  mov     rax, [rbx+8]
0x180042fb3  lock xadd [rax], ebp
0x180042fb7  lea     r8d, [rbp+1]; unsigned int
0x180042fbb  movzx   eax, dx
0x180042fbe  lea     rcx, [rax+rax*4]
0x180042fc2  shl     rcx, 4
0x180042fc6  add     rcx, r9; this
0x180042fc9  mov     rdx, rdi; struct wil::FailureInfo *
0x180042fcc  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180042fd1  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180042fd8  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180042fdf  mov     rbx, [rsp+48h+arg_18]
0x180042fe4  add     rsp, 20h
0x180042fe8  pop     r15
0x180042fea  pop     r14
0x180042fec  pop     rdi
0x180042fed  pop     rsi
0x180042fee  pop     rbp
0x180042fef  retn
```
