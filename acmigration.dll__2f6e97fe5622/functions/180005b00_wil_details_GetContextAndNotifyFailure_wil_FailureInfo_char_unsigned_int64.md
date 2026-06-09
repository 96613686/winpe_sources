# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005b00`
- end: `0x180005d10`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005b00`
- `0x18000622c`
- `0x180006310`
- `0x180006db4`
- `0x1800086d0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180005b33`
- `KERNEL32!GetCurrentThreadId` at `0x180005bf5`
- `KERNEL32!GetCurrentThreadId` at `0x180005b33`
- `KERNEL32!GetCurrentThreadId` at `0x180005bf5`

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
0x180005b00  push    rbx
0x180005b02  push    rbp
0x180005b03  push    rsi
0x180005b04  push    rdi
0x180005b05  push    r14
0x180005b07  sub     rsp, 30h
0x180005b0b  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180005b14  mov     r14, r8
0x180005b17  mov     rsi, rdx
0x180005b1a  mov     rdi, rcx
0x180005b1d  mov     byte ptr [rdx], 0
0x180005b20  xor     bpl, bpl
0x180005b23  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005b2a  test    rbx, rbx
0x180005b2d  jz      loc_180005BC9
0x180005b33  call    cs:__imp_GetCurrentThreadId
0x180005b39  mov     r9d, eax
0x180005b3c  mov     r8d, eax
0x180005b3f  shr     r8, 2
0x180005b43  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005b4d  mul     r8
0x180005b50  shr     rdx, 3
0x180005b54  lea     rcx, [rdx+rdx*4]
0x180005b58  add     rcx, rcx
0x180005b5b  sub     r8, rcx
0x180005b5e  mov     rbx, [rbx+r8*8]
0x180005b62  jmp     short loc_180005B6D
0x180005b64  cmp     [rbx], r9d
0x180005b67  jz      short loc_180005BE4
0x180005b69  mov     rbx, [rbx+8]
0x180005b6d  test    rbx, rbx
0x180005b70  jnz     short loc_180005B64
0x180005b72  test    rbx, rbx
0x180005b75  jz      short loc_180005BC9
0x180005b77  cmp     qword ptr [rbx], 0
0x180005b7b  jz      short loc_180005BC9
0x180005b7d  mov     [rsi], bpl
0x180005b80  mov     r9, r14; unsigned __int64
0x180005b83  mov     r8, rsi; char *
0x180005b86  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005b89  mov     rcx, rdi; struct wil::FailureInfo *
0x180005b8c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005b91  test    al, al
0x180005b93  jz      short loc_180005B99
0x180005b95  mov     [rdi+48h], rsi
0x180005b99  mov     rbx, [rbx]
0x180005b9c  mov     al, [rbx+28h]
0x180005b9f  mov     byte ptr [rbx+28h], 1
0x180005ba3  test    al, al
0x180005ba5  jnz     short loc_180005BC0
0x180005ba7  mov     rcx, [rbx+8]
0x180005bab  mov     rax, [rcx]
0x180005bae  mov     rdx, rdi
0x180005bb1  mov     rax, [rax]
0x180005bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb9  or      bpl, al
0x180005bbc  mov     byte ptr [rbx+28h], 0
0x180005bc0  mov     rbx, [rbx+10h]
0x180005bc4  test    rbx, rbx
0x180005bc7  jnz     short loc_180005B9C
0x180005bc9  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005bd0  test    rax, rax
0x180005bd3  jz      short loc_180005BF5
0x180005bd5  test    bpl, bpl
0x180005bd8  jnz     short loc_180005BEA
0x180005bda  test    byte ptr [rdi+4], 2
0x180005bde  jnz     short loc_180005BEA
0x180005be0  xor     ecx, ecx
0x180005be2  jmp     short loc_180005BEC
0x180005be4  add     rbx, 10h
0x180005be8  jmp     short loc_180005B72
0x180005bea  mov     cl, 1
0x180005bec  mov     rdx, rdi
0x180005bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf4  nop
0x180005bf5  call    cs:__imp_GetCurrentThreadId
0x180005bfb  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005c01  cmp     ecx, eax
0x180005c03  jz      loc_180005D05
0x180005c09  mov     ecx, 1
0x180005c0e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005c16  inc     ecx; this
0x180005c18  cmp     ecx, 4
0x180005c1b  jge     loc_180005CFE
0x180005c21  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005c27  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005c2c  mov     rbx, rax
0x180005c2f  test    rax, rax
0x180005c32  jz      loc_180005CF4
0x180005c38  mov     esi, [rax+10h]
0x180005c3b  mov     ebp, 50h ; 'P'
0x180005c40  cmp     qword ptr [rax+18h], 0
0x180005c45  jnz     short loc_180005C7C
0x180005c47  test    esi, esi
0x180005c49  jz      short loc_180005C7C
0x180005c4b  mov     edx, 190h; dwBytes
0x180005c50  lea     ecx, [rbp-48h]; dwFlags
0x180005c53  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005c58  mov     [rbx+18h], rax
0x180005c5c  test    rax, rax
0x180005c5f  jz      short loc_180005C7C
0x180005c61  mov     dword ptr [rbx+20h], 5
0x180005c68  lea     rcx, [rax+190h]
0x180005c6f  jmp     short loc_180005C77
0x180005c71  mov     [rax], bp
0x180005c74  add     rax, rbp
0x180005c77  cmp     rax, rcx
0x180005c7a  jnz     short loc_180005C71
0x180005c7c  mov     r9, [rbx+18h]
0x180005c80  test    r9, r9
0x180005c83  jz      short loc_180005CF4
0x180005c85  test    esi, esi
0x180005c87  jz      short loc_180005CBA
0x180005c89  mov     rcx, r9
0x180005c8c  movzx   eax, word ptr [rbx+20h]
0x180005c90  lea     rdx, [rax+rax*4]
0x180005c94  shl     rdx, 4
0x180005c98  add     rdx, r9
0x180005c9b  cmp     r9, rdx
0x180005c9e  jz      short loc_180005CBA
0x180005ca0  mov     r8d, [rbx+10h]
0x180005ca4  cmp     [rcx+4], r8d
0x180005ca8  jbe     short loc_180005CB2
0x180005caa  mov     eax, [rdi+8]
0x180005cad  cmp     [rcx+8], eax
0x180005cb0  jz      short loc_180005CF4
0x180005cb2  add     rcx, rbp
0x180005cb5  cmp     rcx, rdx
0x180005cb8  jnz     short loc_180005CA4
0x180005cba  movzx   eax, word ptr [rbx+22h]
0x180005cbe  inc     eax
0x180005cc0  movzx   ecx, word ptr [rbx+20h]
0x180005cc4  xor     edx, edx
0x180005cc6  div     ecx
0x180005cc8  mov     [rbx+22h], dx
0x180005ccc  mov     rax, [rbx+8]
0x180005cd0  mov     r8d, 1
0x180005cd6  lock xadd [rax], r8d
0x180005cdb  inc     r8d; unsigned int
0x180005cde  movzx   eax, dx
0x180005ce1  lea     rcx, [rax+rax*4]
0x180005ce5  shl     rcx, 4
0x180005ce9  add     rcx, r9; this
0x180005cec  mov     rdx, rdi; struct wil::FailureInfo *
0x180005cef  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180005cf4  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005cfe  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005d05  add     rsp, 30h
0x180005d09  pop     r14
0x180005d0b  pop     rdi
0x180005d0c  pop     rsi
0x180005d0d  pop     rbp
0x180005d0e  pop     rbx
0x180005d0f  retn
```
