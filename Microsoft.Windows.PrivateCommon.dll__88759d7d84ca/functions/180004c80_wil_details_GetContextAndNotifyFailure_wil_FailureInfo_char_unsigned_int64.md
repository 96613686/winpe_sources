# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004c80`
- end: `0x180004e90`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(wil::details *this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800025d0`
- `0x1800046d0`
- `0x180004a50`
- `0x180004b20`
- `0x180004c80`
- `0x18000b930`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004cb2`
- `KERNEL32!GetCurrentThreadId` at `0x180004d6c`
- `KERNEL32!GetCurrentThreadId` at `0x180004cb2`
- `KERNEL32!GetCurrentThreadId` at `0x180004d6c`

## pseudocode

```c
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
0x180004c80  mov     [rsp+arg_18], rbx
0x180004c85  push    rbp
0x180004c86  push    rsi
0x180004c87  push    rdi
0x180004c88  push    r14
0x180004c8a  push    r15
0x180004c8c  sub     rsp, 20h
0x180004c90  mov     rbp, r8
0x180004c93  mov     r14, rdx
0x180004c96  mov     rdi, rcx
0x180004c99  mov     byte ptr [rdx], 0
0x180004c9c  xor     sil, sil
0x180004c9f  xor     r15d, r15d
0x180004ca2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004ca9  test    rbx, rbx
0x180004cac  jz      loc_180004D3F
0x180004cb2  call    cs:__imp_GetCurrentThreadId
0x180004cb8  mov     r9d, eax
0x180004cbb  mov     r8d, eax
0x180004cbe  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004cc8  mul     r9
0x180004ccb  shr     rdx, 3
0x180004ccf  lea     rcx, [rdx+rdx*4]
0x180004cd3  add     rcx, rcx
0x180004cd6  sub     r8, rcx
0x180004cd9  mov     rcx, [rbx+r8*8]
0x180004cdd  test    rcx, rcx
0x180004ce0  jz      short loc_180004CF0
0x180004ce2  cmp     [rcx], r9d
0x180004ce5  jz      short loc_180004D5A
0x180004ce7  mov     rcx, [rcx+8]
0x180004ceb  test    rcx, rcx
0x180004cee  jnz     short loc_180004CE2
0x180004cf0  mov     rbx, r15
0x180004cf3  test    rbx, rbx
0x180004cf6  jz      short loc_180004D3F
0x180004cf8  cmp     [rbx], r15
0x180004cfb  jz      short loc_180004D3F
0x180004cfd  mov     [r14], sil
0x180004d00  mov     r9, rbp; unsigned __int64
0x180004d03  mov     r8, r14; char *
0x180004d06  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004d09  mov     rcx, rdi; struct wil::FailureInfo *
0x180004d0c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004d11  test    al, al
0x180004d13  jz      short loc_180004D19
0x180004d15  mov     [rdi+48h], r14
0x180004d19  mov     rbx, [rbx]
0x180004d1c  nop     dword ptr [rax+00h]
0x180004d20  mov     rcx, [rbx+8]
0x180004d24  mov     rax, [rcx]
0x180004d27  mov     rdx, rdi
0x180004d2a  mov     rax, [rax]
0x180004d2d  call    cs:__guard_dispatch_icall_fptr
0x180004d33  or      sil, al
0x180004d36  mov     rbx, [rbx+10h]
0x180004d3a  test    rbx, rbx
0x180004d3d  jnz     short loc_180004D20
0x180004d3f  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004d46  test    rax, rax
0x180004d49  jz      short loc_180004D6C
0x180004d4b  test    sil, sil
0x180004d4e  jnz     short loc_180004D60
0x180004d50  test    byte ptr [rdi+4], 2
0x180004d54  jnz     short loc_180004D60
0x180004d56  xor     ecx, ecx
0x180004d58  jmp     short loc_180004D62
0x180004d5a  lea     rbx, [rcx+10h]
0x180004d5e  jmp     short loc_180004CF3
0x180004d60  mov     cl, 1
0x180004d62  mov     rdx, rdi
0x180004d65  call    cs:__guard_dispatch_icall_fptr
0x180004d6b  nop
0x180004d6c  call    cs:__imp_GetCurrentThreadId
0x180004d72  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004d78  cmp     ecx, eax
0x180004d7a  jz      loc_180004E7F
0x180004d80  mov     ebp, 1
0x180004d85  mov     ecx, ebp
0x180004d87  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004d8f  inc     ecx; this
0x180004d91  cmp     ecx, 4
0x180004d94  jge     loc_180004E78
0x180004d9a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004da0  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004da5  mov     rbx, rax
0x180004da8  test    rax, rax
0x180004dab  jz      loc_180004E71
0x180004db1  mov     esi, [rax+10h]
0x180004db4  cmp     qword ptr [rax+18h], 0
0x180004db9  jnz     short loc_180004DFE
0x180004dbb  test    esi, esi
0x180004dbd  jz      short loc_180004DFE
0x180004dbf  mov     edx, 190h; dwBytes
0x180004dc4  mov     ecx, 8; dwFlags
0x180004dc9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004dce  mov     [rbx+18h], rax
0x180004dd2  test    rax, rax
0x180004dd5  jz      short loc_180004DFE
0x180004dd7  mov     dword ptr [rbx+20h], 5
0x180004dde  lea     rcx, [rax+190h]
0x180004de5  cmp     rax, rcx
0x180004de8  jz      short loc_180004DFE
0x180004dea  nop     word ptr [rax+rax+00h]
0x180004df0  mov     word ptr [rax], 50h ; 'P'
0x180004df5  add     rax, 50h ; 'P'
0x180004df9  cmp     rax, rcx
0x180004dfc  jnz     short loc_180004DF0
0x180004dfe  mov     r9, [rbx+18h]
0x180004e02  test    r9, r9
0x180004e05  jz      short loc_180004E71
0x180004e07  test    esi, esi
0x180004e09  jz      short loc_180004E3D
0x180004e0b  mov     rcx, r9
0x180004e0e  movzx   eax, word ptr [rbx+20h]
0x180004e12  lea     rdx, [rax+rax*4]
0x180004e16  shl     rdx, 4
0x180004e1a  add     rdx, r9
0x180004e1d  cmp     r9, rdx
0x180004e20  jz      short loc_180004E3D
0x180004e22  mov     r8d, [rbx+10h]
0x180004e26  cmp     [rcx+4], r8d
0x180004e2a  jbe     short loc_180004E34
0x180004e2c  mov     eax, [rdi+8]
0x180004e2f  cmp     [rcx+8], eax
0x180004e32  jz      short loc_180004E71
0x180004e34  add     rcx, 50h ; 'P'
0x180004e38  cmp     rcx, rdx
0x180004e3b  jnz     short loc_180004E26
0x180004e3d  movzx   eax, word ptr [rbx+22h]
0x180004e41  inc     eax
0x180004e43  movzx   ecx, word ptr [rbx+20h]
0x180004e47  xor     edx, edx
0x180004e49  div     ecx
0x180004e4b  mov     [rbx+22h], dx
0x180004e4f  mov     rax, [rbx+8]
0x180004e53  lock xadd [rax], ebp
0x180004e57  lea     r8d, [rbp+1]; unsigned int
0x180004e5b  movzx   eax, dx
0x180004e5e  lea     rcx, [rax+rax*4]
0x180004e62  shl     rcx, 4
0x180004e66  add     rcx, r9; this
0x180004e69  mov     rdx, rdi; struct wil::FailureInfo *
0x180004e6c  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004e71  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004e78  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004e7f  mov     rbx, [rsp+48h+arg_18]
0x180004e84  add     rsp, 20h
0x180004e88  pop     r15
0x180004e8a  pop     r14
0x180004e8c  pop     rdi
0x180004e8d  pop     rsi
0x180004e8e  pop     rbp
0x180004e8f  retn
```
